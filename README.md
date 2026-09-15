# clone-lin-bech32

LIN clone of the **scalar checksum kernel** from [sipa/bech32](https://github.com/sipa/bech32) (`ref/c/segwit_addr.c`, MIT, Pieter Wuille).

- **Class:** EXPERIMENTAL (not a Bitcoin Core replacement).
- **In scope:** `bech32_polymod_step`, fail-closed charset, BIP-173 `A12UEL5L` gate.
- **Out of scope:** `bech32_encode` / `bech32_decode` (C pointers; rejected by the LIN C transpiler).

Pinned upstream commit `7a7d7ab158db7078a333384e0e918c90dbc42917`.
File SHA-256 `aa73529c41142d2a9fed384676910943692236eda2ec583f96a95b5283c3042d`.

Proofs and Compiler 0 live in [lin-open](https://github.com/kbelludoo/lin-open):

```bash
python3 test/prove_bech32_sipa_external.py
make -C transpile/c c0
./transpile/c/bin/lin_c0 vm src/lin_bech32_polymod.lin bech32_gate
```
