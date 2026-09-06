<div align="center">

<img src="assets/banner.png" alt="Boogie" width="100%" />

### Rent a GPU by the hour. Pay with the stocks you already hold.

<img src="https://readme-typing-svg.demolab.com?font=Space+Mono&weight=700&size=17&pause=2600&color=22C55E&center=true&vCenter=true&width=760&lines=Pick+a+machine%2C+pay+from+your+wallet%2C+get+a+card+that+boots+ready+to+work.;NVDA%2C+SPY%2C+QQQ%2C+TSLA+or+USDG.+The+swap+happens+inside+the+order.;Hours+start+when+the+machine+is+up%2C+not+when+you+pay.;Unused+time+comes+back.+Nothing+runs+longer+than+it+was+paid+for." alt="" />

[![Site](https://img.shields.io/badge/site-boogiecompute.com-22C55E?style=for-the-badge&labelColor=0d0f0e)](https://boogiecompute.com)
[![App](https://img.shields.io/badge/app-rent%20a%20GPU-22C55E?style=for-the-badge&labelColor=0d0f0e)](https://app.boogiecompute.com)
[![Docs](https://img.shields.io/badge/docs-read-8b938e?style=for-the-badge&labelColor=0d0f0e)](https://boogiecompute.com/docs)
[![X](https://img.shields.io/badge/X-@Boogie__Software-111111?style=for-the-badge&labelColor=0d0f0e)](https://x.com/Boogie_Software)

<sub>Robinhood Chain · settled onchain · no account, no API key</sub>

</div>

---

## The idea

Renting compute usually means a sales call, a quota request or a queue. Buying a
card means owning a depreciating machine for work that lasts an afternoon.

The work is short and heavy. Owning is long and expensive.

Boogie sells hours. You approve a ceiling in the asset you already hold, the
contract sells exactly as much of it as those hours cost, and the remainder comes
back in the same transaction. Nobody holds an equity position between the quote
and the machine.

```
   your wallet              the contract                 the machine
   ───────────              ────────────                 ───────────
   NVDA  SPY  QQQ           sells only what the          boots with the tool
   TSLA  USDG        ──▶    hours actually cost   ──▶    you picked, ready
                            returns the rest             to work
```

## Running today

| | |
|---|---|
| **Settled onchain** | Every order is a transaction you can read. The price at checkout is the amount recorded. |
| **Machines arrive ready** | A notebook with PyTorch, ComfyUI, a local model with a chat window, or an OpenAI-compatible endpoint. Models download while the machine boots. |
| **Hours start at boot** | Booting takes minutes and somebody pays for them. That somebody is us. |
| **Nothing overruns** | Time ends, machine stops. Stop earlier and the unused hours come back to the wallet that paid. |
| **No account** | Your SSH key is bound to your wallet by a signature. That binding decides whose key goes on the machine. |
| **Funds in one step** | Send USDC from six networks and it lands as USDG, usually within seconds. |

## Renting from code

No API key to request. The wallet that pays is what proves who you are, so a
script or an agent rents on the same terms as a person, with no human in the path.

```python
listings = requests.get("https://app.boogiecompute.com/api/catalog").json()["listings"]
machine  = min(listings, key=lambda m: m["usdPerHour"])

quote = requests.post("https://app.boogiecompute.com/api/quote", json={
    "machineId": machine["id"],
    "hours": 1,
    "template": 1,              # 0 notebook · 1 ComfyUI · 2 local LLM · 3 model API
    "payer": wallet.address,
}).json()
```

Six calls cover the whole path. Full walkthrough in the [docs](https://boogiecompute.com/docs#api).

## Repositories

| | | |
|---|---|---|
| [**boogie-contracts**](https://github.com/boogiecompute/boogie-contracts) | Settlement contract, tests and a worked example of renting from code | MIT |

The contract is live at
[`0x96Ce…F107`](https://robinhoodchain.blockscout.com/address/0x96Ce146534837BC995a8e65F45A34fEFFaF9F107)
on Robinhood Chain.

## Next

Work that survives the machine, so a folder follows you to the next card you rent.
Then hosting, so an idle GPU earns instead of collecting dust. That one waits on
proving the hours a host actually served, because supply nobody can verify is
worth nothing to the people renting it.

<div align="center">
<br>
<sub>Compute you rent by the hour, that behaves like it belongs to you.</sub>
</div>
