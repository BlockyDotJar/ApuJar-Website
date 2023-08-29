# Owner command overview

??? info "addowner"
    Promotes a user as an bot owner.

    ```java
    Usage: <prefix>addowner @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch api
        * User already promoted


??? info "delowner"
    ```yaml
    Alias: deleteowner
    ```

    Demotes a bot owner.

    ```java
    Usages:
    <prefix>delowner @username
    <prefix>deleteowner @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * User is not an owner


??? info "addadmin"
    Promotes a user as an bot admin.

    ```java
    Usage: <prefix>addadmin @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch api
        * User already promoted


??? info "deladmin"
    ```yaml
    Alias: deleteadmin
    ```

    Demotes a bot admin.

    ```java
    Usages:
    <prefix>deladmin @username
    <prefix>deleteadmin @username
    ```

    | Parameter   | Description                                                                             |
    | ----------- | --------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                     |
    | `username`  | The name of the user            (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No username specified
        * Specified user is not even an admin
        * Specified user is an owner
    

??? info "exit"
    Closes database connection, disconnects from every Twitch websocket and exits the System

    ```java
    Usages: <prefix>exit
    ```

    | Parameter   | Description                                         |
    | ----------- | --------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!) |

    !!! failure "Possible errors"
        * Message sender is not an owner


??? info "sql"
    Executes sql commands in the connected database and sends database metadata.

    ```java
    Usages: <prefix>sql <SQL-code>
    ```

    | Parameter   | Description                                         |
    | ----------- | --------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!) |
    | `SQL-Code`  | The sql code to execute.                            |

    !!! failure "Possible errors"
        * Message sender is not an owner
        * No sql code specified

