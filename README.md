<h1 align="center">SaveSites</h1>

<p align="center">The collection of scripts for wget and wayback_machine_downloader.</p>

## Features

- Save sites by domain, saving as much content as possible.
- Automatically zip downloaded sites (see the "Notes" section).
- Save by lists (gently).

---

## Installation (Linux, macOS)

Install `wget`, `dig`, `whois`.

Install [MiceWeb](https://github.com/Robotizing/MiceWeb/).

Install [Wayback Machine Downloader](https://github.com/ImportTaste/wayback-machine-downloader/).

Create a folder where you want your sites downloaded in a drive where you have enough space available.

---

## Installation (Windows)

Install [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) (requires about 2GB disk space), [Cygwin](https://www.cygwin.com/), [Git Bash](http://git-scm.com), or some other tool that enables Bash functionality in Windows.

Follow the above section.

Also, there are alternative ways to download web sites: `Teleport Pro`, `PageNest`.

---

## Usage

Open a terminal in the folder and run `./save` or other script with arguments.

### Save quickly:
`./save example.com`

### Save from start URL:
`./save example.com http://www.example.com/page.htm`

### Save with parameters (see the save script to understand the logic):
`./save example.com http://www.example.com/subdir --include-directories=/subdir`

`./save example.com http://www.example.com --exclude-directories=/trash --header="Accept: text/html"`

`./save example.com http://www.example.com --wait=15 --random-wait`

`./save example.com http://www.example.com --reject="morehead.php3*"`

`./save forum.example.com http://forum.example.com --reject-regex="members.php|search.php"`

`./save example.com http://www.example.com --exclude-domains=ftp.example.com`

`./save example.com http://www.example.com/keyword-article.htm --accept-regex=keyword`

`export SAVESITES_DOMAINS=otherdomain1.com,otherdomain2.com ; ./save example.com` 

### Save gently (little delays):
`./save_gently example.com`

### Save by list (gently):
`./save_by_list example.txt`

### Save from the Wayback Machine:
`./save_archived example.com`

`./save_archived_by_list example.txt`

### Save site maps:
`./save_archivedmap portal.com`

`./save_maps_by_list portals.txt`

### Save all sites from collection.txt:
`./save_collection`

---

## Notes

Each site may contain thousands and tens thousands files, that's why the scripts zip downloaded sites. Also, it resolves porential issues related to supporting filenames in various file systems.

Mount zips: use [Zipster](https://ipfs.io/ipfs/QmUBbaw45ebpNB8oTPd5jR8n6v8oGJ9UMKMmnWYmX4Sk8Z) on macOS, `avfs` on Linux, some tool like `WinMount` on Windows. So, you don't have to unpack zip-files to work with sites.

Visit Cloudflare sites in browser, then use generated cookie as a parameter.

Savings from the Wayback Machine are designed for restoration, not for browsing. Limited to `100K` snapshots per site (however, you can set `SAVESITE_MAXSNAPSHOTPAGES` environment variable to some other value). Also, use `save_archivedmap` for portals.

Check downloaded sites.

---

## TODO

Version for Windows Shell, maybe with a simple GUI.

Autotest sites after downloaded.

Indicate date when existing site was downloaded, maybe resave it (preserving old) if it was a long time ago.

Save from the Wayback Machine with parameters (e.g., only specified URL).

Save site maps from Web (using wget `--spider` flag), seeing something like [this](https://jcode.me/find-missing-content-with-wget-spider/).

Allow resuming incompleted downloads (backup it first).

---

## Stargazers

[![Stargazers over time](https://starchart.cc/defder-su/SaveSites.svg)](https://starchart.cc/defder-su/SaveSites)

---

## Related Projects

- [SaveMedia](https://github.com/defder-su/SaveMedia)

- [SaveGit](https://github.com/defder-su/SaveGit)

- [RatBrowser](https://ratbrowser.com)

- [IPFS](https://ipfs.io)

- [ZeroNet](https://zeronet.dev)

---

## Contact

You are welcome in [Defder.info](https://defder.info).
