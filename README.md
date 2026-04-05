<b>NOTE: Original guide is from MrRubberDucky [(Wayback Machine link)](https://web.archive.org/web/20251230122148/https://gist.rubberverse.xyz/MrRubberDucky/HMM).</b><br> 
I'm posting this here for backup purposes. I also added some bits of information to make the guide as complete as possible.<br><br>

## HMM Custom Path

Some games won't get detected by HedgeModManager properly if they're in custom directories. It's annoying, directory look-ups seem to be hardcoded and apparently you have to edit registry keys to make it possible.

If it seems daunting, don't worry it's not. It's just mod developers sometimes feel like creating a 'up your own ass' approach with their modding frameworks because it's easy to forget not everyone is an developer.

1. Run HedgeModManager.exe once
2. Open Regedit (Press `Windows Key + R` and type in 'regedit' then press Enter)
3. Navigate to `HKEY_CURRENT_USER\Software\HEDGEMM`
4. Double-click on `CustomGames`
5. Paste in the full game path (Look at "Constructing game path" below)
6. Launch HMM

## Constructing game path

Now here's the tricky part. At some point, dev updated HMM to change what registry key is required and what arguments it needs.
Don't worry, this part is also relatively easy to figure out.

Note down the full path of your game, it will be something like this (excluding the executable):

`C:\Games\Sonic Frontiers`

Great, we have full path to our game! Now let's add the executable at the end.

`C:\Games\Sonic Frontiers\SonicFrontiers.exe`

Splendid. We have almost constructed whole path needed for HMM to recognize our game. We are just missing one vital component.
HMM expects extra two entries at the end like so: `|GameName|Platform`. This makes HMM recognize the game properly.

Possible `GameName` values:
- `SonicFrontiers`
- `SonicLostWorld`
- `SonicColorsUltimate`
- `SonicOrigins`
- `ShadowGenerations`
- `UnleashedRecompiled`
- `PuyoPuyoTetris2`
- `Tokyo2020`

<br>

Possible `Platform` values:
- `Steam`
- `EGM`
- `None`
<br>

Now that we know that, let's add the remaining bits.

`C:\Games\Sonic Frontiers\SonicFrontiers.exe|SonicFrontiers|Steam`

That's about it! Now paste that whole path into the `Value` portion and click `OK`. You can now close Registry editor and launch HMM.

<br>

If you want to add more games, add a semicolon (;) between different paths (example: `GameDir1|GameName1|GameType1;GameDir2|GameName2|GameType2;GameDir3|GameName3|GameType3`).
