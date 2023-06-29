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

## Known issues

- It seems like the Steam Overlay is not working, if you launch the game while the Deck is in Desktop mode.

## Contributing

Any help is appreciated. Feel free to open a pull request or an issue.