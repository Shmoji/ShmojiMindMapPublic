  * how TOs ^RisYOH69U
    * how to get more info in console logs (such as what event called method)
      * Just throw new Exception("test") and youll get more info such as what event it was that called method
    * how to use a newly imported package in Visual Studio ^qtzoarWSv
      * If it doesn't work automatically, at the lowest folder level: create -> assembly definition. Click on that file, add needed packages as Assembly Definition References. The files to add to that file are usually asmdef and in a runtime folder. This is how i was able to use WebXR in VS. This also allowed me to use Tilia package in VS. Before, i couldnt even import it into file.