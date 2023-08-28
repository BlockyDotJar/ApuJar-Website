# Admin command overview

??? info "join"
    Lets the bot join a specific chat.

    ```java
    Usage: <prefix>join @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch api
        * Chat already joined


??? info "part"
    Lets the bot leave from a specific chat.

    ```java
    Usage: <prefix>part @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * Bot not connected to chat
        * Username does match with an owner name


??? info "say"
    Lets the bot say a message in the current chat.

    ```java
    Usage: <prefix>say <message>
    ```

    | Parameter   | Description                                                     |
    | ----------- | --------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix                (**Default:** kok!) |
    | `message `  | The message to send in the current chat.                        |

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

    | Parameter   | Description                                                                                                  |
    | ----------- | ------------------------------------------------------------------------------------------------------------ |
    | `prefix`    | Your channel specific prefix                            (**Default:** kok!)                                  |
    | `amount`    | The amount of messages to spam in the current chat      (Can't be higher than 100 without owner permissions) |
    | `message`   | The message to spam in the current chat.                                                                     |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No number specified
        * First parameter not numeric
        * Number bigger than 100 without having owner permissions
        * No message specified
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat


??? info "usay"
    ```yaml
    Alias: usersay
    ```

    Lets the bot say a message in a specific chat.

    ```java
    Usages: 
    <prefix>usay @username <message>
    <prefix>usersay @username <message>
    ```

    | Parameter   | Description                                                                                         |
    | ----------- | --------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix                (**Default:** kok!)                                     |
    | `username`  | The name of the user                        (**Case-Insensitive**, Can contain the **@** character) |
    | `message `  | The message to send in the specified chat.                                                          |

    If a bot command/channel specific command/global command is specified in the message, the output from the command will be sent.

    **For example:**

    ```yaml
    kok!usay blockydotjar kok!ping
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
        * User not found by Twitch api
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat
        * Message contains owner or admin commands


??? info "uspam"
    ```yaml
    Alias: userspam
    ```

    Lets the bot spam a certain amount of messages in the specified chat.

    ```java
    Usages: 
    <prefix>uspam @username <amount> <message>
    <prefix>userspam @username <amount> <message>
    ```

    | Parameter   | Description                                                                                                     |
    | ----------- | --------------------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix                            (**Default:** kok!)                                     |
    | `username`  | The name of the user                                    (**Case-Insensitive**, Can contain the **@** character) |
    | `amount`    | The amount of messages to spam in the specified chat    (Can't be higher than 100 without owner permissions)    |
    | `message`   | The message to spam in the specified chat.                                                                      |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No username specified
        * No number specified
        * Second parameter not numeric
        * Number bigger than 100 without having owner permissions
        * No message specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch api
        * Message contains **/** (slash) commands without having owner permissions
        * Message contains **/** (slash) commands with owner permission, but sender isn't mod at the specified chat
        * Message contains **/** (slash) commands with owner permission, but bot isn't mod at the specified chat


??? info "addgcmd"
    ```yaml
    Aliases: addgcommand, addglobalcmd, addglobalcommand
    ```

    Adds a global command that can be used in every chat, the bot currently is in.

    ```java
    Usages: 
    <prefix>addgcmd <command-name> <command-message>
    <prefix>addgcommand <command-name> <command-message>
    <prefix>addglobalcmd <command-name> <command-message>
    <prefix>addglobalcommand <command-name> <command-message>
    ```

    | Parameter           | Description                                                                                                                                                                              |
    | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | `prefix`            | Your channel specific prefix                (**Default:** kok!)                                                                                                                          |
    | `command-name`      | The name for the global command             (Can contain prefix, Can't contain the **'** character, Can't have the same name as already existing (bot/global/channel specific) commands) |
    | `command-message`   | The message for the global command          (Can't contain the **'** character)                                                                                                          |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * No command message specified
        * Global command name already exists
        * Bot command with specified global command name already exists
        * Command name only contains **'** character
        * Command message only contains **'** character


??? info "editgcmd"
    ```yaml
    Aliases: editgcommand, editglobalcmd, editglobalcommand
    ```

    Edits a global command message.

    ```java
    Usages: 
    <prefix>editgcmd <command-name> <new-command-message>
    <prefix>editgcommand <command-name> <new-command-message>
    <prefix>editglobalcmd <command-name> <new-command-message>
    <prefix>editglobalcommand <command-name> <new-command-message>
    ```

    | Parameter               | Description                                                                         |
    | ----------------------- | ----------------------------------------------------------------------------------- |
    | `prefix`                | Your channel specific prefix                    (**Default:** kok!)                 |
    | `command-name`          | The name of the global command.                                                     |
    | `new-command-message`   | The new message for the global command          (Can't contain the **'** character) |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * No command message specified
        * Global command doesn't exists
        * New command message only contains **'** character
        * New command message matches exactly with the old one


??? info "delgcmd"
    ```yaml
    Aliases: delgcommand, delglobalcmd, delglobalcommand, deletegcmd, deletegcommand, deleteglobalcmd, deleteglobalcommand
    ```

    Deletes a global command.

    ```java
    Usages: 
    <prefix>delgcmd <command-name>
    <prefix>delgcommand <command-name>
    <prefix>delglobalcmd <command-name>
    <prefix>delglobalcommand <command-name>
    <prefix>deletegcmd <command-name>
    <prefix>deletegcommand <command-name>
    <prefix>deleteglobalcmd <command-name>
    <prefix>deleteglobalcommand <command-name>
    ```

    | Parameter               | Description                                            |
    | ----------------------- | ------------------------------------------------------ |
    | `prefix`                | Your channel specific prefix       (**Default:** kok!) |
    | `command-name`          | The name of the global command.                        |

    !!! failure "Possible errors"
        * Message sender is not an admin
        * No command name specified
        * Global command doesn't exists

