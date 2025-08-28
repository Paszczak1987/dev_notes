# 1. Sprawdzić dostępne ścieżki folderów z `PATH`

W terminalu wpisz:

```powershell
$env:PATH -split ';'
```

Powinieneś zbaczyć listę folderów np.:

```
C:\Program Files (x86)\Common Files\Oracle\Java\java8path
C:\Program Files (x86)\Common Files\Oracle\Java\javapath
C:\WINDOWS\system32
C:\WINDOWS
C:\WINDOWS\System32\Wbem
C:\WINDOWS\System32\WindowsPowerShell\v1.0\
...
```

# 2. Utwórz plik wsadowy `.bat` w wybranym folderze

Załóżmy że system nie widzi `npx`.

1. Wejdź do wybranego folderu.
2. Utwórz plik wsadowy za pomocą edytora, np. `nvim`

```powershell
nvim npx.bat
```

3. Treść pliku:

```
 @echo off
 "C:\Nodejs\npx.cmd" %*
```

> **Uwaga:** Zmień ścieżkę na właściwą lokalizację `npx.cmd` w Twoim systemie.

4. Zapisz i `npx` powinien już być widoczny w systemie.
