  * tracking thoughts
    * [[2023-09-27]]
      * Using CLI today using large-v2 model, it's taking around 10 minutes to transcribe a 4 minutes video. idk if it's using CPU or GPU. Took about 6 minutes to download large-v2 model - it was about 3GB.
      * I was confused at first how the model used was local if the code imported it, but then i realized it's basically the same as node_modules. If you have it installed locally, you dont even need internet. 
      * i ran python code file to transcribe 4 minute video using large-v2 model and it took like 2 minutes.
    * [[2023-12-04]]
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/whisper from openai, transcription, to text#^IzQmaYRc_|how long to download large-v3 model?]]
      * it literally took 1 minute to transcribe 7 and half minute video using large-v3
      * discovered Insanely Fast Whisper and Facebook's Seamless Communication models - one of which does real-time transcription
    * [[2023-12-15]]
      * i compared large-v2 model using whisperx and diarization to large-v3 in Pinokio - specifically using really bad hard-to-hear voices at CWP - surprisingly the whisperx was better - it 1) recognized more of the speech 2) didnt hallucinate like Pinokio one - i wonder why - like if there's something OP going on in whisperx in terms of picking up hard-to-hear speech. The performance benefits in this narrow use-case could just be due to random settings too lol.

  * how TOs
    * how to download whisper model locally?
      * Running the script (that transcribes) OR running CLI transcription the first time for a model will download that specific model; it stores (on windows) the model at C:\Users\<username>\.cache\whisper\<model> (you can google location for other OS)
      * Looks like actual Download links are in [**init**.py](https://github.com/openai/whisper/blob/f296bcd3fac41525f1c5ab467062776f8e13e4d0/whisper/*init*.py) @ lines 17-27
      * Once downloaded, the model doesn't need to be downloaded again. Considering that the medium model alone is ~1.5 GB, that seems to be the best solution
      * NOTE: there is a command to change the directory that model is cached to
    * how to setup backend Flask server that allows you to transcribe audio/video to text
      * [How to Build an OpenAI Whisper API - Deepgram Blog ⚡️ | Deepgram](https://deepgram.com/learn/how-to-build-an-openai-whisper-api)
      * also: checkout whisper-hosted in users/jacks/projects/random (the project starting with nextjs name is actually frontend connected to this backend)
    * how to quickly run whisper locally?
      * [[Pinokio computer]]
  * questions
    * how long to download large-v3 model? ^IzQmaYRc_
      * about 5 minutes at 11MB/s
