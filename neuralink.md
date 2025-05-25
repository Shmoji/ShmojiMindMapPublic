  * tracking thoughts
    * tracking Neuralink team talks/presentations - general/non-specific
      * [[2024-07-10]]
        * rn they do 10 bits/s. very soon will do 1Mb/s. 1Gb/s is possible years from now
        * Elon just said they just now moved to 2nd human patient
        * Noland's device takes about 4 hours to charge fully. He uses for 70 hours per week
        * they plan to have it charge while you sleep eventually (maybe some pillow) 
        * brain is done growing by age 25 they said
    * tracking learnings about bci or Neuralink due to something Neuralink-related
      * [[2024-08-14]] Bliss Chapman interview, hair width, action potential width in time, samples, hertz #memo
        * Bliss Chapman: 100 microns/micrometers is about average width of human hair. An electrode needs to be in that distance or less to detect action potential of a single neuron
        * Bliss Chapman: the width of action potential is about one millisecond - from start of spike to end of spike. in order to detect if spike is occurring or not, you NEED to SAMPLE that signal (sample the local field potential nearby that neuron) MUCH more frequently than once per millisecond - in order to detect this is characteristic waveform of neuron producing an action potential - me: bc otherwise you dont detect any change since the thing is finished in 1 ms. 
        * Bliss: neuralink samples across all 1024 electrodes about 20K times/samples per second (20kHz). 20kHz means for any given 1ms window, there is about 20 SAMPLES that tell what the exact shape of that action potential looks like. Bc: 20k samples per sec / 1000 ms = 20 samples per ms
        * Hertz means cycles/samples/data-points per second (always relative to 1 second) ^Yyimhk6vK
        * Bliss: after doing that sampling, we can process that electrical signal into "where do we detect spike" and "where do we not" in this 1ms - 0 or 1. This allows to take very high density signal and convert to something much more compressed that can be sent out over wireless radio like Bluetooth
  * their tech, features
    * Neuralink electrode thread
      * what are cool factz about it?
        * SUPER SKINNY: a human hair is 100 micrometers; neuralink thread is 5 micrometers
        * 16 ELECTRODES PER THREAD (Emotiv Epoc X has total of 14 electrodes WOW)
  * anecdotes
    * Musk thinks AGI will happen before Neuralink is ready for humans at a real production level for non-ill people
    * David Shapiro thinks Neuralink wont solve the [[bandwidth problem]] - he thinks it's more likely that a headband or hat or whatever that reads brainwaves is more likely to solve that issue.
    * Sumner Norman: would take 6 Neuralink implants to cover just 1 percent of the human cortex. And that's just surface cortex. That doesn't include the sulcal folds or deep brain areas.
  * [[search map]]: #[[bci, bmi, brain interfaces]] #[[invasive bci]]