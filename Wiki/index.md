#Subreddit information
##[](//hex/0)Coordinate sharing explained

No Man's Sky gamers can travel across universe to get/see some interesting objects, if they know their coordinates    
(the presence of some objects may vary depending on game mode/platform, see variables below) 

**The same objects for all platforms and game modes:**

* Ships (class and slot number is random value ^[1](https://www.reddit.com/r/NoMansSkyTheGame/comments/6kdl94/this_took_me_weeks_to_get_to_spawn_not_even/),[1b](https://imgur.com/a/BaOOL) )
* Multi-Tools (slot number is pseudo random value and depends on current multi-tool's slot number, [class - ?](https://www.reddit.com/r/NMSCoordinateExchange/comments/6mmj87/need_help_with_experiment_is_multitool_class/))
* Planetary terrain/flora/fauna
* Rare resources on planets
* In space station trade terminal: there are the same commodity list and prices ^[2](https://www.reddit.com/r/NMSGalacticHub/comments/6i3upx/110_nipnip_95_ap_and_impact_damage_omega_blueprint/dk1uuna/)
* In space station blueprint trader: there are the same blueprint list ^[2](https://www.reddit.com/r/NMSGalacticHub/comments/6i3upx/110_nipnip_95_ap_and_impact_damage_omega_blueprint/dk1uuna/)

**Different by platforms, for all game modes:**

* Discoveries made by gamers (also renamed discoveries will be visible in other game modes)

**Different by platforms, different by game modes:**

* Player constructions
	* Player's base locations
	* [Communications station](https://nomanssky.gamepedia.com/Communications_Station), marking interesting planetary locations ^[3](https://www.reddit.com/r/NMSGalacticHub/comments/6phz8x/found_my_permadeath_home_system_in_survival_in/dkpld1a/) (biome is different between game modes)

***
#Helpful Navigation Information##
***
##[](//hex/0)Obtain coordinates from Signal Booster
After constructing a Signal Booster, activate it to show a string of coordinates    
[Signal booster](https://steamuserimages-a.akamaihd.net/ugc/781785533832150145/7C30E7BA3315F5D87C17D71B5D4BCF46D30CF854/ "RAIK:0373:0081:0D1D:00C4")    
First part - `RAIK`is scanner ID, other 4 parts - `0373:0081:0D1D:00C4` is the star system coordinates

>Coordinates are the same for PS4 and PC. For example, you found a cool ship in a PS4 star system, this ship will be in the same system on PC.   

Signal Booster doesn't show galaxy/dimension (my coordinates `0373:0081:0D1D:00C4` captured in Euclid galaxy)

***
##[](//hex/1)Convert coordinates

coordinates[format]:|x|y|z|star class
-|-|-|-|-:
*starsystem[[hex](https://en.wikipedia.org/wiki/Hexadecimal)]*|0373|0081|0D1D|00C4
||→|→|→|→
*starsystem[[dec](https://en.wikipedia.org/wiki/Decimal)]*|883|129|3357|196
||-|-|-|▼
*SHIFT[dec]*|2047|127|2047|▼
||=|=|=|▼
*voxel[dec]*|-1164|2|1310|196
**JSON object:**|**VoxelX**|**VoxelY**|**VoxelZ**|**SolarSystemIndex**|

Conversion formula example:    
`z[hex]=D1D → 3357=z[dec]`

`VoxelZ[dec]=z[dec]-SHIFT[dec]=3357-2047=1310`

and vice versa for extraction coordinates from save:    
`z[dec]=VoxelZ[dec]+SHIFT[dec]=1310+2047=3357`

`3357=z[dec] → z[hex]=D1D`    

>Star class determines star temperature(color)/radius/luminosity and unique inside voxel, but the same class can be in a nearby voxel    


>SHIFT is constant    

***
##[](//hex/2)Portal coordinates

Table of correspondence between Hexadecimal numerals and Portal dial disk symbols:

Hex numeral:| 0|1|2|3|4|5|6|7|8|9|a|b|c|d|e|f
-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-
**Dial disk glyph**|[](//hex/0)|[](//hex/1)|[](//hex/2)|[](//hex/3)|[](//hex/4)|[](//hex/5)|[](//hex/6)|[](//hex/7)|[](//hex/8)|[](//hex/9)|[](//hex/a)|[](//hex/b)|[](//hex/c)|[](//hex/d)|[](//hex/e)|[](//hex/f)
**Glyph name**|sunset|bird|face|diplo|eclipse|balloon|boat|bug|dragonfly|galaxy|voxel|fish|tent|rocket|tree|atlas

***
##[](//hex/3)[Convert portal coordinates to star coordinates](/r/NMSCoordinateExchange/wiki/tutorials/convert_portal_coordinates)


***
##[](//hex/4)Coordinate system

      Y
      ▲
      │  ☐voxel
      │
      ┗━━━━━► X
     ╱
    v
    Z

       ┍━━━━━━━┓
      ╱┆ *star╱│
     ╱ ┆     ╱ │
    ┏━━┿━━━━┓  │
    │  └----│--┘
    │ ╱     │ ╱
    ┗━━━━━━━┛
      voxel

* Galaxy center coordinate is: `07FF:007F:07FF:0XXX` (or translated `VoxelX - VoxelY - VoxelZ - SolarSystemIndex` format `0 - 0 - 0 - 0XXX` )
* Star systems on Game's galaxy map are located in the following coordinate range: `0001:0001:0001:0001 .. 0FFF:00FF:0FFF:02FF` ("teleporting" out of this range possible on PC, but not on PS4 - this is an unplotted region)
* Galaxy center and spherical region with radius ~ 3*voxel are also unplotted on game map

***
##[](//hex/5)Star Systems - Region - Galaxy hierarchy
Hierarchy is: Star System -> Region (contains unknown number of star systems, but less than 2FF[hex]) -(additional research needed) ->  Voxel (contains ~ 3-5 regions) -> Galaxy (contains more than 500 regions)
>

For example:   `01EF:0086:0B34:00F6 (Euclid)` and `01EF:0086:0B34:0025 (Euclid)` are coordinates inside one voxel (last coordinate part is SolarSystemIndex).

***
##[](//hex/6)[Biggest HUBs](https://www.reddit.com/r/NMSCoordinateExchange/wiki/hubs)

***
#Guides
##[](//hex/7)[How to find and use Portals](/r/NMSCoordinateExchange/wiki/guides/portals-how_to_find_and_use_them)
##[](//hex/2)[Galactic portals grid(work in progress)](/r/NMSCoordinateExchange/wiki/guides/galactic_portals_grid)
##[](//hex/9)[How to Properly Maintain a Functional Terminus Teleport](/r/NMSCoordinateExchange/wiki/guides/maintain_terminus_teleport)
##[](//hex/8)[Multi-tools and how to find them](/r/NMSCoordinateExchange/wiki/guides/multi-tools_and_how_to_find_them)
##[](//hex/d)[Understanding the current star-ship economy (outdated)](/r/NMSCoordinateExchange/wiki/guides/understanding_the_current_star-ship_economy)
##[](//hex/a)[(MODDING) "Warp" in any Star System](https://www.reddit.com/r/NoMansSkyMods/comments/6fr5td/tutorial_convert_signal_booster_coordinates_to/)

***
#Subreddit features
##[Flairs](https://www.reddit.com/r/NMSCoordinateExchange/wiki/flairs)
##[Glyphs](https://www.reddit.com/r/NMSCoordinateExchange/wiki/glyphs)
##[Templates](https://www.reddit.com/r/NMSCoordinateExchange/wiki/templates)

***
#Other
##[](//hex/d)[Navigation tools (work in progress)](/r/NMSCoordinateExchange/wiki/guides/navigation_tools)
##[](//hex/a)[Glossary (work in progress)](/r/NMSCoordinateExchange/wiki/guides/glossary)