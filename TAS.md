  * what is TAS? #[[fast memo]] ^YOMAgayRP
    * Tool-Assisted Speedrun (or Superplay). superplay bc maybe not always trying to be fastest (maybe showing off cool tricks)
    * basically a file of framebyframe inputs for a specific game
    * Playback: During the actual run, this input file is played back on an emulator or specialized hardware. It's not a computer program actively making decisions in real-time.
    * Frame-by-Frame Precision: The program applies inputs on a frame-by-frame basis, matching the exact timing specified in the TAS input file.
    * No Real-Time Decision Making: While it is a program applying the inputs, it's not making decisions about what inputs to apply. It's simply following the pre-recorded script with precise timing.
    * Q: isnt there certain parts of game that are so RNG heavy that even if the same input, it cant always produce the same results?
      * Yes. While TAS runs are generally designed to be deterministic (same inputs always produce the same results), there are indeed cases where pure RNG can introduce variability.
      * YES, but they are relatively rare. Most TAS runs are designed to be perfectly reproducible given the same inputs and starting conditions. When inconsistencies do occur, they often lead to **interesting discussions** and **further research** within the TAS community to understand and potentially overcome these challenges.
      * Speedrun.com Controversy: There have been cases where TAS runs were rejected from speedrun.com leaderboards due to inconsistent results on **real hardware**
      * Q: how could you run a TAS on real hardware?
        * TASBot: special device for console verification of TAS runs - plugs into controller ports to input commands exactly
        * other ways too, like software, but TASBot makes sense 2 me
