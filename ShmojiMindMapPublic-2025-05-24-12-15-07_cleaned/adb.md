  * paths in regards to adb

    * if there are spaces or special characters in path, it messes adb up, so use double quotes around path (at least on Windows). 
  * how TOs

    * how to see filesystem on headset
      * adb shell

    * how to see devices adb has access to

      * adb devices

    * how to install apk to headset
      * adb install "apks/Ribbit.apk" (dont need to worry about putting path of headset)
    * how to get logs from adb device
      * adb logcat > filename.txt
      * you wont see anything in console when sending to file like this. So just close connection anytime
