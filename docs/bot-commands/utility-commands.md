# Utility command overview

??? info "join"
    Lets the bot join a specific chat.
    <br>If optional parameter **user** is specified, you need to make sure to be mod or broadcaster at this chat.
    <br>If you aren't mod or broadcaster at this chat, you need to have bot admin/owner permissions.

    ```java
    Usage: <prefix>join @username?
    ```

    | Parameter   | Description                                                                                           |
    | ----------- | ----------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                                   |
    | `username`  | The name of the user            (**Optional**, **Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Username specified, where sender isn't even a mod or broadcaster at, without having admin/owner permissions
        * Chat already joined
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch api


??? info "part"
    Lets the bot leave from a specific chat.
    <br>If optional parameter **user** is specified, you need to make sure to be mod or broadcaster at this chat.
    <br>If you aren't mod or broadcaster at this chat, you need to have bot admin/owner permissions.

    ```java
    Usage: <prefix>part @username?
    ```

    | Parameter   | Description                                                                                           |
    | ----------- | ----------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                                   |
    | `username`  | The name of the user            (**Optional**, **Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * Username specified, where sender isn't even a mod or broadcaster at, without having admin/owner permissions
        * Bot not connected to chat
        * Username does match with an owner name

