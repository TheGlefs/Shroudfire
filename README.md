# Shroudfire

This repository contains the website for [shroudfire.com](https://shroudfire.com), the home of Shroudfire for Counter-Strike 2 and Counter-Strike: Source.

Shroudfire is an asymmetric combat mode: **Invisant** (*invisible assailants*) hunt with invisibility and knives, while **Armitive** (*armed fugitives*) fight back with firearms or survive until time runs out. Roles rotate each round, and progression persists between sessions.

## Game editions

- [Shroudfire for Counter-Strike 2](https://github.com/TheGlefs/Shroudfire-CS2) - The native C++ MetaMod:Source plugin for Counter-Strike 2.
- [Shroudfire for Counter-Strike: Source](https://github.com/TheGlefs/Shroudfire-CSS) - The SourceMod plugin for Counter-Strike: Source.

Visit the game repositories for downloads, installation instructions, gameplay guides, upgrade details, server settings, and source code.

## How to play

This guide covers Counter-Strike 2. See the [Counter-Strike: Source README](https://github.com/TheGlefs/Shroudfire-CSS#how-to-play) for edition-specific details.

**All values below are defaults and can be adjusted with server cvars.**

Rounds last **2 minutes**, with a roster that scales toward **4 Armitive per Invisant**.

### Invisant

You're invisible and armed only with a knife. Armitive cannot hear your footsteps. **Kill all Armitive to win.**

- Track living Armitive through walls and take no fall damage.
- Your knife hits in a **60° cone**, reaches **72 units**, and deals **50–75 raw damage**.
- Knife attacks run at **66% of normal speed**, with **no backstab bonus**.

**Starvation:** Once 60 seconds of live play have elapsed, 45 seconds without dealing or taking damage triggers starvation. You lose **1 HP/s**, rising to **3 HP/s** after 20 seconds of continuous starvation. If it starts at full health with 1:00 left, you'll die with roughly 0:15 left unless combat resets it.

### Armitive

Find the Invisant using firearms, blood, and contact. **Armitive win if anyone survives until time runs out.**

- The **M249** is blocked from purchase.
- Headshot damage against Invisant is **halved and capped at 90**. One headshot cannot kill a full-health Invisant.
- Move at least **256 units** from your tracked position to avoid camping. You'll receive a warning after **20 seconds**. After another **10 seconds**, you lose **10 HP/s** until you move away.

### Role rotation

Roles rotate every round. Killing an Invisant as Armitive gives you priority to become Invisant next round.

Otherwise, the longest-waiting eligible player becomes Invisant. **Suicide forfeits your eligibility for the next round.**

### Progression

Armitive and Invisant each have separate **XP, levels up to 40, upgrade points, and persistent combat rankings**. Your progression carries over between sessions.

- Earn XP through kills, qualifying damage assists, and completed-round wins.
- As Armitive, knife kills award **150% kill XP** and pistol kills award **125%**.
- Level up to earn upgrade points.
- Type `upgrade` for upgrade effects, `menu` to spend points, or `reset` to refund them.

### Kill streaks

In rounds with at least **2 players per side**, the first enemy kill earns **First Blood** and **125% kill XP**.

Your second kill within **10 seconds** of your last earns **120% kill XP**. Each additional kill within 10 seconds adds another **10 percentage points**, reaching **200% on your tenth kill**.

Only you hear your kill streak sounds.

### Rank

Type `rank` to view your statistics and rankings for both roles.

Kills after the round ends award **no XP, rank, or role priority**. Surviving Invisant are revealed during the transition after a timeout.

## ESP and wallhacks

Invisant aren't simply made transparent. During the hunt, the server doesn't send their player data, weapon sounds, or movement sounds to Armitive computers.

ESP and wallhacks can only display information a computer receives, so they **cannot reveal or track an Invisant** without that player data.

Missed knife swings and wall impacts remain audible clues. Armitive can also see blood and bullet impacts, and hear damage sounds. Surviving Invisant are revealed after timeout.

## Upgrades

Each role has **8 upgrades**, with **5 stages per upgrade**. Unlocks depend on your level in that role.

- **Normal stages:** levels **1, 5, 10, 15, 20**.
- **Ultimate stages:** levels **8, 16, 24, 32, 40**.
- Type `menu` to spend points or `reset` to refund them.
- Changes apply immediately during the opening **20 seconds** of a round. After that, they take effect next round.

### Armitive

- **Fortitude:** Gain 10 maximum health per stage.
- **Recovery:** Gain 1 health per stage every 3 seconds.
- **Overload:** Gain 10% extra magazine capacity per stage.
- **Stockpile:** Gain 1 extra reserve ammo clip per stage.
- **Barrage:** Gain 7% faster weapon fire rate per stage.
- **Control:** Gain 10% less recoil and bullet spread per stage.
- **Dexterity:** Gain 12% less weapon switch and reload time per stage.
- **Ultimate: Ward:** Press E for 2 seconds of immunity at 1/5, plus 0.5 seconds per later stage.

### Invisant

- **Lightweight:** Gain 10% less gravity per stage.
- **Momentum:** Gain 3% faster run speed per stage.
- **Resilience:** Gain 15 armor per stage and helmet at 5/5.
- **Reforging:** Gain 1 armor per stage every 3 seconds.
- **Vampirism:** Gain 3 health per stage when dealing damage.
- **Bloodlust:** Gain 6 health per stage when killing an enemy.
- **Mobility:** Gain 15% faster crouching speed per stage.
- **Ultimate: Surge:** Press E for a 480 unit speed boost at 1/5, increased by 30 per later stage.

## Chat shortcuts

Type these directly in chat **without a prefix**:

- `help` — Open the gameplay guide.
- `menu` — Open your current role's upgrade menu.
- `upgrade` — Open the upgrade guide.
- `reset` — Refund your current role's upgrades and open the upgrade menu.
- `rank` — Open your rank menu, including Armitive stats, Invisant stats, and menu navigation.
- `audio` — Open your audio settings.
- `bugs` — Open the known bugs guide.
- `cheat` — Open the visibility and anti-cheat guide.
- `close` — Close an open upgrade menu or guide.

### Menu controls

These controls work while **alive or dead**. Release each key before pressing it again.

- **A / D:** Change pages.
- **W / S:** Choose an option.
- **SPACE:** Select. On an informational guide page, jump to its options.
- **R:** Jump to the final page with **Exit Menu** selected, then press **SPACE** to exit.

While dead, an open panel takes priority over spectator controls. You can also choose upgrades by typing `1`–`8` in chat.

The `audio` menu lets you toggle **Round Start, Round End, Kill Streak, Starvation, Timeout, Camping, AFK, and Menu** sounds. Your choices persist across roles and sessions.

## Play and community

To join the CS2 server, enter this in the developer console:

```text
connect cs2.shroudfire.com
```

Join the [Shroudfire Discord](https://discord.gg/TMV2DEPhqT) for community discussion and support.

## Website files

| File | Purpose |
| --- | --- |
| [index.html](index.html) | Landing page, styling, and links to the game editions. |
| [shroudfire.png](shroudfire.png) | Shroudfire banner. |
| [CNAME](CNAME) | Custom domain: `shroudfire.com`. |
| [.nojekyll](.nojekyll) | Static-site marker for GitHub Pages. |