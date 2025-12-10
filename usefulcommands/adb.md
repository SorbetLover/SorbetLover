## check last reboot cause
```
adb shell getprop | grep -i boot
```
## app deletion 
### normal
```
adb uninstall package
```
### forced (apps protected by the sys, needs higher permission)

```
adb shell pm uninstall --user 0 package
```
