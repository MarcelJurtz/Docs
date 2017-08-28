# USB-Sticks verwenden

Anzeige von Kernel-Messages mit ```dmesg -w```. Wird nun ein USB-Stick eingesteckt, erscheint hier ein neuer Eintrag:
```[sdc] Attached SCSI removable disk```. Viele Linux-Distributionen mounten anschließend direkt das Gerät, 
nachdem es im Explorer sichtbar wird.

```df -Th``` zeigt alle Datenspeicher an, anhand der Speichergröße lässt sich der Stick oft leicht ermitteln, beispielsweise ist dies ```/dev/sdc1```.

Gerät anschließend mit ```sudo umount /dev/sdc1``` unmounten. Zur Formatierung darf der Stick nicht gemounted sein.

Nun muss ein Dateisystem gewählt werden, im folgenden Beispiel ist das ext4.

Stick formatieren mit ```sudo mkfs.ext4 -L USB_LABEL /dev/sdc1```, der L-Flag legt ein Label fest, was hier auf USB_LABEL gesetzt wurde.
Mittels ```df -Th``` wird der Stick nun nicht mehr angezeigt, mit ```sudo fdisk -l``` ist der Stick aber noch sichtbar.

Nachdem der Stick gemounted wurde, ist er wieder vorhanden.

Problem: Der Stick wurde mit sudo, also als root formatiert (erforderlich), der normale User hat keinen Schreibzugriff auf diesen.
```ls -la /pfad/zum/mountverzeichnis``` listet einen Eintrag unter dem zuvor erstellten Label mit Besitzer *root*.

```id``` zeigt Informationen zum angemeldeten User, wie die Gruppe.

Änderung des Besitzers: ```chown -R user:gruppe /pfad/zum/mountverzeichnis/usbstick```. (chown = change owner, -R = rekursiv).


Wenn ein grafisches Programm verwendet werden soll, kann auch GParted (Gnome Partition Editor) verwendet werden.
