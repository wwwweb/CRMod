# 🧙 Chaos Reborn — Community Patch 1.14

> *Because 1.13 was never the end.*

Snapshot Games may have laid down their staffs, but the arcane fires have not gone cold. With the magic of artificial intelligence and the stubbornness of a Chaos wizard who just won't disbelieve, **Blubber** proudly presents ten client-side mods for [Chaos Reborn](https://store.steampowered.com/app/319050/Chaos_Reborn/), requiring no server-side sorcery.

*May your casts be true, your illusions undetected, and your Gooey Blob land exactly where intended.* 🧙

---

## ✨ Mods v1.4.0

### 🗺️ Map Preview `[F9]`

A wise wizard never steps onto a battlefield they haven't scouted.

See a preview image of the current map right in the lobby before a single spell is committed. Toggle with **F9**, resize with **S/M/L** buttons.

---

### ⚔️ Map Setup `[F10]`

The art of war begins before the first creature is summoned.

For **6-player lobby creators**: instantly assigns balanced teams for **3v3**, **2v2v2** or **2v4** with a single click. Appears automatically when you open a 6-player lobby. Law and Chaos, brought into balance, at least for the setup. Toggle with **F10**.

---

### 🎨 Wizard Skins `[F4]`

Let your aura speak for itself.

Lets you set the displayed skin for any wizard in the game, independently for each one. The skin is only visible on your own screen; other players see your and their own skins as usual. Use **F4** to toggle the overlay, **↑/↓** to select a wizard, **←/→** to cycle through skins (Apprentice → Forgemaster → Wizard Lord → Wizard King → Demigod → God).

A `*` next to a wizard's name indicates the displayed skin differs from their actual skin.

---

### 💬 Chat Commands

Every great battle deserves a chronicle. Adds commands for reporting to in-game chat.

| Command | Effect |
|---|---|
| `/report [format]` | Outputs a match report at battle end. Visible only to you, or to all players |
| `/reportdiscord [format]` | Same, but also sends the report to Discord (needs setup) |

Reports are fully customizable: define multiple named formats in the config file, each with its own template, webhook URL, and visibility setting (`local` or `all`). Set a format to `local` to keep reports off the shared chat entirely — useful when you just want a personal log or a Discord post without spamming other players. See [Setting up own report formats and Discord connection](#️-setting-up-own-report-formats-and-discord-connection-optional) below.

---

### 📜 Async Creator

Ever wanted to start with a solely disbelieve deck in async?

In live lobbies, Reward and Taboo controls are available directly in the UI. In **async lobbies**, these controls are missing entirely. This mod fills that gap via lobby chat commands.

As the server does not store the configuration, all settings are reconstructed from chat history when you reopen the lobby. The mod only needs to be installed by the lobby creator. Other players can join without it.

| Command (Lobby Chat) | Effect |
|---|---|
| `/reward none\|gold\|crystals` | Set the reward for the winner |
| `/taboo <slot(s)> <taboo(s)>` | Sets taboos for one or more slots (additive) |
| `/status` | Show reward + taboos for all slots locally |
| `/share` | Show reward + taboos for all in lobby chat |
| `/help` | List available commands |

> ⚠️ Taboos apply to deck cards only. The wizard's Mega Spell (staff ability) cannot be restricted.

---

### 🔖 Taboo Display

Know thy enemy's constraints.

When you select an opponent's wizard during battle, their active taboos are shown in the top-left panel at the same spot your own taboos normally appear. Deselecting restores your own taboo display. No configuration needed. Kind of a companion mod to Async Creator taboos, but can also be used for live games.

---

### 🔀 Equip Sort

A tidy spellbook is a powerful spellbook.

Sorts your equipment configurations alphabetically — no more hunting through an unsorted list. Click the **Name**, **Staff**, or **Bodygear** column headers on the equipping screen to sort by that column (click again to reverse). The selected configuration stays highlighted after sorting. Also keeps the equipment dropdown in lobbies sorted alphabetically at all times. No configuration needed.

---

### 📍 Team Ping `[Ctrl+P]`

Point your allies where the magic happens.

Right-click any tile during battle to place a ping marker visible to your team. Cycle through modes with **Ctrl+P**: in team games **Off → Team → All**, in FFA **Off → All → Private**. One marker per player, automatically expires after one round. Right-click an existing marker in Off mode to dismiss it locally.

> ⚠️ Only players that have the Team Ping mod installed can see the pings. The ping is transmitted via in-game chat. For other mod users, this is invisible. For players without the mod, a short `CRMod.Ping` message appears in chat.

> ⚠️ Team Ping is hard to test for a single wizard, so it is declared experimental and needs testing.

---

### 🏔️ Height Map `[F3]`

Because knowing the terrain is half the battle.

Displays the total height of every tile as an overlay label during battle. Useful for evaluating attack and movement options at a glance. Toggle with **F3**.

---

### 🔧 Async Lobby Fix

Fixes a bug in the base game where joining your own async custom lobby causes many UI elements (including wizard names) to be invisible. No configuration needed, just drop it in and forget about it.

---

## ⚙️ Requirements

- **Chaos Reborn** (both 32/64 bit versions are supported)
- **BepInEx 5.4.x** — download link below

> ⚠️ BepInEx **5.4.x only** — version 6 is not compatible.

---

## ⚙️ Installation

1. Download **[BepInEx 5.4.23.5](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.23.5/)** and extract it into your Chaos Reborn folder (the folder where Steam or another manager installed the game, e.g. `C:\SteamLibrary\steamapps\common\ChaosReborn`):
   - **Windows (Steam, 64 bit):** use `win_x64` (the zip under Assets)
   - **Windows (GOG, 32 bit):** use `win_x86`
   - **Mac:** use `macos_universal` — should work but untested

   > ⚠️ Make sure you download the BepInEx version that matches your Chaos Reborn installation (32/64 bit). In your Chaos Reborn folder you will find either `ChaosRebornWin64.exe` or `ChaosRebornWin32.exe`.
2. Download **`CRMods-v1.4.1.zip`** from the [Releases page](https://github.com/wwwweb/CRMod/releases) and extract it into the same folder. The files will drop into the right places automatically
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
        plugins\
            CRMod.AsyncCreator.dll
            CRMod.AsyncLobbyFix.dll
            CRMod.ChatCommand.dll
            CRMod.EquipSort.dll
            CRMod.HeightMap.dll
            CRMod.MapPreview.dll
            CRMod.MapSetup.dll
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

---

## ⚙️ Setting up own report formats and Discord connection (optional)

The chat command mod supports multiple configurable report formats. Reports can optionally be sent to Discord.

1. Launch the game once with `CRMod.ChatCommand.dll` in place, then close it; this creates the config file `BepInEx\config\CRMod.ChatCommand.cfg` in your Chaos Reborn folder
2. Open `BepInEx\config\CRMod.ChatCommand.cfg` in any text editor. It provides two pre-defined report formats and a help to add your own format
3. If you want to connect to Discord, in your Discord server: **Server Settings → Integrations → Webhooks → New Webhook**
4. Copy the Webhook URL and set it in the config file
   ```ini
   WebhookUrl=https://discord.com/api/webhooks/...
   ```
5. Save the file and restart the game (or type `/reloadconfig` in in-game chat)

---

## 🗑️ Uninstall

To remove all mods, just remove the `BepInEx` folder and `winhttp.dll` from your Chaos Reborn folder. To remove single mods, remove the according dll from `BepInEx/plugins`.

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
