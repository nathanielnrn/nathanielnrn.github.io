+++
title = "CUAUV"
description = "CUAUV is an autonomous underwater vehicle team that annually builds an autonomous submarine to compete in the RoboSub competition."
weight = 2

[extra]
local_image = "projects/auv/subs.png"
+++

[CUAUV](https://cuauv.org) is a Cornell Project Team that annually creates an
autonomous underwater vehicle for competition in [Robosub](https://robonation.org/programs/robosub/).
The submarine uses a from-scratch software stack to understand the world around
it, control itself, and remain funcaiton in the face of distrubances.


#### CUAUV development happens on a private repo and can be viewed upon request {.centered-text}

## Contributions

 - Optimized **control system**, incorporating a closed-loop PID system, a
 desire-to-thrust optimizer, and updated pwm-to-thrust curves with empirical measurements.
 Our control system produces a responsive and predictively-behaved submarine.
 - Tuned **CV algorithms** incorporating SIFT, contour denoising, and associated
 locomotion logic.
 - **Auto-PID-tuner** rewrite that utilizes [Zeigler-Nichols](https://en.wikipedia.org/wiki/Ziegler%E2%80%93Nichols_method)
 to caculate PID values that produce desired behavior. This rewrite included
 updated logic and quality of life improvements for the auto-tuner and associated
 tools.
