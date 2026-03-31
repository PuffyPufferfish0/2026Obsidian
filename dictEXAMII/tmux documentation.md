# `tmux` Documentation & Cheat Sheet

> [!info] **Prefix Key Note:** Most `tmux` shortcuts require you to press the "Prefix" key first before typing the command letter. By default, the prefix is **`Ctrl + b`**.

## 1. Core Concepts

|Concept|Description|
|---|---|
|**What is it?**|A terminal multiplexer that allows you to run and manage multiple "pseudo-terminals" from a single terminal window.|
|**Session Persistence**|`tmux` keeps processes running in the background even if your SSH connection drops or you close the terminal.|
|**Attach**|Connecting your current terminal view to a background `tmux` session.|
|**Detach**|Disconnecting your view from the `tmux` session while leaving it running.|

## 2. Session Management (Typed in standard terminal)

_These commands are typed directly into your normal command line, outside of a `tmux` window._

|Command|Action|
|---|---|
|`tmux ls`|List all active `tmux` sessions.|
|`tmux new -s [name]`|Create a new session with a specific name.|
|`tmux attach -t [name]`|Attach to a specific running session.|
|`tmux kill-session -t [name]`|Kill a specific session.|

## 3. Window Management (Inside tmux)

_Press **`Ctrl-b`**, release, then press:_

|Keybind|Action|
|---|---|
|`c`|Create a new window.|
|`w`|List all windows.|
|`n`|Move to the next window.|
|`p`|Move to the previous window.|
|`f`|Find a window.|
|`,`|Rename the current window.|
|`&`|Kill the current window.|

## 4. Pane Management (Inside tmux)

_Press **`Ctrl-b`**, release, then press:_

|Keybind|Action|
|---|---|
|`%`|Split pane vertically (left/right).|
|`"`|Split pane horizontally (top/bottom).|
|`o`|Swap panes.|
|`q`|Show pane numbers.|
|`x`|Kill the current pane.|
|`+`|Break pane into its own new window.|
|`-`|Restore pane from window.|
|`Space`|Toggle between pane layouts.|
|`{`|Move pane left.|
|`}`|Move pane right.|
|`z`|Toggle pane zoom (maximize/restore).|
|_Arrow Keys_|Resize current pane (Up, Down, Left, Right).|

## 5. Copy Mode (Inside tmux)

_Press **`Ctrl-b`**, release, then press:_

|Keybind|Action|
|---|---|
|`[`|Enter copy mode (allows scrolling and selecting).|
|`Space`|Start text selection.|
|`Enter`|Copy the selected text.|
|`Esc`|Clear the selection.|
|`]`|Paste the copied text.|