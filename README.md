[![release-badge]][latest-release]

[release-badge]: https://img.shields.io/github/v/release/Rosto75/vstrack?include_prereleases
[latest-release]: https://github.com/Rosto75/vstrack/releases/latest

# VSTrack (Vagrant Story Tracker)
[about-vstrack]: #about-vstrack

***VSTrack*** is a simple but powerful tool for [Vagrant Story][vagrant-game] players, streamers, and speed-runners. 


It collects a bunch of useful data from the runnig game, and stores it in standard `.txt` files. This gives you an easy access to information that is often burried behind multiple levels of UI, or not available to the player at all.

One way to use the collected data is to feed the output files into your streaming software as a text input (i.e. Text (GDI+) plugin in [OBS][obs]), and use it as a part of your layout. Keep in mind, that most of the data is formatted with fixed-width fonts in mind (use proportional fonts at your own risk).

At this moment, you can track the following:
* Weapon, Blade, and Shield stats and properties
* Armor (all slots, plus necklace) stats and properties
* Player stats (HP, MP, RISK, STR, INT, AGL, range, walking/running speed)
* Player location (area name, room name)
* In-game play timer (with 1 second precision)

*VSTrack* also detects when the last boss dies, and auto-magically stores the record play time in this very moment.

Weapon, armor and shield data are stored in two formats:
* full
* short: only CLASS and AFFINITY values (useful for item leveling)

## Prerequisites
[prerequisites]: #prerequisites

Currently, *VSTrack* can work with [ePSXe][epsxe-emulator] and [BizHawk][bizhawk-emulator] emulators, but the plan is to add support for more in the future.

To use *VSTrack* you'll need:
* One of the supported emulators:
	* **ePSXe** version *1.9.0*, *1.9.25* or *2.0.5*
	* **BizHawk** version *2.3.0* or *2.3.2*
* Copy of the game:
	* **Vagrant Story** NTSC-US version *(SLUS-01040)* <sup>1</sup>

<sup>1</sup> Other SKUs of the game might work, but weren't tested yet.

## How to use it
[usage]: #usage

No installation is required. Just copy the executable into preffered folder, and run it from the command-line or by double-clicking. **WARNING** If you're not sure your user account has the writing privileges for the chosen folder, run the program as an administrator. 

When you'll see the start menu, press key `1-5` to choose emulator version you're using to play the game,  or `0` to exit. If your selection was correct, you should see some basic game information in the console window.

Alternatively, you can pass preferred emulator number as a command-line parameter, so if you want to use *VSTrack* with `BizHawk 2.3.0`, type:
```bash
vstrack.exe 4
```

During the first use, the program will create a subfolder called `game_stats`, where all the output files will be stored. When you finish the game, record time will be stored in the folder `game_stats/records`. Each record is preserved in separate file, with an unique name. For example, if the record file is named:
```
20191112T201730-record-time.txt
```
it means, that the last boss died at ***20:17.30, November 12, 2019***. Easy.

After writing the record, *VSTrack* will wait for your input and terminate itself. If you want to play another game session, simply restart the program.



## Contributing
[contributing]: #contributing

### Pull Requests
[pull-requests]: #pull-requests

To make changes to *VSTrack*, please send in pull request to the `master` branch on GitHub. I will review it, and either merge or request further changes.

### Issue Tracker
[issue-tracker]: #issue-tracker

If you found a bug, want to suggest a new feature, or disscuss how the program works, please use the Issue Tracker on its GitHub page.

I encourage you to use the following labels:
* `enhancement`: when you request new functionality
* `bug`: if you want to report a part of *VSTrack* that is not working correctly, or not working at all
* `discussion`: if you want to discuss improving something in *VSTrack* 


## Known Issues
[known-issues]: #known-issues

Everything's fine. Really.


## Acknowledgements
[acknowledgements]: #acknowledgements

I would like to thank:
* [Square-Enix][square-enix] and the game dev team, for creating and publishing such excellent piece of software
* [GameFAQs][game-faqs] guide authors, especially:
  * Jay Tilton
  * Samuel Riesterer
  * Matt Hamand
  * Zy Nicholson
* [Data Crystal][data-crystal], for collecting and sharing a huge collection of information about the inner-workings of the game
* [Cheat Engine][cheat-engine] authors and community:
  * besides being a direct inspiration for my little tool, CE allowed me to extract information from the game with ease, and test *VSTrack* behaviour in a very reliable way 
  * CE forums are the huge vault of technical knowledge; I found a lot of programming gems out there
* [MSDN][msdn], for state-of-the-art documentation, which makes developing on Windows such a pleasure


[vagrant-game]: https://en.wikipedia.org/wiki/Vagrant_Story
[obs]: https://obsproject.com
[epsxe-emulator]: https://www.epsxe.com
[bizhawk-emulator]: http://tasvideos.org/BizHawk.html
[data-crystal]: http://datacrystal.romhacking.net/wiki/Vagrant_Story
[game-faqs]: https://gamefaqs.gamespot.com/ps/914326-vagrant-story/faqs 
[square-enix]: https://www.jp.square-enix.com/game/detail/vagrantstory/
[cheat-engine]: https://www.cheatengine.org
[msdn]: https://msdn.microsoft.com/en-us/