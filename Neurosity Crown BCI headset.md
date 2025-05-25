  * tracking thoughts
    * tracking research on how to use (not actual experience)
      * [[2024-01-23]]
        * Two different Datwyler electrodes that ship with every Crown. Large electrodes are better for long and dense hairstyles. Ten large electrodes and ten medium electrodes ship with every Crown so the user may swap electrodes to fit their hairstyles.
    * tracking thoughts on the different hardware-software pieces of the device FROM RESEARCH
      * [[2024-01-23]]
        * analogue frontend AFE - electronic device that sits near the sensors
        * [[active electrodes]]:
          * their paper: are on-electrode circuits that actively amplify
voltage at the electrode to minimize noise while allowing for higher electrode impedances. Amplifiers must provide amplification selective to the physiological signal, reject superimposed
noise and interference signals, and guarantee protection from damages through voltage and
current surges for patients and electronic equipment
        * holy poop, most of parts are for getting noise tf out of there

    * tracking thoughts on data privacy
      * [[2024-01-12]]
        * they mention a lot of good stuff on data privacy, but they dont have details, so im uncertain i trust it
        * altho, i do see repos on github for their oauth, so maybe that's a good sign?
        * they literally say they collect personal info in their PP. And will give to people if needed - which can be bad if your gov doesnt care about your privacy. We need a decentralized version

  * questions
    * what da deal on data privacy?
      * apparently "Hardware-Enabled Security" thanks to the N3 chipset, but couldnt figure out why. EDIT: oh apparently they built the N3 chipset
        * they say this: "Inscribed in every N3 chipset we make are two statements: never lose raw data, never send raw data.
The N3 chipset handles all signal processing. It translates your raw brainwaves into metadata so that those brainwaves never leave the device. It's the heart of the Crown because the brain is, you."
      * neurosity site: Your thoughts stay with you.
        * "As a team, we've built the N3 chipset to empower you. It's created to translate your brain's electrical signals into action and insight for you to shape your world.
It doesn't watch. It doesn't listen. It doesn't know that you actually love broccoli. And it never stores your brainwaves.
The N3 chipset ensures that no third-party will ever see or receive your brain data. By having all computation executed on device, it eliminates the need to have data analyzed by an external source. Your thoughts are yours, and we keep it that way."
        * their PP: "INFORMATION THAT WE SHARE

We will not disclose, trade, rent, sell, or otherwise share personal information, without consent, except as otherwise set out herein, in any special consent you have provided, or as permitted or required by law." - you can imagine in a gov where certain groups can bypass laws, this wouldnt be good - why decentralized versions are needed
          * mm dont like this either in PP: "TRANSFER OF PERSONAL INFORMATION TO OTHER COUNTRIES

Your personal information may be collected, used, processed, transferred, and retained by us, our affiliates and our service providers in multiple countries"

      * them: "state-of-the-art Encryption, Authentication, and Authorization" - but what are the details to prove that?
