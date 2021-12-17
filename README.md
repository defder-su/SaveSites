# SaveSites

## Features:

- Save sites by domain, saving as much content as possible.
- Automatically zip downloaded sites (see the "Notes" section).
- Save by lists (gently).

---

## Installation (Linux, macOS):

Install `wget`.

Create a folder where you want your sites downloaded in a drive where you have enough space available.

Open a terminal in the folder and run `chmod +x save*`.

---

## Installation (Windows):

Install [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) (requires about 2GB disk space), [Cygwin](https://www.cygwin.com/), [Git Bash](http://git-scm.com), or some other tool that enables Bash functionality in Windows.

Follow the above section.

---

## Usage:

Open a terminal in the folder and run `./save` or other script with arguments.

### Save quickly:
`./save example.com`

### Save from start URL:
`./save example.com http://www.example.com/page.htm`

### Save with parameters (see the save script to understand the logic):
`./save example.com http://www.example.com/subdir -np`

`./save example.com http://www.example.com -X /trash --header="Accept: text/html"`

### Save with random delays:
`./save_gently example.com`

### Save list:
`./save_by_list example.txt`

### Save default list:
`./save_by_list collection.txt`

`./save_collection`

---

## Notes:

Each site may contain thousands and tens thousands files, that's why the scripts zip downloaded sites.

Mount zips: use [Zipster](https://coriolis-systems.com) (seeing `/ipfs/QmUBbaw45ebpNB8oTPd5jR8n6v8oGJ9UMKMmnWYmX4Sk8Z`) on macOS, `avfs` on Linux, some tool like `WinMount` on Windows. So, you have not unpack zip-files to work with sites.

Limited to `100K` files per site (you can edit `MAXFILES` variable in the `save` script).

Visit Cloudflare sites in browser, then use generated cookie as parameter.

Check sites after downloaded.

---

## TODO:

Version for Windows Shell, maybe with a simple GUI.

Something like `./save example.com http://www.example.com otherdomain1.com otherdomain2.com`.

Autotest sites after downloaded.

---

## Contact:

You are welcome in [Defder.SU](https://defder.su).
