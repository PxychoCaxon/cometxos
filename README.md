# cometxos
A linux-based OS (for now on Arch).

1. Creating the "Comet" Package Manager

run:
```
sudo nano /usr/bin/comet
```
then enter the following:
```
#!/bin/bash
# Rebranded Pacman: Comet

echo -e "\033[1;33m Incoming Comet...\033[0m"

# Now run the original pacman command
/usr/bin/pacman "$@"

if [ $? -eq 0 ]; then
    echo -e "\033[1;32m Comet successfully landed.\033[0m"
else
    echo -e "\033[1;31m Comet crashed!\033[0m"
fi
```

The script greets with "Incoming Comet..." in a bold yellow.
It runs the original pacman command (/usr/bin/pacman "$@"), so the underlying functionality stays the same.
Success (0 status code): It prints "Comet successfully landed." in green.
Failure (non-zero status code): It prints "Comet crashed!" in red.

2. update neofetch ascii

```
neofetch --ascii ~/path/to/comet.txt
```
in bashrc.

3. edit os-release

```
nano /etc/os-release
```

edit the following:

```
NAME="CometxOS"
PRETTY_NAME="CometxOS"
ID=comet
```
