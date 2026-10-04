# One-block
Oneblock
asset OneBlock

A lightweight OneBlock gameplay system for Minecraft: Bedrock Edition.
Automatically generates a new block whenever the central OneBlock is broken.

Author: Mc1271
Project: asset OneBlock
Platform: Minecraft: Bedrock Edition
Target Version: Minecraft Bedrock Edition 1.26.52
Script API: @minecraft/server 2.10.0
Pack Type: Behavior Pack
Language: JavaScript

⸻

📖 Overview

asset OneBlock is a Minecraft Bedrock Edition OneBlock system developed with the official Script API.

The basic gameplay is simple:

1. A single block is generated at the center of the world.
2. The player breaks the block.
3. The system immediately generates another random block.
4. The player continues breaking the same block.
5. The block pool contains a large selection of vanilla Minecraft blocks.
6. Technical, dangerous, or unsuitable blocks are automatically excluded.
7. Players who fall below the protected area are automatically returned to the OneBlock position.

The system is designed to be lightweight and easy to integrate into an existing Bedrock world or server.

⸻

✨ Features

OneBlock Gameplay

The main OneBlock is located at:

X: 0
Y: 100
Z: 0

Players spawn at:

X: 0.5
Y: 101.1
Z: 0.5

The OneBlock is automatically replaced after being broken.

⸻

🎲 Random Block Generation

Every time the OneBlock is destroyed, the script selects another block from the available block pool.

The system contains blocks from many categories, including:

* Stone
* Dirt
* Sand
* Gravel
* Snow
* Ice
* Logs
* Planks
* Ores
* Metal blocks
* Bricks
* Sandstone
* Quartz
* Nether blocks
* End blocks
* Ocean blocks
* Glass
* Wool
* Concrete
* Concrete Powder
* Terracotta
* Copper
* Amethyst
* Obsidian
* Natural blocks
* Light-source blocks
* Functional blocks
* Fences
* Ladders
* Iron Bars
* Other vanilla blocks

Wood types include:

* Oak
* Spruce
* Birch
* Jungle
* Acacia
* Dark Oak
* Mangrove
* Cherry

The system also automatically generates additional wood variants such as:

* Slabs
* Stairs
* Fences
* Fence Gates
* Doors
* Trapdoors
* Buttons
* Pressure Plates

Duplicate block IDs are automatically removed.

⸻

🛡️ Protected / Forbidden Blocks

The system intentionally excludes blocks that should not be generated as normal OneBlock blocks.

Examples include:

minecraft:air
minecraft:cave_air
minecraft:void_air
minecraft:bedrock
minecraft:barrier
minecraft:command_block
minecraft:chain_command_block
minecraft:repeating_command_block
minecraft:structure_block
minecraft:jigsaw
minecraft:light
minecraft:end_portal
minecraft:end_gateway
minecraft:nether_portal
minecraft:water
minecraft:flowing_water
minecraft:lava
minecraft:flowing_lava
minecraft:fire
minecraft:soul_fire
minecraft:moving_block
minecraft:piston_arm_collision

This prevents the OneBlock from generating blocks that could:

* Break the gameplay loop
* Create infinite liquids
* Cause technical problems
* Prevent the block from being broken normally
* Create portals
* Generate invisible or technical blocks
* Destroy the intended OneBlock experience

⸻

📍 World Requirements

Recommended World

It is strongly recommended to create a new, dedicated world for OneBlock.

Example:

World Name:
asset OneBlock

Recommended game settings:

Game Mode:
Survival

Recommended difficulty:

Normal

or

Hard

Creative mode may be used for testing, but Survival mode is recommended for actual gameplay.

⸻

🌎 Important World Information

This system is designed around the following coordinates:

OneBlock

0, 100, 0

Player Spawn

0.5, 101.1, 0.5

The script uses the Overworld:

minecraft:overworld

The current version is not designed to operate the main OneBlock in the Nether or End.

⸻

⚠️ Recommended World Setup

For the best experience:

1. Create a new world.
2. Enable Cheats during development/testing if needed.
3. Activate the Behavior Pack.
4. Make sure the script module loads correctly.
5. Enter the world.
6. Wait a few seconds for initialization.
7. Check the center position.
8. The OneBlock should appear at:

0, 100, 0

9. Stand above the block.
10. Break it.
11. A new block should automatically appear.

⸻

🧪 Experimental Features

Important

Minecraft Bedrock experimental features change between versions.

Microsoft’s documentation explicitly notes that the available experimental toggles can change between Minecraft releases. (GitHub)

Therefore, do not blindly enable every experimental option.

For this project, enable only the experiment required by the specific Script API/pack version you are using.

⸻

Recommended Setting

For versions where Script API 2.x requires it, enable:

Beta APIs

Microsoft’s current Script API documentation states that Script API v2 experimental APIs require the Beta APIs experiment. (Microsoft Learn)

However, if your exact Minecraft release already provides the required API without this experiment, do not enable unnecessary experimental features.

⸻

❗ Do NOT Enable Everything

Avoid randomly enabling:

Holiday Creator Features
Upcoming Creator Features
Custom Biomes
GameTest Framework
Molang Experimental Features
Vanilla Experiments

unless another component of your world specifically requires them.

The purpose of this project is to keep the OneBlock world as stable and simple as possible.

⸻

🔐 Experimental World Warning

Experimental worlds should always be backed up.

Microsoft warns that experimental features can cause worlds to stop working correctly after future updates. Worlds using experimental features may also not be able to return to a completely non-experimental state. (GitHub)

Recommended workflow

Original World
      ↓
Create Backup
      ↓
Create Test Copy
      ↓
Install OneBlock
      ↓
Enable Required Experiments
      ↓
Test
      ↓
Only then use for gameplay

Never test an experimental add-on directly on the only copy of an important survival world.

⸻

📦 Installation

Method 1 — Minecraft Bedrock Edition

1. Obtain the OneBlock Behavior Pack.
2. Import the pack into Minecraft.
3. Open:

Play

4. Create a new world or edit an existing test world.
5. Open:

Behavior Packs

6. Find:

asset OneBlock

7. Select:

Activate

8. Check the world experiments if required by your Minecraft/API version.
9. Create or launch the world.

Microsoft’s official add-on instructions follow the same general process: open the world settings, select Behavior Packs, locate the pack under available packs, and activate it. (Minecraft.net)

⸻

🖥️ Server Installation

The Behavior Pack can also be used with a Bedrock Dedicated Server.

Bedrock Dedicated Server supports JavaScript Script APIs, although some APIs can have additional experimental requirements. (Microsoft Learn)

Place the behavior pack according to your server setup.

Typical server structure:

BedrockServer/
│
├── bedrock_server.exe
├── worlds/
├── behavior_packs/
├── resource_packs/
├── config/
└── server.properties

The official Bedrock Dedicated Server documentation explains that worlds are stored under the worlds directory and that behavior/resource packs can be installed either globally or for an individual world. (Microsoft Learn)

⸻

🌐 Server World

Make sure the correct world is selected in:

server.properties

Example:

level-name=asset-OneBlock

The name must match the world folder being used by the server.

Only one world is active at a time through the server’s level-name setting. (Microsoft Learn)

⸻

⚙️ Server Requirements

Recommended:

Minecraft Bedrock Dedicated Server:
1.26.52
Minecraft Client:
1.26.52
Script API:
@minecraft/server 2.10.0

The client and server should preferably use the same Minecraft release family.

Do not assume that a Script API pack designed for one Minecraft version will work perfectly on an older or newer version.

⸻

🧩 Pack Structure

The recommended project structure is:

asset-oneblock/
│
├── README.md
│
├── manifest.json
│
└── scripts/
    └── main.js

The important files are:

manifest.json
scripts/main.js

⸻

📜 Script Entry Point

The behavior pack should point to:

scripts/main.js

The script uses:

import {
    world,
    system,
    ItemStack
} from "@minecraft/server";

⸻

🔧 Configuration

The main configuration is located near the beginning of main.js.

OneBlock Position

const ONE_BLOCK = {
    x: 0,
    y: 100,
    z: 0
};

To move the OneBlock, change these coordinates.

Example:

const ONE_BLOCK = {
    x: 100,
    y: 80,
    z: 100
};

The OneBlock will then operate around:

100, 80, 100

⸻

👤 Player Spawn Position

Current configuration:

const SPAWN = {
    x: 0.5,
    y: 101.1,
    z: 0.5
};

The player is positioned slightly above the OneBlock.

⸻

🌍 Dimension

The current system uses:

const DIMENSION_ID = "overworld";

This means the main OneBlock is located in the Overworld.

⸻

🚀 Automatic Teleport

The current configuration is:

const AUTO_TELEPORT = true;

When enabled, players are automatically moved to the OneBlock location when the system initializes them.

⸻

🎒 Starter Items

The current version gives the player starter items such as:

Oak Sapling
Bone Meal ×4

These are intended to help players begin building a sustainable island.

⸻

🛟 Fall Protection

The system checks the player’s position periodically.

If a player falls far below the OneBlock area, the script automatically returns them to the OneBlock.

The current protection threshold is approximately:

Y < -70

and the player must be relatively close to the OneBlock’s X/Z area.

This prevents players from becoming permanently lost below the world.

⸻

🔄 Block Replacement System

When the player breaks the OneBlock:

Break Block
     ↓
Detect Block Break
     ↓
Prevent Duplicate Replacement
     ↓
Wait One Tick
     ↓
Generate Next Block

A replacement lock is used to prevent multiple replacement operations from happening at the same time.

⸻

🧱 Block Validation

Before a random block is selected, the script validates the block against the safe block pool.

If the system cannot successfully generate the selected block after multiple attempts, it falls back to:

minecraft:stone

This prevents the OneBlock from becoming permanently empty because of an invalid block ID.

⸻

💬 In-Game Messages

When the system starts, players may receive messages similar to:

OneBlock
You are now at 0, 100, 0
Break the only block to generate the next block!

The system also displays the number of blocks available in the generated block pool.

Example:

OneBlock block pool: XXX blocks

The exact number can change depending on the Minecraft version and which block IDs are supported.

⸻

🧪 Testing Procedure

After installation, test the system in this order.

Test 1 — Pack Loading

Enter the world and check whether the script loads without errors.

⸻

Test 2 — Initial Block

Check:

0, 100, 0

There should be a OneBlock.

⸻

Test 3 — Block Breaking

Break the OneBlock.

A new block should appear shortly afterward.

⸻

Test 4 — Repeated Breaking

Break the generated block several times.

Verify:

Block A
↓
Block B
↓
Block C
↓
Block D
↓
...

⸻

Test 5 — Fall Protection

Move or fall below the protected area.

The system should return the player to the OneBlock.

⸻

Test 6 — Server Restart

Stop the server.

Start it again.

Enter the world and verify that the OneBlock system initializes normally.

⸻

🐛 Troubleshooting

Problem: Nothing happens

Check:

1. Behavior Pack is activated.
2. manifest.json is valid.
3. scripts/main.js exists.
4. The script module is declared correctly.
5. The Minecraft version is compatible.
6. The required Script API version is installed.
7. Required experiments are enabled if your version requires them.

⸻

❌ Problem: Script Import Error

For example:

Could not find export ...

This normally means the script is using an API export that does not exist in the installed Script API version.

Do not randomly add imports.

For example, this project should not reintroduce:

isSinglePlayerTest

unless the target API version explicitly supports it.

⸻

❌ Problem: OneBlock Does Not Reappear

Check the content log.

Possible causes include:

* Invalid block ID
* Unsupported block
* API version mismatch
* Script execution error
* Incorrect behavior pack manifest
* Another add-on modifying the same block
* World corruption

The script contains validation and fallback logic to reduce this problem.

⸻

❌ Problem: World Does Not Load Correctly

First:

1. Stop the server/game.
2. Back up the world.
3. Disable the OneBlock pack.
4. Test the world again.
5. If the world works normally, create a fresh test copy.
6. Reinstall the OneBlock pack.

Never test experimental add-ons on your only important world.

⸻

❌ Problem: Experimental Toggle Is Missing

Experimental feature names can change between Minecraft versions.

Do not rely on screenshots from an older Minecraft release.

Open:

World Settings
→ Game
→ Experiments

and check the available options for your installed version.

Microsoft specifically notes that the experiment list is subject to change. (GitHub)

⸻

🌐 Official Navigation

Minecraft

Minecraft Official Website

Minecraft Bedrock Server Download

Minecraft Bedrock Dedicated Server Download

Minecraft Creator Documentation

Minecraft Creator Documentation

Script API Documentation

Minecraft Script API Reference

Script API V2 Documentation

Scripting V2 Overview

Bedrock Dedicated Server Documentation

Bedrock Dedicated Server Documentation

Add-On Installation Guide

Official Add-On Activation Guide

⸻

🔗 Useful Project Links

Replace the following links with your actual GitHub repository after publishing:

GitHub:
https://github.com/Mc1271/asset-oneblock
Issues:
https://github.com/Mc1271/asset-oneblock/issues
Releases:
https://github.com/Mc1271/asset-oneblock/releases
Wiki:
https://github.com/Mc1271/asset-oneblock/wiki

These are placeholders. Replace Mc1271/asset-oneblock with your actual GitHub repository if the repository uses another name.

⸻

🖥️ Recommended Development Environment

Recommended:

Operating System:
Windows 10 / Windows 11
Editor:
Visual Studio Code
Language:
JavaScript
Runtime:
Node.js (optional for development tools)
Minecraft:
Bedrock Edition 1.26.52
Script API:
@minecraft/server 2.10.0

Visual Studio Code is recommended because it provides a convenient environment for editing JSON and JavaScript files.

⸻

📋 Compatibility

Component	Version
Minecraft Bedrock Edition	1.26.52
Script API	2.10.0
Behavior Pack Format	Format Version 2
Main Script	scripts/main.js
Dimension	Overworld
OneBlock	0, 100, 0
Spawn	0.5, 101.1, 0.5
Language	JavaScript

⸻

⚠️ Version Compatibility Warning

Minecraft Bedrock changes frequently.

A future Minecraft version may change:

* Block IDs
* Script API methods
* Event behavior
* Manifest requirements
* Experimental features
* Block availability
* World behavior
* Server behavior

Therefore:

Always test the pack on the exact Minecraft version you intend to use.

Do not automatically assume that the latest Minecraft version is compatible with this release.

⸻

🔒 Backup Policy

Before installing this pack into an important world:

BACK UP YOUR WORLD.

Recommended backup structure:

Backups/
├── OneBlock-Test-01/
├── OneBlock-Test-02/
└── OneBlock-Production/

Keep the original world untouched until the new version has been tested.

⸻

🏗️ Recommended Production Workflow

For a public server:

Development World
       ↓
Local Testing
       ↓
Backup
       ↓
Dedicated Server Test
       ↓
Player Testing
       ↓
Bug Fixes
       ↓
Final Backup
       ↓
Production Server

Never update a public production world without testing the new pack first.

⸻

🧑‍💻 Development Notes

This project intentionally uses the official Minecraft Bedrock Script API.

The script does not require Java.

The main implementation is:

JavaScript
      ↓
Minecraft Bedrock Script API
      ↓
Behavior Pack
      ↓
Minecraft World

⸻

📄 License

This project is developed by Mc1271.

If you redistribute or modify this project, please keep the original author attribution unless a different license is explicitly added to this repository.

Recommended attribution:

asset OneBlock
Author: Mc1271

⸻

❤️ Credits

Created by:

Mc1271

Project:

asset OneBlock

Built for:

Minecraft: Bedrock Edition

Powered by:

Minecraft Bedrock Script API

⸻

⭐ Support

If you find a bug:

1. Reproduce the problem.
2. Check the content log.
3. Record your Minecraft version.
4. Record your Script API version.
5. Record whether the world is single-player or a Dedicated Server.
6. Record enabled experiments.
7. Provide the relevant error message.
8. Open a GitHub Issue.

Please do not report only:

It doesn't work.

Instead provide:

Minecraft Version:
1.26.52
Script API:
2.10.0
Platform:
Windows / Android / iOS / Dedicated Server
World:
New World / Existing World
Experiments:
...
Error:
...

This makes debugging much easier.

⸻

🚀 Quick Start

For experienced users:

1. Create a new Bedrock world.
2. Back up the world.
3. Activate asset OneBlock Behavior Pack.
4. Enable the required Script API experiment for your version if necessary.
5. Start the world.
6. Wait for initialization.
7. Go to 0, 100, 0.
8. Break the OneBlock.
9. Continue playing.

⸻

🎮 Gameplay Summary

The entire gameplay loop is:

                 ┌───────────────┐
                 │   OneBlock    │
                 │   0,100,0     │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │ Break Block   │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │ Select Random │
                 │ Safe Block    │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │ Generate Next │
                 │ Block         │
                 └───────┬───────┘
                         │
                         ▼
                    Repeat Forever

⸻

📌 Final Notes

asset OneBlock is intended to provide a simple and reliable OneBlock experience for Minecraft Bedrock Edition.

Always:

* Use a backup.
* Test on a separate world first.
* Use the correct Minecraft version.
* Use the correct Script API version.
* Check the Experiments menu when required.
* Check the content log when something goes wrong.
* Do not enable unnecessary experimental features.
* Do not install the pack into an important production world without testing it first.

For the current release, the recommended target environment is:

Minecraft Bedrock Edition 1.26.52
@minecraft/server 2.10.0
Overworld
OneBlock: 0, 100, 0
Spawn: 0.5, 101.1, 0.5

⸻

asset OneBlock © Mc1271
