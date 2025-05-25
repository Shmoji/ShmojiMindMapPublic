  * tracking
    * tracking my settings changes
      * [[2023-09-24]]
        * For shmoji, changed "preset" setting to "max quality" from "quality"
      * [[2023-12-26]]
        * For evilshmoji, changed bitrate to 6000.  On MSI looks like this slightly fixed lagging issue that happens even when not streaming - maybe. Seems fine with OBS in bg, but once i open the app it seems to lag again
        * changed keyframe interval to 2
        * changed "preset" to quality instead of max quality - bc saw that on a streamlabs site
        * think i finally figured out and fixed MSI lag issue. It's because OBS defaulted to GPU 0 which was a GPU built into the same chip as the CPU. I changed it to 1 which is the actual GPU and now seems to be good
    * tracking thoughts and research on bitrate
      * [[2023-12-28]]
        * reddit person: dont do dynamic bitrate. also, it’s better to have a rock solid 720p 60fps 4000bit than an unstable 1080p 60fps 6000bit
        * reddit person: Dynamic should only be used if you know that your connection is very unstable and fluctuates at a consistent basis
        * i used speedtest to see my upload speed and https://bitratecalc.com - seems 6000 is good bitrate on this network (on ethernet). Honestly on wifi, may need dynamic bc how poop the connection is.

  * Audio levels
    * Audio levels for desktop
      * When streaming a game: -22dB
      * When podcasting: 0dB
  * how TOs
    * how to set settings so stream audio is heard by viewers AND the different audio tracks are recorded separately (that way can put different gain amounts on different tracks)
      * in global settings (cog near audio stuff), you can set THE streaming track and then set how many audio tracks you want
      * then, in source settings of audio settings, make sure stream track is highlighted. AND it will forcefully be highlighted as recording track. You can then highlight the other tracks in order to only record one type of audio on that track (hopefully that makes sense lol)
    * how to know what encoder to use when streaming on streamlabs obs?
      * ME: dont worry too much about this. If your GPU is pretty good, then just use hardware encoder.
      * The software encoder (x264) uses your CPU to encode video, while hardware encoders like NVENC utilize a dedicated encoder in the GPU, allowing you to play and stream without compromising game performance. If you have a particularly powerful GPU or a dedicated streaming PC, consider using a hardware encoder. In most cases, the software encoder (x264) will be able to handle the encoding process, as long as you have a powerful CPU.
      * If you are using an NVIDIA graphics card, it is recommended to stream with NVENC New. However, if you are using other GPUs, you should check the manufacturer's website for information on their hardware encoding capabilities.
    * how to set bitrate
      * streamlabs recommends using this calc: [Bitrate Calculator](https://bitratecalc.com/)
        * based on your upload speed, so will be different depending on what network you are on
      * streamlabs: 6000 kbps
      * [this source](https://www.esports.net/streaming/streamlabs/settings/): Use a bitrate of at least 4000 kbps for 1080p resolution and 6000 kbps for 4k resolution
    * how to set keyframe interval
      * seems every source i saw recommends 2 seconds - including Streamlabs
  * questions
    * what is video encoding?
      * process of converting video files from one format to another. It involves the compression and processing of raw video data into a digital format that is suitable for storage, transmission, and playback on various devices
      * Compression: One of the primary purposes of video encoding is to compress video files. Raw video files are typically large and impractical for streaming or storage. Encoding compresses these files to a more manageable size, making it easier to transmit over the internet or store on digital media.
    * what is GPU setting in output section?
      * you use an index number to choose GPU to use for encoding when using hardware encoder. If you only have 1 GPU, then keep it 0. The next GPU would be 1 if you had another.
    * what is bitrate?
      * the rate at which bits are transferred from one location to another. In other words, it measures how much data is transmitted in a given amount of time. In simple terms, it's like the flow rate of water through a pipe
    * what is Keyframe Interval?
      * setting related to video encoding that determines how often keyframes are sent in the video stream. A keyframe is a complete image frame, while the frames in between (interframes) contain only the information that has changed from the previous frame.
      * Impact on Quality and Bandwidth: A shorter keyframe interval (more frequent keyframes) can improve video quality, especially in videos with lots of scene changes or motion, but it requires more bandwidth. A longer interval reduces the bandwidth requirement but might lower the video quality, particularly in fast-moving scenes.
        * In the context of streaming and video encoding, "bandwidth" refers to the amount of data that can be transmitted over an internet connection in a given amount of time
        * Internet Connection Limits: Viewers' internet connection speeds limit how much bandwidth is available for streaming. If a stream's bitrate exceeds the viewer's available bandwidth, it can lead to buffering, delays, or the need to reduce the video quality.
