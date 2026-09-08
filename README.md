# BIMSurfTool — releases

This repository is how BIMSurfTool is distributed and how an installed copy finds out that a newer
one exists. It is not the project.

## There is no source code here

BIMSurfTool is closed source. Its source lives in a private repository and is not published
anywhere.

Every GitHub release page carries **Source code (zip)** and **Source code (tar.gz)** links. GitHub
attaches those to every release automatically and offers no way to remove them. On this repository
they contain this README file and nothing else — there has never been a line of product source in
this repository, and there never will be.

## What is here

- One release per version, tagged with that version number.
- A single asset on each: `BIMSurfTool-<version>-Installer.exe`, for Windows.
- Release notes saying why that version is worth installing.

That is the whole of it. This repository is public for one reason: the add-in reads the newest
version number from it without needing a token, and a token shipped inside an installer is a token
anybody can take back out.

## Getting it

**Contact the BIM team for the installer.** Whoever hands out installers decides who gets which
build and when.

Installing is per-user. It writes to your own `%APPDATA%` and needs no administrator rights.
Installing over an existing copy keeps every Set, Job and schedule you have saved. Windows
SmartScreen may question the installer, because it is not code-signed yet.

Revit 2021 to 2027. The installer sets up only the releases you have.

## What the update check sends

Once a day at most, and only in a Revit session with somebody in front of it, BIMSurfTool asks this
repository for the number of the newest release. The request reaches GitHub, which can see the IP
address it came from, as any web request would.

Nothing else is sent. Not the models you have open, not file names or paths, not project or account
names, not your user name, and nothing about what you did in Revit. The answer that comes back is a
version number and the release notes text.

If the request fails — offline, behind a proxy, blocked, or rate-limited — the add-in says so
plainly in its About window and carries on. Nothing waits on it and nothing is retried in a hurry.

---

© 2026 BIM Surf Co., Ltd. All rights reserved.
