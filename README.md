# 🧙 Chaos Reborn — Community Patch 1.14

> *Because 1.13 was never the end.*

Snapshot Games may have laid down their staffs, but the arcane fires have not gone cold. With the magic of artificial intelligence and the stubbornness of a Chaos wizard who just won't disbelieve, **Blubber** proudly presents eighteen client-side mods for [Chaos Reborn](https://store.steampowered.com/app/319050/Chaos_Reborn/), requiring no server-side sorcery.

*May your casts be true, your illusions undetected, and your Gooey Blob land exactly where intended.* 🧙

---

## ✨ Mods v1.8.4

### 📜 Async Creator `[F8]`

Ever tried to run a taboo match in async, only to find the controls missing?

In live lobbies, Reward and Taboo controls are available directly in the UI. In **async lobbies**, these controls are missing entirely. This mod fills that gap. Taboos and rewards can be set and viewed by using an enhanced UI that is enabled by pressing **F8** on the async games lobby screen. Alternatively, chat commands can be used for configuration without using the enhanced UI.

As the server does not store the configuration, all settings are reconstructed from chat history when you reopen the lobby. The mod only needs to be installed by the lobby creator. Other players can join without it. If you use the UI for setting taboos, do not forget to post the setting by `/share`, so non-mod users know about them.

| Command (Lobby Chat) | Effect |
|---|---|
| `/reward none\|gold\|crystals` | Set the reward for the winner |
| `/taboo <slot(s)> <taboo(s)>` | Sets taboos for one or more slots (additive) |
| `/status` | Show reward + taboos for all slots locally |
| `/share` | Show reward + taboos for all in lobby chat |
| `/help` | List available commands |

> ⚠️ Taboos apply to deck cards only. The wizard's Mega Spell (staff ability) cannot be restricted.

> `/status`, `/share`, `/help` are available to all lobby participants. Configuration commands (`/reward`, `/taboo`) are creator only.

---

### 🔧 Async Lobby Fix

Fixes a bug in the base game where UI elements (including wizard names) can become invisible in async custom lobbies. No configuration needed, just drop it in and forget about it.

---

### ⏳ Async Ready Status `[F5]`
 
See at a glance how many are ready to rumble.
 
On the custom games screen, this mod enhances the game list by changing the display content of some columns. The lobby name is shown instead of a raw battle ID. Press **F5** to scan all fully booked lobbies for their ready status. Your own ready status is shown with ✓ or ✗ in the turn column.

> ⚠️ Note: F5 works by automatically entering and exiting each lobby to gather ready information. This generates no more server requests than a wizard normally generates by entering each lobby, but in quicker succession. Please don't spam it.

---

### 🎭 Battle Emotes
 
Say it with pixels.
 
Trigger pixelart animations over the battle field through lobby chat. Type `!gg`, `!wp`, `!glhf`, `!mb` and many more to drop an animated emote; combine several in a single message (`!gg !wp`) to play them together. Use `!help` in battle chat to see the full list of available emotes.
 
| Command (Battle Chat) | Effect |
|---|---|
| `!<emote name>` | Play the emote animation |
| `!moon <text>` | CR moon with a text overlay |
| `!replay` | Replay this session's emotes locally |
| `!help` | Show the full list of available emotes |
 
If you join an async battle after opponents have already played emotes since your last turn, they are replayed in sequence once you enter.
 
> ⚠️ Only players with the Battle Emotes mod installed see the animations. For everyone else, the command text (`!gg`) appears in chat as a normal message.

---
 
### 🗂️ Chaos Manager
 
One panel to rule them all.
 
A mod manager button on the login screen opens a list of all installed CRMod mods. Enable or disable individual mods with a checkbox; the header checkbox toggles all at once. Disabled mods are moved out of `BepInEx/plugins/` on the next game launch and re-enabled when you check them again.

> ⚠️ `CRMod.ChaosManager.dll` must be placed in **both** `BepInEx/plugins/` and `BepInEx/patchers/` to work correctly. The zip from the Releases page handles this automatically.

---

### 💬 Chat Commands

Every great battle deserves a chronicle. Adds commands for reporting to in-game chat.

| Command | Effect |
|---|---|
| `/report [format]` | Outputs a match report at battle end. Visible only to you, or to all players |
| `/reportdiscord [format]` | Same, but also sends the report to Discord (needs setup) |

Works out of the box. Optionally, reports are fully customizable: define multiple named formats in the config file, each with its own template, webhook URL, and visibility setting (`local` or `all`). Set a format to `local` to keep reports off the shared chat entirely — useful when you just want a personal log or a Discord post without spamming other players. See [Setting up own report formats and Discord connection](#️-setting-up-own-report-formats-and-discord-connection-optional) below.

---

### 🔀 Equip Sort

A tidy spellbook is a powerful spellbook.

Sorts your equipment configurations alphabetically — no more hunting through an unsorted list. Click the **Name**, **Staff**, or **Bodygear** column headers on the equipping screen to sort by that column (click again to reverse). Click on Staff column header multiple times to sort by **Mega Spell**. The selected configuration stays highlighted after sorting. Also keeps the equipment dropdown in lobbies sorted alphabetically at all times.

---

### 🏔️ Height Map `[F3]`

Because knowing the terrain is half the battle.

Displays the total height of every tile as an overlay label during battle. Useful for evaluating attack and movement options at a glance. Toggle with **F3**.

---
 
### 👗 Infinite Wardrobe
 
Your equipment, unlimited.
 
The game limits how many equipment configurations you can store on the server. Infinite Wardrobe lifts that ceiling by saving additional configurations locally. Local configs appear in **yellow** in the configuration list; configs with missing items appear in **red**.
 
A **+** button on the equipping screen saves a local copy of the current configuration. Click a local config to load it back to the server, delete it, or rename it. When you want to promote a local config to the server, the mod handles the upload automatically. If the server is full, it offers to save an existing server config locally so its slot can be reused for the upload.
 
Local configs are stored in `BepInEx/config/CRMod.InfiniteWardrobe.json`.

---
 
### 🔭 Map Cam `[Ctrl+Scroll]`
 
See the bigger picture — or zoom in for the kill.
 
Extends the camera zoom range beyond the game's defaults: hold **Ctrl** and scroll to zoom further in or out. Release Ctrl in the normal zoom range to snap back to standard limits; release it while zoomed beyond the normal range to stay at the current level.

---

### 🗺️ Map Preview `[F9]`

A wise wizard never steps onto a battlefield they haven't scouted.

See a preview image of the current map right in the lobby before a single spell is committed. Toggle with **F9**, resize with **S/M/L/Max** buttons.

---

### ⚔️ Map Setup `[F10]`

The art of war begins before the first creature is summoned.

For **6-player lobby creators**: instantly assigns balanced teams for **3v3**, **2v2v2** or **2v4** with a single click. Appears automatically when you open a 6-player lobby. Law and Chaos, brought into balance, at least for the setup. Toggle with **F10**.

---
 
### 🎲 Random Equip
 
Fortune favors the bold — and the unprepared.
 
Adds a **Random Equip** button to the equipping screen. It rolls a random Staff, Gear, and all Talismans from your inventory. **Roll again** re-rolls everything; **Cancel** restores your configuration from before the first roll.

---
 
### 🎬 Replay
 
Every great duel deserves to be remembered.
 
Export any finished battle to a `.chaos` file with `/export [name]` in the battle chat. Replays are listed on the login screen and can be launched with a single click.
 
| Command (Battle Chat) | Effect |
|---|---|
| `/export [name]` | Saves the finished battle as a `.chaos` file |
 
Replay files are stored in `BepInEx/config/replays/`. Replay files are small (about 10 KBytes per file) and can be manually shared amongst wizards.
 
> ⚠️ The `/export` command is only available after the battle has ended.

---

### 🪄 Setup Wizard `[F6]`

Batch lobby setup, tamed.

Press **F6** on the custom games screen to open the Setup Wizard, a file-driven lobby manager. Each `.setupwizard` file in `BepInEx/config/setupwizard/` describes a set of lobbies to create, including slots, teams, rewards, taboos, and AI or player invites. The **+ New template** button generates a ready-to-edit template file with format reference and examples.

Lobbies move through a clear lifecycle: **idle → todo → waiting → ready → started**, with **ignored** and **archived** for housekeeping. The UI shows live status, flags discrepancies between a running lobby and its confuration in file, and lets you sync individual lobbies or all at once. A search field and filter pills keep large game series setups manageable.

Once a lobby is configured and all reward/taboo settings have been applied, the **▶ Start game** button becomes available. Setup Wizard coordinates with Async Creator automatically: rewards and taboos defined by Async Creator chat commands in the `.setupwizard` file are applied to the lobby.

---

### 🔖 Taboo Display

Know thy enemy's constraints.

When you select an opponent's wizard during battle, their active taboos are shown in the top-left panel at the same spot your own taboos normally appear. Deselecting restores your own taboo display. Kind of a companion mod to Async Creator taboos, but can also be used for live games.

---

### 📍 Team Ping `[Ctrl+P]`

Point your allies where the magic happens.

Right-click any tile during battle to place a ping marker visible to your team. Cycle through modes with **Ctrl+P**: in team games **Off → Team → All**, in FFA **Off → All → Private**. One marker per player, automatically expires after one round. Right-click an existing marker in Off mode to dismiss it locally.

> ⚠️ Only players that have the Team Ping mod installed can see the pings. The ping is transmitted via in-game chat. For other mod users, this is invisible. For players without the mod, a short `CRMod.Ping` message appears in chat.

> ⚠️ Team Ping is hard to test for a single wizard, so it is declared experimental and needs testing.

---

### 🎨 Wizard Skins `[F4]`

Let your aura speak for itself.

Lets you set the displayed skin for any wizard in the game, independently for each one. The skin is only visible on your own screen; other players see your and their own skins as usual. Use **F4** to toggle the overlay, **↑/↓** to select a wizard, **←/→** to cycle through skins (Apprentice → Forgemaster → Wizard Lord → Wizard King → Demigod → God).

A `*` next to a wizard's name indicates the displayed skin differs from their actual skin.

🎄 Toggle **Winter Mode** with **W** in the F4 overlay to place festive hats on wizards and selected creatures.
> Winter Mode is not yet complete. More seasonal elements may be added in future updates.

🐉 Toggle **Dragon Skins** with **D** in the F4 overlay to summon Emerald and Ruby Dragons! The secret to their appearance, though, is yours to uncover through arcane studies.

---

## ⌨️ Keyboard Reference

A quick overview of all mod key bindings is available [here](https://wwwweb.github.io/CRMod/CRModKeyboardReference.html).

---

## 📋 Requirements

- **Chaos Reborn** (both 32/64 bit versions are supported)
- **BepInEx 5.4.x** — download link below

> ⚠️ BepInEx **5.4.x only** — version 6 is not compatible.

---

## 🔧 Installation

1. Download **[BepInEx 5.4.23.5](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.23.5/)** and extract it into your Chaos Reborn folder (the folder where Steam or another manager installed the game, e.g. `C:\SteamLibrary\steamapps\common\ChaosReborn`):
   - **Windows (Steam, 64 bit):** use `win_x64` (the zip under Assets)
   - **Windows (GOG, 32 bit):** use `win_x86`
   - **Linux/Mac:** see [below](#linux--mac)

   > ⚠️ Make sure you download the BepInEx version that matches your Chaos Reborn installation (32/64 bit). In your Chaos Reborn folder you will find either `ChaosRebornWin64.exe` or `ChaosRebornWin32.exe`.
2. Download **`CRMod-v1.8.4.zip`** from the [Releases page](https://github.com/wwwweb/CRMod/releases) and extract it into the same folder. The files will drop into the right places automatically
   - 🧙 Advanced wizardry: Those who know what they are doing may alternatively download individual mod files or clone the repository directly into their Chaos Reborn folder.
3. Launch the game once, then close it. BepInEx will finalize its setup
4. Launch the game again. Now the mods are active

If you are updating from a previous version of CRMod, steps 1 and 3 can be omitted.

Your folder structure should look like this afterwards:
```
ChaosReborn\
    ChaosRebornWin64.exe
    winhttp.dll                        ← added by BepInEx
    BepInEx\
        patchers\                      ← from here on added by CRMod
            CRMod.ChaosManager.dll
        plugins\
            CRMod.AsyncCreator.dll
            CRMod.AsyncLobbyFix.dll
            CRMod.AsyncReadyStatus.dll
            CRMod.BattleEmotes.dll
            CRMod.ChaosManager.dll
            CRMod.ChatCommand.dll
            CRMod.EquipSort.dll
            CRMod.HeightMap.dll
            CRMod.InfiniteWardrobe.dll
            CRMod.MapCam.dll
            CRMod.MapPreview.dll
            CRMod.MapSetup.dll
            CRMod.RandomEquip.dll
            CRMod.Replay.dll
            CRMod.SetupWizard.dll
            CRMod.Skin.dll
            CRMod.TabooDisplay.dll
            CRMod.TeamPing.dll
        config\
            maps\
                2_Backbone.jpg
                ... (all map images)
                6_Triple_Double.jpg
```

> Not sure if BepInEx loaded? Check `BepInEx\LogOutput.log`. The mod names should appear there.

### Linux / Mac

Linux and macOS are supported by BepInEx, but step 1 of the installation above needs some extra steps. Chaos Reborn is usually run as a Windows game through a compatibility layer (Proton/Crossover/...), so the Windows version of BepInEx is used, and the game has to be launched with an additional command line parameter. The exact steps depend on your setup and are easy to find via a web search. I have not tested this myself, so please look up the exact parameter for your platform.

Untested on Linux/Mac - feedback welcome.

---

## 📡 Setting up own report formats and Discord connection (optional)

The chat command mod supports multiple configurable report formats. Reports can optionally be sent to Discord.

1. Launch the game once with `CRMod.ChatCommand.dll` in place, then close it; this creates the config file `BepInEx\config\CRMod.ChatCommand.cfg` in your Chaos Reborn folder
2. Open `BepInEx\config\CRMod.ChatCommand.cfg` in any text editor. It provides two pre-defined report formats and a help to add your own format
3. If you want to connect to Discord, in your Discord server: **Server Settings → Integrations → Webhooks → New Webhook**
4. Copy the Webhook URL and set it in the config file
   ```ini
   WebhookUrl=https://discord.com/api/webhooks/...
   ```
5. Save the file and restart the game (or type `/reloadconfig` in in-game chat)
6. Test the connection by sending a report. Type `/reportdiscord` (with optional template name from the config file where you set the Webhook URL) in in-game chat. The report should appear in the Discord channel you used in step 3.

---

## 🗑️ Uninstall

To enable or disable individual mods without uninstalling, use the Chaos Manager on the login screen. To remove all mods entirely, remove the `BepInEx` folder and `winhttp.dll` from your Chaos Reborn folder. To remove a single mod permanently, delete the according dll from `BepInEx/plugins`.

---

## 💡 Got a mod idea?

Rule of thumb: Mods can **read and display** most of what the game sends to your client, and **automate** most of what you can click yourself: lobby setup, chat commands, UI interactions. What's out of reach is anything the **server decides**: cast results, combat outcomes, balance, new cards.

Ideas and suggestions are welcome. Open an issue or drop a message on Discord.

---

## Disclaimer

This is private fan work. No guarantee that it works, no warranty that it doesn't break something. See the License for details.

Tested under Windows 11 with the Steam version (64 bit) and GOG version (32 bit) of Chaos Reborn.

---

## 📜 License

[MIT](LICENSE) — © 2026 Blubber
