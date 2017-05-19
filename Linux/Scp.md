# SCP - Secure Copy

Kopieren von Dateien zwischen Hosts.

## Remote -> Local

Kopiere die Datei *hello.txt* von einem entfernten Host auf das lokale Gerät.

```Bash
    scp username@remote.de:hello.txt /local/folder
```

## Local -> Remote

Kopiere die Datei *hello.txt* vom lokalen Gerät auf einen entfernten Host.

```Bash
    scp hello.txt username@remote.de:/remote/folder
```

Kopiere das lokale Verzeichnis *folder1* auf einen entfernten Computer unter dem Namen *folder2*

```Bash
    scp -r folder1 username@remote.de:/remote/folder/folder2
```

## Remote -> Remote

Kopiere die Datei *hello.txt* von entferntem Rechner *PC1* zu entferntem Rechner *PC2*.

```Bash
    scp username@PC1:/remote/directory/foobar.txt username@PC2:/remote/directory/
```
