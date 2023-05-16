## P3EmptyGame

[P3EmptyGame](https://github.com/clempo2/P3EmptyGame) is the HelloWorld example for the [Multimorphic](https://www.multimorphic.com/) [P3 Pinball platform](https://www.multimorphic.com/p3-pinball-platform/). P3EmptyGame is a complete functional game resulting from trimming down the sample game distributed in the [P3 SDK V0.8](https://www.multimorphic.com/support/projects/customer-support/wiki/3rd-Party_Development_Kit).

P3EmptyGame has two purposes:
- As a learning aid to study other P3 applications.

  Since P3EmptyGame consists nearly exclusively of boilerplate code, any difference must be the code specific to that other application. P3 applications now appear much smaller to study.

- As the foundation to create new P3 applications.

  Since dead code and unused assets have been removed from P3EmptyGame, it is a cleaner basis to start a new application compared to P3SampleApp.

## Statistics

| Metric | P3SampleApp | P3EmptyGame |
| ------ | ----------- | ----------- |
| files | 1146 | 735 |
| C# files | 133 | 95 |
| C# lines of code | 13374 | 8777 |

## Features

P3EmptyGame has the following game specific features:

- app code is P3EG
- compatible with all playfield modules
- side targets hits and completion
- lower lanes hits and completion
- playfield module targets score when hit
- playfield module holes score when entered
- balls are relaunched when entering a hole
- static HUD

P3EmptyGame has the following features inherited from the P3 SDK:

- game simulator in Unity development environment
- mapping of keyboard keys to generate events in game simulator
- selectable in App Launcher
- attract mode
- last game results in attract mode
- play for credits or free play
- 3-ball game
- 1 to 4 player game
- player profiles and team play
- removing players not started yet
- ball saver
- extra balls
- end of ball bonus
- bonus multiplier
- high scores
- tilt
- adjustable volume
- service menu
- game settings
- statistics
- logs

## Installation

P3EmptyGame is distributed as a patch created by [P3Distrib](https://github.com/clempo2/P3Distrib). To recreate the P3EmptyGame Unity project, you must apply the patch against an unmodified copy of P3SampleApp.

- Download P3Distrib
    ```
    git clone https://github.com/clempo2/P3Distrib
    ```
- Open the P3Distrib solution in Visual Studio
    ```
    cd P3Distrib  
    P3Distrib.sln
    ```
- Build the P3Patch executable
  Right-click the P3Patch project, select Rebuild
- Apply the patch against P3SampleApp, adjust the paths for your environment.  
  The output path is the patch path with the .p3patch extension removed.  
  In the example below, the Unity project is stored in the directory C:\P3\P3EmptyGame
    ```
    P3Patch\bin\Debug\P3Patch.exe C:\P3\P3_SDK_V0.8\P3SampleApp C:\P3\P3EmptyGame_V0.8.1.p3patch
    ```

## Instructions

Running in the simulator:

- Launch Unity
- Click "Open" to open a new project.
- Select the top-level folder of P3EmptyGame and click "Select Folder".
- If you don't see the Project window, open it by selecting Window/Project in the main menu.
- In the Project window, click on Scenes
- Double click on the Bootstrap scene to open it.
- Click the play button (triangle icon).
- Press the s key to start the game.
- Press the l (lowercase L) to launch a ball.
- Click the left mouse button and drag the cursor to move the ball.
- Press 0 (zero) to drain.

Deployment to the real machine:

- Launch Unity
- Click "Open" to open a new project.
- Select the top-level folder of P3EmptyGame and click "Select Folder".
- Select Multimorphic/Package App for Distribution in the main menu.
- Enter the values
    - Display name: P3EmptyGame
    - Version: 1.0.0.0
    - Description: P3 Minimal Sample Application
    - Compatible module ids: Any
- Leave Feature flags and Tags empty
- Select a USB drive.
- Click Continue.
- Take the USB drive to the real machine and install the software.
- Start the App Launcher and select P3EmptyGame to start the game.
- The certificate lasts 3 days. Repackage and redeploy to get another 3 days.

## List of Changes

These are the differences between P3SampleApp and P3EmptyGame

- Removed dead code
- Removed unused assets
- Changed AppCode from P3SA to P3EG
- Changed launcher media images
- Changed game title in Attract mode
- Marked some member variables private
- Removed unfinished mode summary and instructions
- Removed unused skillshot
- Removed unimplemented cheat detection
- Removed ramp shot counter mode
- Removed attempted/completion state of a scene
- Launches cycle between all launchers with inlane or lower playfield destination
- Launches cycle between launchers with upper playfield destination on Drained
- Removed Twitch integration
- Removed ramp shots high score categories
- Changed version of game attributes to 1
- Changed default for side target difficulty to 2 (one target per hit)
- Side target completion and reset
- Added score to lower lanes
- Added score to BallPath Targets, BallPath Holes and TroughLauncherEntry
- Relaunch ball when entering hole or TroughLauncher
- Support mode events in BallPath Targets
- Removed HUD inventory
- Added BumpersMode
- Removed MovingTargetMode and cube in Home scene
- Removed unused Multiball mode
- Removed character intros in Attract mode
- Allow Results stage to be first in Attract mode

## Known Issues

P3EmptyGame is missing some assets that are also missing in P3SampleApp. See [Issue1](https://github.com/clempo2/P3EmptyGame/issues/1).

## Support

Please submit a [GitHub issue](https://github.com/clempo2/P3EmptyGame/issues) if you find a problem.

You can discuss P3EmptyGame and other P3 Development topics on the [P3 Community Discord Server](https://discord.gg/GuKGcaDkjd) in the dev-forum channel under the 3rd Party Development section.

## License

P3EmptyGame is a subset of P3SampleApp and therefore inherits its license.  
Copyright (c) 2022 Multimorphic, Inc. All Rights Reserved

The difference between P3SampleApp and P3EmptyGame is  
Copyright (c) 2023 Clement Pellerin  
MIT License.
