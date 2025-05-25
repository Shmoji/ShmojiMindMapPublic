  * journal
    * [[2023-10-10]]
      * I got the CLI working quick, but then could not get the flask API version to work due to crazy errors.
      * Finally got API version to work and i have no idea what solution was, but here's some things i did:
      * 1) couldnt get it to work when running flask app on windows command line, so i switched to ubuntu WSL command line.
      * 2) sudo apt-get update
      * 3) sudo apt install nvidia-cudnn

  * how TOs
    * CLI how TOs
      * how to use certain model: "--model large-v2"
      * how to label the transcript with speaker ID's
        * --diarize (need to give huggingface api token right?)
        * --hftoken <token> (this is how you pass in HF token to cli) - full explanation here: https://github.com/m-bain/whisperX#speaker-diarization
        * (set number of speakers if known e.g. --min_speakers 2 --max_speakers 2)
