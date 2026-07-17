# Recommended technology stack

Coding agents may adjust, but this is the strong default.

## Core

- Rust
- Tokio
- Quinn for QUIC
- libp2p where useful
- WebRTC for browser and NAT traversal compatibility
- rustls
- sqlcipher-compatible SQLite or encrypted SQLite layer
- CBOR via serde

## Cryptography

- ed25519-dalek
- x25519-dalek
- blake3
- chacha20poly1305
- hkdf
- established Double Ratchet implementation
- OpenMLS

## Client

Initial target:

- desktop CLI or TUI reference client
- daemonised networking core
- later GUI clients

## Planned crates

```text
nettle-core / nettle-node
nettle-protocol
nettle-crypto
nettle-storage
nettle-transport
nettle-discovery
nettle-chain-client
nettle-chain-runtime
nettle-relay
nettle-cli
```

Plus supporting crates listed in the root README.

## Blockchain

Options:

- Rust application chain
- CometBFT-compatible state machine
- Substrate-based chain
- custom prototype consensus for development only

Chain remains isolated behind a clean interface.

## Non-negotiables

- reviewed cryptographic libraries only
- no custom primitives
- structured tracing without plaintext or secret keys
- fuzzing for parsers and event verification
