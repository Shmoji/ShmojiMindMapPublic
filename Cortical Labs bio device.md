  * what is it?
    * not really sure at the moment
    * they call it:
      * DishBrain
      * Synthetic biological intelligence
      * organoid intelligence
  * random notes from video on device
    * the cells are placed in a [[chassis]]. This chassis takes input and output (of what exactly) through some sort of wires
    * device has triple ?diasonic? pump. They are like a [[kidney dialyzer]]
    * has a feeding reservoir
    * has a waste reservoir
    * has 2 filtration units (how is this different from pump above?)
      * there are 2 of them bc there is inner loop and outer loop
        * inner loop circulates around
        * outer loop circulates the (1) nutrients and (2) waste. It (does it mean just outer loop or both loops?) has a semi-permeable membrane inside that contacts with the 2 media (does this mean the nutrients and waste?)
    * has gas exchange system. takes gas from outside device and does something with it lol. I think the gas comes from ports that are always closed unless something is input into the port
      * 3 ports: normal air, C02, and N2 (apparently there are right amounts to mix these)
    * biological device is more energy efficient by a large amount than an NVIDIA GPU ^0q1MAU3ns
      * 800k-1M neurons is about 10^-4 (or -5) W. GPU is like 500 W. 
    * sample efficiency is better than pure device/NVIDIA GPU. Biological device doesnt compute same as GPU bc they do NOT train at inference (one loop). Bc one loop, amount of data you require to train these is a lot less
    * You have to feed it. Instead of electricity, it takes "pink fluid", "artificial cerebral spinal fluid"
    * For most part, new neurons cant be generated that we know of rn in 2023. There's some studied of small amounts being regenerated, but mostly not. Lifespan of human is about lifespan of their neurons. All of this to say: this device could prob last like 20-30 years  - just keep feeding it!
      * Have to maintain PH. Cant be too acidic. Cant be too basic. That's what C02 is for bc C02 in liquid form converts to [[bicarbonate (bicarb)]] - which is a very good acid-base buffer
      * Control how much oxygen goes in. Room air has about 20% oxygen as a partial pressure at sea level. Much higher than what brain has. Brain has around 5-8% oxygen concentration. They put nitrogen in to drop the oxygen pressure in the gas mixer
      * Maintain stability so dont get contamination (what dat mean?)
      * Have heat pad under chassis to keep temp steady at 37 degrees C (i think i heard this number wrong but idk).
    * Apparently chip of neurons looks like lil ivy growing up a wall over time as it grows.
    * does chip get smarter over time just from running? A: no! bc you need to give it a structure info landscape which apparently means you need to implement a simulation. 
      * if you dont put cells/device into a simulation, they all turn into oscillators
        * Metronome table/resonance - experiment with table full of metronomes, you turn them at different rates - after few oscillations they all start to tick at same rate despite not in beginning. They all converge into resonant frequency. These neurons do this exact same thing. If you dont interrupt them with a structure info landscape (simulation), they all turn into oscillators. 
        * in terms of this device, why is that bad?
          * my guess: bc either: 1) they cant learn 2) they can learn, but cant get smarter
      * me: so does simulation stop too many nodes from being the same? like without simulation they all resonate together, but with it...they dont always - they can be unique??
      * structure info landscape: when you're giving stimulations (electrical signals to the neurons that are based on some sort of rules)
        * ex: game of pong is SIL. It has paddle and ball. 2 states. States have an update rule - ball that's moving at a vector (set trajectory) and rules around what to do if hits 3 not death walls. Hitting back wall is game over. Can control paddle. All these rules make up the SIL. 
        * feel he didnt really answer what SIL is aside from rules, a controller, and states. 
      * They only learn game if you give them rewards and punishments. Not actually zapping the cells lol, but just sending them different types of info/signals. 
        * Based on free energy principle. Systems try to come up with good hypothesis about the world to match the observations. (1) They generate what they think the world is - (2) they observe the world. - and that feeds on itself like a loop - they get better at making predictions. 
        * Do not have ability to go in and change the "weights" (synaptic weights of neurons). We can change environment and what stimulations are given to cells tho.
        * They can make the world more predictable for the cells by giving them low [[entropy]] signal (like a SIN wave) as reward, the neurons respond well to that when they hit the paddle. +1 predictability
        * If they miss the ball and it hits back wall, they give high entropy signal like random WHITE NOISE as punishment. This signal makes world more unpredictable
        * Not good at math. But is good at stochastic noisy computation that digital devices are bad at.
    * has ARM chip and FPGA module - this is how they do really fast digital to analog and vice versa conversion. 
    * the cells used in 2023 are hippocampal cells. They think they have no memory, but hippocampus is known for memory storage and retrieval.
    * again, no training and inference - just one loop
  * future use-cases
    * put your cells into this and then debug to fix any issues you may have

  * questions
    * what is it not good at?
      * Math
  * related
    * [[biological hardware]]
