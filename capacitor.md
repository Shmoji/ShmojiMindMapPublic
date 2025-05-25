  * what is capacitor?
    * tracking learning what is capacitor
      * [[2024-09-03]] first shot at learning what is capacitor, dielectric #memo
        * memes: bucket/buffer, 2 alum plates inside dielectric, farads, C/v, LC circuit, about STORAGE of charge (per unit volt) in any system...if no storage then no capacitance even if there is voltage - like outlet, SHC, more capacitance always mean more stored charge PER VOLT but not always mean more energy output OR MORE total stored charge...bc circuits are complex lol
        * small electrical component used in almost every circuit board that stores and releases charge, electrical energy, force
        * similar to battery, but store energy in different way (using electric field instead of chemically). Cant store as much energy as battery, but it can charge and release energy much FASTER. 
        * linear process:
          * connect 2 ports of capacitor to battery/voltage source. due to voltage, electrons flow in one side to a metal plate and electrons flow out metal plate on other side until capacitor has same voltage as source, which causes current to stop flowing (thanks insulator/dielectric!)
        * what they look like: often cylinders like batteries, but sometimes a rectangle or circle shape too - and always have 2 legs for input and output
        * UNIT for capacitance: Farads (F) or microfarads
        * ANALOGY: water bucket separating a water pipe (first part of pipe at top and 2nd part of pipe at bottom). Without the water bucket, when flow is turned off, water stops and starts instantly. With bucket, you can store water and smooth out interruptions to the supply (output from end pipe). This is what capacitor is useful for often
        * inside capacitor you have 2 separate conductive metal plates (usually aluminum) and a dielectric insulating material (like ceramic) in between to separate plates
          * dielectric is crucial for separating 2 metal plates bc otherwise no charge would ever get stored since it's a complete circuit (electrons would keep flowing in loop)
            * so stored charge is the electrons themself being stuck (no movement) - but specifically in a config that creates voltage with one side positive and one side negative (but not connected). Even if capacitor disconnected, the charge is still there until connected to something conductive (like your hand mwhaha)
            * it kinda makes sense that the smaller you get with these electrical components, the more electrons matter - whereas in big circuits like your whole home, the individual electrons really dont matter when considering how things work (it's more about how the info/waves/force/energy propagates through the electric field)
          * dipolar electric material
          * dielectric is obviously an insulator (doesnt conduct electricity), BUT can still be polarized (exhibits electric dipole structure) - PS: not all insulators can be polarized
          * dielectric means the material will polarize when in contact with an electric field - induced polarization. Without electric field, the atoms/molecules in material are facing wherever the hecc they want. Once metal plates gain charge (negative on one and positive on another), this causes atoms/molecules in middle material to stretch towards their attractor. Each atom has a stretched neg side attracted to pos plate and a stretched pos side attracted to neg plate. This causes one end of dielectric to be overall neg and one end to be overall pos (this is polarization). This increases capacitance (bc u have more charge without changing voltage amount - meaning more energy can be released for same voltage)
          * how energy is stored and that energy amount increased even more by dielectric:
            * energy is primarily stored in efield between 2 charged plates - thanks voltage
            * energy within dielectric: work/force is required to polarize the dielectric and this creates energy that can be released when time comes
              * Q: so is there energy stored between the pos and neg charges of the plates, but another energy stored between the ends of the dielectric and the plates?
                * NO. well yes that first part is how primary energy is stored, but energy from dielectric is due to work/force to polarize CAUSED by voltage from the plates and not due to separate internal voltages
        * GPT: Capacitors are used in various applications, such as:
          * **Energy storage:** Capacitors can store small amounts of energy to provide power in short bursts.
          * **Filtering:** In power supplies, capacitors smooth out voltage fluctuations by filtering out noise (is noise just no charge flow?)
          * **Timing circuits:** Capacitors work with resistors to create time delays in circuits, as the time it takes to charge or discharge can be precisely controlled.
          * **Coupling and decoupling:** Capacitors can block DC while allowing AC to pass, used to separate different parts of a circuit or to stabilize power supplies by decoupling noise.
        * memo thoughts
          * Main things i forgot last study:
            * dipolar and polar had me confused - but they basically same. Also forgot importance of membuhing not all insulators can be polarized (at least not significantly - like a diamond)
            * forgot unit for capacitance
          * [[2024-11-06]]
            * my best guess what capacitance is: energy felt by unit positive charge by voltage from capacitor (lol i was thinking of eV...but also got that wrong). EDIT: lol wrong. Capacitance is the ability of a system to store electrical energy in the form of an electric field (battery uses chemicallsss). It’s a measure of how much electric charge Q can be stored per unit of electric potential V
            * think this deserves own memo one day if cant membuh: An **electron volt** (eV) is a unit of energy equal to the amount of KINETIC energy gained or lost by a single electron when it moves through an electric potential difference of **one volt**. It’s commonly used in physics, especially in atomic, nuclear, and particle physics, to express very small amounts of energy.  1eV=1.602×10−19joules (J) - This energy is derived from the charge of an electron (e≈1.602×10−19 coulombs) moving through a potential difference of one volt: Energy=Charge×Voltage=e⋅1V
            * The capacitance of a capacitor depends on:
              * **Area of the plates** (A): Larger plates store more charge, increasing capacitance.
              * **Distance between plates** (d): Closer plates increase the electric field strength, increasing capacitance (imagine efield sandwich making it stronger)
              * **Dielectric material**: Different materials affect the electric field between the plates. Materials with higher dielectric constants increase capacitance.
            * my understanding is that dielectric can increase CHARGE, but voltage stays same - hurts my head bc usually just voltage tells you energy output, but this means more energy output due to charge...maybe dis why F unit needed lol bc charge distribution/polarization important...plus small details of other stuffff that increases efield strength aside from voltage. So iz specifically useful when knowing charge in relation to voltage
            * 1F=1C/V (capacitor that stores 1C of charge with voltage of 1V across it)
            * tried membuhing what F for Faraday Constant was. Think it's like electric charge of a mole - which is like 96485 C
          * [[2024-11-12]]
            * i learnt that energy usage due to JUST voltage is approximate. i asked Q: does this mean if you have just voltage and you use that to determine how much charge and energy can be used, it wont be as accurate as using capacitance?
              * YES. The energy stored in a capacitor is given by E=1/2CV^2
            * Q: does capacitance works for other systems or just capacitors?
              * originates from caps, but it can be generalized to other systems that store and release energy through a change in an electrical potential difference. It is fundamentally a measure of how a system responds to changes in electric potential (how much charge you get per volt...which means how much energy you get per volt too)
            * GPT that clicked 4 me bc reminds of water bucket example: 
              * Capacitance is a measure of a capacitor’s ability to store and release charge per unit voltage. While knowing the total charge and voltage tells you how much charge a capacitor holds at a given voltage, it doesn’t reveal how the physical properties of the capacitor (e.g., plate area, distance between plates, and dielectric material) affect its ability to store or release additional charge as the voltage changes. Capacitance quantifies this inherent characteristic.
              * A higher capacitance means the capacitor can store and release more charge without a significant change in voltage, indicating that it is more efficient at storing and delivering charge. This implies that it can better handle changes in voltage by adjusting the amount of charge it stores or releases, helping to stabilize voltage levels in circuits.
              * For example, in a circuit, if there is a sudden voltage spike, a high-capacitance capacitor can absorb a larger amount of excess charge, dampening the spike and stabilizing the voltage. Conversely, if the voltage drops, it can release a larger amount of charge to help maintain the voltage level. This property is crucial in applications like power supply/noise filtering (noise in voltage which is often the literal signal), where capacitors smooth out fluctuations in voltage to provide a stable output. In other words, higher capacitance means the capacitor can "keep up" with changes in the voltage better by adjusting the amount of charge it stores, which helps maintain the voltage more consistently.
              * so standard voltage is one aspect and then capacitance comes from "(e.g., plate area, distance between plates, and dielectric material)" - all props about storage of charge or increasing efield strength - and in different systems - probably totally diff physical props than these. Related to amount of charge that can be STORED (and hence released) per volt. Whereas plain voltage with no capacitance isnt about storage - it doesnt have storage
              * Q: is it possible to have voltage without a capacitance?
                * yes. EX: **Electrical Outlets**: The voltage across an electrical outlet is due to the electric potential generated by the power supply system. Again, this is not dependent on capacitance (this is 0 capacitance. no storage). Also battery terminals surprisingly
                * You can have voltage without any significant capacitance, such as when there is simply a potential difference with little or no capability to store charge (e.g., a single charged object in space). However, the reverse isn't true: if there is capacitance, it implies the potential for voltage when charge is present.
              * the memes of it being a buffer or a bucket are gooood
            * lots of resonance between specific heat capacity (J/C) and capacitance
