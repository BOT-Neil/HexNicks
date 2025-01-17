<img align="right" src="https://raw.githubusercontent.com/Majekdor/HexNicks/master/hexnicks.png" height="200" width="200">

# HexNicks

HexNicks is a simple nickname plugin that allows players to set their nickname to anything they like containing normal colors, hex colors, and even gradients! It fully supports Spigot and Paper, though forks of those should work as well. There are only a few commands and permissions to limit what players use what commands. Though the plugin does have support for MySQL storage, it's mostly intended to be a simple nickname plugin for smaller Spigot/Paper servers.

## Commands

There are 5 plugin commands:
- `/nick <nickname>` - Set your own nickname.
- `/nickother <player> <nickname>` - Set another player's nickname.
- `/nonick [player]` - Remove your nickname or another player's nickname.
- `/nickcolor <color>` - Change the color of your nickname.
- `/nicksreload` - Reload the plugin.

## Permissions

`hexnicks.nick`, `hexnicks.nonick`, and `hexnicks.nickcolor` are given to all players by default but can be negated by a permissions manager like [LuckPerms](https://luckperms.net/).
- `hexnicks.nick` - Permission to change your own nickname.
- `hexnicks.nick.other` - Permissions to change other player's nicknames.
- `hexnicks.nonick` - Permission to remove your own nickname.
- `hexnicks.nonick.other` - Permission to remove other player's nicknames.
- `hexnicks.nickcolor` - Permission to change your nickname color.
- `hexnicks.reload` - Permission to reload the plugin.

## Colors

### Introducing gradients!

Unless changed in the config, legacy color codes (&c, &l, etc.) are not supported. They can be losely supported when the config option is enabled, but the plugin uses [MiniMessage](https://docs.adventure.kyori.net/minimessage.html) for colors and formatting.

<img align="middle" src="https://i.imgur.com/zdn80Qe.png">

Now HexNicks makes it easy to get beautiful gradients in your nicknames. The formatting is simple, for the example above the command was: `/nick <gradient:#1eae98:#d8b5ff>Majekdor</gradient>`

> Note: The closing tag is optional if you don't want anything after the initial text.

The first gradient tag can also take more than 2 hex codes, though they must be in the standard six-character hex format.


### Hex Colors:

I'll just leave this here for you :)

<img align="middle" src="https://i.pinimg.com/originals/f2/08/30/f2083044743edea046c2bc16b082b4fe.gif" height="900" width="800">

## For the nerds... I mean devs :P

HexNicks does have an api and all commands trigger an event when executed. These events can be listened to the same way as other Bukkit events. You can see the events [here](https://github.com/Majekdor/HexNicks/tree/master/src/main/java/dev/majek/hexnicks/api). No JavaDocs yet.

Event example:
```java
@EventHandler
public void onNickname(SetNickEvent event) {
  Player player = event.player();
  player.sendMessage("Setting nickname...");
  event.newNick(Component.text("New nickname"));
}
```

There are multiple ways to retrieve nicknames, but the easiest way is:
```java
Nicks.api().getNick(player); // You can pass thru a player, offlineplayer, or uuid
```

## Support

If you need help with the plugin and can't find the answer here or on Spigot, then the best way to get help is to join my [Discord](https://discord.gg/CGgvDUz). Make sure you read the frequently-asked channel before posting in the bug-reports channel (if it's a bug) or in the simple-homes channel (for general help).

If you have discovered a bug you can either join my [Discord](https://discord.gg/CGgvDUz) and report it there or open an issue here on GitHub. Please do not message me on Spigot in regard to a bug, there are easier ways to communicate.


## Contributing

SimpleHomes is open-source and licensed under the [MIT License](https://github.com/Majekdor/SimpleHomes/blob/main/LICENSE), so if you want to use any code contained in the plugin or clone the repository and make some changes, go ahead!

If you've found a bug within the plugin and would like to just make the changes to fix it yourself, you're free to do so and make a pull request here on GitHub. If you make significant contributions to the project, and by significant I mean one little PR to fix a tiny bug doesn't count as significant, you can earn the Contributor role in my [Discord](https://discord.gg/CGgvDUz).


## Donate

I'm a full time college student who makes and supports these plugins in my free time (when I have any). As a long time supporter of open source, most of my plugins are free. If you enjoy my plugins and would like to support me, you can buy me coffee over on  [PayPal](https://paypal.com/paypalme/majekdor). Donations of any amount are appreciated and a donation of $10 or more will get you the Supporter role in my [Discord](https://discord.gg/CGgvDUz)!
