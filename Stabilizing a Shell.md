
## **Process**
1. First, verify `python` or `python3`
	-  `which python`
		- or
	- `which python3`
2. Next, import the `pty` Module and Spawn a Bash Shell :
	1. `python3 -c 'import pty;pty.spawn("/bin/bash")'`
3. Background the Process
	1. Press -> `Ctrl + Z`
4. Adjust Terminal Line Settings and Bring the Shell to the Foreground
	1. `stty raw -echo; fg`
5. Set the Terminal Emulator to xterm
	1. `export TERM=xterm`

---
## Explanation

- The `pty` module is pivotal for creating and managing pseudo-terminals, which allow us to interact programmatically with processes and their controlling terminals.
- The `pty.spawn()` function is used to start a new process and link its controlling terminal with the current process’s standard I/O. This establishes a more interactive connection.
- The `stty` command enables us to modify terminal settings. By using `stty raw`, we activate raw mode, which reads characters one at a time instead of waiting for a complete line. The `stty -echo` command disables echoing, preventing your input from being displayed on the screen.
- The `export TERM=xterm` command sets the terminal emulator to `xterm`. This ensures that the system interprets the terminal characteristics correctly for a smoother interaction.