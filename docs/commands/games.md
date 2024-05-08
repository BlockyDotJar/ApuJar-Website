# Game command overview

??? info "tictactoe"
    ```yaml
    Alias: ttt
    ```

    Starts a classic round of tictactoe with another user.
    <br>If you specify ApuJar as the user to play with, you will play against a tictactoe ai.

    To play tictactoe you need to use the `tic` command with a value between 0 and 9.
    <br>The top left field is the number 1, the middle left field is the number 4 and the bottom left field is the number 7 and so on.

    To exit a game use the `leave` command.

    If the game is still running after 10 minutes, it will be deleted from the database.

    ```java
    Usages:
    <prefix>ttt @username
    <prefix>tictactoe @username
    ```

    | Parameter  | Description                                                                  |
    | ---------- | ---------------------------------------------------------------------------- |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                |
    | `username` | The name of the user (**Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * A game already exists for the current channel
        * No username specified
        * Username doesn't match with regex `^(?!_)\w+$`
        * User not found by Twitch API
        * You want to play with yourself


??? info "tic"
    Claims a field on the tictactoe board.
    <br>All classic tictactoe rules are considered.

    You can't claim a field twice and you can't claim already used fields by the opponent.
    <br>The first user to get 3 fields either horizontally, vertically or diagonally together wins.
    <br>If nobody wins after 9 rounds it is a draw.

    ```java
    Usage: <prefix>tic <field>
    ```

    | Parameter | Description                                                 |
    | --------- | ----------------------------------------------------------- |
    | `prefix`  | Your channel specific prefix (**Default:** #)               |
    | `field`   | The field to claim (Number must be between **1** and **9**) |

    !!! failure "Possible errors"
        * No tictactoe game exists in the current channel
        * It's not your turn
        * No field specified
        * Field number is not inbetween 1 and 9
        * The chosen field is already in use


??? info "leave"
    Leaves the current tictactoe session.
    <br>The other user of the tictactoe round will win the game, if you're leaving the session.

    ```java
    Usage: <prefix>leave
    ```

    | Parameter | Description                                   |
    | --------- | --------------------------------------------- |
    | `prefix`  | Your channel specific prefix (**Default:** #) |

    !!! failure "Possible errors"
        * No tictactoe game exists in the current channel
        * You don't play along

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).