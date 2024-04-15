### Dodian
This is the Develop Client for the Dodian OSRS base.
Join our discord: https://discord.com/invite/CVUcp6ST

***This is no live server! It contains still tons of bugs! Player saving can be resetted!***

# Run Local
Clone this project using Intellij or w.e you're using, then on top right click on `Current File` then `Edit Configurations` press the plus icon and select gradle,
inside Gradle Task text field insert:
`run --args="--developer-mode --debug --jav_config "https://raw.githubusercontent.com/Eikenb00m/dodian-develop-resources/main/jav_config-beta.ws"" -x checkStyleMain -x checkStyleTest -x test` press apply and run.
Find Private Server plugin inside plugin menu, open settings --> Insert ur modulus key and done.
Create your own key!


# Run Beta
Clone this project using Intellij or w.e you're using, then on top right click on `Current File` then `Edit Configurations` press the plus icon and select gradle,
inside Gradle Task text field insert:
`run --args="--developer-mode --debug --jav_config "https://raw.githubusercontent.com/Eikenb00m/dodian-develop-resources/main/jav_config-beta.ws"" -x checkStyleMain -x checkStyleTest -x test` press apply and run.
Find Private Server plugin inside plugin menu, open settings --> Insert ur modulus key and done.
URL: 
`http://89.35.91.151/`
Key:
`b12d6264d90fdda125c442130b76bad87eb42f0b463c29bf6fef3f5ff0cc831e1fd5e93d17a3ba48b6d8a104ae3f770d937c3b136fb0f97ad5706d7b366b26ac0a5486c6cefb3db5d0da74355d480f1ac2e276d5a1b73d6602934f8e2f359c4dbb9924de258ea1eb940d764f3a898c02db78a9d96f5d9915b1ade3fb93bbe9a5`



# Launcher

The client launcher can be downloaded here:

https://github.com/jbx5/devious-launcher/releases

# Devious Client
A non-compliant and open source fork of OpenOSRS and Unethicalite.
This client is slightly modified in order to be compatible with our api. Updates to OpenOSRS are directly synced with this fork.

**All existing OpenOSRS or RuneLite plugins ARE compatible with this client.**

## Features

### Extended RuneLite API
- RuneLite classes such as Actor, TileObject, Item, are extended with an Interactable api, which allow interaction with the
object (ex. ``NPC.interact("Attack")``)
- Mixins are customized and optimized for the api & client

### OpenOSRS extensions
- The external plugin manager now also supports private GitHub repositories.

### Definitions/Compositions
- Methods such as getName(), getActions(), etc. of Items, TileObjects and NPCs rely on retrieving their composition
from the client, which in some cases needs to be run on the client thread. 
We have modified the client in such a way that compositions get cached, so that client thread lookups are only needed
if the composition is not cached. This allows for stuff like Widget.isVisible() and TileObject.getName() to work off
client thread.

### Packets
- Our api exposes most of the available client packets, which can be used to for example directly send interactions
to the server. An example use case is stacking multiple npc dialogs in one tick ([Example](https://cdn.discordapp.com/attachments/793302998443884557/885509804846616586/zfJSpw7f98.mp4))
- These packets are very easy to use with our Packet api. (ex. ``ItemPackets.createFirstAction(widget, id, slot).send()``)

### Pathfinding
- The client has a pathfinding api which covers the majority of the map. All collision data is crowdsourced using the 
internal Regions plugin. The data can be accessed from our backend.
- Besides walking, Transports and Teleports are also supported.

### Automation
- The client has different methods of interaction: invokes, clicks, packets. Using the Interaction plugin, all sorts of
interaction settings can be customized.
- Our API has classes such as LoopedPlugin and TaskPlugin, for easy creation of automation plugins.

### Natural mouse
- The interaction api supports the NaturalMouse library. Can be toggled in the Interaction plugin.

### Game API
- We have a simplified game api that helps developers to retrieve things such as entities, inventories, widgets, etc. from the client.
  (ex. ``Inventory.getFirst("Coins")`` ``NPCs.getNearest("Goblin")`` ``Magic.cast("Wind strike")`` etc.)

### Minimal environment
- The client can also be built as a typical (unethical) third party client, meaning without all the RuneLite stuff such as plugins. 
- The minimal environment may be ideal for people who want to run (multiple) script(s) and preserve cpu/ram usage.
- Check out the discord to see how to build using the minimal environment.

<br> There's much more that this fork offers which simply can't be fit into this small readme.
