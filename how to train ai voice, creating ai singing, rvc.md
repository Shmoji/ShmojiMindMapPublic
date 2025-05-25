  * journal
    * [[2023-10-20]]]
      * took best parts of my voices from my songs and trained model on that and used it - but didnt sound good - almost sounded the same. Felt like it was using too much of the vocals that were meant to be replaced.
    * [[2023-12-16]]
      * experiment: train model on singer i like. Have them sing my bad vocals with their voice.
      * then, have my bad voice sing their good version of my vocals    
      * got this stupid error: FileNotFoundError: [Errno 2] No such file or directory:
        * converting mp4s to wavs didnt fix it
        * using input folder and drag and dropping files didnt fix it
        * checked console and saw ffmpeg not installed
        * uninstalled RVC and reinstalled but ran into bug with vs build tools. Uninstalled those, reinstalled RVC and then all good
    * [[2023-12-17]]
      * Still working on experiment from 16th of Dec. 
      * Also, training my voice model on my songs, which may suck. May actually be better to train on me singing to songs that i know i sound good to like in car
      * i learned filenames cant have spaces in them or breaks things, good to know lol
      * experiment done: results are that my singing authentic flow just isnt good bc even guardin's voice doesnt sound good with it
      * NOTE: can also use RVC for regular voices, not just singing
    * [[2023-12-18]]
      * think i learned something about LLM training. I tried deleting my ShmojiVoice model and training new, but it started from checkpoint. This is because i saved pretrained model G and D path defined in RVC ui. I used this same path for every model so far (shmojitry1, guardin, and sadeyes), so now cant delete bc the other 2 models are good. In future, change the D and G path pretrained path names.
      * okay think i was wrong about the above - but then im confused how model was starting from checkpoint and not even actually training
      * i still wonder: how to delete checkpoints? bc i already know how to delete models
  * how TOs for RVC
    * how to train ai voice
      * if audio is in video format, convert it to mp3/wav. can just use kdenlive - drag vid into kdenlive, right click it, extract audio, audio file instantly goes to folder that vid is in - quick af
      * using [[Pinokio computer]], RVC webUI app - extract vocals/voice if there's other noises in background
      * using train tab in pinokio, follow this tut starting from around 4 mins: https://www.youtube.com/watch?v=9TroP5mR3CM
      * Nerdy Rodent: around 10-50 minutes of vocals recommended for training
      * Nerdy Rodent: he says harvest is slowest but best quality
    * how to download model and use it
      * download the pth file which is the model
      * place it in C:\Users\user\pinokio\api\rvc.pinokio.git\app\assets\weights
      * refresh on inference page and use it
    * how to delete a model you created
      * idk if there's more to it, but i found my trained models in here: C:\Users\user\pinokio\api\rvc.pinokio.git\app\assets\weights
    * how to choose model when removing instruments and bg noises
      * idk, but i found HP2-instrumental worked really well for extracting vocals of Control
      * Nerdy Rodent: HP2 is for input vocals without harmony and HP5 is input vocals with harmony (but output wont have harmony i guess)
    * how to edit voice in general once training and inference is done
      * Bandlab autopitch https://www.bandlab.com/studio?id=fae28a07-e39d-ee11-8926-000d3a428257
  * questions
    * what to do if it wont acccept my file path?
      * 1: make sure if it's asking for file or folder
      * 2: make sure no spaces in names
  * notes
    * the term that seems to be sticking is RVC when it comes to ai singing
  * terms
    * transpose - basically turning audio up or down in pitch