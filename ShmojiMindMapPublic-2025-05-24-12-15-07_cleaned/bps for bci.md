  * tracking thoughts
    * tracking trying to understand what it is
      * [[2024-08-02]] #memo
        * Noland got world record for bps with neuralink...at least for a lilbit as person0
        * meme: GRID TASK so fast
        * stands for bits per second - it is the standard measure for SPEED and ACCURACY of cursor control (in general, not just bci)...also think it works for just control of device in general; not JUST cursor control. meme: bit is 2 states and 2 general measures: speed to reduce uncertainty and accuracy of device/system's signal processing converting person intention to command...which reduces uncertainty
        * QUESTION: so how much of this quantity is determined by user and how much by device used? my guess: some devices will make your min score (bps) on gridtask much different than with other devices. But user can also determine outcomes/bps. if you not trying, you can get 0.
        * but i still dont understand, so gonna try to summarize:
          * TASK and USER GENERATING SIGNALS: hey YOU. Perform task like moving cursor to changing targets in grid. User thinks about the movement, which generates neural/electrical signals
          * SIGNAL CAPTURE: bci records neural activity associated with user's intentions. So, capturing electrical signals from brain via implanted electrodes
          * SIGNAL PROCESSING: recorded neural signals processed and decoded by algos to interpret user's intended actions. Translating patterns of neural activity into COMMANDS that move the cursor
          * PERFORMANCE MEASUREMENT:
            * ACCURACY of human-machine system turning electrical sigs to CORRECT intentions/commands: system measures how accurately user's intended actions are decoded. Higher accuracy means decoded commands closely match user's intentions
            * SPEED: system measures how fast user can perform task. Faster task completion indicates more efficient signal decoding and transmission (diff than accuracy of this same thing). Speed of decoding and speed of transmission sound like different quantities too.
            * INFO RATE: by combining accuracy and speed, the system calculates the info rate - expressed in bps. This represents the AMOUNT of info successfully transmitted from brain to the external device per second
          * INFO THEORY: it seems "bit" in this context comes from information theory - where info content (measured in bits) depends on 1) number of possible choices and 2) the probabilities of those choices
          * woah, iz like it's quantifying a YOU/person/agent
          * QUESTION: so in this context, a bit is info that isnt necessarily digital? whereas bits are typically thought of as computer thing
            * GPT4o: yes. Not necessarily digital but instead conceptual. it's based on info theory where a bit represents the amount of info needed to distinguish between two equally likely alternatives
              * key points
                * 1 BIT = 1 NEURAL SIGNAL SAMPLE (of some type) DETERMINING ONE VALUE FROM 2 CHOICES, bit is measurement of REDUCTION of UNCERTAINTY, bit is MEASUREMENT OF USEFULNESS, maybe MEASUREMENT of AMOUNT of INFO which can then be used as rate: in BCIs: it measures reduction of uncertainty in understanding the user's intent. For ex: if a neural signal helps system determine one out of 2 possible actions, that's one bit of info
                * digital bits are concrete representations of data in electronic devices. info theory bits are abstract measure of info content - applicable in various fields like bcis, communication systems, etc
            * me: so it seems bits measure reduction of uncertainty
          * me: so a bit is a measurement of info...whatever the heck info is. i think info is something that reduces uncertainty (is that bc it is useful data?)
          * GPT4o: the abstraction of bits helps quantify the efficiency and effectiveness of BCIs in how much meaningful info can be extracted from the brain and used to control external devices
          * CAN HAVE MANY MEASUREMENT TYPES 4 BIT/info/reduction-of-uncertainty: so bits can probably use several different hard quantity measurements related to speed, accuracy, etc in order to measure info bc info IS reduction of uncertainty or useful data - and many quantities can be used to measure that - and bit is a wrapper for all those quantities
          * bit seems closer to info than to data. closer to subjective than objective
          * Elon: a human doesnt even do 1 bps over course of one day. there are 86400 seconds in a day and you dont communicate 86400 tokens in a day (meme: 3600s=1H, kinda look like 3600 * 24 outcome would be 86400 lol)
            * me: ehh not really, it depends how you're measuring tokens. But if trying to be narrow and measure some sort of "usefulness of FAST communication" quantity then maybe this makes sense
            * seems he thinks most useful measure of value is objective symbols per time. don't think i agree. But also he understands memes, so this more just shows his bias OR he just like this measure as most objective one possible (well for now, im sure in future you can approximate info content of each symbol relative to society/group(s)). And makes sense, could see that being good objective measure to track tech progress as things foom
          * Elon: a lot of what your neurons are doing is compressing concepts to symbols/syllables/qualia OR key strokes or whatever you doing. This is what most of brain compute goes to. 
          * there is argument that this compression is healthy bc as you compress more and more, you find what is most essential
        * me: bit = quantifying info into an amount. info is useful data bc this data reduces uncertainty. many things reduce uncertainty. bps = rate of info transfer/communication from human to machine
      * [[2024-08-03]] #memo
        * it's interesting bc bit in digital is kinda measuring info too, but it's less subjective i guess...closer to data. Whereas bit in info theory is more subjective and more close to the agent it feels like - measuring something ephemeral like the soul...i may be wrong about this tho
        * if you think about it, bit in digital is defs reducing uncertainty too by doing either 0 or 1
        * information reduces uncertainty. but not always for all agents. it depends on your goals. digital "bits" are univeral. info theory "bits" are not universal