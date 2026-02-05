# Charmsbot-site# CharmsBot

<p align="center">
  <img src="https://i.imgur.com/FjCwTyg.png" alt="CharmsBot Logo" width="200"/>
</p>

**CharmsBot** is a comprehensive Discord bot designed for Tibia players to optimize their hunting experience. It provides advanced charm assignment calculations, element efficiency analysis, loot splitting, and various utility tools to help players maximize their damage output and manage their hunts efficiently.

---

## 🎯 Features

### Character Management
Create and manage your Tibia characters with full stat tracking and charm configuration.

- **Charm Points Budget System**: Set your total charm points and the bot will calculate optimal charm assignments within your budget
- **Multi-Level Charm Support**: Configure charms at Level 1 (5%), Level 2 (10%), or Level 3 (11%) proc rates
- **Character Limits**: Up to 15 characters per user, with 20 saved analyses and 20 saved bestcharms per character

### Hunt Analysis Tools
Paste your Tibia Hunt Analyzer data and get instant insights.

- **Optimal Charm Assignments**: Calculate the best charm-to-creature assignments using the Hungarian Algorithm
- **Element Efficiency Analysis**: See which elements deal bonus damage or are resisted by the creatures in your spawn
- **Damage Calculations**: Detailed breakdowns including vulnerability, mitigation, and damage per proc

### Loot Management
- **Split Loot Calculator**: Equitably distribute party hunt loot with support for extra expenses
- **Transfer Instructions**: Get exact in-game transfer commands for settling debts

### Utility Tools
- **Weapon Proficiency XP Calculator**: Track your weapon proficiency progress
- **Hot Cuisine Quest Calculator**: Calculate ingredients for the Hot Cuisine Quest

---

## 📋 Commands

### Character Management

| Command | Description |
|---------|-------------|
| `/character add` | Add a new character with stats, charm points, and charms |
| `/character view` | View all your saved characters and their configurations |
| `/character edit` | Edit an existing character's stats and charms |
| `/character delete` | Delete a character and all associated data |

### Hunt Analysis

| Command | Description |
|---------|-------------|
| `/analysis` | Analyze your hunt using your character's saved charms |
| `/bestcharms` | Find the optimal charm configuration using ALL available charms |
| `/element` | Quick element efficiency checker (no character required) |

### Hunt Management

| Command | Description |
|---------|-------------|
| `/hunt view` | View your saved analyses and bestcharms configurations |
| `/hunt delete` | Delete a specific saved hunt |
| `/hunt rename` | Rename a saved hunt |

### Utilities

| Command | Description |
|---------|-------------|
| `/splitloot` | Split party hunt loot with optional extra expenses |
| `/weaponxp` | Calculate weapon proficiency XP from your hunt |
| `/hotcuisine` | Calculate ingredients for Hot Cuisine Quest |
| `/help` | Get detailed information about all commands |

---

## 🚀 Getting Started

### Quick Start Guide

1. **Create a Character**
   ```
   /character add
   ```
   - Enter your character name, level, max HP, and max mana
   - Enter your **Total Charm Points** (find it in Tibia: `Cyclopedia → Bosstiary & Charms → Charms`)
   - Select your unlocked charms and set their levels

2. **Analyze Your Hunt**
   ```
   /analysis
   ```
   - Select your character
   - Paste your Hunt Analyzer data from Tibia
   - Optionally save the analysis for future reference

3. **Find the Best Charms**
   ```
   /bestcharms
   ```
   - Evaluates ALL damage charms to find the optimal configuration
   - Shows which new charms you need and the reset cost

---

## 🔧 Technical Details

### Charm Damage Calculations

CharmsBot uses accurate Tibia charm mechanics:

- **Elemental Charms** (Enflame, Freeze, Zap, Poison, Curse, Wound, Divine Wrath):
  - Base damage: `min(5% × creature_health, player_level × 2)`
  - Final damage: `base_damage × vulnerability × (1 - mitigation/100)`

- **Physical Charms** (ignores vulnerability and mitigation):
  - Overpower: `min(5% × max_hp, player_level × 2)` capped at `8% × creature_health`
  - Overflux: `min(2.5% × max_mana, player_level × 2)` capped at `8% × creature_health`
  

### Charm Level Ratios

| Level | Proc Rate | Damage Multiplier |
|-------|-----------|-------------------|
| 🔹 Level 1 | 5% | 0.5× |
| ✨ Level 2 | 10% | 1.0× |
| ⭐ Level 3 | 11% | 1.1× |

### Algorithm

The bot uses the **Hungarian Algorithm** (scipy.optimize.linear_sum_assignment) to solve the optimal assignment problem, ensuring maximum total damage output.

---

## 🛡️ Security Features

CharmsBot implements comprehensive security measures:

- **Account Age Verification**: Prevents abuse from newly created accounts
- **Rate Limiting**: Per-user and per-guild rate limits for heavy commands
- **Input Validation**: All user inputs are validated and sanitized
- **Creature Limits**: Prevents resource exhaustion from excessively large spawns

---

## 📊 Supported Data

### Creatures
CharmsBot includes a comprehensive database of Tibia creatures with:
- Health points
- Mitigation values
- Elemental vulnerabilities and resistances

### Charms
All 9 ELEMENTAL charms are supported:
-  Enflame
-  Freeze
-  Zap
-  Poison 
-  Curse
-  Wound
-  Divine Wrath
-  Overpower
-  Overflux

---

## 🌐 Language Support

CharmsBot is available in **English** and designed to support the international Tibia community.

---

## 🤖 Add to Your Server

[![Add to Discord](https://img.shields.io/badge/Add%20to%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/oauth2/authorize?client_id=1324908850431791184)

[🔗 Click here to add CharmsBot to your server](https://discord.com/oauth2/authorize?client_id=1324908850431791184)

---

## 📜 License

CharmsBot is a fan-made project and is not affiliated with or endorsed by CipSoft GmbH. Tibia is a registered trademark of CipSoft GmbH.

---

## 🙏 Acknowledgments

- **CipSoft** for creating Tibia
- **TibiaWiki** for creature data reference
- The Tibia community for feedback and suggestions

---

<p align="center">
  Made with ❤️ for the Tibia community
</p>
