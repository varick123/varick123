# Varick Teo

I’m a Computer Science student studying Real-Time Interactive Simulation at SIT–DigiPen. These projects cover engine timing, gameplay state and testing boundary cases.

## WaterBound · Game engine timing

I worked on a C++20 team engine that had to coordinate input, collision, physics, audio and rendering even when frames took different amounts of time. Updating the simulation once per rendered frame would tie its progress to frame rate. I implemented a fixed-timestep loop so simulation updates could run at a consistent interval. I also worked on saving and loading scenes and prefabs to keep level data consistent with the engine’s runtime state.

**Illustrative timing check.** Over one second, a frame-driven loop would update physics 30 times at 30 frames per second and 60 times at 60. A loop with a fixed 60 Hz simulation step would run 60 updates in both cases. This illustrates the timing choice in WaterBound.

## Thalassa · Repeated hazard damage

For this C++ platformer, I implemented player, camera and hazard systems, including health and checkpoint respawns. A hazard can overlap the player across consecutive frames. Treating each overlapping frame as a fresh hit would subtract health repeatedly. I added a 0.3-second invincibility window after a hit so the player could move away before taking damage again.

**Example test case.** After a hit at 0.00 seconds, continued contact at 0.10 seconds should leave health unchanged. A fresh hit at 0.31 seconds should be eligible to deal damage again.

## EV Battery Reserve Checker · Testing the reserve boundary

This standalone JavaScript demo, built with Codex assistance, estimates whether an electric vehicle can finish a trip with the requested battery reserve. It works from user-entered values and assumes constant consumption with no charging stops. A trip that runs out of energy before reaching its destination cannot report a valid arrival charge, so the demo displays the energy shortfall and leaves arrival charge blank.

**Verified in the browser.** One preset arrives at 29% against a 15% reserve, another arrives at exactly 15%, and the long trip needs another 5.1 kWh to finish. Clearing the battery capacity also clears the estimate, and selecting a preset restores it.

[Live demo](https://varick123.github.io/ev-battery-reserve-checker/) · [Source code](https://github.com/varick123/ev-battery-reserve-checker)
