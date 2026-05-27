100 µF + 0.1 µF decoupling

they are fixing two different types of power supply noise.
⚡ Why two capacitors?
🔴 1. 100 µF capacitor = low-frequency stability

This is the “energy reservoir”.

It handles:

slow voltage dips (bass peaks, speaker load changes)
ripple from battery/adapter
general supply sag

👉 Think of it as a water tank that keeps voltage steady over milliseconds.

But it is too slow to react to fast noise.

🔵 2. 0.1 µF capacitor = high-frequency noise filter

This one handles:

RF noise (phone signals, Wi-Fi, switching noise)
fast spikes from the IC itself
high-frequency oscillations

👉 Think of it as a fine mesh filter that catches tiny fast ripples.

But it stores very little energy, so it cannot handle big dips.
