# 🧙 Chaos Reborn — Community Patch 1.14

> *Because 1.13 was never the end.*

Snapshot Games may have laid down their staffs, but the arcane fires have not gone cold. With the blessing of artificial intelligence and the stubbornness of a Chaos wizard who just won't disbelieve, **Blubber** proudly presents four client-side mods for [Chaos Reborn](https://store.steampowered.com/app/319050/Chaos_Reborn/), requiring no server-side sorcery.

*May your casts be true, your illusions undetected, and your Gooey Blob land exactly where intended.* 🧙

---

## ✨ Mods

### 🗺️ Map Preview `[F9]`

A wise wizard never steps onto a battlefield they haven't scouted.

See a preview image of the current map right in the lobby — before a single spell is committed. Toggle with **F9**, resize with **S/M/L** buttons. Knowledge is power.

---

### ⚔️ Map Setup `[F10]`

The art of war begins before the first creature is summoned.

For **6-player lobby creators**: instantly assigns balanced teams for **3v3**, **2v2v2** or **2v4** with a single click. Appears automatically when you open a 6-player lobby. No more pre-game negotiations. Law and Chaos, brought into balance, at least for the setup.

---

### 💬 Chat Commands

Every great battle deserves a chronicle.

| Command | Effect |
|---|---|
| `/report` | Summons a full kill log and final standings at match end, copied to clipboard |
| `/reportdiscord` | Same, but dispatches the scroll directly to a Discord webhook of your choice |

---

### 🔧 Async Lobby Fix

Fixes a bug in the base game where joining your own async custom lobby causes many UI elements (including wizard names) to be invisible. No configuration needed — just drop it in and forget about it.

---

## ⚙️ Requirements

- **Chaos Reborn** via Steam
- **BepInEx 5.4.x** — download link below

> ⚠️ BepInEx **5.4.x only** — version 6 is not compatible.

---

## ⚙️ Installation

1. Download **[BepInEx 5.4.23.5 (win_x64)](https://github.com/BepInEx/BepInEx/releases/download/v5.4.23.5/)** and extract it into your Chaos Reborn folder
2. Download **`CRMods_v1.0.0.zip`** from the [Releases page](../../releases) and extract it into the same folder — the files will drop into the right places automatically
3. Launch the game once, then close it — BepInEx will finalize its setup
4. Launch the game again — the mods are active

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

> Not sure if BepInEx loaded? Check `BepInEx\logs\LogOutput.log` — your mod names should appear there.

---

## ⚙️ Setting up `/reportdiscord` (optional if you want to have the map preview)

1. In your Discord server: **Server Settings → Integrations → Webhooks → New Webhook**
2. Pick a channel and copy the Webhook URL
3. Launch the game once with `CRMod.ChatCommand.dll` installed, then close it; this creates the config file
4. Open `BepInEx\config\CRMod.ChatCommand.cfg` in any text editor and paste your URL:
   ```ini
   DiscordWebhookUrl = https://discord.com/api/webhooks/...
   ```
5. Save the file and restart the game

---

## 💡 Got a mod idea?

Rule of thumb: Mods can **read and display** most of the things the game sends to your client (player data, lobby info, match events) and show it in new overlays. What's out of reach is anything the **server decides**: cast results, combat outcomes, balance, new cards.

Ideas and suggestions are welcome. Open an issue or drop a message on Discord.

---

## 📜 License

[MIT](LICENSE) — © 2026 Blubber
