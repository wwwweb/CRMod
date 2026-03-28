# 🧙 Chaos Reborn — Community Patch 1.14

> *Because 1.13 was never the end.*

Snapshot Games may have laid down their staffs, but the arcane fires have not gone cold. With the magic of artificial intelligence and the stubbornness of a Chaos wizard who just won't disbelieve, **Blubber** proudly presents four client-side mods for [Chaos Reborn](https://store.steampowered.com/app/319050/Chaos_Reborn/), requiring no server-side sorcery.

*May your casts be true, your illusions undetected, and your Gooey Blob land exactly where intended.* 🧙

---

## ✨ Mods

### 🗺️ Map Preview `[F9]`

A wise wizard never steps onto a battlefield they haven't scouted.

See a preview image of the current map right in the lobby before a single spell is committed. Toggle with **F9**, resize with **S/M/L** buttons.

---

### ⚔️ Map Setup `[F10]`

The art of war begins before the first creature is summoned.

For **6-player lobby creators**: instantly assigns balanced teams for **3v3**, **2v2v2** or **2v4** with a single click. Appears automatically when you open a 6-player lobby. Law and Chaos, brought into balance, at least for the setup. Toggle with **F10**.

---

### 💬 Chat Commands

Every great battle deserves a chronicle. Adds commands for reporting to in-game chat.

| Command | Effect |
|---|---|
| `/report` | Summons a full kill log and final standings at match end, copied to clipboard for manual paste, e.g. at Discord |
| `/reportdiscord` | Same, but dispatches the scroll directly to a Discord webhook of your choice |

---

### 🔧 Async Lobby Fix

Fixes a bug in the base game where joining your own async custom lobby causes many UI elements (including wizard names) to be invisible. No configuration needed, just drop it in and forget about it. (Only briefly tested.)

---

## ⚙️ Requirements

- **Chaos Reborn** via Steam
- **BepInEx 5.4.x** — download link below

> ⚠️ BepInEx **5.4.x only** — version 6 is not compatible.

---

## ⚙️ Installation

1. Download **[BepInEx 5.4.23.5](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.23.5/)** and extract it into your Chaos Reborn folder (the folder where Steam or another manager installed the game, e.g. `C:\SteamLibrary\steamapps\common\ChaosReborn`):
   - **Windows:** use `win_x64` (the zip under Assets)
   - **Mac:** use `macos_x64` — should work but untested
2. Download **`CRMods_v1.0.0.zip`** from the [Releases page](https://github.com/wwwweb/CRMod/releases) and extract it into the same folder. The files will drop into the right places automatically
3. Launch the game once, then close it. BepInEx will finalize its setup
4. Launch the game again. Now the mods are active

Your folder structure should look like this afterwards:
```
ChaosReborn\
    ChaosRebornWin64.exe
    winhttp.dll                        ← added by BepInEx
    BepInEx\
        plugins\
            CRMod.ChatCommand.dll
            CRMod.MapSetup.dll
            CRMod.MapPreview.dll
            CRMod.AsyncLobbyFix.dll
        config\
            maps\
                2_Twin_Lake.jpg
                4_Equilibrarium.jpg
                ... (all map images)
```

> Not sure if BepInEx loaded? Check `BepInEx\logs\LogOutput.log`. The mod names should appear there.

---

## ⚙️ Setting up `/reportdiscord` (optional)

1. In your Discord server: **Server Settings → Integrations → Webhooks → New Webhook**
2. Pick a channel and copy the Webhook URL
3. Launch the game once with `CRMod.ChatCommand.dll` in place, then close it; this creates the config file
4. Open `BepInEx\config\CRMod.ChatCommand.cfg` in any text editor and paste your URL:
   ```ini
   DiscordWebhookUrl = https://discord.com/api/webhooks/...
   ```
5. Save the file and restart the game

---

## 🗑️ Uninstall

To remove all mods, just remove the `BepInEx` folder and `winhttp.dll` from your Chaos Reborn folder. To remove single mods, remove the according dll from `BepInEx/plugins`.

---

## 💡 Got a mod idea?

Rule of thumb: Mods can **read and display** most of what the game sends to your client, and **automate** most of what you can click yourself — lobby setup, chat commands, UI interactions. What's out of reach is anything the **server decides**: cast results, combat outcomes, balance, new cards.

Ideas and suggestions are welcome. Open an issue or drop a message on Discord.

---

## Disclaimer

This is private fan work. No guarantee that it works, no warranty that it doesn't break something. See the License for details.

Tested under Windows 11 with the Steam version of Chaos Reborn.

---

## 📜 License

[MIT](LICENSE) — © 2026 Blubber
