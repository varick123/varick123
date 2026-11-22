<div align="center">

# Varick Teo

**Computer Science · Real-Time Interactive Simulation · SIT–DigiPen**

[LinkedIn](https://www.linkedin.com/in/varick-teo/) · [Repositories](https://github.com/varick123?tab=repositories)

</div>

I build C++ systems and TypeScript prototypes. I like working on the parts of software that determine what happens when timing changes, data is missing, or a user hits an edge case.

## About

I’m a Computer Science undergraduate at the Singapore Institute of Technology and DigiPen. Before university, I spent two years in National Service with the Digital and Intelligence Service, where I worked on intelligence research and geospatial analysis.

I’m interested in backend and systems engineering, especially how to test the behaviour of applications that depend on external data. I’m available for a full-time internship from May 2027 to April 2028.

## Selected projects

### ChargedUp · Electric vehicle journey planning

`TypeScript` · `Qwen` · `Ollama` · `external data`

On this team project for Upsight, I built a scoring package that checks whether the battery can make the trip and ranks charging stops by cost, travel time and detour. I also helped connect the conversational assistant to those calculations and check how it handled missing or stale charger information.

### WaterBound · Game engine timing

`C++20` · `OpenGL` · `fixed-timestep simulation`

I worked on a team engine that had to coordinate input, collision, physics, audio and rendering even when frames took different amounts of time. I implemented a fixed-timestep loop so simulation updates could run at a consistent interval. I also worked on saving and loading scenes and prefabs to keep level data consistent with the engine’s runtime state.

**Illustrative timing check.** Over one second, updating physics once per rendered frame gives 30 updates at 30 frames per second and 60 at 60. A fixed 60 Hz simulation step gives 60 updates in either case. This illustrates the timing choice in WaterBound.

### Thalassa · Repeated hazard damage

`C++` · `Alpha Engine` · `collision and gameplay state`

I implemented player, camera and hazard systems, including health and checkpoint respawns. A hazard can overlap the player across consecutive frames. Treating every overlapping frame as a fresh hit would drain health repeatedly. I added a 0.3-second invincibility window after a hit so the player had time to move away.

**Example test case.** After a hit at 0.00 seconds, continued contact at 0.10 seconds should leave health unchanged. A fresh hit at 0.31 seconds should be eligible to deal damage again.

### EV Battery Reserve Checker · Testing the reserve boundary

`JavaScript` · `HTML` · `CSS`

This standalone demo, built with Codex assistance, estimates whether an electric vehicle can finish a trip with the requested battery reserve. It uses driver-entered values and assumes constant consumption with no charging stops. If a trip runs out of energy before the destination, the demo reports the shortfall and leaves the arrival charge blank.

**Verified in the browser.** The presets cover arriving at 29% against a 15% reserve, arriving at exactly 15%, and needing another 5.1 kWh to finish. Clearing the battery capacity clears the estimate, and selecting a preset restores it.

[Live demo](https://varick123.github.io/ev-battery-reserve-checker/) · [Source code](https://github.com/varick123/ev-battery-reserve-checker)

## Tools

- **Systems and graphics** — C, C++, OpenGL, CMake
- **Application logic and testing** — TypeScript, JavaScript, Git, Vitest, CTest
