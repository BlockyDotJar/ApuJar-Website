# Utility command overview

??? info "join"
    Lets the bot join a specific chat.
    <br>If the optional parameter **username** is specified, you need to make sure to be mod or broadcaster (if it is your own chat) in this chat.
    <br>If you aren't mod or broadcaster in this chat, you need to have bot admin/owner permissions to let the bot join there. (based on the sentence above)

    ```java
    Usage: <prefix>join @username?
    ```

    | Parameter   | Description                                                                                           |
    | ----------- | ----------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                                   |
    | `username`  | The name of the user            (**Optional**, **Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * **If username is specified:** Username specified, where sender isn't even a mod or broadcaster at, without having admin/owner permissions
        * **If username is specified:** Username doesn't match with regex `^(?!_)\w+$`
        * **If username is specified:** User not found by Twitch API
        * Chat already joined


??? info "part"
    Lets the bot leave from a specific chat.
    <br>If the optional parameter **username** is specified, you need to make sure to be mod or broadcaster (if it is your own chat) in this chat.
    <br>If you aren't mod or broadcaster in this chat, you need to have bot admin/owner permissions to let the bot part from there. (based on the sentence above)

    ```java
    Usage: <prefix>part @username?
    ```

    | Parameter   | Description                                                                                           |
    | ----------- | ----------------------------------------------------------------------------------------------------- |
    | `prefix`    | Your channel specific prefix    (**Default:** kok!)                                                   |
    | `username`  | The name of the user            (**Optional**, **Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * **If username is specified:** Username specified, where sender isn't even a mod or broadcaster at, without having admin/owner permissions
        * **If username is specified:** Username does match with an owner name
        * Bot not connected to chat

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).