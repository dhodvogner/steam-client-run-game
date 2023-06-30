# Hodi's unofficial steam-client-run-game fix for Steam Deck (Unreal Engine 5)

Currently, launching a game from the Unreal Editor on the Steam Deck does not work. This is because the `steam-client-run-game` script is missing from the `Engine/Build/SteamDeck` folder. 

I tried to fix this issue by re-creating the missing script. This is a temporary fix until Epic Games adds the script to the Engine. Please visit this [thread](https://forums.unrealengine.com/t/launching-on-steam-deck-does-not-work-on-ue-5-1/737750) for more information.

Tested with Unreal Engine 5.2.1

## How to use

1. Download the latest release from [here](https://github.com/dhodvogner/steam-client-run-game/archive/refs/heads/main.zip)
2. Extract the archive to a folder of your choice
3. Create a folder called `SteamDeck` in your Engine's installation `Engine/Build` folder (e.g. `C:\Program Files\Epic Games\UE_5.2\Engine\Build\SteamDeck`)
4. Copy the `steam-client-run-game` file and `vdf` folder with all of its content to the newly created `SteamDeck` folder
5. Launch the game from the Unreal Editor as described [here](https://docs.unrealengine.com/5.2/en-US/steam-deck-quick-start-in-unreal-engine/)
6. **When you launch a game for the first time, it won't work.** You need to navigate on your Deck to Steam -> Library -> Non-Steam Games and launch the game from there. This will register the new appid in the `screenshots.vdf` file. After that, you can launch the game from the Unreal Editor.

## Known issues

- It seems like the Steam Overlay is not working, if you launch the game while the Deck is in Desktop mode. (I'm not sure if this is an issue with the script or with the Deck itself)
- If the game was previously installed on the Deck, but then it was removed, the previous appid stays in the `screenshots.vdf` and the script tries to launch the wrong game. (Might need to collect all appids from the `screenshots.vdf` file and try to launch the game with each of them OR try to find a way to validate the appid)
- No app in the `screenshots.vdf` file on the first ever launch :( (Can we force steam somwhow to refresh that file?)

## Contributing

Any help is appreciated. Feel free to open a pull request or an issue.