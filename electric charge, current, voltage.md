  * electric fields
    * tracking learning what is electric fields
      * [[2024-09-21]] i finally get how non-chord charging works #[[fast memo]]
        * FIELDS DONT NEED CIRCUIT/CONDUCTOR: efields dont have to travel through a circuit. battery can have voltage that creates force/work/change and efield that spans space around it and even light an LED or charge device. i imagine stereotypical pics of efields and mfields coming out ends of battery
        * YOU DONT EVEN NEED CHAIN OF ELECTRONS or closed circuit - there's of course kinda limits to size of efields tho
        * conductors/circuits are just good for conducting the electricity quicker i think
        * PS: i heard from Veritasium that even wifi can charge your phone - which is electromagnetic radiation instead of efield. But it just wouldnt be super good charger lol
        * thing that keeps popping up in my mind: how does the force started at config of charges (voltage) make the jump without chain of electrons? well it's similar to space and gravity - just different dynamic. That force/voltage travels space no matter substrate and then can act on charges due to force it be putting down. Further hits home how fields do the acting - which makes it harder to think of it in linear way (bc prev was thinking about stack of electrons pushing each other like dominos lol)
        * NOTE: actual non-chord charging is thanks to magnetic induction and starts with magnetic energy/EMF. The efield energy i mentioned is very minimal and can barely light an LED (as saw with Veritasium vid) - although maybe if this is minimal or not is controversial
  * what is electric charge?
    * tracking learning what is electric current?
      * [[2024-09-01]] what is electric charge? first try #memo
        * me in 2020: at a fundamental level: charge is just a physical property of these 2 particles IN RELATION TO EACH OTHER: 1) electrons (negative charge) and 2) protons (positive charge) that causes electrons/protons (or the whole they are a part of) to experience a force (the electromagnetic force) when placed in an electromagnetic field - which just about everything has an electromagnetic field - but not all electromagnetic fields are significant or detectable in everyday life. The fields around most objects are extremely weak unless they involve large amounts of charge or high-speed movement of charges.
        * So, strength of experienced force of one object is based on difference in protons and electrons on said object vs difference in protons and electrons on interacting object. EDIT: this is wrong. that is how you determine charge of one object, but not how the amount of force is found out BETWEEN objects. GPT: the difference in charges alone does not give any meaningful measure of the force. Really just tells net charge of 2 interacting objects as 1 object. the correct calculation involves using Coulomb's Law and considering both the magnitude and sign of each charge, as well as the distance between them (so i feel like it was almost right bc both these charges are part of the equation)
        * basically you dont start thinking bout that force until one charged object interacts with another charged object -but the charge is there even before/without the force. Even in vacuum, there will be electric field and potentially a magnetic field if in motion, but no force would be exerted or experienced until interaction with another charged object 
        * for molecules (and larger objects), it is caused by total net charge which means either more electrons or more protons on that object (duh difference)
        * an ion is an atom (or group of atoms) that has lost one or more electrons, giving it a net positive charge (cation), or that has gained one or more electrons, giving it a net negative charge (anion).
        * most atoms are electrically neutral. Despite this, they still always have electromagnetic fields due to distribution of charges inside. Just their effects might be very subtle or require specific conditions to be noticed (charge distribution change - reminds me of fusion in a star)
        * it seems quarks have electric charge - so guess it's not just protons and electrons carrying charge at smallest level.
        * Neutrons have no charge, but are made up of charged quarks (protons too). But quarks are confined by strong force inside - so not really useful to think of charge in terms of them i think
        * for the values you see, each value in the efield is the literal electric force felt by a unit positive charge in that point/time by field - but measured in force/charge or Newtons/Coulomb. Coulombs Law tells force between 2 point charges. You can kinda get value of point in field from this Law tho - but complex
  * what is electric current?
    * tracking learning what is electric current?
      * [[2024-08-30]] what is electric current first try #memo
        * Q: so is electric current tracking the flow of the electrons or the flow of the electric field?
          * So, electric current in conventional terms tracks the flow of electrons, but the practical implications and the speed at which circuits operate are governed by the propagation of the electric field. Both perspectives are correct but apply to different aspects of understanding and utilizing electricity.
          * so practically, it's basically the EFFECT of moving charges rather than the moving charges themselves. This is kinda bc some change in voltage far away in same efield can quickly cause charge/force changes in other part of efield
          * **Signal Speed**: The speed at which devices react to changes in voltage or current, like a light turning on when you flip a switch, is due to the propagation of the electric field, not the physical movement of electrons from one end of the wire to the other (altho u do typically get physical movement of charges where change happens, but it's not from starting voltage electrons lol)
        * the flow of electric charge through a material or a vacuum
        * **Circuit Analogy**: Think of electric current like water flowing through a pipe. The voltage (pressure) pushes the water (charge) through the pipe, and any resistance (narrow parts of the pipe) affects how much water can flow through.
        * UNIT: amp/ampere - In practical terms, if you have a current of 1 ampere flowing through a wire, it means that approximately 6.242 x 10^18 electrons (which constitute one coulomb of charge) are passing through a cross-section of the wire each second. ^IuCVqxJd5
        * **Ohm's Law**
          * Allows us to calculate way electricity flows through a circuit
          * **Ohm's law** states that the [current](https://en.m.wikipedia.org/wiki/Electric_current) through a [conductor](https://en.m.wikipedia.org/wiki/Electrical_conductor) between two points is directly [proportional](https://en.m.wikipedia.org/wiki/Proportionality_%28mathematics%29) to the [voltage](https://en.m.wikipedia.org/wiki/Voltage) across the two points.
          * I = V/R
          * V = voltage (Volts), I = current (Amps), R = resistance (Ohms)
          * Power = V * I OR I^2 * R (measured in watts)
        * **Types of Current**:
          * **Direct Current (DC)**: The flow of electric charge in one direction. This is what you typically get from batteries.
          * **Alternating Current (AC)**: The flow of electric charge that periodically reverses direction. This is the type of current used in most household electrical outlets AND power lines.
        * **Magnetic Field**:
          * A current, by definition, involves moving charges. According to Ampère's Law, any moving charge (current) generates a magnetic field around it. This is why electric currents are inherently linked to magnetism.
      * [[2024-08-31]] current is a bulk property of efield #memo
        * when resistance happens in a circuit (from heater or computer, etc), current decreases, work/energy-transfer is done to do cool stuff
        * since current is bulk property - this current decrease can be detected in whole efield (this is how power companies detect power you use)
          * GLOBAL OBJECT OF EFIELD: so current is variable of global object of efield, but it is caused by all discrete particles in efield (and some have more influence on current than others). 
        * CURRENT FEEDBACK SYSTEM: a sensor somewhere detects change in current from your home, then you are supplied with more current for however much is needed for device - this is important bc if you just had current decrease due to one device and didnt receive any from power company - your other devices may lose their needed current/power
        * also learned that power company generate power in realtime based on demand from resistance triggering current changes from devices of all u ppl. They dont detect your changes directly APPARENTLY, but the LOAD of all these changes in certain areas and then supply to these general areas
        * Q: how does power company increase current sent to your home without increasing voltage? are they sending more electrons or something?
          * **Electrons and Current**: Electrons are the charge carriers that flow through the wires to create current. When the power company increases current, they're not sending more electrons per se but are increasing the flow rate of these electrons. In other words, more electrons are moving through the wires per unit time, which corresponds to higher current. (sounds to me like this ramped up dat speed bb)
          * so current is kinda 1) MOTION: the flow of these charged particles and their rates/speed and how all particles in efield are effected by all others - changing forces/energies in all points, but also 2) the energy transfer from point of power generation to target (device in your home that uses energy) - can also think of as force transfer - or 0/less force to increased force (or replace force in last sentence with movement of particles with fundamental forces attached to interface with)
          * voltage seems like a config that applies constant force/energy in all points of efield. you cant use up the voltage your home is given. it's like a baseline provided energy (but it's only potential until used). while current seems like a finite resource providing limited energy. resistance happens due to your devices and then you need more current supplied from power generation (turning x energy into electric energy using...forces i think) increasing rate of flow of electrons (and forces on all of em) - which propagates that energy and force to you QUICK BOI
          * since voltage is potential, dis y u no charged until ur house uses powah. but current is actualized finite resource measuring energy used (voltage can be used to help calculate it since voltage is like baseline energy)
  * what is voltage? (electric potential difference between 2 points) ^C7fOY-XnZ
    * tracking learning what voltage is
      * [[2024-08-29]] first go at learning voltage #memo
        * Not a pressure, not a force. (The force only comes into this when charges are present - the electric force)
        * But it works to just think as pressure, especially in a circuit. Pressure = force per surface area
        * Voltage is kinda like the effects of a controlled electric charge. Ppl control by deciding how many positive and negative charges. It's about charge amount of 2 or more different objects and their distance separation in space
        * Voltage is basically a measure of the force put on electrons that go by, but not THE force itself bc voltage is still there even when no force - hence "potential"
        * voltage analogy: Think of voltage like the height difference in a gravitational field. A ball at the top of a hill has potential energy due to its position (height), not because it's being pushed or under pressure. The "force" (gravity) acts on the ball when it's allowed to roll down, converting potential energy to kinetic energy. Similarly, voltage sets up the condition for electric force to act on charges.
        * me: can think of voltage like height in relation to measurement.
        * Wikipedia definition: the difference in electric potential between two points
        * Q: "voltage sets up the condition for electric force to act on charges" - i dont get how voltage sets it up - it seems like voltage is emergent from electric charge more than the other way around - or am i wrong?
          * me: it seems im right. this is how things naturally emerge. But us experimenters tend to set a voltage to control and get desired effects on charges within circuits - it a tool. me again: ur still just setting up specific charges to control that specific voltage amount - but i guess voltage measurement tells a lot more useful info that allows you to predict many things (like force) in future compared to the measurements of charge - charge amounts are more indirect to those future predictions than voltage measurements
          * me: voltage is an incredibly useful interface - bridging the gap between electric charges (and all that goes into those configs) and predicting the future effects of those configs
        * Q: how can you measure voltage with a device without first measuring all the electric charges (the config)?
          * you dont need to know config of EACH charge - you just need to interact with the electric field as a whole through current or whatever. But i still agree with myself that fundamentally it's the config of charges where this all emerges from - but fundamentals arent whats most useful when measuring and whatnot
        * unit: volts
      * [[2024-08-30]]
        * **Force Exertion**, energy, work: #memo ^W53UnZFm5
          * Voltage, serves as a convenient scalar value that encapsulates how much energy per unit charge is associated with moving through an electric field. It's a measure of the "electrical height" from which charges can "fall," converting potential energy into other energy forms (or vice versa)
          * so voltage tells you about the push/pull thanks to efields over a distance - which this push/pull is what does work - which changes/converts energy - reducing potential energy as it's converted to other forms of energy - which is when all kinds of useful stuff happens (basically errthing around u rn)
          * voltage basically tells you when you choose any point in an efield, what the force is there and what the work/energy is there (knowing that potential can tell you about the potential energy which can tell about what energy it converts to and then does cool stuff with devices) - all ultimately caused by config of charges. The thing really useful about this is its a really fast way for info to travel and be detected (turn light switch on far away and almost instantly the light detects/experiences the change of potential energy to something else). You basically use switches to turn the force on and off across the efield and when you turn it on and know the voltage - you already know the potential energy available to convert to do other cool stuff
        * CONFUSION: i know voltage is electric potential between 2 points. are these 2 points where the initial voltage is setup OR are those two points not related to where the initial voltage is created - like can you choose any 2 points? #memo ^2DBeta3qN
          * CANNOT CHOOSE:
            * You can't choose just any two points at random; the voltage is defined between specific points. Typically, this is between the hot wire and neutral (or ground).
            * If you measure between two hot wires in a 240V system (like what powers oven), you'd see the full 240V difference between them - they are both 120V
          * you can basically choose, but typically not what ya do. And when thinking of voltages at different points in the efield, your typically thinking of the EFFECTS of the initial voltage (initial 2 points) on that point (in terms of force and energy) - which can be used for info transfer and powering devices, doing work/transfer of energy, etc
          * there's always only 2 points (and dependent on if conductor is there along that path) - so you can choose. BUT most of the time the initial voltage from power source propagates same voltage throughout the circuit until it is transformed by something (which is very explicitly done, not just gonna happen at some spot on a wire). So initial voltage has strong influence
          * in terms of ultimate origin: The "initial voltage" at the power plant is the voltage across two points in the electricity generator, and that voltage sets up the potential difference that gets distributed and modified across the grid, down to the voltage you measure between the hot and neutral wires in your home.
          * so, voltage does drop in devices plugged into an outlet bc resistance from device creates work, but hot wire and neutral wire stays same voltage. Also, power plant provides more current when you get drops like this (which corrects voltage drop). dont think much use of dwelling on this too much tbh

  * tracking understanding electric charge units
    * [[2024-08-30]] units for electric charge first try #memo
      * grok2mini:
        * 1. **Coulomb (C)**
          * **Definition**: The coulomb is the SI unit (standard) of electric charge. One coulomb is the amount of charge transported by a current of one ampere (which is defined as one second). And ampere is grounded by using elementary charge since 2019
          * me: i like to think of as measurement of the number of electrons traveling over 1 sec and elementary charge fundamentally attached to those electrons. so this: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/electric charge, current, voltage#^IuCVqxJd5|UNIT: amp/ampere - In practical terms, if you have a current of 1 ampere flowing through a wire, it means that approximately 6.242 x 10^18 electrons (which constitute one coulomb of charge) are passing through a cross-section of the wire each second.]]
          * UPDATE: like to think of as FORCE of those electrons acting on whole efield starting from a point - and charge is in a particular point in space/time - it's where the FORCE/WORK/POWER originates from - push/pull of pos/neg charge. So it's still tightly attached to the electrons and local - but these discrete effects are what scale to give current. So these are not property of whole efield and not exactly directly related to the signal propagation bc they are focused on local - but they give rise to the non-local stuff like current. So current is given when you change speed at which charge is moving. In AC, current still represents the rate/speed at which charges are changing position, even if that change is oscillatory rather than unidirectional.
          * UPDATE 2: charge is just a force, but it's potential until it happens - and it can originate from config of "objects,env,or field"/voltage very far away
        * 2. **Elementary Charge (e)**
          * **Value**: Approximately 1.602 x 10^-19 coulombs.
          * **Definition**: This is the charge of a single proton or the magnitude of the charge of a single electron.
        * **Conversion**:
          * **1 Coulomb** = **6.242 x 10^18 elementary charges**.
        * 3. **Faraday CONSTANT (F)**
          * more like a constant (similar to speed of light), than a unit
          * **Definition**: The Faraday constant is the charge of one mole of electrons. It's used in electrochemistry. (what is a mole?)
          * **Value**: Approximately 96,485.3329 coulombs per mole.
          * **Conversion**:
            * **1 Faraday** = **96,485.3329 Coulombs**.
        * FARAD (also F)
          * capacitance = amount of charge a CAPACITOR can store for a given voltage. Farad is unit used for this (which makes sense bc at capacitor level u dealing with individual electrons). one farad is the capacitance of a capacitor that has a charge of one coulomb when the potential difference (voltage) across it is one volt (so, C/V)
          * capacity: when talking about total charge of battery, just use term capacity. unit Ah. This is bc batteries store charge, but also have chemical potential to generate charge when needed. Whereas capacitor are just stored charge/electrons. Also i guess capacitor current is not steady but battery is
        * 4. **Ampere-Hour (Ah)**
          * **Definition**: This is a unit of electric charge commonly used in battery capacities. One ampere-hour is the electric charge transferred by a steady current of one ampere for one hour.
        * **Conversion**:
          * **1 Ampere-Hour** = **3600 Coulombs** (since there are 3600 seconds in an hour).
    * [[2024-09-18]] why are both voltage (volts) and charge (ampere hours) needed to describe a battery? #[[fast memo]]
      * answer with anotha Q: so does charge tell you how much total charge can be used from that battery and voltage tells you how fast you can use that charge (and thus max power that can be provided)?
        * YES. GPT:
          * **Charge capacity** tells you **how much total energy** the battery holds (how long it can run your device - although this can depend on voltage or device usage). NOTE: charge cap can actually be increased while voltage stays same like in capacitor using dielectric. I bet chemical portions of battery prob does same thing
          * **Voltage** determines **how quickly** that energy can be used at any given moment because it affects the current (bc voltage determines force/movement/energy/change at all points in circuit), which in turn decides **power**
          * **Power** is the **rate at which the battery delivers energy**, which is a product of the voltage and the current.
        * Example:
          * A **9V battery** and a **1.5V battery** might have the same charge (capacity), but the 9V battery can push more current through the same device because of its higher voltage, allowing it to provide more power/force/movement/change at any given moment. The 1.5V literally cant provide - in terms of speed and in terms of quantity of energy.
          * so, voltage changes speed of energy/change AND quantity of energy/change at any moment
      * A: charge/capacity will tell total charge available that is depleted over time. volts use that total and will tell how much powah you got and how fast the powah/flow-of-energy/charge/change will be - based around volts putting force on each spot of circuit (and efield in general)
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/2024-09-26]] GW vs GWh and relation to Ah, instant unit -> rate (i/o) -> capacity/total using i/o - time-dense/bound #[[fast memo|2024-09-26]] GW vs GWh and relation to Ah, instant unit -> rate (i/o) -> capacity/total using i/o - time-dense/bound #[[fast memo]]
      * it seems Ah is for defining CAPACITY. how much TOTAL of this thing (charge through rate of current - Amp) do we have to use?
      * GW is telling you quantity of power which is work/energy-transfer over time which goes back to 1W=1J/s
      * GWh is also defining CAPACITY or TOTAL of this thing (energy through rate of power - Watts). Tells how much energy is available to use
      * i think it gets confusing bc it's taking a rate and using a UNIT to say how much OF THAT THING is offered in x time with that rate staying steady. This is confusing bc that CAPACITY likely wont be used in some steady way - but it allows you to know the TOTAL available so it niceeee
      * axiom/unit (sample of thing - without time or after very-short x time passed and time assumed so dont need to think about) -> rate (unit over time - i/o) = new steady rate unit ->  historically-set defined time amount OF new steady rate unit = new axiom/unit (discrete time units, discrete rate/axiom-over-time)
        * C (telling how much charge without time or after-the-fact of very-short-time) -> 1C/1s = 1Amp (telling how much charge is flowing over time) -> 1Amp/1h = 1Ah (telling about total charge available to use - less tied to time)
        * J (telling how much energy without time or after-the-fact of very-short-time) -> 1J/1s = 1W (telling how much energy over time) -> 1W/1h = 1Wh (telling about total energy available to use - less tied to time)
        * you have a thing -> thing over time as i/o -> thing over time BUT defining how much time specifically = capacity/total
        * Q: so what is difference in lowest level unit VS capacity/total unit that comes after integrating the rate over a certain time amount?
          * even tho the lowest level often uses time in definition, these are about the thing being measured in an instant without considering time (bc such small time amount is used). it is a capacity/total with least time involved - so think of it as a sample of that thing in an INSTANT/very-short-duration
          * the capacity/total unit that comes after integrating the rate is telling you about a sample of that axiom thing over TIME PERIOD (take a steady rate of thing and do that rate for specific x time). it is a capacity/total with more time involved. it's kind of like turning a list of samples into a new sample type that is more time-dense. Not a sample of thing in an instant - sample of thing over TIME. It's still the OG axiom thing, but much more time - and definitions make new unit a sample of samples - but realistically that's not even the case - you arent actually recording the lower-timescale samples most likely (i think lol)
          * SO, they are both capacities/totals, BUT one is MUCH more time dense. You bound THAT THING to time and sampled the time-bound version
        * Q: as Wh increases, is it still over just one hour? or does number of hours increase too?
          * nope can be diff than just 1 hour. Remember this is a capacity/total. So it depends on how reality plays out what time will be
          * 200 Wh could be:
            * 200 W for 1 hour, or
            * 100 W for 2 hours, or
            * 2 W for 100 hours, etc.
          * In essence, as Wh increases, it indicates more total energy, which could be due to a higher power level, a longer duration, or both, not necessarily tied to just one hour.
          * BUT in terms of thinking bout how much TOTAL ENERGY u got - makes sense to always collapse back to how many W in 1 hour (then if need to make that fit irl situation, u start from there)
          * me: in terms of thinking of it as a TOTAL/cap...prob good to just think of the 1 hour version i think bc it just easier..."yea we got dis much powah/energy/change in 1 single hour"
      * can think of rate as an input OR output of system. next unit is how much of that input or output over some defined time (like 1h) to tell u a capacity/total
      * Q: why do you even need both J and Wh? couldnt you just use J?
        * you could yea
        * J is usually for small amounts of energy. Wh is for bigger amounts of energy - so usually energy over long periods of time
        * much stuff uses the rate (J/s or W) for important measurements, so making the quantized capacity version of that rate (Wh) just kinda makes sense - rather than going back to the base unit of J
        * also just seeing joules doesnt give any info on time, whereas Wh tells how much energy you got in some defined time like 1h (can help you understand time and/or power like in examples earlier, but J cant do dat)
  * what is electric potential?
    * tracking learning what is electric potential?
      * [[2024-08-31]] what is electric potential - first try #memo
        * ep: amount of electric potential energy that a unit POSITIVE charge would have at a specific point in an electric field
        * RELATION OF EFIELD MATRIX and EP MATRIX: the quantities in matrix of efield are telling you FORCE on unit pos charge in each point - which is different than telling your epotential energy in each point (but v related)
        * Q: is electric potential an energy?
          * NO, but it is related to energy.
          * But there is a separate value called "electric potential energy". the diff:
            * **Electric Potential (V)**:
              * SAME AS EFIELD EXCEPT FOCUSED ON epENERGY: it's basically the effect of the total electric field on a specific point DEFINED by how the whole field would effect A UNIT POSITIVE charge at that point. depends on the influence of all nearby charges
              * POTENTIAL RELATED TO NET CHARGE ON A POINT: the more NET POSITIVE charge on that point, the higher the potential (bc it boops unit pos charge away which is higher energy). the higher the NET NEGATIVE charge, the more a pos charge wants to just chill there (spending 0 energy, less potential)
              * NET POS CHARGE: electric potential is basically just net positive charge at a point - which tells you negative charges are attracted and pos charges are repelled
              * WHOLE EFIELD's epENERGY / TEST CHARGE: The formula for electric potential is V=U/q​, where U is the electric potential energy, and q is the charge in coulombs (of ur test unit positive charge at that point - literally JUST that test charge). BUT U includes contributions of entire efield on that one point. irl charge of q could totally be something else than just +1, but thaz **most useful standard** - almost never used other ways. Even if was just large charge, i would just simplify to that standard of +1 for q for good reference frame compared to other things
              * CRUCIAL that this definition is based around A POSTIVE CHARGE. Mainly defined this way bc history of 1) these concepts deved b4 discovery of electron 2) Ben Franklin assumed current was flow of positive charges
            * **Electric Potential Energy (U)**: This is the energy a charged object possesses due to its position in an electric field. It depends on both the charge q and the electric potential V (V similar to gravity/height)
        * FUNDAMENTAL: The general principle is that **charges move in a way that reduces their electric potential energy**
          * NOTE: thinking in terms of potential energy doesnt consider sign of charges - but thinking in potentials does. So energy always decreases, but the potential depends on the charge sign
          * **Positive charges** move from higher potential (net pos charge on point) to lower potential.
          * **Negative charges** move from lower potential to higher potential.
        * **Higher Potential**: A point with higher electric potential means that point has the potential to attract more electrons (or repel positive charges) compared to a point with lower electric potential.
        * The key is understanding that the movement aims to minimize the system's total energy
        * epotential alone tells you potential for change in a point - but epotential difference (voltage) tells you potential for change/work/force/power between 2 points (like action potential!)
        * unit: volts
        * memo notes
          * [[2024-12-07]]
            * i dont have the formula for voltage/ePotential/volt memorized, but it seemed to click today in way it never has. Wrote some extra notes on it. i mixed q up with efield strength for a sec, but then straightened up. q is more tied to matter as fundamental property like mass. efield strength is V/meter - so iz bit more complex thing containing q, except over area imo (i say this bc V/volt is EP - iz U/q)
            * Q: is an efield filled with values of force per point OR with values of efield strength for each point. A: efield strength per point (force per charge at each point)
            * NOTE: efield strength is not FORCE. It is force per unit charge, but it is not equivalent to force
              * yes efield strength = V/meter AND force(newton)/q. im not gonna memo the details bc ouch my brain. tldr: 1V=1J/C (for V/meter the J stays at top and C goes to bottom with meter). 1J=1Nm. meters cancel. 1N/C
              * EFIELD STRENGTH is INDEPENDENT of charge q: efield strength stays constant no matter the charge involved. Not case for the force at that point (and when finding force, you dont really wanna simplify to test unit pos charge bc v likely iz not +1 charge at that point...but can still define using test pos charge and for theroetical discussions)
                * me: i think iz independent bc it contains V, which is defined using the test pos charge lol
                * force is just newtons...ma...so needs total charge at that point, not test pos charge
              * TLDR: force at point is more likely to consider actual non-test charge at that point, but EP is not...it use test pos charge
              * NOTE: efield strength doesnt need to use test unit pos charge, but just useful and in definition
              * BUT, if you assume a test positive charge, arent they both the same? A: YES. Literally magnitude is equal. force = efield strength
            * in reality, efield strength is from point in all directions, but for simple sake we usually just think of 1 1D line from that point which is the "meter"
            * Henry is unit for inductance (v/A/s)...i had mixed that up. Unit for capacitance is Farad (c/v)
            * oo Henry was good meme for connecting and membuhing this stuff


  * questions
    * why is individual charges considered discrete? and why is the field that emerges considered continuous? #memo ^jFCQRTO6I
      * FUNDAMENTAL LIMIT: well charges are discrete bc you can find a fundamental limit at the elementary charge - cant break down no more. Well, actually you have quarks with fundamental charge limit too, but quarks stay inside nucleus of atom, so less useful to think about i guess 
      * LIKE A BODY: electric field is continuous bc it emerges from tons of discrete charges and the effects of all these charges blend together as a whole - even in a mathy sense. This is analogous to how a solid object appears smooth to the naked eye, even though it is made up of discrete atoms. This continuous description allows for precise mathematical modeling of how charges interact at different points in space and time. 
      * Charge is the cell. Field is the body made of cells.
      * **Definition of a Field**: A field is a mathematical construct that assigns a value (like a vector or scalar) to every point in space and time. For an electric field, this means that at every point in space, there is a defined electric field vector, which represents the force that a unit positive charge would experience at that point.
      * Q: you keep saying fields act on other charges. is the the fields that do the acting or the charges or?
        * the force comes from the individual charges - but the field is all these charges as a WHOLE - so both charges and the field do acting. Often field can move pretty far from matter it originates from and still act on other charges/matter
    * why do electrons flow to ground or neutral or wherever they flow, how electricity go from powah plant to house to device to exit house #memo ^cmVgKF49g
      * GET TO GROUND/STABLE/MINIMAL STATE: bc of fundamental principle that electric charges move from regions of higher electric potential ENERGY to regions of lower potential ENERGY. The key is understanding that the movement aims to minimize the system's total energy. 
      * bc of voltage - which is bc of config of charges between 2 points - which places force on points all throughout the efield based on the initial voltage - which causes work/energy-transfer to be done when something changing there (resistance) - and then charges are trying to minimize their energy so they head to area with least particle movement/force/energy (i imagine hole getting filled up with water by strong stream on both sides as analogy 4 resistance device)
      * WOAH: i learned the electron flow (drift velocity) isnt even really what's important. it's the flow of the electric field (signal speed) that is important usually.
        * grok2: **Drift Velocity**: The actual speed at which individual electrons move through a conductor (like a wire) is surprisingly slow, often on the order of millimeters per second. This is known as the drift velocity. However, this isn't really what we're tracking when we think about electricity "flowing" through a circuit.
          * why it slow: because electrons are constantly colliding with atoms in the conductor, which slows down their overall progress.
        * grok2: **Signal Propagation**: When you flip a switch, the electric field that pushes the electrons travels at a significant fraction of the speed of light. This is what we perceive as the "speed of electricity." For most purposes in household wiring, this propagation speed is roughly 50% to 99% of the speed of light (c), depending on the material and conditions
          * how it work: 
            * When you apply voltage across a conductor, an electric field is set up almost instantaneously throughout the conductor. This field causes electrons to start moving everywhere in the wire at nearly the same time, not just from one end to the other.
            * Think of the wire like a hose already filled with water. If you push water in one end (apply voltage), water immediately starts coming out the other end, even though the individual water molecules (electrons) haven't traveled the length of the hose yet. The pressure wave (electric field) moves through the water (electrons in the wire) much faster than the water itself moves.
      * Q: what is process for: how does electricity start from utility provider, go in ur house, through a device, and then exit house...?
        * most interfaceable object for me and most ppl: the outlet - each outlet in your house has a hot wire in small vertical slot (meme: small/tight holes are hot lmaoo) that is at high voltage always and neutral wire in big vertical slot that is at 0 volts. Current flows from hot wire to neutral wire always
        * GPT:
          * energy source: power plant converts energy from various sources into electrical energy. Fossil fuels (coal, natural gas, oil), nuclear energy, renewable sources
          * ### 1. **Power Supply to Your Home**
            * **Utility Power:** Electricity is generated at power plants and transmitted over long distances through high-voltage transmission lines. This electricity is typically in the form of alternating current (AC).
            * **Step-Down Transformers:** Near your home, transformers step down this high-voltage electricity to a safer, usable level (e.g., 120/240V in North America). For homes, typically these transformers are mounted to close-by utility pole OR on ground concrete pad with green box-like structure
            * **Service Entrance:** The electricity enters your home through a service drop (overhead lines) or service lateral (underground lines), connecting to the electric meter (measures power usage to bill u) and then to your electric panel.
          * ### 2. **Inside the Electric Panel**
            * **Main Breaker:** The main breaker controls the flow of electricity into your home and can shut off all power. It is usually rated to handle the total current that your home can use, such as 100, 150, or 200 amps.
            * **Bus Bars:**
              * **Hot Bus Bars:** Inside the panel, there are two metal bus bars that carry the voltage from the utility company. In North America, each bus bar typically carries 120V, but they are 180 degrees out of phase with each other. This allows for both 120V circuits (from one bus bar) and 240V circuits (using both bus bars).
              * **Neutral Bus Bar:** There is also a neutral bus bar in the panel, which is connected to the neutral wire coming from the utility company. This bus bar is connected to the ground, typically via a grounding rod driven into the Earth near your home. NOTE: important to have neutral wire return current to powah plant bc cant just have it go out to yard and be all dangerous (plus that would be losing CURRENT instead of reusing it like normal - PS: not reusing or sending back ENERGY tho in realistic scenario, unless u using solar power and generating extra. ALTHO, if current WAS going to yard hypothetically, that is losing energy lol)
          * ### 3. **Creating Hot and Neutral Wires**
            * **Hot Wires:**
              * The hot wires in your home's circuits are connected to one of the hot bus bars in the electric panel. These wires carry the 120V AC potential (relative to the neutral bus bar) to outlets, lights, and appliances.
              * In a 240V circuit (e.g., for a large appliance like a stove or dryer), two hot wires are used, each connected to a different bus bar, creating a 240V potential difference between them.
              * 2 HOT BUS BARS: i was confused how it's 240V - it's bc they are out of phase - which means signs are different: Since the hot wires are 180 degrees out of phase, when one is at +120V, the other is at -120V. So, +120V and −120V don’t cancel each other out; instead, they add up to create a 240V difference because they are 180 degrees out of phase.
              * PHASE: phase is only a thing for AC current
            * **Neutral Wires:**
              * The neutral wires are connected to the neutral bus bar in the electric panel. Since this bar is connected to the ground, the neutral wires are at or near ground potential (0V).
              * The neutral wire serves as the return path for the electric current after it has flowed through the device or appliance. Because it is grounded, it provides a reference point for the 120V or 240V provided by the hot wires.
          * ### 4. **Voltage Creation and Distribution**
            * **120V Circuits:**
              * A 120V circuit in your home uses one hot wire (from one bus bar) and one neutral wire. The voltage difference between these wires (120V) drives the current through devices plugged into the circuit.
            * **240V Circuits:**
              * A 240V circuit uses two hot wires, each connected to a different bus bar. The voltage difference between these two hot wires (240V) powers large appliances.
              * The neutral wire may or may not be used in these circuits, depending on whether the appliance requires 120V for certain components.
          * ### 5. **Grounding**
            * **Ground Wires:**
              * The ground wires in your home are connected to the neutral bus bar in the electric panel, which in turn is connected to the Earth via a grounding rod for extra safety
              * Grounding provides a safety mechanism. If there’s a fault in a device (like a short circuit), the ground wire provides a direct path for the current to flow to the Earth, reducing the risk of electric shock or fire.
      * places i struggled in this memo sesh
        * [[2024-10-19]]
          * remembered electric meter, but couldnt remember name of electric panel - which is where main breaker and bus bars are...which i kinda forgot what breaker even does too
          * kinda forgot that small hole is hot wire, but intuition had it
          * kept calling neutral wire as cold wire, no idea if okay or not
          * neutral wire from utility company - added new stuff there
        * [[2024-12-18]]
          * would like to memba how much amps house typically gets...but idk if brain will memba. meme: keep it hundred in yo house

    * how does electric potential difference (voltage) tell you about force placed on moving charge - wouldnt a high potential at pointA have a high net positive charge and a high potential at pointB have a high net positive charge - so subtracting the 2 would be 0...but that sounds off but idk #memo ^FDZ6ojhKo
      * **Point A and Point B**: If both points A and B have high potentials (say 1000V each), the potential difference between them is 0V, meaning no work is done on the charge as it moves between these two points, implying no net force due to the electric field between them. The force is related to the potential difference, not the absolute potentials.
        * this confused me bc i assumed this would mean no charges are moving - but this says explicitly the charges are moving:
        * The charge could be moving due to reasons unrelated to the electric field between points A and B, such as thermal energy, an initial velocity from elsewhere, or an external force. The statement is simply saying that **if** the charge happens to move between these two points, the electric field won’t contribute to its motion or change its kinetic energy.
      * **High Potential Difference**: If point A has a much higher potential than point B, there's a significant potential difference, meaning the electric field will do work on a charge moving from A to B, exerting a force on it.
      * also important to remember that voltage can scale far from initial set point (it's like height). it's set strong in one point and then stays same from building on one side of earth to building on other side of earth
