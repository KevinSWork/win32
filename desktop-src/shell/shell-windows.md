---
Description: Creates and returns a ShellWindows object. This object represents a collection of all of the open windows that belong to the Shell.
title: Shell.Windows method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Shell.Windows
api_type: 
- COM
api_location: 
- Shell32.dll
---

# Shell.Windows method

Creates and returns a [**ShellWindows**](shellwindows.md) object. This object represents a collection of all of the open windows that belong to the Shell.

## Syntax


```JScript
retVal = Shell.Windows()
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>Shell.Windows() As IDispatch</code></pre></td>
</tr>
</tbody>
</table>



## Parameters

This method has no parameters.

## Return value

### JScript

Type: **[**IDispatch**](https://msdn.microsoft.com/en-us/library/ms221608(v=VS.71).aspx)\*\***

An object reference to the [**ShellWindows**](shellwindows.md) object.

### VB

Type: **[**IDispatch**](https://msdn.microsoft.com/en-us/library/ms221608(v=VS.71).aspx)\*\***

An object reference to the [**ShellWindows**](shellwindows.md) object.

## Examples

The following example uses **Windows** to retrieve the [**ShellWindows**](shellwindows.md) object and display a count of the number of items that it contains. Proper usage is shown for JScript, VBScript, and Visual Basic.

JScript:


```JScript
<script language="JScript">
    function fnShellWindowsJ()
    {
        var objShell = new ActiveXObject("shell.application");
        var objShellWindows;
        
        objShellWindows = objShell.Windows();

        if (objShellWindows != null)
        {
            var Shell = new ActiveXObject("WScript.Shell");
            Shell.Popup(objShellWindows.Count);
        }
    }
</script>
```



VBScript:


```VB
<script language="VBScript">
    function fnShellWindowsVBS()
        dim objShell
        dim objShellWindows
        
        set objShell = CreateObject("shell.application")
        set objShellWindows = objShell.Windows

        if (not objShellWindows is nothing) then
            WScript.Echo objShellWindows.Count
        end if

        set objShellWindows = nothing
        set objShell = nothing
    end function
 </script>
```



Visual Basic:


```VB
Private Sub fnShellWindowsVB()
    Dim objShell        As Shell
    Dim objShellWindows As ShellWindows
    
    Set objShell = New Shell
    Set objShellWindows = objShell.Windows

    If (Not objShellWindows Is Nothing) Then
        Debug.Print objShellWindows.Count
    End If

    Set objShellWindows = Nothing
    Set objShell = Nothing
End Sub
```



## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional, Windows XP \[desktop apps only\]<br/>                                         |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                           |
| Header<br/>                   | <dl> <dt>Shldisp.h</dt> </dl>                           |
| IDL<br/>                      | <dl> <dt>Shldisp.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Shell32.dll (version 4.71 or later)</dt> </dl> |



 

 



