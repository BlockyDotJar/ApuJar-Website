# Admin command overview

??? info "say"
    Lets the bot say a message in the current chat.

    ```java
    Usage: <prefix>say <message>
    ```

    | Parameter | Description                                      |
    | --------- | ------------------------------------------------ |
    | `prefix`  | Your channel specific prefix (**Default:** kok!) |
    | `message` | The message to send in the current chat          |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No message specified
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat


??? info "spam"
    Lets the bot spam a certain amount of messages in the current chat.

    ```java
    Usage: <prefix>spam <amount> <message>
    ```

    | Parameter | Description                                                                                             |
    | --------- | ------------------------------------------------------------------------------------------------------- |
    | `prefix`  | Your channel specific prefix (**Default:** kok!)                                                        |
    | `amount`  | The amount of messages to spam in the current chat (Can't be higher than 100 without owner permissions) |
    | `message` | The message to spam in the current chat                                                                 |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No number specified
        * First parameter not numeric
        * Number bigger than 100 without having owner permissions
        * No message specified
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat


??? info "usersay"
    ```yaml
    Alias: usay
    ```

    Lets the bot say a message in a specific chat.

    ```java
    Usages: 
    <prefix>usay @username <message>
    <prefix>usersay @username <message>
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** kok!)                             |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |
    | `message`  | The message to send in the specified chat                                    |

    If a channel specific (global) command is specified in the message, the output from the command will be sent.

    **For example:**

    ```yaml
    kok!usay blockydotjar kok!ping
    ```

    !!! danger "Prefix needs to match the prefix of the specified channel"
        **For example:** A user set the prefix to `lolxd!`, than the command must look like this:

        ```yaml
            kok!usay blockydotjar lolxd!ping
        ```

    **A message like this will be sent in chat 'blockydotjar':**

    ```cpp
    ppPong Chat-Ping: 296ms FeelsLateMan I'm active in 7 chats Okay Uptime: 0d 0h 0m 32s FeelsOldMan RAM: 7,80 / 15,80 GiB hmmMeeting CPU(%): 1,21% top 
    ```

    This is possible with every command, expect for admin and owner commands.

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * No message specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat
        * Message contains owner or admin commands


??? info "userspam"
    ```yaml
    Alias: uspam
    ```

    Lets the bot spam a certain amount of messages in the specified chat.

    ```java
    Usages: 
    <prefix>uspam @username <amount> <message>
    <prefix>userspam @username <amount> <message>
    ```

    | Parameter  | Description                                                                                               |
    | ---------- | --------------------------------------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** kok!)                                                          |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character)                              |
    | `amount`   | The amount of messages to spam in the specified chat (Can't be higher than 100 without owner permissions) |
    | `message`  | The message to spam in the specified chat                                                                 |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * No number specified
        * Second parameter not numeric
        * Number bigger than 100 without having owner permissions
        * No message specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat


??? danger "crossban (Not fully functional atm; functionality will change in future)"
    ```yaml
    Alias: cb
    ```

    Lets the bot ban a user in every chat, he is mod in.

    ```java
    Usages: 
    <prefix>cb @username
    <prefix>crossban @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** kok!) 					         |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * No one got banned, because the bot is not a mod in any chat


??? danger "crossunban (Not fully functional atm; functionality will change in future)"
    ```yaml
    Alias: cub
    ```

    Lets the bot unban a user in every chat, he is mod in.

    ```java
    Usages: 
    <prefix>cub @username
    <prefix>crossunban @username
    ```

    | Parameter  | Description                                                     	         |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** kok!) 					         |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * No one got unbanned, because the bot is not a mod in any chat


??? info "addglobalcommand"
    ```yaml
    Aliases: addgcmd, addglobalcmd
    ```

    Adds a global command that can be used in every chat, the bot currently is in.
    <br>The global command name can't have the same name as already existing (built in/global) commands.

    ```java
    Usages: 
    <prefix>addgcmd <command-name> <command-message>
    <prefix>addglobalcmd <command-name> <command-message>
    <prefix>addglobalcommand <command-name> <command-message>
    ```

    | Parameter         | Description                                                                             |
    | ----------------- | --------------------------------------------------------------------------------------- |
    | `prefix`          | Your channel specific prefix (**Default:** kok!)                                        |
    | `command-name`    | The name for the global command (Can contain prefix, Can't contain the **'** character) |
    | `command-message` | The message for the global command (Can't contain the **'** character)                  |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * No command message specified
        * Global command name already exists
        * Bot command with specified global command name already exists
        * Command name only contains **'** character
        * Command message only contains **'** character


??? info "editglobalcommand"
    ```yaml
    Aliases: editgcmd, editglobalcmd
    ```

    Edits a global command message.

    ```java
    Usages: 
    <prefix>editgcmd <command-name> <new-command-message>
    <prefix>editglobalcmd <command-name> <new-command-message>
    <prefix>editglobalcommand <command-name> <new-command-message>
    ```

    | Parameter             | Description                                                                |
    | --------------------- | -------------------------------------------------------------------------- |
    | `prefix`              | Your channel specific prefix (**Default:** kok!)                           |
    | `command-name`        | The name of the global command                                             |
    | `new-command-message` | The new message for the global command (Can't contain the **'** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * No command message specified
        * Global command doesn't exists
        * New command message only contains **'** character
        * New command message matches exactly with the old one


??? info "deleteglobalcommand"
    ```yaml
    Aliases: delgcmd, delglobalcmd, delglobalcommand, deleteglobalcmd
    ```

    Deletes a global command.

    ```java
    Usages: 
    <prefix>delgcmd <command-name>
    <prefix>delglobalcmd <command-name>	
    <prefix>delglobalcommand <command-name>
    <prefix>deleteglobalcmd <command-name>
    <prefix>deleteglobalcommand <command-name>
    ```

    | Parameter      | Description                                      |
    | -------------- | ------------------------------------------------ |
    | `prefix`       | Your channel specific prefix (**Default:** kok!) |
    | `command-name` | The name of the global command                   |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * Global command doesn't exists

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).