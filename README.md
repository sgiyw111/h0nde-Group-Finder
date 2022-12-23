# Roblox Group Finder

# Don't waste your time
If you're simply just looking to claim a couple groups, use some discord servers.
- https://discord.gg/hF7YqcUebc [Rx's Server]
- https://discord.gg/eSjbvZvUFN [Tokyo Club]
- https://discord.gg/XPqSrE5pxX [Metrik Utilities]
- https://discord.gg/HxnPVn8hAf [Rose Traders]

# Features
- High-performance scanning (up to 50M+ checks-per-minute)
- Zero dependencies
- Automatic ID calibration on start
- Webhook and HTTP proxy support

# Setup
0. Download the [latest release](https://www.python.org/downloads/) of Python and install it with the [Add to PATH](https://datatofish.com/wp-content/uploads/2018/10/0001_add_Python_to_Path.png) option checked.
1. [Download](https://github.com/NotZkoo/h0nde-Group-Finder/archive/refs/heads/main.zip) this repository and extract it to a folder.
2. Fill proxies.txt with your HTTP proxies.
3. Click the `File` tab on your file explorer window, then click `Open PowerShell`.
4. Execute the command in the `Usage` section below.

# Usage
```bash
python finder.py --workers 16 --proxy-file proxies.txt
```

```
-w <num>, --workers <num>
                      Number of workers
-t <num>, --threads <num>
                      Number of threads (per worker)
-r <range> [<range> ...], --range <range> [<range> ...]
                      Range(s) of group IDs
-p <file>, --proxy-file <file>
                      File containing HTTP proxies
-u <url>, --webhook-url <url>
                      Send group results to <url>
-c <id>, --cut-off <id>
                      ID limit for skipping missing groups
-C <size>, --chunk-size <size>
                      Number of groups to be sent per batch request
-T <seconds>, --timeout <seconds>
                      Timeout for connections and responses
```

# --webhook-url
If the `--webhook-url` arg. is specified, an embed will be sent whenever a claimable group is found. E.g.:

![68747470733a2f2f692e696d6775722e636f6d2f56654d426f43412e706e67](https://user-images.githubusercontent.com/110559679/209333716-9385412c-59f9-453a-b283-bb4b294b6f3e.png)

# --cut-off
By default, when encountering a missing/deleted group, it's ID will be removed from the queue so that it won't be checked again.

The `--cut-off` argument specifies at which ID (and above) missing groups shouldn't be removed from the queue. This is ideal in scenarios where you also wanna scan groups that haven't been created yet.
