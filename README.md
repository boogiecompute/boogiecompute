<p align="center">
  <img src="assets/banner.png" alt="StockBack" width="100%" />
</p>

<!-- logo: drop the mark here -->

<h3 align="center">Buy from the brand. Own the brand.</h3>

<p align="center">
  Receipts and order emails, paid back in the brand's own tokenized stock.<br/>
  A Costco run pays in COST. Netflix pays in NFLX. GameStop pays in GME.<br/>
  Live on Robinhood Chain.
</p>

<p align="center">
  <a href="https://usestockback.xyz">Website</a> ·
  <a href="https://usestockback.xyz/app">Shelf</a> ·
  <a href="https://usestockback.xyz/scan">Scan a receipt</a> ·
  <a href="https://usestockback.xyz/docs">Docs</a> ·
  <a href="https://x.com/StockBackfam">X</a>
</p>

---

**How it works.** Photograph the till receipt or forward the order email. A model reads the merchant, the date and the total, checks the receipt is real and not already claimed, and matches the merchant to its ticker. The reward is bought at market as a tokenized share and sent to your own wallet in one step. Every brand on the shelf prints how long the last hundred rewards took to settle, in minutes, so you know before you scan.

**What is here**

- [stockback](https://github.com/stockbackrh/stockback): the site, the scanner, the claims API and the keeper, wired together.
- [receipt-reader](https://github.com/stockbackrh/receipt-reader): reads a till receipt in the browser. OCR, merchant match, total, date, fingerprint.
- [shelf](https://github.com/stockbackrh/shelf): every brand that pays in its own stock, its rate, its proof routes, its token on Robinhood Chain.
- [settlement-keeper](https://github.com/stockbackrh/settlement-keeper): one transaction from an accepted claim to shares in the claimant's wallet.
- [settlement-log](https://github.com/stockbackrh/settlement-log): the settlement medians the shelf prints, appended every few hours.

No points, no coupons, no card to apply for. Keep the receipt. It is a share now.
