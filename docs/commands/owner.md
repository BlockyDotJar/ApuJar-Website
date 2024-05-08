# Owner command overview

??? info "addowner"
    Promotes a user as an bot owner.

    ```java
    Usage: <prefix>addowner @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not the bot founder
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * User already promoted


??? info "deleteowner"
    ```yaml
    Alias: delowner
    ```

    Demotes a bot owner.

    ```java
    Usages:
    <prefix>delowner @username
    <prefix>deleteowner @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not the bot founder
        * No username specified
        * User is not an owner


??? info "addadmin"
    Promotes a user as an bot admin.

    ```java
    Usage: <prefix>addadmin @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * User already promoted


??? info "deleteadmin"
    ```yaml
    Alias: deladmin
    ```

    Demotes a bot admin.

    ```java
    Usages:
    <prefix>deladmin @username
    <prefix>deleteadmin @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * Specified user is not even an admin
        * Specified user is an owner
    

??? info "exit"
    Closes database connection, disconnects from every Twitch websocket and exits the System.

    ```java
    Usage: <prefix>exit
    ```

    | Parameter | Description                                   |
    | --------- | --------------------------------------------- |
    | `prefix`  | Your channel specific prefix (**Default:** #) |

    !!! failure "Possible errors"
        * Message sender is not an owner


??? info "sql"
    Executes sql commands in the connected database and sends database metadata.

    ```java
    Usage: <prefix>sql <SQL-code>
    ```

    | Parameter  | Description                                   |
    | ---------- | --------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #) |
    | `SQL-Code` | The sql code to execute                       |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No sql code specified


??? info "globalsay"
    ```yaml
    Alias: gsay
    ```

    Lets the bot say a message in every chat he is in.

    ```java
    Usages:
    <prefix>gsay <message>
    <prefix>globalsay <message>
    ```

    | Parameter | Description                                   |
    | --------- | --------------------------------------------- |
    | `prefix`  | Your channel specific prefix (**Default:** #) |
    | `message` | The message to send in the every chat         |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No message specified
        * Message contains **/** (slash) commands

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).