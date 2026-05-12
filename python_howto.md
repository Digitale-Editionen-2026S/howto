# Python howto

## First: check if Python is already installed
Do this before installing anything.

### Windows
1. Open `cmd` (search for `cmd` in the Start menu).
2. Run `python --version`.
3. Also run `py --version`.

If one of them shows a version (for example `Python 3.12.x`), Python is already installed and in PATH, so you can stop here.

### Linux / macOS
1. Open a terminal.
2. Run `python3 --version`.

If it shows a version, Python is already installed and in PATH, so you can stop here.

## If you use Windows (and Python is missing)
1. Download Python from the official site: https://www.python.org/downloads/windows/
2. Run the installer.
3. Very important: on the first (?) installer screen, check the box `Add python.exe to PATH` (or `Add Python to PATH`).
4. Click `Install Now`.
5. Open a new `cmd` window and run:
	- `python --version`
	- `py --version`

If these commands work, installation is correct.

What PATH means (very short): PATH is the list of folders where Windows looks for commands. If Python is not added to PATH, `python` in `cmd` will not work.

## If you use Linux
Maybe Python is already there. If not, install it with your package manager:
- Debian/Ubuntu: `sudo apt update && sudo apt install python3`
- Fedora: `sudo dnf install python3`
- Arch: `sudo pacman -S python`

Then verify with `python3 --version`.

## If you use macOS
1. Open Terminal.
2. Check `python3 --version`.
3. If missing, install Homebrew if needed: https://brew.sh/
4. Install Python: `brew install python`
5. Verify again: `python3 --version`
