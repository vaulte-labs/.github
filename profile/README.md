Vaulte keeps passwords, API keys, env vars, cards, 2FA codes, passkeys and SSH keys in a vault
whose keys never leave your device's secure hardware. People and AI agents use those secrets
through Vaulte, and an agent never gets to read one: each use is approved from your phone and
logged.

| Repository | What it is |
|---|---|
| [libvault](https://github.com/vaulte-labs/libvault) | The core: vault, broker, proxy, fill and sync, and the relay server |
| [sdk](https://github.com/vaulte-labs/sdk) | The C ABI every app and SDK is built on |
| [ts](https://github.com/vaulte-labs/ts) | The TypeScript SDK, for Bun |

These are open source under the AGPL-3.0, and a commercial license is available. The hosted relay,
which carries approvals and sync between your devices on any network, is what you pay for. It only
ever sees ciphertext.

[vaulte.caeser.workers.dev](https://vaulte.caeser.workers.dev) ·
[Contributing](https://github.com/vaulte-labs/.github/blob/main/CONTRIBUTING.md) ·
[Report a vulnerability](https://github.com/vaulte-labs/.github/blob/main/SECURITY.md)
