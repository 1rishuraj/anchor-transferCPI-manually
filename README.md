# anchor-transferCPI-builtin

A simple **Solana program built with Anchor** that demonstrates how to perform a **Cross-Program Invocation (CPI)** to the **System Program** for transferring SOL between accounts.

---

## 🧠 What It Does
- Uses the System Program to transfer lamports (SOL) from a **sender** to a **recipient**.
- Demonstrates how to build and use a **CpiContext** in Anchor.
- Shows the difference between `Signer<'info>` and `SystemAccount<'info>`.

---

## ⚙️ Key Concepts

| Concept | Description |
|----------|--------------|
| `transfer()` | Anchor helper function to perform SOL transfer CPI. |
| `Transfer` | Struct defining `from` and `to` accounts for CPI. |
| `CpiContext::new()` | Bundles program + accounts for the CPI call. |
| `SystemAccount<'info>` | A normal wallet account (receiver). |
| `Signer<'info>` | Wallet that signs the transaction (sender). |

---

## 🧾 Instruction

### `sol_transfer(ctx, amount)`
Transfers `amount` lamports from the signer (`sender`) to the recipient using:
```rust
transfer(CpiContext::new(system_program, Transfer { from, to }), amount)?;
````

---

## 🧪 Run Test

```bash
anchor test
```

This runs your Mocha tests locally, calling the `sol_transfer` instruction and verifying the balances.

---

## 🧰 Files

```
programs/
 └── transfer_cpi/
     ├── src/lib.rs        # Rust program
tests/
 └── transfer_cpi.ts       # Anchor test file
```

---
"# anchor-transferCPI-manually" 
