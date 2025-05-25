  * tracking learning
    * [[2025-02-10]] trying to understand deltaTime, independent vs dependent vars, fixedUpdate, fixedTimestep #[[fast memo]]
      * ALL change needs to be tightly coupled to time. if it's not, both visuals and the math no longer stays consistent...1) across different devices 2) across one device with changing FPS and refreshrate
      * memes im playin with
        * independent vars = coupled to framerate (despite deltaTime allowing it to not LOOK that way) AND dont depend on change from prior frames. dependent vars = decoupled from framerate AND do depend on change from prior frames
        * independent vars: variable updateRate bc coupled to framerate. dependent vars = constant updateRate (const num updates per second AND const time set that update happens every x time) set using fixedTimeStep
        * independent var job of deltaTime: decouple from framerate and make game speed/change LOOK same for every user/device
        * dependent var job of BOTH fixedTimestep AND fixedsteps/updates: same as independent AND make sure values stay precise from frame to frame...bc using deltaTime is for syncing/decoupling...BUT for dependent vars it actually causes HARM by adding in nonprecise change - not consistent across frames
      * even some visuals need to use fixedUpdate and fixedTimestep if they are a dependent var (dependent vs independent is the determining factor)
      * dependent var = value of var/value of change being applied to that var is dependent on previous frame. To keep these values consistent across frames of differing devices, you gotta fix 2 things talked about later. Otherwise differing devices/FPS will get different values. TECHNICALLY, independent vars do indeed get differing VALUES too, BUT they will still LOOK consistent across all devices
      * The key difference isn't whether a var uses its previous value, but whether the RATE OF CHANGE is:
        * Calculated fresh each frame or constant (independent)
        * Accumulated from previous frames (dependent)
        * so a change in rate-of-change lol specifically between frames
        * "position += speed * deltaTime" uses previous position, but rate of change is (speed * deltaTime) and assume speed is constant - so this is independent. Even if speed was changing BUT only calced fresh each frame, still independent.
        * contrasting ex of dependent var:
          * speed += acceleration * deltaTime    __// key is that acceleration is not constant and coupled to prior frames. if is constant, then this is independent
          * position += speed * deltaTime        *// position uses that accumulated speed*
        * some vars are dependent on their own, but some are dependent bc they use a dependent var
      * dependent vars are dependent on some change from the previous frame. They accumulate change over time that is stored in 1 or more vars. Bc change is accumulated over time, change applied needs to be in 1) fixed change-chunk (fixedTimestep) and 2) fixed amount of apply-those-change-chunks (updates, fixed num steps = deltaTime / fixedTimeStep). Otherwise, things break if 1 or 2 is NOT FIXED. 
        * so the number of times fixedUpdate is called PER FRAME may be different depending on device FPS, but numtimes fixedUpdate is called is FIXED PER any x period of time (like 1 sec). Also, since 1 and 2 are fixed, after x time, the values of say something like velocity (or any dependent var) will be same across devices
        * Q: so fixedTimeStep determines how many updates per second? and fixedNumSteps tells how many updates happen per frame/deltaTime?
          * CORRECT. grok3: 
          * **fixedTimeStep** sets the rhythm (e.g., 50 updates per second if fixedTimeStep is 0.02 seconds). ideal UPDATE RATE
          * **fixedNumSteps** tells you how many of those updates you need to squeeze into each frame based on how much time has passed (deltaTime). This number varies frame-to-frame because deltaTime depends on the actual frame rate, but the updates themselves remain consistent because they’re based on fixedTimeStep.
          * So, if your game runs at 60 FPS (deltaTime ≈ 0.0167 seconds) with a fixedTimeStep of 0.02 seconds:
            * 0.0167/0.02=0.835, meaning less than 1 update per frame—updates might not happen every frame, and time accumulates until it hits 0.02.
            * If it slows to 30 FPS (deltaTime ≈ 0.0333 seconds):
            * 0.0333/0.02=1.665, so 1 update per frame with some leftover time.
        * Q: is it correct that with regular non-fixed update, the update rate is not constant, but with fixedupdate it is constant
          * CORRECT.
          * Q: so even if nonfixed update uses deltaTime to decouple, it still depends on frame rate?
            * CORRECT. 