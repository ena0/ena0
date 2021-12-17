[![downloadsBadge](https://img.shields.io/npm/dt/discord.js-logs-tool?style=for-the-badge)](https://npmjs.com/discord.js-logs-tool) [![versionBadge](https://img.shields.io/npm/v/discord.js-logs-tool?label=version&style=for-the-badge)](https://npmjs.com/discord.js-logs-tool) [![npms.io (final)](https://img.shields.io/npms-io/final-score/discord.js-logs-tool?label=npms%20version&style=for-the-badge)
](https://npmjs.com/discord.js-logs-tool)

# discord.js-logs-tool

## Table of contents
1. [Table of contents](#table-of-contents)
2. [Installation](#Installation)
3. [Usage](#Usage)
4. [Events](#Events):
	1. [Channel](#Channel):
		1. [ChannelNameUpdate](#ChannelNameUpdate)
		2. [ChannelParentUpdate](#ChannelParentUpdate)
		3. [ChannelPermissionsUpdate](#ChannelPermissionsUpdate)
		4. [ChannelPositionUpdate](#ChannelPositionUpdate)
		5. [TextChannelNsfwStatusUpdate](#TextChannelNsfwStatusUpdate)
		6. [TextChannelRateLimitPerUserUpdate](#TextChannelRateLimitPerUserUpdate)
		7. [TextChannelTopicUpdate](#TextChannelTopicUpdate)
		8. [VoiceChannelUserLimitUpdate](#VoiceChannelUserLimitUpdate)
		9. [VoiceChannelBitrateUpdate](#VoiceChannelBitrateUpdate)
		10. [channelUndefinedUpdate](#channelUndefinedUpdate)
    2. [Emoji](#emoji):
       1. [emojiNameUpdate](#emojiNameUpdate)  
## Installation
```bash
npm i discord.js-logs-tool
```
## Usage
```js
const { Client, Intents } = require('discord.js')
const { Event } = require('discord.js-logs-tool')
const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS,
        Intents.FLAGS.GUILD_MESSAGES,
        Intents.FLAGS.GUILD_VOICE_STATES,
        Intents.FLAGS.GUILD_PRESENCES,
        Intents.FLAGS.GUILD_MEMBERS
    ]
})

client.login('YOUR_DISCORD_BOT_TOKEN')

client.on("channelNameUpdate", (channel, oldName, newName) => {
	console.log(`${channel.name} channel's name has been updated: \`${oldName}\` -> \`${newName}\``)
})
```
## Events:
### Channel events: <a name="channel"></a>
-	`channelNameUpdate`: Emitted when a channels's name was update <a name="channelNameUpdate"></a>
parametters:

| name    | type      | description                              |
| ------- | --------- | ---------------------------------------- |
| channel | `Channel` | The channel whose name have been updated |
| oldName | `String`  | The old channel name                     |
| newName | `String`  | The new channel name                     |

```js
client.on("channelNameUpdate", (channel, oldName, newName) => {
	console.log(`${channel.name} channel's name has been updated: \`${oldName}\` -> \`${newName}\``)
})
```
---
-	`channelParentUpdate` Emitted when a channel's parent was updated <a name="channelParentUpdate"></a>
parametters:

| name      | type              | description                                |
| --------- | ----------------- | ------------------------------------------ |
| channel   | `Channel`         | The channel whose parent have been updated |
| oldParent | `CategoryChannel` | The old parent                             |
| newParent | `CategoryChannel` | The new parent                             |

```js
client.on("channelParentUpdate", (channel, oldParent, newParent) => {
	console.log(`${channel.name} channel's parent has been updated: \`${oldParent.name}\` -> \`${newParent.name}\``)
})
```
---
-	`channelPermissionsUpdate` Emitted when a channel's permissions was updated <a name="channelPermissionsUpdate"></a>
parametters:

| name           | type                    | description                                     |
| -------------- | ----------------------- | ----------------------------------------------- |
| channel        | `Channel`               | The channel whose permissions have been updated |
| oldPermissions | `PermissionsOverwrites` | The old Permissions                             |
| newPermissions | `PermissionsOverwrites` | The new Permissions                             |

```js
client.on("channelPermissionsUpdate", (channel, oldPermissions, newPermissions) => {
	console.log(`${channel.name} channel's permissions has been updated`)
})
```
---
-	`channelPositionUpdate` Emitted when a channel's position was updated <a name="channelPositionUpdate"></a>
parametters:

| name        | type      | description                                  |
| ----------- | --------- | -------------------------------------------- |
| channel     | `Channel` | The channel whose position have been updated |
| oldPosition | `Number`  | The old position                             |
| oldPosition | `Number`  | The new position                             |

```js
client.on("channelPositionUpdate", (channel, oldPosition, newPosition) => {
	console.log(`${channel.name} channel's position has been updated: \`${oldPosition}\` -> \`${newPosition}\``)
})
```
---
-	`textChannelNsfwStatusUpdate` Emitted when a text channel's NSFW status was updated <a name="textChannelNsfwStatusUpdate"></a>
parametters:

| name    | type      | description                                          |
| ------- | --------- | ---------------------------------------------------- |
| channel | `Channel` | The text channel whose NSFW status have been updated |
| oldNSFW | `Boolean` | The old NSFW status                                  |
| newNSFW | `Boolean` | The new NSFW status                                  |

```js
client.on("textChannelNsfwStatusUpdate", (channel, oldNSFW, newNSFW) => {
	console.log(`${channel.name} channel's position has been updated: \`${oldNSFW}\` -> \`${newNSFW}\``)
})
```
---
-	`textChannelRateLimitPerUserUpdate` Emitted when a text channel's rate limit was updated <a name="textChannelRateLimitPerUserUpdate"></a>
parametters:

| name         | type      | description                                         |
| ------------ | --------- | --------------------------------------------------- |
| channel      | `Channel` | The text channel whose rate limit have been updated |
| oldRateLimit | `Number`  | The old rate limit                                  |
| newRateLimit | `Number`  | The new rate limit                                  |

```js
client.on("textChannelRateLimitPerUserUpdate", (channel, oldRateLimit, newRateLimit) => {
	console.log(`${channel.name} channel's rate limit has been updated: \`${oldRateLimit}\` -> \`${newRateLimit}\``)
})
```
---
-	`textChannelTopicUpdate` Emitted when a text channel's topic was updated <a name="textChannelTopicUpdate"></a>
parametters:

| name     | type      | description                                    |
| -------- | --------- | ---------------------------------------------- |
| channel  | `Channel` | The text channel whose topic have been updated |
| oldTopic | `String`  | The old topic                                  |
| newTopic | `String`  | The new topic                                  |

```js
client.on("textChannelTopicUpdate", (channel, oldTopic, newTopic) => {
	console.log(`${channel.name} channel's topic has been updated: \`${oldTopic}\` -> \`${newTopic}\``)
})
```
---
-	`voiceChannelUserLimitUpdate` Emitted when a voice channel's user limit was updated <a name="voiceChannelUserLimitUpdate"></a>
parametters:

| name         | type      | description                                          |
| ------------ | --------- | ---------------------------------------------------- |
| channel      | `Channel` | The voice channel whose user limit have been updated |
| oldUserLimit | `String`  | The old user limit                                   |
| newUserLimit | `String`  | The new user limit                                   |

```js
client.on("voiceChannelUserLimitUpdate", (channel, oldUserLimit, newUserLimit) => {
	console.log(`${channel.name} channel's user limit has been updated: \`${oldUserLimit}\` -> \`${newUserLimit}\``)
})
```
---
-	`voiceChannelBitrateUpdate` Emitted when a voice channel's bitrate was updated <a name="voiceChannelBitrateUpdate"></a>
parametters:

| name       | type      | description                                       |
| ---------- | --------- | ------------------------------------------------- |
| channel    | `Channel` | The voice channel whose bitrate have been updated |
| oldBitrate | `Number`  | The old bitrate                                   |
| newBitrate | `Number`  | The new bitrate                                   |

```js
client.on("voiceChannelBitrateUpdate", (channel, oldBitrate, newBitrate) => {
	console.log(`${channel.name} channel's bitrate has been updated: \`${oldBitrate}\` -> \`${newBitrate}\``)
})
```
---
-	`channelUndefinedUpdate` Emitted when the ChannelUpdate event was emitted but any event was trigerred <a name="channelUndefinedUpdate"></a>

parametters:

| name       | type      | description     |
| ---------- | --------- | --------------- |
| oldChannel | `Channel` | The old channel |
| newChannel | `Channel` | The new channel |

```js
client.on("channelUndefinedUpdate", (oldChannel, newChannel) => {
	console.log(`${channel.name} channel was updated but any event was triggered`)
})
```



