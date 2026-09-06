<div align="center">

### Rent a GPU by the hour, pay with the stocks you already hold

Boogie is a compute marketplace on Robinhood Chain. Pick a machine, pay from your
wallet in USDG or tokenized NVDA, SPY, QQQ and TSLA, and get a card that boots
ready to work.

[![Site](https://img.shields.io/badge/site-boogiecompute.com-22C55E?style=flat-square)](https://boogiecompute.com)
[![Docs](https://img.shields.io/badge/docs-boogiecompute.com%2Fdocs-22C55E?style=flat-square)](https://boogiecompute.com/docs)
[![X](https://img.shields.io/badge/X-@Boogie__Software-111111?style=flat-square)](https://x.com/Boogie_Software)
[![License](https://img.shields.io/badge/license-MIT-555555?style=flat-square)](https://github.com/boogiecompute/boogie-contracts/blob/main/LICENSE)

</div>

---

## The idea

Renting compute usually means a sales call, a quota request or a queue, and buying
a card means owning a depreciating machine for work that lasts an afternoon. The
work is short and heavy. Owning is long and expensive.

Boogie sells hours. You approve a ceiling in the asset you already hold, the
contract sells exactly as much of it as the hours cost, and the remainder comes
back in the same transaction. Nobody holds an equity position between the quote
and the machine.

```
  your wallet          the contract              the machine
  NVDA, SPY, QQQ  ->   sells what the hours  ->  boots with the tool
  TSLA or USDG         actually cost             you picked
```

## What is running today

**Rentals settle onchain.** Every order is a transaction you can read, and the
price agreed at checkout is the amount recorded.

**Machines arrive ready.** Choose a notebook with PyTorch, ComfyUI for images and
video, a local model with a chat window, or an OpenAI-compatible endpoint. The
models come down while the machine boots, so the tool is useful the moment it
opens.

**Hours start when the machine does.** Boot takes minutes and somebody pays for
them. That somebody is us.

**Nothing runs longer than it was paid for.** When the time ends the machine is
shut down and released. Stop earlier and the unused hours come back to the wallet
that paid.

**No account anywhere.** Your SSH key is bound to your wallet by a signature, and
that binding is what decides whose key goes on the machine.

## Renting from code

There is no API key to request. The wallet that pays is what proves who you are,
so a script or an agent rents on exactly the same terms as a person, with no human
in the path.

```python
listings = requests.get("https://app.boogiecompute.com/api/catalog").json()["listings"]
machine  = min(listings, key=lambda m: m["usdPerHour"])
quote    = requests.post(f"{API}/api/quote", json={
    "machineId": machine["id"], "hours": 1, "payer": wallet.address,
}).json()
```

Full walkthrough in [the docs](https://boogiecompute.com/docs#api) and a working
example in [boogie-contracts](https://github.com/boogiecompute/boogie-contracts).

## Next

Work that survives the machine, so a folder follows you to the next card you rent.
Then hosting, so an idle GPU earns instead of collecting dust. That one waits on
proving the hours a host actually served, because supply nobody can verify is
worth nothing to the people renting it.

<div align="center">
<sub>Compute you rent by the hour, that behaves like it belongs to you.</sub>
</div>
