## AutoVol - A GUI Memory Forensics Tool Based on Volatility 2&3
<img src=https://raw.githubusercontent.com/hermit403/AutoVol3/refs/heads/master/icon.png width="20%">

### Quick Start

1. Configure your Python virtual environment

```bash
python -m venv env
.\env\Scripts\activate
```

2. Configure pip

```bash
python -m pip install --upgrade --force-reinstall pip
```

3. Install Volatility3

```bash
pip install volatility3
```

4. Now you can run this program.

### Custom Task

We use the `.toml` file to configure the task of AutoVol3. You may need to know some grammars about TOML first.

And the configuration is very simple. The following is a complete task example:

```toml
name = "tiny-scan"
# The name of this task
author = "AutoVol3"
# Author name
arch = "windows"
# The arch of target, e.g. windows | mac | linux
[settings]
# Main Settings
parent = []
# The parent task, your task will execute these parent tasks before this task
tasks = []
# Volatility3 commands
findstr = []
# Find target strings in output and parent tasks' output, AutoVol3 will try to find these strings and save them in the end of output file
regex = ["^\\w+([-+.\\w+)*@\\w+([-.]\\w+)*\\.\\w+([-.]\\w+)*$"]
# Find target strings in output and parent tasks' output, same as above, but use regex
dumpfiles = false
# If you set "true", AutoVol3 will dump matching files after this task
[output]
console = false
# Output full content to the console
```
