# player

Allows you to send/recieve data for the player, exponentially increasing the amount of things your plugin can do.

[This](https://github.com/Solar-Tweaks/SolarStats/blob/main/src/player/Player.ts) is the actual code for it.

> Accessible through `player` or `Command.player` or `PlayerModule.player`

## Properties <!-- {docsify-ignore} -->

| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| uuid? | string | The player UUID |
| online? | boolean | Whether the player is online (aka on the proxy) |
| client? | [Client](Scope/player/Client.md) | The player's client |
| server? | [ServerClient](Scope/player/ServerClient.md) | The server client for the 
| lcPlayer? | [LunarClientPlayer](Scope/player/LunarClientPlayer.md) | The player's Lunar Client Player (used for sending lunar client specific packets) |
| status? | [Status](Scope/player/Status.md) | The Hypixel status of the player |
| teams? | Array&lt;[Team](Scope/player/Team.md)&gt; | <span style="color:red">UNDOCUMENTED</span> |
| connectedPlayers | Array&lt;[IPlayer](Scope/player/IPlayer.md)&gt; | All the connected players in the server |
| lastGameMode? | string | The last played gamemode of the player |
| overriddenPackets | {<br/>&nbsp;&nbsp;&nbsp;&nbsp;incoming: Array&lt;string&gt;,<br/>&nbsp;&nbsp;&nbsp;&nbsp;outgoing: Array&lt;string&gt;<br/>} | The packets that are not sent and expected to be handled by something else |
| <span style="color:lightblue">readonly</span> plugins | Array&lt;[PluginInfo](Scope/player/PluginInfo.md)&gt; | The plugin info for each plugin that is currently running on this player |
| <span style="color:lightblue">readonly</span> modules | Array&lt;[PlayerModule](Scope/player/PlayerModule.md)&gt; | The modules that are currently running for this player |
| <span style="color:lightblue">readonly</span> crashedModules | Array&lt;[PlayerModule](Scope/player/PlayerModule.md)&gt; | The modules that have currently crashed on this player |
| <span style="color:lightblue">readonly</span> proxy | [InstantConnectProxy](Scope/player/InstantConnectProxy.md) | The proxy running for this player (lets you recieve all (raw) packets) |
| <span style="color:lightblue">readonly</span> listener | [Listener](Scope/player/Listener.md) | The listener for the player (lets you recieve a limited amount of parsed packets with types) |
| <span style="color:lightblue">readonly</span> commandHandler | [CommandHandler](Scope/player/CommandHandler.md) | The command handler/registry for the player |

## Methods <!-- {docsify-ignore} -->

```javascript
async refreshPlayerLocation(): Promise<void>
// Refreshes the player status value, thus running any module.onLocationUpdate()'s

async dodge(): Promise<void>
// Dodges the currently queued game

isInGameMode(gamemode: string): boolean
// Tells you whether the player is in a certain gamemode

sendMessage(text: string): void
// Shows a chat message to the player

executeCommand(command: string): void
// Sends a message to the server pretending to be the player
```