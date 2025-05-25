  * tracking learning magnetism in general
    * [[2024-09-07]] magnetism basics, discrete magnetism, types of momentum #memo
      * you have:
        * electromagnets: charges move and creates magnetic field/magnet (all magnets are electromagnets - even if at quantum level bc only get magnetic field from moving charge)
        * permanent magnets: ur typical magnet (doesnt have current flowing in it) - it stays magnetic "forever" (over time - 1000s of years - can lose magnetism, especially if gets hot)
        * but in the end both types are caused by the same thing
      * POLES: in a magnetic field, there is always 2 OPPOSITE "sources" called poles - north and south pole. sometimes magnets have more than 1 pair of poles, but there is always at least one pair...and they only come in pairs. Maybe i need to update my understanding, but poles just tell direction of effects of mfield AND quantify strength of mfield which scales to effects of mfield
      * understanding how permanent magnets can be magnets without current:
        * using iron as example. it has 26 electrons. each one in an orbital. each orbital in variety of shapes with diff available properties. in these orbitals, the electrons have orbital angular momentum around nucleus. we can measure total angular momentum and its orientation (just these properties make it a tiny magnet bc charge be moving). Any electron with non-zero angular momentum will act like a tiny magnet.
        * NOTE: depends totally on context, sometimes that doesnt turn entire iron atom into magnet bc 1) effects could just be insignificant 2) electrons tend to pair up in opposite directions - for each one in clockwise orbital, there's another in counterclockwise (magnetic effects cancel out for these pairs)
        * SO we may need to zoom in even more. A single electron has axiomatic property called spin angular momentum. Not REALLY motion, but it is momentum and that's enough for magnetism. When you zoom back out to atom level, many of these magnetic effects can cancel out too - just depends on context
        * Q: wait so wat diff in diff angular momentums?
          * **Orbital Angular Momentum**: This refers to the angular momentum of an electron due to its motion around the nucleus in an orbital. Each orbital has a specific shape (like s, p, d, f orbitals) and can contribute to the total angular momentum of the atom. Electrons in these orbitals indeed have angular momentum, which can give rise to magnetic moments.
          * **Spin Angular Momentum**: This is the intrinsic spin of the electron, which is not related to its orbital motion but is an inherent property. Not dependent on electrons position or motion. As mentioned earlier, electrons have a spin quantum number s=1/2, leading to two possible spin states. This also gives rise to tiny magnetic moments.
        * Q: so is Spin Angular Momentum basically the discrete part of magnetic fields? like the most elementary magnetic piece? (similar to charge for electric stuff)
          * YES, but mainly for perm magnets does it SCALE and not electromagnets
          * **Discrete Nature**: While both spin and orbital angular momenta are quantized, spin's discrete nature is particularly fundamental because:
            * It's not dependent on the electron's position or motion in an atom but is an inherent property of the electron itself.
        * going further, just bc atom is magnetic doesnt mean the material/molecule is. The orbital and spin angular momentums arent enough. You also have to get nearby atoms to line up with each other and then get enough REGIONS of atoms to line up - these regions are called DOMAINS
        * there are only 4 elements that do all dis at room temp - iron, cobalt, nickel, gadolinium. Beyond that you either gotta get material really cold or use specially-designed molecule
      * NOTE: spin does not scale up in moving charges. The mfield from that just kinda appears and not from any obvious discrete pieces that i can tell. HOWEVER, permanent magnets are scaled up from discrete spin pieces at particle level. Some magnetic effects of perm mags come from moving charge of Orbital Angular Momentum as electrons orbit nucleus too, but not as significant as spin
        * DONT TAKE SERIOUS: if there was a discrete value that is used to scale magnetic effects, it would probably be "permeability of free space" - It essentially provides the "scaling factor" for how the microscopic magnetic effects contribute to the macroscopic magnetic field, but it remains a constant that does not itself change. And it's not tied to discrete units of space, it's of the continuous field of all space - BUT only a certain part of that field of space is activated - the part close to permanent magnet or electromagnet
      * memo updates
        * [[2024-10-30]]
          * kinda forgot a bit why angular momentum would cause magnetic effects. well i have no idea what momentum is, so makes sense. but i know its typically related to movement of a charge. and we know what Ampere's Law says about that
          * kinda mixup names of angular momentum, but basically remember there is one from moving electron and one that doesnt depend on any movement/position at all (attached to an electron)
    * [[2024-09-08]] magnetic moment, magnetic effects of 3 forces and 1 induction, magnetic stength/magnitude #memo
      * NOTE: magnetic fields are like efields in sense that they can exist and be quantified, yet their EFFECTS arent seen until interacts with another mfield or some other observation through interaction
      * WHAT IS MFIELD: dont forget that fields are always a bunch of vectors. for mfield it's a bunch of vectors representing point-in-space and the strength AND direction of mfield in that point in space
      * YAY EXPERIMENTS: i find lots of this magnet stuff is hard to understand without understanding people did bunches of experiments to get observables to understand all this
      * word puke of my mfield understanding: so fundamentally you have particles with axiomatic properties of magnetism like spin. Tiny magnets even without movement of charge. BUT movement of charge also always create mfield and mfield only really scales with either 1) moving charge (even without correct config at smallest scales) or 2) special elements in correct config for permanent magnet. mfield always has 2 poles
      * **Magnetic moment**
        * a measure of the strength and direction of a magnetic source. a tiny vector. 
        * magMOMENTS IN REGARDS TO FORCES: Magnetic moments themselves aren't forces, but they can interact with external magnetic fields or other magnetic moments and result in forces. What cancels out in the case of **paired electrons** is the **magnetic field** that each electron generates due to its movement and spin, not a force (altho this cancels out all the mforces too). When two electrons have opposite spins (or orbital directions), their magnetic moments point in opposite directions. Since magnetic fields are directional, they **cancel each other's contribution** to the overall magnetic field of the atom.
        * Q: what the hecc is the "strength" of a magnetic source?
          * measure of how much of a "magnetic effect" the object can produce
          * Q: what is a magnetic effect? to me, it just seems to be 3 forces in the end. and inducing a current/EMF
            * AT ITS CORE: a **magnetic effect** refers to the ability of an object (like a magnet, a current-carrying wire, or an electron) to create a **magnetic field** in the space around it. A **magnetic field** is an invisible field that exerts **influence** on other magnetic materials, charged particles, or other currents in its vicinity.
            * **Observable Magnetic Effects**
              * basically: 3 diff types of forces and inducing current
              * **1) Force on Moving Charges in external mfield lorentz force**: If a moving charged particle (like an electron) enters an EXTERNAL magnetic field, it experiences a force due to the **Lorentz force law**: F=q(v×B) where F is the force on the charge q, v is its velocity, and B is the magnetic field. This FORCE is perpendicular to both the velocity of the charge AND the direction of the external magnetic field the particle is moving through
                * Q: why is it assumed that the velocity of charge and the mfield are aligned?
                  * EXTERNAL vs INTERNAL: this is only in regards to charge moving through external mfield. internal mfield generated by a moving charge is ALWAYS **perpendicular to the velocity** of the charge at every point around the charge (interesting bc that is max unaligned)
                  * NO LFORCE IF ALIGNED: it is not. In fact, for the Lorentz force to affect the particle's path, the VELOCITY of the charge and the external magnetic field must **not** be aligned. If the velocity v and the external magnetic field B are aligned (parallel or anti-parallel), the cross product becomes zero, and there would be **no magnetic force** acting on the particle.
                  * NOTE: i dont understand why this is physically, i just understand bc the equation given AND bc experiments show force arising when movement of charged particle is perp to magnetic field direction. Good analogy: river with you swimming straight down it with sideways/perp current pushing you sideways. if you align with current, now no force is pushing you sideways
                  * ### The magnetic force is maximized when:
                    * The velocity and the external magnetic field are perpendicular to each other. This is when the force is the strongest.
                  * ### The magnetic force is zero when:
                    * The velocity and the external magnetic field are parallel or anti-parallel, meaning the charge moves along the direction of the field lines, in which case no magnetic deflection occurs.
                * CURVY MOTION OF CHARGED PARTICLE: This directly affects the motion of charged particles. This is what causes particle to move in curvy path
                  * Visualizing the Path:
                    * **Imagine**: A charged particle moving into a page with a magnetic field pointing upwards. The force on the particle will be to the side (bc that is perp to both), causing it to start moving in a circle around the magnetic field line (since already moving one direction at some speed and then force pushing it sideways now thanks to mfield)
                * Q: so all moving charges also generate a magnetic field AND a lorentz force?
                  * No not for this force. There is no self-induced Lorentz force. And when we talk about it, we are always talking about a moving charge going through EXTERNAL mfield. BUT there is some very minimal (rarely used) self-induced forces due to a **charge accelerating** and this **causing radiation** to be emitted - The **Abraham-Lorentz force**, but it's totes different, just self-induced so thot id mention
              * **2) attract/repulse Force Between Magnets**: This is the direct attraction or repulsion between magnetic poles.
                * mfields attact/repulse forces, it's p much only considering the external field lines of mfields. each mfield has external mfield and internal mfield.
                  * EXTERNAL: goes from north to south outside the object. meme: typically used, so UPTOP start, bigboss
                  * INTERNAL: goes from south to north inside the object (usually only for talking about internal structure of magnet itself). meme: bottom-up internal self lol
                  * grok: However, it's worth noting (skim this):
                    * **Boundary Effects**: At the boundary of a magnet, the transition from internal to external field lines can be complex. But for most practical purposes, especially when considering how magnets interact at a distance, focusing on the external field lines is sufficient.
                    * **Complete Picture**: For a complete and detailed analysis, especially in advanced applications like magnetic resonance imaging (MRI) or precise engineering, one might consider the entire magnetic field, including internal configurations, but for basic understanding and most practical scenarios, external field interactions are what matter.
              * **3) magnetic torque due to parallel alignment or not**
                * When a magnet (or any object with a magnetic moment) is placed in an external magnetic field, if its magnetic moment isn't aligned/parallel with the field, it experiences a torque. This torque tries to rotate the magnet so that its magnetic moment aligns with the external field, minimizing the system's energy.
                * NOTE: all movement of magnets is bc minimization of energy. Going from high to low potential energy. Which with 2 mfields in regards to this specific force - would be opposing/perp mfield (high p energy) to aligned/parallel mfield (low p energy)
                * example of a compass:
                  * **Torque** (rotational force) is exerted on the compass needle's mfield by the Earth's mfield.
                    * The Earth's magnetic field exerts a **torque** on the compass needle because the magnetic moment of the needle and the external field are not initially aligned.
                    * GOOD EX TO SKIM: The torque τ on the compass needle can be described by the equation: τ=μ×B Where:
                      * μ​ is the magnetic moment of the compass needle.
                      * B is the Earth's magnetic field.
                      * The cross product (×) indicates that the torque depends on the **angle** between the magnetic moment and the magnetic field.
                  * This torque causes the needle to rotate and align with the magnetic field.
                  * As the needle aligns, the **magnetic potential energy** of the system decreases.
                    * When the magnetic moment of the needle is fully aligned with the Earth's field, the torque becomes zero, and the system has reached a state of **minimum energy**.
                  * The motion is driven by **force** (in this case, torque), even though the overall process is guided by energy minimization.
                  * DIFF IN MAGNETIC POLES AND GEOGRAPHIC POLES: compasses (their north pole) always point to **Earth's EXTERNAL magnetic south pole** (which is Earth's geographic North Pole - but off by like 11 degrees due to tilt of E's mfield)
                  * WE DEFINED MAGNETIC NORTH OF ALL MAGNETS ON EARTH USING EARTH'S MFIELD: Main reason compass N pole (instead of S pole) does the moving when torqueing to minEnergy is rooted in historical standards - we literally defined N/S pole of every magnet based on how it moves relative to Earth's mfield. If that pole moves to point to Earth's magnetic south pole, then that is N pole of that magnet. This obv doesnt work outside of Earth, but these magnets still have their own N/S pole (defined by the internal mfield instead of needing external reference point from largest mfield like with many Earth magnets)
                  * dont really need to define relative to big mfield tho. bc internal mfield always flows S to N and then external mfield is opposite (and when comparing 2 mfields, it's the external ones you talk about - except in edge cases). And yes, if one magnet defines poles using historical standard of how magnets move relative to Earth's mpoles and one magnet defines its poles based on itself...this can cause much confusion
              * **4) Inducing Current** (Faraday's Law): When a magnetic field **changes over time**, it can induce an **electric current** in a nearby conductor. This is the basis of electromagnetic induction, and it’s described by **Faraday’s Law of Induction**: E=−dΦB/dt​​ where E is the induced electromotive force (EMF - basically voltage), and ΦB​ is the magnetic flux through a loop of wire. This is how electric generators work—changing magnetic fields create electric currents.
          * so...does strength/magnitude represent 1) force on moving charges 2) attract/repulse magnetic force or 3) magnetic torque?
            * represents none of those directly but rather the POTENTIAL to exert those effects. thaz a lot of data compression holy shit
            * typically measured in Tesla (T) or Gauss (G) - and mflux in Webers! (Tm^2)
      * FORCES ON 2 OBJECTS ALWAYS EQUAL AND OPPOSITE - NEWTON'S 3RD LAW:
        * woah, the magnetic field of a small compass can be thousands times stronger than magnetic field of the Earth
        * in my mind at first that meant the stronger field applies the greater force on others...
        * but they apply the same force on each other!
        * it's just that the objects the fields emmanate from have totally different masses! hard to move the Earth ... it a big boi
        * whereas the compass has a smol mass that can be moved, DESPITE stronger mfield
      * memo thoughts
        * [[2024-10-26]]
          * first thought before starting today was just interesting how each value in efield is measuring a literal force - the force felt on a unit positive charge at point in time/space. Whereas, each value in mfield is measuring a value that can then be used to compute all 3 different mforces and minduction
          * think my brain somewhat forgot the Lorentz Force is only when going through external mfield. Forgot a lot about the Abraham-Lorentz force too
          * new data added on why and where compasses point
        * [[2024-12-07]]
          * brain kinda forgot NtoS for external mfield and StoN for internal mfield...so i added memes 4 dem
          * kinda forgot about how we historically decided to define most magnets on earth relative to Earth's south pole (which is E's geographic North pole)

    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/2024-09-10]] how can you determine if magnetic moment is aligned/parallel with external magnetic field when magnetic moment is one vector but mfield is a tons of vectors? what the heck is the direction of the mfield if its many many vectors? #[[fast memo|2024-09-10]] how can you determine if magnetic moment is aligned/parallel with external magnetic field when magnetic moment is one vector but mfield is a tons of vectors? what the heck is the direction of the mfield if its many many vectors? #[[fast memo]]
      * you only need to compare the direction of the magnetic moment vector with the magnetic field vector **at the location of the magnetic moment**. Where they intersect in space
      * also good to note: near poles a mfield can be pretty non-uniform (meaning the direction can change quick), but away from the poles mfields tends to be fairly uniform - so mostly keeping same approx direction
    * [[2024-10-10]] first try learning magnetic induction, conventional current vs electron flow, how does mfield form around wire, science asylum motor and generator coil experiment, how most electrical energy/power is generated #memo
      * ### Conventional Current vs. Electron Flow:
        * **Conventional current**: flow of **positive charges** to negative. Historically, assumed to be the direction of current flow (from positive to negative) before discovery that it's actually electrons doing the moving - thanks Ben Franklin
        * **Electron flow**, on the other hand, is the actual movement of **negatively charged electrons**, which flow from the negative terminal to the positive terminal in a circuit.
        * In most physics and engineering contexts, we use **conventional current**. However, the reality is that in metal wires, **electrons** are the particles that move, and they move in the opposite direction to the conventional current.
      * Q: say you have current flowing through wire moving downwards. on left side of wire, which way is magnetic field pointing? what about on right side? Q: how does a magnetic field form around a wire
        * you can use the right or left hand rule! but depends if you are using "conventional current" (right hand) OR electron flow (left hand)
        * how hand rules work: point thumb in direction of flow and wrap other fingers around wire. mfield forms around wire in circles (always perpendicular to moving current tho)
        * so only difference is that directions in plane of the circles are opposite between the 2. so for this example for electron flow, left side mfield is pointing towards you and right side is pointing away from you. Then, iz opposite for conventional current
      * learned later: magnetic induction does not happen just bc reversed Lorentz force (like science asylum taught me) - it actually happens because change in magnetic flux. Well what is magnetic flux?
        * me: mflux = mfield strength + area mfield penetrates + alignment/angle between mfield vector and area vector
        * me: mflux = how much mfield is in some defined AREA in terms of strength
        * mflux Φ=B⋅A⋅cos(θ) where:
          * B is the magnetic field strength (in teslas, T),
          * A is the area through which the field lines pass (in square meters, m²) - imagine inside plane of coil from science asylum experiment (flat circle inside coil above mfield pointing up)
            * Q: what is the area defined by? like how do you know the orientation of that area?
              * Simple for science asylum experiment bc just flat circle and orientation is plane of that circle
              * for more complex areas, that plane can vary quite a bit
              * NOTE: for inductors, the coils dont increase flux bc of area or orientation of area - it's bc each mfield from each loop comes together to create one strong mfield. So, area and orientation of that area stays constant - it's the mfield strength that changes as current changes (altho diff coils do change flux due to area and num loops)
          * θ is the angle between the magnetic field direction and the normal plane to the area. Perp = max. Parallel = 0 magnetic flux.
          * **Units**: Magnetic flux is measured in **webers (Wb)**, where 1 weber equals 1 tesla-meter squared (1Wb=1T⋅m2)
        * induce: change/cause through influence/persuasion. cause emfield through changing mflux (changing mstrength, morientation, marea. often originating from force like generator)
        * note: there's basically 3 main types of magInduction (from my learnings)
          * EMF ROLE IN mINDUCTION: i like to think of EMF as changing mflux + conductor sets up efield with a certain voltage config that is the EMF, which then induces current with another mfield (altho it’s not a new mfield in self inductance) - and i think this new mfield is what interacts with original mfield in first place - new mfield opposes change in mflux (opposes increase in mflux by storing energy in mfield and cancelling old mfield with induced; and opposes decrease in mflux by release energy and helping old mfield with induced) - Lenz's Law
          * 1: type where errthing constant except the angle (generator, some force drives it, changing mflux + force)
            * same type for motor here. Note: EMF doesnt drive motors - it actually opposes current from battery. Lforce from battery current moving through permMagnet is what creates force of motor that drives stuff like boats etc
            * generator: force spins coil, changing mflux thanks to angle + conductor spawns EMF that sets up efield that spawns current (and another mfield with it)
          * 2: type where errthing constant except mfield strength (inductor, changing current drives it, changing mflux + EMF)
          * 3: Science Asylum no-current parallel wires example isnt practical, but iz interesting bc it is basically generator in sense that a Lorentz Force causes it - but it is the mfield strength that changes (so it mixes up 2 main types sorta)
            * move left wire to left, making changing mfield strength on right wire. EMF induces efield on right wire which then that induces current with new mfield (since decrease in mflux/mstrength, new mfield releases energy to create current - energy came from force on left wire)
            * this fits vsauce experiment too of magnet dropped through copper tube. mfield strength changes near a conductor - a moving mfield. this spawns efield/EMF/eddy-currents and mfield that opposes increases and decreases in mflux - slowing velocity of falling magnet
        * Q: but why does mfield being parallel with the area (that doesnt have another mfield) cause 0 magnetic flux?
          * GPT: bc means mfield lines are not actually penetrating the plane of that area (but i dont really like this)
          * me: well if there's 2 magnets it kinda makes sense to me bc energy minimized and you feel no magnetic torque force (hence no strength) once mfields are aligned...so i guess that's it. Altho...in generator example (like Science asylum) there's only 1 mfield and maginduction generates a new one as Lforce applied...so i guess mflux here is between external mfield and induced/generated one in that defined area...but diz quite confusing tbh (seems this is right after much research)
            * a force can cause mflux to change and EMF appears and generates a moving charge (and mfield with it). If static magnet sitting there, it will interact with that generated mfield instantly - and as we know, if mfield vectors between 2 are parallel - the torque force wont be felt! (0 mstrength and mflux)...this is what makes sense to me - i dont think im gonna go any deeper
        * MOVING CHARGE vs MOVING MFIELD: it's easy to understand moving charge create mfield, but not easy to understand that moving mfield creates efield (i guess bc mfield isnt quantized on particles, but charge is)
    * [[2024-10-12]] what is induce, magnetic induction from science asylum parallel wires experiment, reversed Lorentz force, backwards motor, where is most mflux for our powah generation (like what var of mflux)? #memo
      * what is induce?: A: to cause something by persuasion or influence
      * changing mflux persuades/induces electricity/current to happen - charge to literally spawn! (charge doesnt always spawn if no conductor, but EMF does!) - so it's more like it's inducing EMF
      * 1: you start with 2 parallel wires pointing down with both having current flow, but in opposite directions
      * 2: one current in wire exerts Lorentz force (magnetic force) on another opposite direction current wire using exerting-current's mfield (actually both wires exert on each other)
        * NOTE: i dont think this part is thatttt important to understand
        * The two wires can either **attract** or **repel** each other, depending on the relative direction of the currents:
          * If the currents are in the **same direction**, the wires will **attract** each other.
          * If the currents are in **opposite directions**, the wires will **repel** each other.
        * NOTE: you can of course hold a wire steady
      * Q: say you have 2 wires parallel to each other. one has current flowing through it. for the other wire to feel the lorentz force, does it also have to have current flowing through it or will it feel lorentz force without current flowing through it?
        * YES, it needs current flowing through it to feel lorentz force (even if induced current) - otherwise there will be no lorentz force felt (bc you get Lforce from moving charge in external mfield)
        * Q: so if one wire has current going through but the other does not, the current-flowing wire wont induce current in other wire?
          * if current-flowing wire is DC, no current will be induced in other wire...BUT if it is AC...current spawns bc changing mflux! (so Lorentz force will be felt too)
          * changing current of DC does have maginduction too, but not significant enough i think - if no inductor at least
      * 3: LORENTZ FORCE REVERSED = MAGNETIC INDUCTION: the above process from 2 is reversible. Somehow pushing/force a current-flowing WIRE sideways will cause/induce a current to spawn in parallel wire (assume no current already)
        * NOTE: i learned reversed Lforce is not the driver, so stop letting mind get stuck on that. Just like moving efield creates mfield - moving mfield creates efield - so force to move magnet (and change mflux) near a conductor will create EMF which generates current
        * The reversed Lforce can manifest changing mflux which then that + conductor induces current through EMF
      * Q: can this happen when starting with no charge at all?? bc i assume that's how power plants do it lol
        * YES. This is what electric generator is - a backwards motor - bc motor consumes energy from battery to get started (then current from battery + external mfield from magnet keeps it going bc Lforce); generator generates energy without battery (magnet's mfield is what combined with force to generate the energy!) 
        * Imagine science asylum experiment with battery, coil, and magnet - after he took battery away. When he spins it, this induces current in the coil - well if that current has somewhere to go. If nowhere to go, then you just get VOLTAGE/EMF.
        * in both cases, it's the voltage doing the good stuff/work (providing force or providing energy) (altho starting point is voltage in one..that generates force; and force that generates voltage/EMF in another)
          * motor: voltage and current created by battery, you spin coil which then you have moving charge (from battery) in the magnets mfield, which create lorentz force - this keeps the coil spinnin (or car/boat/plane moving)
            * battery - short-timed starting force - moving charge from battery - charge in external mfield creates lorentz force - force be generated constantly
          * generator: you spin coil with hand (Lorentz force), this rotating force combined with magnet's mfield induces voltage/EMF - if connected to something this will turn into moving charge! otherwise it just stays voltage
            * you create Lorentz force constantly - this force + external mfield induces voltage/emf - generates moving charge if connected to something - powah!
          * this show why electric generator = backwards motor
          * NOTE: voltage and electromotive force (EMF) technically arent the same thing despite both using volts unit. Not gonna study deeper, but EMF is typically used when talking of magnetic induction and voltage is usually more for electrostatic forces like in circuits
      * 4: reversed Lorentz force wire example isnt very practical - AC wall sockets are often 50-60Hz - youd have to wiggle wire back and forth 50-60 times per second to induce enough EMF/current - which is why you got spinning coils! (the mflux angle changes v rapidly)
        * oh neat, so the mflux from generators/power plant energy sources is mainly from the changing orientation of plane of mfield with plane of spinning coil. Altho, parallel wires example is mechanical push that changes mfield strength (not orientation) - which changes mflux. Generator example is mechanical push that rapidly changes orientation of mfield relative to area/coil which changes mflux. Changing mflux induces EMF/current/voltage - which leads to energy generation
        * COOL: as of 2024, most of our electrical energy/power is made through magnetic induction. By making coils spin in mfields. Wind power = wind turns blades which are attached to coil. Water power = flowing water turns a coil. Coal or natural gas or oil (fossil fuels) = heat from burning it boils water into steam and steam turns a coil. Nuclear = heat from reactor boils water into steam and steam turns a coil (steam has lot of heat and conversion of thermal energy to mechanical is what rotates coil)
      * memo thoughts
        * [[2024-10-26]]
          * learned most, if not all, generators induce current in AC - which stays same from generator to every building - there's no thing converting ur houses outlets to AC. Not gonna memo details of why rn tho (iz basically bc parallel/aligned is 0, so can visualize spinning coil and max point at perpendicular and there's 2 perps, so those are pos and neg signs)
    * [[2024-10-14]] Q: is it electric force from opposing EMF that slows down falling magnet in copper pipe (vsauce) OR is it the Lorentz force that is a part of the induced current that slow down the falling magnet? electromagnetic damping/braking, what is energy flow of pipe example and how damping force a part, is damping force in inductor? #memo
      * MFIELDofMagnet + CONDUCTOR + INDUCEDMFIELDofEDDYCURRENTS GENERATE EDDYCURRENTS: there probably is a Lforce, but iz not that. Entire process is driven by conversion of **mechanical energy** (KE + PE) into heat; the Mfields of eddycurrents generate braking force bc they are what spawn eddycurrents holding electricenergy which then transfer to heat lost to resistive losses (force is about mass movement and mfields main controller that allows mass to move)
      * ### Summary of Energy Flow:
        * **Gravitational potential energy** → **kinetic energy** (falling magnet).
        * **Kinetic energy** → **electrical energy** (eddy currents induced in the copper pipe).
          * CHANGING MFLUX > EMF > EDDYCURRENTS: The **EMF** spawned from changing mflux causes electrons to move in the copper, creating **eddy currents**. These eddy currents are circular currents INDUCED within the conductor.
          * JUST SUMMING UP MINDUCTION: These currents are induced in such a way that their magnetic fields oppose the change in magnetic flux (in accordance with **Lenz’s Law**). Essentially, the copper pipe generates its own magnetic field to resist the motion of the falling magnet.
          * **Kinetic energy** (from the falling magnet) is **reduced** by the **damping force** from eddy current's mfield against magnet's mfield
          * IZ ACTUAL FORCE: this is an actual force that can be measured in Newtons and can be thought of as the **damping force** that resists the magnet’s motion.
          * MULTIPLE FORCES CONTAINED IN ONE: it's kinda like multiple energy-transfer/work processes combined with dynamics of fields (and containing other forces like electric force of EMF of eddy currents) creating one force - damping force
        * Q: so is there no transfer to magnetic energy and then to something else? or none that is significant or what?
          * correct, none - bc the eddy currents are so **short lived** and most energy going from electric energy straight to thermal energy through resistive losses. These mfields of eddy currents are mostly used to **generate damping/braking force** which reduces kinetic energy
        * **efield energy** → **thermal energy** (heat dissipated in the copper pipe through resistive losses).
          * JOULE HEATING, OHMIC HEATING: as the eddy currents flow through the copper, they experience resistance, which causes the copper to heat up (this is known as Joule heating or Ohmic heating). This is where the energy ends: in the form of heat.
          * NOTE: the force and the path of energy transfer is different. damping force decreases the kinetic energy of magnet. Q: so the damping force decreases the kinetic energy of the magnet - but doesnt that mean the damping force is causing energy to go from one place to another?
            * The **force itself** is a result of the interaction between magnetic fields, but the **energy conversion process** follows from the induced eddy currents encountering resistance in the copper.
            * ACTUAL DAMPING FORCE: told by Lenz's Law - mforce of induced eddycurrent's mfield opposing change in mflux. EMF (electric) → induced Current (electric) → Induced Magnetic Field of that current → Interaction with Original Field (magnetic) → Damping Force (magnetic)
            * FORCE AS PORTAL 4 ENERGY FLOW: previously was saying force was governor of energy flow, but its more like an interface or portal that opens up allowing energy to flow in various ways
            * VISUAL: i imagine damping force as force on falling magnet against force of gravity pushing it down. It happens initially due to Lenz's law/changes in mflux near conductor (but energy flow process more complex)
      * names of force: braking force, damping force, electromagnetic damping, eddy current damping (yes in this example, but not in inductor)
      * Q: is damping force a part of LC circuits? not LC circuits, but yes for RLC circuits
      * REGEN BRAKING: not many other times where electromagnetic damping is prominent that i know of EXCEPT regenerative braking in EVs - i dont totally get it, but you break - motor becomes generator and kinetic energy of slowing-rotating-motor turns to electric energy that is caught and stored in battery (instead of wasting that energy) - all while stopping the car lol. NOTE: everything talked of here was electromagnetic damping - but there is also mechanical damping - but i no go into that
    * [[2024-10-16]] how does inductor work in LC circuit, Lenz's Law and Faraday's Law of Induction, meme-recall all dese questions below #memo
      * what is inductor
        * usually just a coil, sometimes iron or other magnets inside coil to increase inductance
        * what is inductance? A: standard definition i **dont like**: ability to resist changes in current (which is also changes in mflux) (will define more detailed later - not actual resistance like in resistor)
        * MAIN THING I LEARNED WAS ACTUALLY SELF-INDUCTANCE: **self-inductance** or self building up of magnetic field as current changes in it (EMF on self). self-inductance literally is what i learned at first - when you have ONE coil. **Broader inductance** can be used for that OR when you have more than just 1 coil like in a transformer: **Mutual inductance**: This occurs when a changing current in one coil induces an EMF in a different, nearby coil. For instance, in a transformer, the primary coil's changing current induces an EMF in the secondary coil (so not self-inductance)
        * meme: inductance...induce...iz all about measuring ability to induce EMF/voltage/current (which is same as ability to store magnetic energy in inductor)
        * UNIT FOR INDUCTANCE: henry (H)
          * 1H = 1v/1A/s (1H is inductance of a circuit where an electromotive force (emf) of 1 volt is GENERATED when the current changes at a rate of 1 ampere per second)
          * compared to capacitance unit of F farads: 1F=1C/V
      * LC circuit = resonant circuit = inductor (L) and capacitor (C). Not just the 2 parts at ends with wire between. However, flow of electrons in circuit do reverse after each pass through inductor. Also, flow of charge DOES stop in capacitor, but DOES NOT stop in inductor - it just goes right through
      * Q: so there is no magnetic induction in an inductor? (my confused question lol bc i was thinking magnetic induction just means current being spawned)
        * Q: is it the electric force of back EMF doing the opposing of current or is it the back EMF voltage itself doing the opposing?
          * not gonna do any deeper, but seems it's the induced EMF/voltage itself (which maybe sets up that electric force to do the resisting all around circuit...but not sure). me: im just gonna say both
        * ON ITS SELF LOL: This induced voltage tries to oppose the change in the current that created the magnetic field in the first place. So, if the current is increasing as flowing out of capacitor, the inductor will generate a back EMF that tries to reduce the current (energy not being lost as heat, back EMF lessens efield of current with opposing efield/voltage/electric force - which converts reduced elecEnergy to be magnetic energy), and if the current is decreasing, it will generate a back EMF that tries to keep the current flowing.
        * Q: is all energy stored in inductor from the back EMF or is some just stored individual from the back EMF? (bad question, but useful to skim i think)
          * basically both: back EMF does regulate/control rate at which energy is stored, but energy comes from external source obv
          * Q: so energy is not stored in the magnetic field without the back EMF but you (GPT) previously told me that not all energy stored in mfield is because of the back EMF
            * In one sense, back EMF is crucial because it provides the opposition to current changes, ensuring that the energy transfer to the magnetic field happens gradually. But on the other hand, **not all the energy stored in the magnetic field is "caused" by the back EMF**, meaning the energy doesn’t originate from the back EMF but rather from the **external source** (like a capacitor or power supply) pushing current through the inductor.
            * ### If There Were No Back EMF:
              * the current could increase without any opposition, and there would be no controlled energy transfer to the magnetic field. Energy storage depends on the interaction between the current and the magnetic field, and the back EMF is a crucial part of making this process **smooth and stable**.
              * **No back EMF** would lead to an unrealistic, unstable system where energy could not be stored efficiently because current could change too quickly, leading to unpredictable behavior.
            * ### Final Clarification:
              * The **back EMF is necessary** for the controlled storage of energy in the magnetic field, but it does not **produce or store the energy** itself. The energy comes from the external voltage source, and the back EMF is part of the **mechanism** that ensures the energy flows into the magnetic field at a controlled rate.
              * me: back EMF is like a governor of energy transfer based on what fields and env is there - but it doesnt create or store energy itself
              * NOTE: if steady current, energy can be sitting there stored in mfield of inductor
        * inductor is not the same magnetic induction as with the force of a generator - they are both magnetic induction, but arising from different physical circumstances. Mechanical induction vs electromagnetic induction
          * GPT: **Both processes involve magnetic induction**, but they are **different mechanisms**.
            * A **generator** relies on **mechanical induction** (always some force - imagine Science Asylum coil, magnet experiment with hand pushing except wind pushing instead of hand)
            * An **LC circuit** relies on **electromagnetic induction** (a changing magnetic field inducing an electric field via Faraday’s Law).
            * so in both, magnetic flux is changing, but by different methods. GENERATOR: changing flux caused by motion of conductor/coil through external mfield/magnet (thanks to some force). LC circuit: changing flux caused by increase and decrease in current flowing through coil/inductor which generates incr/decr mfield
            * point of above point: this changing mflux is what generates EMF/induced voltage which generates (or transfers) energy/power/current in both types of induction
        * Q: if you had a capacitor on a circuit that had wire go from one plate to the other plate of capacitor - would this current flow back and forth? (no inductor in this example)
          * charge would equalize between plates bc energy minimization and flow of charge stops bc no voltage
          * Q: so why does inductor cause oscillations instead of doing same as capacitor-only circuit?
            * the inductor literally stores energy in its mfield (but not charge/electrons) and which allows for the reversal of flow of energy and charges eventually. This back EMF generated by the collapsing magnetic field essentially "recycles" the energy back into the circuit
            * TIMING OF FIELD vs FORCE vs PARTICLE: field dynamics before force. particle dynamics before force. but sometimes field before particle OR particle before field - just depends on context really
            * inductance = inductor/mfield resists any change (incr/decr) of current. This is not same resistance as in resistor. But this does slow down the RATE of current increase or decrease - making it more gradual - which is why you get sine curve (S-looking curve) when measuring current of this circuit - which shows the oscillation back and forth. Back EMF and eforce spawned from field configs enforces this power change
              * MEME FOR INDUCTANCE: all proportional: mfield strength, amount energy mfield can store, inductance, stronger resistance from mfield of coil, amount of energy EMF can INDUCE (thinking of transformer and 1 coil inducing on another coil)
              * inductance seems like a measure of Lenz's Law or Faraday's Law of Induction
              * hmm...i wonder if there's relation of voltage of OG current vs EMF/voltage. Just pondering on how voltage is changed by a stepdown or up transformer. maybe will doc this next time. EDIT: there is but idc that much...BUT what iz cool is that transformers do stepping just based on number of loops in the 2 coils. And energy stays the SAME despite steps. if voltage goes down, then current will increase and vice versa to maintain stable energy flow or whatever
            * lol moment: ohhh you need to think in terms of energy. i think i get it now. energy in capacitor empties out. then you have energy in mfield of inductor bc it caught the energy - which then empties out to next capacitor plate once mfield collapses (bc C voltage finished) - which the force emptying out the mfield is back EMF/induced voltage
            * The back EMF **keeps current flowing**, even though the capacitor is no longer providing the charge/voltage. Once the capacitor is nearly discharged, you’d expect the current to stop, just like in the capacitor-only case. But the inductor steps in here.
            * The current continues to flow from the inductor’s energy/EMF/voltage, causing the capacitor to start charging again, but in the **opposite polarity** (the plates’ charges swap).
            * Q: in capacitor-only circuit, where does the energy go?
              * capacitor discharges, equal charges on both plates, **Most of the energy** from the capacitor is **lost as heat** from resistance in the wire during discharge.
              * There is **no energy left** in the capacitor once it’s fully discharged. The system reaches an energy minimum when the capacitor is fully discharged, but all the ORIGINAL energy is dissipated (primarily as heat), not redistributed elsewhere. Now it has ground state energy or minimum energy or stable/equilibrium energy
            * Q: so is there no back EMF until mfield collapses?
              * Wrong. **During Current Changes**: Back EMF is generated **whenever there is a change in current** through an inductor (including during the collapse of the magnetic field).
            * Q: so what is back EMF and what direction?
              * induced voltage that is very short lived bc mfield cant store energy forever - only when current/mflux changes
              * it opposes the increase or decrease in mflux. it wants to maintain mflux instead of it changing
              * it seems weird that the current's own mfield would induce back EMF on itself to oppose itself
                * this is known as self-induction
                * if current is constant, no back EMF occurs - but energy can be stored in mfield from prior current changes (but energy doesnt change during steady flow)
                * mfields like to be stable/constant, but also are only that way if paired with an efield (which has its own force)
            * Q: so is the stored energy in the mfield generated by the current that passed through the coil? is this mfield attached to those electrons or to the coil?
              * Yes it is generated by the current passing through coil. The current generates the magnetic field, and the energy associated with that field is stored in the space around the coil, not directly in the coil or in the electrons themselves.
              * The **magnetic field** is a property of the **space** around the coil (not attached to the electrons), and the energy is stored in this field. This is why we say that the energy is stored in the **magnetic field**, rather than in the coil or in the charges.
            * Q: so what is Lenz's law?
              * me: about changing current/mflux causing opposing back EMF
              * Q: how is Lenz's law different from Faraday's Law of Induction?
                * very similar. **Faraday's Law** tells you how much (magnitude) EMF is induced when there’s a change in magnetic flux, while **Lenz's Law** tells you the direction of the induced current.
                * Faraday's Law of Induction: Relates changing magnetic fields to induced voltage magnitude
                * Lenz's Law: Ensures conservation of energy and opposition to change (in current and mflux)
                * meme: together they make a vector. magnitude is FLaw and arrow is LL
            * NOTE: flow of charge and flow of energy not same as we already know from house circuit light switch causing change instantly in diff location and bc power lines are AC but energy only one way (tbh dont remember why i thought this important to remember)
