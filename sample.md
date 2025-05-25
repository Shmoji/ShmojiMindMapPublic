  * what is it?
    * in LLMs
      * A training dataset is comprised of many rows of data, e.g. many samples. A sample may also be called an instance, an observation, an input vector, or a feature vector.
      * A sample is a single row of data.

It contains inputs that are fed into the algorithm and an output that is used to compare to the prediction and calculate an error.
    * in SIGNAL PROCESSING (like for bci): #memo ^fTq7O6_4W
      * refers to the process of converting a continuous signal (like an electrical signal from a neuron) into a series of discrete values at specific time intervals. me: action potential lasts 1 ms - so you need to measure that electrical signal many more times than 1ms to detect all change during that 1ms (so sometimes youre turning something discrete into more discrete pieces)
      * me: feel like you can just think of sample as a data point lol - measured at your own frequency - take however many data points you want during this 1ms (1ms just ex, can use any time amount)
      * me: useful to think of this in terms of time, so we measure with Hz - [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/neuralink#^Yyimhk6vK|Hertz means cycles/samples/data-points per second (always relative to 1 second)]]
      * BUT, samples doesnt HAVE to be connected to time - the key point is that a sample represents a single unit of analysis, whether or not time is a factor. Ex: in spatial examples or others, you'd be focusing on spatial, quantitative, or qualitative measurements without reference to how often events occur over time.