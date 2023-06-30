# Hodi's unofficial steam-client-run-game fix for Steam Deck (Unreal Engine 5)

Currently, launching a game from the Unreal Editor on the Steam Deck does not work. This is because the `steam-client-run-game` script is missing from the `Engine/Build/SteamDeck` folder. 

I tried to fix this issue by re-creating the missing script. This is a temporary fix until Epic Games adds the script to the Engine. Please visit this [thread](https://forums.unrealengine.com/t/launching-on-steam-deck-does-not-work-on-ue-5-1/737750) for more information.

Tested with Unreal Engine 5.2.1

## 🚀 How to use

1. Download the latest release from [here](https://github.com/dhodvogner/steam-client-run-game/archive/refs/heads/main.zip)
2. Extract the archive to a folder of your choice
3. Create a folder called `SteamDeck` in your Engine's installation `Engine/Build` folder (e.g. `C:\Program Files\Epic Games\UE_5.2\Engine\Build\SteamDeck`)
4. Copy the `steam-client-run-game` file and `vdf` folder with all of its content to the newly created `SteamDeck` folder
5. Launch the game from the Unreal Editor as described [here](https://docs.unrealengine.com/5.2/en-US/steam-deck-quick-start-in-unreal-engine/)
6. **When you launch a game for the first time, it won't work.** You need to navigate on your Deck to Steam -> Library -> Non-Steam Games and launch the game from there. This will register the new appid in the `screenshots.vdf` file. After that, you can launch the game from the Unreal Editor.

## 🪲 Known issues

### No appid in the screenshots.vdf file on the first launch

When launching the game at the first time from the editor, the `screenshots.vdf` won't be updated with the appid.
After you launch the shortcut from the Non-Steam Games section on the Deck, the `screenshots.vdf` will be updated and you can launch the game from the editor.

Ideas on how to fix this:
- Force steam somehow to refresh that file?
- Try to generate the appid from the game's name? (https://gaming.stackexchange.com/questions/386882/how-do-i-find-the-appid-for-a-non-steam-game-on-steam)

### If the game was previously installed on the Deck, but then it was removed, the previous appid stays in the screenshots.vdf file

You can manually remove the entry from the file. The file is located in `/home/deck/.steam/steam/userdata/<your steam id>/760/screenshots.vdf`

Ideas on how to fix this:
- Collect all appids from the `screenshots.vdf` file and try to launch the game with each of them
- Try to find a way to validate the appid

### Steam Overlay is not working, if you launch the game while the Deck is in Desktop mode

I'm not sure if this is an issue with the script or not.

## 🤝 Contributing

Any help is appreciated. Feel free to open a pull request or an issue.