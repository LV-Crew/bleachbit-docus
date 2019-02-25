---
layout: page
title: "CleanerML Examples"
category: doc
date: 2019-02-25 08:45:00
order: 8
---

**Just some CleanerML Examples...**

###command="ini"

**Cleaning a Parameter in a INI File**  
Deletes in `section` the `parameter`.

**Example:**  
```<action command="ini" search="file" path="%AppData%\GHISLER\wincmd.ini" section="MkDirHistory" parameter="0"/>```

**Explanaition:**  
`command` is always `"ini"`, `search` is always `"file"`, `path` is the path to the INI file, `section` is the higer section and `parameter` is the parameter you want to delete.  

**No wildcards allowed (, yet)!**  

<br>

###command="winreg"

**Cleaning a Windows Registry Key/Path**  
Deletes in the `path` (tree in Regedit) a "folder", or a key.

**Example:**  
```<action command="winreg" path="HKCU\Software\Adobe\Acrobat Reader\5.0\AVGeneral\cRecentFiles"/>```

**Explanaition:**  
`command` is always `"winreg"`, `path` is the path/tree/folder/key you want to delete.

<br>

**Cleaning a Windows Registry Key/Path with a wildcard**  
Deletes in the `path` (tree in Regedit) a "folder", or a key with a wildcard.

**Example:**  
```<action command="winreg" path="HKCU\Software\XnView\Start\FileName_*" />```

**Explanaition:**  
`command` is always `"winreg"`, `path` is the path/tree/folder/key you want to delete, "*" match any string that will be find.

<br>

###command="delete" search="file"

**Deleting a single file**  
Deletes a single file in the file system.

**Example:**  
```<action command="delete" search="file" path="$APPDATA\XnView\XnView.db"```

**Explanaition:**  
`command` is always `"delete"`, `search` is always `"file"`, `path` is the path & name of the file to delete.

<br>

###command="delete" search="walk.files"

**Follows**  

<br>

###command="delete" search="walk.all"

**Follows**  

If you add a "*" at the end of a path by `walk.all`, nothing gets deleted!
```<action command="delete" search="walk.all" path="%windir%\Temp\*"/>```

And this doesn't work, too.   
```<action command="delete" search="walk.all" path="%windir%\Temp\WER*.hdmp"/>```
Use `glob` instead:
```<action command="delete" search="glob" path="%windir%\Temp\WER*.hdmp"/>```

<br>

###command="delete" search="glob"

**Follows**  

<br>

###Delete the content of a folder and the folder itself

**Follows**  

**Example:**  
```<action command="delete" search="walk.all" path="$LocalAppData\Temp\acrord32_sbx"/>```
```<action command="delete" search="glob" path="$LocalAppData\Temp\acrord32_sbx"/>```

<br>

