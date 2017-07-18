# C# Threading

using System.Threading

Keine Garantie, wann ein Thread ausgeführt wird.
Daten müssen während Threadzugriff gesperrt werden, sonst Möglichkeit vorhanden, dass diese kaputt gehen.

Wenn Threads parallel laufen, wechseln sich diese ab. Folgendes Skript verdeutlicht dieses Verhalten:

```Csharp
using System;
using System.Threading;

namespace ThreadingDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Thread t = new Thread(Print1);

            t.Start();

            for (int i = 0; i < 1000; i++)
            {
                Console.Write(0);
            }

            Console.ReadLine();
        }

        static void Print1()
        {
            for(int i = 0; i < 1000; i++)
            {
                Console.Write(1);
            }
        }
    }
}
```

## Sleep

SLeep ermöglicht es, einen Thread über einen gewissen Zeitraum einzufrieren.

```Csharp
int num = 1;

for(int i = 0; i < 10; i++)
{
    Console.WriteLine(num);
    Thread.Sleep(1000);
    num++;
}

Console.WriteLine("Thread ends");
Console.ReadLine();
```


## Argumente

Threads können keine Methoden mit Parametern verwenden, weshalb diese gekapselt werden müssen.
Dies kann durch zusätzliche Methoden umgangen werden:

```Csharp
using System;
using System.Threading;

namespace ThreadingDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            BankAccount bankAccount = new BankAccount(10);
            Thread[] threads = new Thread[15];

            Thread.CurrentThread.Name = "main";

            for (int i = 0; i < threads.Length; i++)
            {
                Thread t = new Thread(new ThreadStart(bankAccount.IssueRemove));
                t.Name = i.ToString();
                threads[i] = t;
            }

            for(int i = 0; i < threads.Length; i++)
            {
                Console.WriteLine("Thread {0} Alive: {1}", threads[i].Name, threads[i].IsAlive);
                threads[i].Start();
                Console.WriteLine("Thread {0} Alive: {1}", threads[i].Name, threads[i].IsAlive);
            }

            Console.WriteLine("Thread {0} ending", Thread.CurrentThread.Name);

            Console.ReadLine();
        }
    }

    class BankAccount
    {
        private Object accountLock = new object();
        double balance { get; set; }
        char unit { get; set; }

        public BankAccount(double balance)
        {
            this.balance = balance;
            unit = '€';
        }

        public double Remove(double amount)
        {
            if(balance < amount)
            {
                Console.WriteLine("Sorry, removing not possible!");
                return balance;
            }

            lock (accountLock)
            {
                if(balance >= amount)
                {
                    Console.WriteLine("Removed {0}, {1} {2} left in your account", amount, balance - amount, unit);
                    balance -= amount;
                }
                return balance;
            }
        }

        public void IssueRemove()
        {
            Remove(1);
        }
    }
}
```

Das Programm prüft ein Bankkonto auf dessen Inhalt und sperrt diesen bei Bedarf um eine Einheit abzuziehen.  
Wenn das *lock* entfernt werden würde, könnten parallele Abfragen stattfinden und somit zu einem negativen Kontostand führen.
Ein Ergebnis wie das Folgende wird dadurch erzeugt:

```
Thread 0 Alive: False
Thread 0 Alive: True
Thread 1 Alive: False
Thread 1 Alive: True
Thread 2 Alive: False
Thread 2 Alive: True
Thread 3 Alive: False
Thread 3 Alive: True
Thread 4 Alive: False
Thread 4 Alive: True
Thread 5 Alive: False
Thread 5 Alive: True
Thread 6 Alive: False
Removed 1, 9 € left in your account
Thread 6 Alive: True
Thread 7 Alive: False
Removed 1, 8 € left in your account
Removed 1, 7 € left in your account
Thread 7 Alive: True
Removed 1, 6 € left in your account
Removed 1, 5 € left in your account
Removed 1, 4 € left in your account
Thread 8 Alive: False
Removed 1, 3 € left in your account
Removed 1, 2 € left in your account
Thread 8 Alive: True
Thread 9 Alive: False
Thread 9 Alive: True
Thread 10 Alive: False
Removed 1, 1 € left in your account
Removed 1, 0 € left in your account
Thread 10 Alive: True
Thread 11 Alive: False
Thread 11 Alive: True
Sorry, removing not possible!
Thread 12 Alive: False
Sorry, removing not possible!
Thread 12 Alive: True
Thread 13 Alive: False
Sorry, removing not possible!
Thread 13 Alive: True
Thread 14 Alive: False
Sorry, removing not possible!
Thread 14 Alive: True
Thread main ending
Sorry, removing not possible!
```

Argumente können aber mithilfe von Lambda-Ausdrücken übergeben werden:

```Csharp
using System;
using System.Threading;

namespace ThreadingDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Thread t = new Thread(() => CountTo(8));
            t.Start();

            new Thread(() =>
            {
                CountTo(8);
                CountTo(8);
            }).Start();

            Console.Read();
        }

        static void CountTo(int maximum)
        {
            for(int i = 0; i <= maximum; i++)
            {
                Console.WriteLine(i);
            }
        }
    }
}
```
