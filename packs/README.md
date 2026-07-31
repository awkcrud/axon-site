# AXON Packs

Hot-update artifacts for clients **1.4.0+**. Published on GitHub branch `catalog` (not Pages).

## Layout

- `packs/index.json` - active pack + optional engine-layer entries
- `packs/axon-stable-vN.axonpack` - ZIP (`manifest.json`, `strategies.json`, `runtime.json`, `probe.json`, optional `lists/`, `bins/`)
- `strategies/catalog.json` - legacy mirror for older clients (Pack Studio writes both)

## Signature

HMAC-SHA256 over pack bytes. Key = `SHA256("AXON-PACK-v1|" + vaultSecret)` (same vault as admin panel).

## Engine layer

Optional zip with only allowlisted fake `*.bin` files. Never ship `WinDivert.sys` / `winws.exe` unsigned from third parties.
