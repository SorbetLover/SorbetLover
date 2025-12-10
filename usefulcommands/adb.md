## check last reboot cause
```
adb shell getprop | grep -i boot
```
then send to chatgpt, its easier
# app deletion 
### * locate package
```
adb shell cmd package list packages --user 0
```

### * confirm the package by opening the app
```
adb shell am start -S package
```
<details>
  <summary><ins>open this if the package is not the thing that opens the app</ins></summary>
  
  ### >> sample with Funkin, that needs to be pointed to another file
  
  - search the file
  ```
  adb shell cmd package resolve-activity --brief me.funkin.fnf
  ```
  
  - start the app
  ```
    adb shell am start -n me.funkin.fnf/.MainActivity
  ```

</details>

### * delete the app

- normal

```
adb uninstall package
```

- forced (apps protected by the sys, needs higher permission)

```
adb shell pm uninstall --user 0 package
```
