# uninstall edge from windows 11
By default, apps and programs doesn't let you uninstall edge, the "uninstall" option is greyed out.  Changing this registry key lets you uninstall edge.  

Launch powershell as admin and run the below code, then uninstall edge from Add & Remove Programs 

```
set-ItemProperty -Path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Microsoft Edge' -Name 'NoRemove' -value 0
```


## Explanation
Run this to check the current registry value, by default it should return 1

`get-ItemProperty -Path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Microsoft Edge' -Name 'NoRemove'`

Run this to set it to 0

`set-ItemProperty -Path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Microsoft Edge' -Name 'NoRemove' -value 0`

Check it again, it should be 0

`get-ItemProperty -Path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Microsoft Edge' -Name 'NoRemove'` 
