# Changelog

All notable changes to Mora are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
This project is currently **0.1.x** (devnet prototype).

## [Unreleased]

### Added

- Landing **How it works** (five-step user path) and **Architecture** (PDAs, 84-byte voucher, settle ix order, demo-only BT/hash chain).
- Nav links, tooltips on Devnet / scenario steps / Alice & Bob, collapsible judge notes, site footer.
- README architecture: Mermaid sequence, account seeds, voucher layout, what is not on-chain.

### Changed

- Hero copy and hierarchy: product sentence first, protocol details second.

## [0.1.0] — 2026-05-09

Devnet prototype. First public snapshot of the repo.

### Added

- Anchor program `mora` (`9fcXHD3pHDKLX79JuVgCEKQiqYkvVqFtpoAEVjBq4aJ8` on devnet):
  - `create_escrow` — lock SOL in PDA `["escrow", authority, seed]`
  - `settle` — Ed25519-preceded voucher pay; Receipt PDA `["receipt", escrow, nonce]` blocks replay
  - `close_escrow` — after expiry, rent + remainder to authority
- Canonical 84-byte voucher: `"MORA" | escrow | nonce | payee | amount`
- CLI (`cli/mora.ts`): `create`, `voucher` (offline), `settle`, `close`, `status`, `list`
- Anchor tests: create, settle, replay reject, close
- Static web demo (`web/`): Alice Pay + Bob POS, simulated BT (`BroadcastChannel`), off-chain hash chain, Phantom as optional funder
- Proprietary license for MORA software
