# DID Zu Method (did:zu)

`did:zu` is the [`did:plc`](https://github.com/did-method-plc/did-method-plc) method, v0.3.0, under its own method name and with its own directory, `https://plc.zuzalu.ink`. The operation formats, signing, hashing, recovery rules and directory API are those of `did:plc`.

An example DID is: `did:zu:ewvi7nxzyoun6zhxrhs64oiz`

- Specification: [website/spec/v0.1/did-zu.md](website/spec/v0.1/did-zu.md)
- Upstream: [did-method-plc/did-method-plc](https://github.com/did-method-plc/did-method-plc), forked at commit `29f1a70`
- Organization: Zuzalu
- Contact: ZuChiangMai

## Changes from upstream

- The specification, the TypeScript library (`@did-plc/lib`), the directory server (`@did-plc/server`), the website and the OpenAPI description use the `did:zu:` prefix and the directory `https://plc.zuzalu.ink`.
- The directory answers `400` for any identifier that is not `did:zu`, including `did:plc` identifiers.
- The interop test vectors in `interop_tests/` carry `did:zu:` identifiers. Only the `did` field of each entry changed; the signed operations are byte-for-byte the upstream ones.
- Package names (`@did-plc/*`) and operation type names (`plc_operation`, `plc_tombstone`) are unchanged.

## Upstream: DID PLC

The text below is from the upstream README.

DID PLC is a self-authenticating [DID](https://www.w3.org/TR/did-core/) which is strongly-consistent, recoverable, and allows for key rotation. PLC stands for "Public Ledger of Credentials".

This git repository contains a TypeScript reference implementation of the method (`@did-plc/lib`) and a directory server `@did-plc/server`, both in the `package/` directory. The separate [go-didplc](https://github.com/did-method-plc/go-didplc) repository contains a Go implementation.

See the [server telemetry guide](packages/server/README.md) for OpenTelemetry configuration.

### Motivation

The DID PLC system was originally developed in 2022 by [Bluesky Social PBC](https://bsky.social/) to support [AT Protocol](https://atproto.com) (atproto). They wanted a strongly consistent, highly available, recoverable, and cryptographically secure method with fast and cheap propagation of updates. Since then over 40 million atproto account identifiers have been registered.

In 2026 the [PLC Organization](https://plcred.org) was founded to be a neutral steward for the DID PLC system. The system may evolve to add functionality or improve security, but will do so in a backwards-compatible manner so that existing DIDs will continue to resolve.

## How it works

See the [specification](website/spec/v0.1/did-zu.md#how-it-works).

## License

This project is dual-licensed under MIT and Apache 2.0 terms:

- Apache License, Version 2.0, ([LICENSE-APACHE](https://github.com/ipfs/kubo/blob/master/LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](https://github.com/ipfs/kubo/blob/master/LICENSE-MIT) or http://opensource.org/licenses/MIT)

Downstream projects and users may chose either license, or both, at their discretion. The motivation for this dual-licensing is the additional software patent assurance provided by Apache 2.0.

Bluesky Social PBC has committed to a software patent non-aggression pledge. For details see [the original announcement](https://bsky.social/about/blog/10-01-2025-patent-pledge).
