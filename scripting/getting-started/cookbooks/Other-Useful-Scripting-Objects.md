---
title: "Andere nützliche Skriptobjekte"
ms.date: 2016-05-11
keywords: powershell,cmdlet
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
translationtype: Human Translation
ms.sourcegitcommit: ebf9d61bd67cc352d6d6404a9b592f856c99759e
ms.openlocfilehash: c68e6d7d26a8a9b1e32a35e82dd705d95480c9bf

---

# Andere nützliche Skriptobjekte
  Die folgenden Objekte bieten zusätzliche Skriptfunktionalität in Windows PowerShell ISE. Sie sind nicht Teil der **$psISE**-Hierarchie.

## Nützliche Skriptobjekte

### $psUnsupportedConsoleApplications
 Es gibt einige Einschränkungen für die Interaktion von Windows PowerShell ISE mit Konsolenanwendungen. Ein Befehl oder ein Automatisierungsskript, das einen Benutzereingriff erfordert, funktioniert möglicherweise anders, als wenn es von der Windows PowerShell-Konsole aus ausgeführt wird. Möglicherweise wollen Sie die Ausführung dieser Skripts oder Befehle im Befehlsbereich von Windows PowerShell ISE sperren. Das Objekt **$psUnsupportedConsoleApplications** hält eine Liste solcher Befehle vor. Falls Sie versuchen, die Befehle in dieser Liste auszuführen, erhalten Sie die Meldung, dass sie nicht unterstützt werden. Das nachfolgende Skript fügt der Liste einen Eintrag hinzu.

```
# List the unsupported commands
psUnsupportedConsoleApplications
# Add a command to this list
psUnsupportedConsoleApplications.Add(“Mycommand”)
#Show the augmented list of commands
psUnsupportedConsoleApplications

```

### $psLocalHelp
 Dabei handelt es sich um ein Wörterbuchobjekt, das eine kontextbezogene Zuordnung zwischen Hilfethemen und den entsprechenden Links in der lokalen kompilierten HTML-Hilfedatei verwaltet. Es wird bei der Suche der lokalen Hilfe für ein bestimmtes Thema verwendet. Sie können Themen zu dieser Liste hinzufügen oder aus dieser Liste löschen. Das folgende Codebeispiel zeigt einige Beispiele für Schlüssel-/Wert-Paare, die in **$psLocalHelp** enthalten sind.

```
# See the local help map
$psLocalHelp | Format-List

```

### Beispielausgabe

|||
|-|-|
|Schlüssel: Add\-Computer|Wert: WindowsPowerShellHelp.chm::\/html\/093f660c\-b8d5\-43cf\-aa0c\-54e5e54e76f9.htm|
|Schlüssel: Add\-Content|Wert: WindowsPowerShellHelp.chm::\/html\/0c836a1b\-f389\-4e9a\-9325\-0f415686d194.htm|

 Das nachfolgende Skript fügt der Liste einen Eintrag hinzu.

```
$psLocalHelp.Add("get-myNoun","c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### $psOnlineHelp
 Dabei handelt es sich um ein Wörterbuchobjekt, das eine kontextbezogene Zuordnung zwischen den Titeln der Hilfethemen und den entsprechenden externen URLs verwaltet. Es wird verwendet, um die Hilfe für ein bestimmtes Thema im Web zu finden. Sie können Themen zu dieser Liste hinzufügen oder aus dieser Liste löschen.

```
$psOnlineHelp | Format-List

```

### Beispielausgabe

|||
|-|-|
|Schlüssel: Add\-Computer|Wert: http:\/\/go.microsoft.com\/fwlink\/p\/?LinkID\=135194|
|Schlüssel: Add\-Content|Wert: http:\/\/go.microsoft.com\/fwlink\/p\/?LinkID\=113278|

 Das nachfolgende Skript fügt der Liste einen Eintrag hinzu.

```
$psOnlineHelp.Add("get-myNoun","http://www.mydomain.com/MyNoun.html")
```

## Weitere Informationen
 [Das Windows PowerShell ISE-Skriptobjektmodell](../../core-powershell/ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  



<!--HONumber=Jul16_HO1-->


