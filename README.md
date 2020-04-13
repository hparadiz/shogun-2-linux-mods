# How to Enable Mods in Linux
1. Find your pack files.
2. Go to the game directory and run `ln -s` for each mod pack.

    Example:
    ```
    $ cd ~/.local/share/Steam/steamapps/common/Total War SHOGUN 2/share/data/data
    $ ln -s /home/akujin/.local/share/Steam/userdata/6722702/ugc/referenced/46502257628106212/mods/better_maps.pack
    $ ln -s /home/akujin/.local/share/Steam/userdata/6722702/ugc/referenced/46502257624024698/mods/better_maps2.pack
    $ ln -s /home/akujin/.local/share/Steam/userdata/6722702/ugc/referenced/46502257627167208/mods/better_maps3.pack
    ```
3. Open `~/.local/share/feral-interactive/Total War SHOGUN 2/VFS/Local/scripts/preferences.script.txt` with an editor that can handle UTF-16 LE. I used VS Code for this.
4. Add a line for every mod you want like so:

    Example:
    ```
    mod better_maps2.pack;
    mod better_maps3.pack;
    mod better_maps.pack;
    mod ai_occupation_resistance.pack;
    mod expanded.pack;
    ```

5. `chmod -w ~/.local/share/feral-interactive/Total War SHOGUN 2/VFS/Local/scripts/preferences.script.txt` to prevent the game from overwriting your mod preferences. **Caution: you will be required to edit this file to manage your graphics settings moving forward.**


### Reference
#### How to Find Mod Pack Files
`~/.steam/steam/userdata/[steamUserID]/ugc/referenced/`

Use:
`locate ugc/referenced | grep pack`

#### Steam Game Directory
`~/.local/share/Steam/steamapps/common/Total War SHOGUN 2/share/data/data`

#### Location of `preferences.script.txt`
`~/.local/share/feral-interactive/Total War SHOGUN 2/VFS/Local/scripts/preferences.script.txt`