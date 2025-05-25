  * what is it?
    * tracking
      * before 2024
        * a [[compiler]] for linear algebra operations.
          * QUESTION: is it only for linear algebra ops?
        * a deep learning framework (between PyTorch and Micrograd apparently. Competes with tensorflow, pytorch, and JAX)
        * Hotz
          * is really an entropics (losing order) research group. Distilling neural networks down to their purest essence. The compression of the compressor.

Someday net size will be measured in gates instead of FLOPS or weights.
            * gate: Control Information Flow: Gates determine how much of the incoming information should be allowed to pass through. This is akin to a gate in a fence, which can be opened or closed to control passage.
      * [[2024-10-17]]
        * from Hotz in stream:
        * language to express *entire* machine learning jobs concisely
        * a scheduler, to determine the order of the sub-jobs
        * a compiler, to compile these sub-jobs to run on real hardware
        * a runtime, to actually run the jobs
        * The Goal: Build a large, free, fair, and simple to access market for thought. ^Mtz1E55mw
  * what does it do?
    * allows you to train models on various hardware
    * can run stable diffusion, can run llama, can train cfar, can train resnet
  * big difference in tinygrad and competitors
    * tinygrad is 100x simpler ^8-ngmIHdP
      * lot of problems with something like pytorch is COMBINATORIAL EXPLOSION - you have an operator, a dtype (data type), a device - and pytorch will write kernel for each one of those and those become MULTIPLIES
      * tinygrad supports dtypes in generic way, devices in generic way, operations in generic way - such that each of those become ADDS
      * you can add a new dtype and that dtype will automatically work for every operation tinygrad supports and on every device tinygrad supports
  * key notes
    * top contributors to github may make moneyz
    * it's a company that is literally just a GitHub and discord
  * questions
    * what is longterm goal of tinygrad?
      * Hotz: to build machine learning ASICS. BUT he starts with software and not hardware bc doesnt want to end up like [[dojo]] 
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/tinygrad#^Mtz1E55mw|The Goal: Build a large, free, fair, and simple to access market for thought.]]
      * "Our mission is to commoditize the petaflop." - AI infra must be taken for granted as free, in the same way Linux is. History is the story of infrastructure improvement.
    * based on nested details here [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/tinygrad#^8-ngmIHdP|tinygrad is 100x simpler]], does some part of tech stack not always support MULTIPLIES? like what are all the CONS of the MULTIPLIES in other machine learning frameworks that are replaced by ADDS in tinygrad? is it just that ADDS allow those 3 things mentioned to be GENERIC? and why does it allow them to be generic?
    * what is an accelerator is this context?
    * questions for myself?
      * why learn tinygrad?
        * i want to understand how this ML stuff works at the fundamental level
        * a lot of the concepts i see on the github are being applied in REAL usecases that you build stuff with. I see these terms used in social media, but they never make sense - i'd like them to make sense - especially since these terms are usually used by people at the edge of innovation when making predictions about the future
