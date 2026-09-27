# # Empyrion - Playtime Rewards Shop Mod

## What is it?
With this mod, players can buy items from their playtime.
This is my first Empyrion mod combining the [Backpack Extender](https://github.com/GitHub-TC/EmpyrionBackpackExtender) and [Playtime Rewards](https://github.com/GitHub-TC/EmpyrionPlaytimeRewards) using the DemoMod as template.
Thanks for all the support from the Empyrion Discord 💜

## Can this mod damage your game files?
<a href="url"><img src="https://github.com/KiloGraf/EmpyrionPlaytimeRewardsShop/blob/main/images/CleanMod.png" align="left" height="48" width="48" ></a>
No. This mod only has access to the Empyrion API and does not modify any game files. To disable the mod, remove the EmpyrionPlayerRewardsShop folder from Content\Mods\

## Installation

This mod only works on servers. Copy the content of the EmpyrionPlayerRewardsShop_vx_x_X.zip into the folder Content\Mods\
You should have this file structure on your server:
- Content\Mods\
	- EmpyrionPlayerRewardsShop\
 		- EmpyrionPlayerRewardsShop.dll
   		- EmpyrionPlayerRewardsShop_Info.yaml

## Configuration
After starting the server or game with the mod in the correct folder, the configuration will be created here:
\[SaveGamePath\]\\Mods\\EmpyrionPlaytimeRewardsShop\\Configuration.json

For each item you want to add to the shop, add an entry in the item rewards sections.
The item ids are the "Game ID" from the database: https://empyrionbuddy.com (with the correct Scenario activated in their settings)

Currently these stats are implemented:
- "life" - increases the maximum health
- "exp" - increases the players experience points

```json
{
	"ChatCommandPrefix":"/\\prs",
	"RewardPeriodInMinutes":30,
	"RewardPointsPerPeriod":1,
	"RewardItems":
	[
		{"Name":"irn","Description":"Iron Ingot","quantity":1000,"price":1,"itemId":8416},
		{"Name":"neo","Description":"Neodynium Ingot","quantity":1000,"price":1,"itemId":8419
	],
	"RewardStats":
	[
		{"Name":"life","Description":"Health","quantity":50,"price":1,"maxStat":4000},
		{"Name":"food","Description":"Food","quantity":50,"price":1,"maxStat":4000},
		{"Name":"stamina","Description":"Stamina","quantity":50,"price":1,"maxStat":4000},
		{"Name":"exp","Description":"Experience","quantity":1000,"price":10,"maxStat":500000}
	]
}
```



## Usage
Enter the command into the server or faction chat in your game.

```
\prs help        : shows all available commands in a Window
\prs points      : updates the points for the player

\prs buy irn     : buys the item iron ingot with the conditions of the configuration file from the player points
\prs buy neo     : buys the item neodynium ingot with the conditions of the configuration file from the player points

\prs buy life    : increases the maximum health of the player with the conditions from the configuration file
\prs buy food    : increases the maximum food of the player with the conditions from the configuration file
\prs buy stamina : increases the maximum stamina of the player with the conditions from the configuration file
```
Source: https://github.com/Cathanys/EmpyrionPlaytimeRewardsShop
