+++
title = 'Hot Chips'
date = 2025-08-25T12:48:50-07:00
draft = false
+++

I attended the [Hot Chips](https://hotchips.org/about/) conference at Stanford this year. This post will briefly cover my highlights, thoughts, and questions. I was fun meeting folks from Normal Computing, Dylan Patel, as well as some Twitter friends.

Here are the key challenges for building GPU clusters:

- The scale-up and scale-out bandwidth/GPU has been doubling every 2 years
- Copper interconnect reach is decreasing with increased SERDES bit rates. There is a limit to SERDES eletrical bit rates.
- Doubling the number of SERDES lanes increases connector size and cable bulk
- The limited copper reach is driving GPU and scale-up switch proximity (rack density)
- The rack compute density drives power supply disaggregation
- More capable multi-reticle sized GPUs are incresing power requirements are force use of liquid cooling.

Google popularized water cooling back in 1980s, then went on air cooling, now back to water cooling as systems become more demanding. Meta is using CLPDs (Cooling Liquid Process Development) to stream real-time water sensor metrics for leak detection. It reminds me of when [Microsoft tried a fully submersible server](https://news.microsoft.com/source/features/sustainability/project-natick-underwater-datacenter/), but [killed the project](https://www.tomshardware.com/desktops/servers/microsoft-shelves-its-underwater-data-center) several years later. Immersion cooling doesn't directly target hot spots. Just get cheap land and pay electricity. 

HBM is a key bottleneck. Improving bandwidth across many chips can and will significantly speed up inference. Better interconnect and network bandwidth is needed for efficient model parallelism. Fiber interconnects have high failure rates, and the pluggable ones are especially expensive. The aggregate memory bandwidth across chips determines scalability for fast inference. Coordination is difficult because hardware and software evolve on different timelines and timescales. Inference latency is driven in part by long chains of thought. Low precision is often sufficient for inference (reminds me of this [tweet](https://x.com/jwt0625/status/1966148895748374870)). Overflow issues in low-level operations can be addressed by adding more accumulator bits.

The brain contains more parameters than training data, suggesting efficiency from intralayer connections and functional specialization. Notably, transformers operate in symbolic/language space, representing information as discrete tokens and excel at short-term reasoning but struggle with long contexts. On the other hand, RNNs operate in neural space, storing information in continuous hidden states that compress and carry meaning across long contexts. Most growth in capability is expected to come from post-training methods.

Humanity acts as both an investor and a reward signal guiding AI development. Even without new hardware, progress toward AGI seems feasible. However, an AGI doesn't seem efficient as Nature has evolved to be specialized. This will be more important for humans and AI systems become better generalists.