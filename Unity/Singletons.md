# Singletons

Ein Singleton ist ein Entwurfsmuster, das die Instanziierung einer Klasse auf
ein einzelnes Objekt beschränkt. Dies bietet sich an, um globale Variablen zu deklarieren,
beispielsweise in Form eines GameManagers.

Der Unterschied zwischen Singletons und statischen Methoden und Variablen fasst sich wie folgt zusammen:

* Statische Klassen sind *lazy-loaded* (Datenobjekte stellen Werte zur Verfügung, laden diese aber erst bei Anfrage aus der Datenquelle) bei der ersten Referenzierung, müssen jedoch einen leeren statischen Konstruktor besitzen. Mit dem Singleton wird automatisch eine statische Initialisierung erstellt, die Eigenschaften werden automatisch uneditierbar gemacht.

* Ein Singleton kann ein Interface implementieren (statische Klassen können dies nicht). Hierdurch wird es ermöglicht, Bedingungen zu erstellen, die für Wrapper-Klassen / andere Singleton-Objekte verwendet werden können. Dies wiederum vereinfacht die Übersichtlichkeit und Organisierbarkeit.

* Singletons können auch von einer Basisklasse erben (statische Klassen können dies nicht).

## Aufbau

Grundaufbau der angelegten Klasse:

```CSharp
public class GameManager : MonoBehaviour
{
  void Start()
  {

  }
  void Update()
  {

  }
}
```

Diese muss nun folgendermaßen angepasst werden:

```CSharp
public class GameManager : MonoBehaviour
{
  public static GameManager instance = null;

  // Variable, auf die später zugegriffen werden soll
  private int level = 1;
  void Awake()
  {
    // Falls bereits eine Instanz existiert, wird diese zerstört
    if(instance == null) instance = this;
    else Destroy(gameObject);

    // Normalerweise wird beim Laden einer Szene
    // alle Elemente in der Hierarchy zerstört
    // Beim Wechsel zwischen Szenen sollen Punkte etc. i.d.R. beibehalten werden
    DontDestroyOnLoad(gameObject);
  }
}
```

Das Funktionsprinzip von Singletons unter Unity ist also folgendes: Beim Aufruf der Awake()-Methode wird die statische Eigenschaft *instance* auf diese Instanz gesetzt.
Wird erneut auf den Singleton zugegriffen, ist *instance* ungleich null, und das GameObject wird zerstört.

Nun wird noch ein Skript benötigt, welches obiges Skript beim Start des Spiels lädt.  
Hierzu wird im Ordner *Scripts* ein neues Skript *Loader* angelegt.

```CSharp
public class Loader : MonoBehaviour
{
  public GameObject gameManager;

  void Awake()
  {
    if(GameManager.instance == null)
    {
      Instantiate(gameManager);
    }
  }
}
```

Das *Loader*-Skript kann an die MainCamera angehängt werden.  
Das zuvor erstellte GameManager-Skript kann als Prefab gespeichert,
und aus der Hierarchy entfernt werden.  
Das Prefab soll anschließend der public-Variable *gameManager* des *Loader*-Skripts hinzugefügt werden.

## Links

[Unity Wiki](http://wiki.unity3d.com/index.php/Singleton)  
[Unity Learn](https://youtu.be/7NYXBUWmFvU)  
[Statics and Singletons in Unity 3D](https://www.youtube.com/watch?v=Jzu2CjnRiwI)
