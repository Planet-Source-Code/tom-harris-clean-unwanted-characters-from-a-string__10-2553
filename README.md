<div align="center">

## Clean Unwanted Characters From a String


</div>

### Description

Function to clean all characters but A-Z, a-z, and 0123456789. When I don't use Regular Expressions I use this function to put only the characters I want into a string. It is very useful for password generation. Look up the Dec number on an ASCII chart and use this for many things.
 
### More Info
 
The string you want to remove unwanted characters from

You will need an ASCII chart to look up the DEC values associated with the ASCII character if you want to modify the specific chars stripped.

http://www.asciitable.com is a good resource.

A String with only A-Z, a-z, and 0-9 charactes


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Tom Harris](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/tom-harris.md)
**Level**          |Beginner
**User Rating**    |4.2 (21 globes from 5 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Strings](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/strings__10-26.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/tom-harris-clean-unwanted-characters-from-a-string__10-2553/archive/master.zip)





### Source Code

```
'Function to clean all characters but A-Z, a-z, and 0123456789
'When I don't use Regular Expressions I use this function to put
'only the characters I want into a string. It is very useful
'for password generation. Look up the Dec number on an ASCII
'chart and use this for many things.
Public Function CleanString(ByVal strDirty As String) As String
Dim strLen As String
Dim strCounter As Integer
Dim strClean As String
strLen = strDirty.Length
strClean = ""
 For strCounter = 1 To strLen
 Select Case Asc(Mid(strDirty, strCounter, 1))
     Case 65 To 90 'A-Z
       strClean = strClean & Mid(strDirty, strCounter, 1)
     Case 97 To 122 'a-z
       strClean = strClean & Mid(strDirty, strCounter, 1)
    Case 48 To 57 ' 0123456789
       strClean = strClean & Mid(strDirty, strCounter, 1)
    Case Else
       'All other characters are stripped out
 End Select
 Next
Return LCase(strClean)
End Function
```

