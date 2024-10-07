# ali

**ali** is a lightweight shell utility to list all active aliases, display their corresponding commands, and show where they were defined. It works with both `bash` and `zsh` shells, and it automatically searches sourced files to identify the origin of aliases.

## Features

- Lists all active aliases with their commands.
- Shows the source file where each alias is defined.
- Truncates long commands for easier readability (with asterisk `*` to indicate truncation).
- Recursively tracks aliases defined in sourced files up to 10 levels deep.

## Installation

### Prerequisites
- `bash` or `zsh` shell.
- Ensure `~/.local/bin` is included in your `PATH`.

### Installation Options

#### 1. Direct Download

To install **ali** directly into your `~/.local/bin/` directory:

```bash
mkdir -p ~/.local/bin
curl -L https://raw.githubusercontent.com/MohamedElashri/ali/main/ali -o ~/.local/bin/ali
chmod +x ~/.local/bin/ali
```

#### 2. Git Clone

You can also clone the repository and install the tool:

```bash
git clone https://github.com/MohamedElashri/ali.git
cd ali
mkdir -p ~/.local/bin
cp ali ~/.local/bin/
chmod +x ~/.local/bin/ali
```

#### 3. Manual Installation

1. Download the `ali` script.
2. Move it to your local binaries folder and give it executable permissions:

```bash
mkdir -p ~/.local/bin
mv ali ~/.local/bin/
chmod +x ~/.local/bin/ali
```

Ensure `~/.local/bin` is in your `PATH`. If not, add it to your shell configuration:

```bash
# For bash users
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# For zsh users
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### Usage

Once installed, simply run:

```bash
ali
```

This will print a table of your current shell aliases, their commands, and the location (file) where they were defined. If a command is too long, it will be truncated and marked with an asterisk `*`. At the end of the output, there will be a note explaining the truncation.

### Example Output

```bash
Alias                Command                                                 Location                         
-----                -------                                                 --------                         
c                    clear                                                        ~/.bash_aliases                      
count                find . -type f | wc -l                                       ~/.bash_aliases                      
cpv                  rsync -ah --info=progress2                                   ~/.bash_aliases
showdisk             echo "The disk usage is: $(df -h | awk '\''$NF=="/...*       ~/.bash_aliases                      
* indicates that the command has been truncated. Please refer to the source file for the full command.
```

### Contributing

Contributions are welcome! If you'd like to contribute, feel free to open issues or submit pull requests.

### License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/MohamedElashri/ali/blob/main/LICENSE) file for details.

---
