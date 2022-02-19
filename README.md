# OpenArena Legacy Repository # 

Legacy source code releases from [OpenArena](http://openarena.ws).
The game data is still in OpenArena's SVN repository hosted on the site itself.

This is an archive of the OpenArena 0.8.8 release code.  No new development
happens here.

The current development of OpenArena code happens in two places

* [engine.git](https://github.com/OpenArena/engine.git) project for the new
engine, and
* [gamecode.git](https://github.com/OpenArena/gamecode.git) for the new game code.

## Checksums ##

Checksums and locations for the original code:

* [OA game code](http://files.poulsander.com/~poul19/public_files/oa/dev088/oa-0.8.8.tar.bz2)
* [OA engine](http://files.poulsander.com/~poul19/public_files/oa/dev088/openarena-engine-source-0.8.8.tar.bz2)

```sh
$ md5sum *.bz2
5a55bb7660a711949a69a2bc40fdc11b  oa-0.8.8.tar.bz2
ca9b239b477ad678ebf781e14ce6ed7a  openarena-engine-source-0.8.8.tar.bz2

$ sha1sum *.bz2
6bb139e469ae00e37decaefb5e2bced070f8b04e  oa-0.8.8.tar.bz2
64f333c290b15b6b0e3819dc120b3eca2653340e  openarena-engine-source-0.8.8.tar.bz2

$ sha512sum *.bz2
517517ea8d8377a6d91d957faf0a55690815b01d8f3e8b1e4a3e6be64750968a6074d26499e707fe2ec5fa7d630ceec022fdc879fdebcbfebbcff8195dd03e2f  oa-0.8.8.tar.bz2
d4ba3655fae500cf5b7475c83d39c81b6abc759da15cfb4ea9e1dc0f47ffb11c1bbbc2b6f85d613ab1d729978eda93d4d7677c9a45a33853e363c820d8b81c43  openarena-engine-source-0.8.8.tar.bz2
```

---

# CI Builds for macOS x86_64

With the release of Catalina (macOS 10.15), Apple dropped support for 32-bit
binaries. This means the "universal binaries" in the official OpenArena 0.8.8
Unified Zip no longer work on macOS. This repository aims to provide 64-bit
replacement binaries that can be copied into the Unified Zip.

1. Go to the GitHub Actions page and download the latest build artifact.
2. Extract the Zip and locate x86_64 binaries inside.
3. Give execute permission and remove quarantine attribute:
    ```
    chmod +x *.x86_64
    xattr -d com.apple.quarantine *.x86_64
    ```
4. Copy files into root folder of OpenArena 0.8.8 Unified Zip from
http://openarena.ws/download.php, replacing existing files with the same names.
5. Run from command line: `./openarena.x86_64`

Currently the game runs (main menu appears) but crashes when you actually try
to load an arena to fight in.
