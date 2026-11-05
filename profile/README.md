<h1 align="center">Object Digital Passport</h1>

<p align="center">
  <b>An open standard for verifiable records about physical and digital objects.</b><br>
  Art, editions, archives and more: an immutable on-chain registration, cryptographic file commitments,<br>
  and independently checkable issuer information. No proprietary verification service required.
</p>

<p align="center">
  <a href="https://object-digital-passport.github.io/verify.html"><b>Try the reference verifier</b></a> ·
  <a href="https://object-digital-passport.github.io/">Website</a> ·
  <a href="https://github.com/object-digital-passport/specifications/blob/main/SPEC.md">Specification</a> ·
  <a href="https://github.com/object-digital-passport/specifications/wiki">Wiki</a> ·
  <a href="https://github.com/object-digital-passport/specifications/discussions">Discussions</a> ·
  <a href="https://github.com/object-digital-passport/specifications/issues/181">Roadmap</a>
</p>

<p align="center">
  <a href="https://github.com/object-digital-passport/specifications/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-green.svg" alt="MIT License"></a>
  <a href="https://github.com/object-digital-passport/specifications/blob/main/SPEC.md"><img src="https://img.shields.io/badge/protocol-v0.7%20alpha-orange.svg" alt="Protocol v0.7 alpha"></a>
  <a href="https://polygonscan.com/address/0x3281492981DCD492cc2F7c17398134e1D3B5CA1F"><img src="https://img.shields.io/badge/registry-v0.7%20Polygon%20mainnet-8247e5.svg" alt="v0.7 registry deployed on Polygon mainnet"></a>
  <a href="https://github.com/object-digital-passport/specifications/actions/workflows/ci.yml"><img src="https://github.com/object-digital-passport/specifications/actions/workflows/ci.yml/badge.svg" alt="Specification CI"></a>
</p>

---

## What ODP records

ODP lets an issuer register **when** a description was committed, **which wallet/profile** registered it, and **which exact descriptions and original files** match the registered hashes. Readers can verify the public record without a wallet or ODP account. An issuer's identity and the object in front of a reader still require independent checks: a blockchain transaction is **not** proof of authenticity, authorship or ownership.

A passport combines a readable immutable on-chain card with the hashes of an off-chain `passport.json` document and its identifying evidence. The portable `.odpass` bundle contains the full document and original files; the blockchain cannot reconstruct missing originals. Corrections and independent statements are separate records, rather than edits to the original registration. The protocol charges no fee of its own; writes require Polygon network gas.

## Current status — November 2026

> **v0.7 alpha is deployed on Polygon PoS mainnet (chain ID 137) since 25 September 2026**, but has **not yet undergone an independent security audit**. Do not mistake a deployed protocol for production-ready client applications. The target for a stable release is January 2027, not a guarantee.

| Component | Status |
|:--|:--|
| **Protocol v0.7 / Solidity registry** | **Deployed**: generation `odp-0.7-redesign-8-polygon-20260925`; deployed core and satellite contracts. [Approved generation manifest](https://github.com/object-digital-passport/specifications/blob/main/chain/generations.json). |
| **Reference website / Verify** | **Older generation still in use**: website/demo/Verify currently target v0.6 by default according to the protocol release notes. Do **not** rely on them to create or fully verify v0.7 passports until compatibility is confirmed. |
| **Earlier v0.x generations** | Separate registries, not upgrades: legacy records remain attached to their own chain/address/ABI. They are not migrated to v0.7. |
| **Apple app and Android NFC companion** | Pre-release projects; functionality and real-hardware validation differ by component (see their READMEs). |
| **ODP MCP / AI integration** | **Planned**, not released. [Tracking issue](https://github.com/object-digital-passport/odp-mcp/issues/1). |

## Code and projects

| Repository | Purpose | Status / scope |
|:--|:--|:--|
| **[specifications](https://github.com/object-digital-passport/specifications)** | **Normative standard:** `SPEC.md`, Solidity contracts, ABIs, schemas, conformance vectors, deployment and offline tools | v0.7 alpha; source of truth |
| **[object-digital-passport.github.io](https://github.com/object-digital-passport/object-digital-passport.github.io)** | Reference browser app for profiles, issuance and verification | v0.6 site integration; v0.7 migration needed |
| **[design-kit](https://github.com/object-digital-passport/design-kit)** | Visual identity, print-ready design assets, Tangem card skins and physical labels | Public, early-stage design repository |
| **[odp-mcp](https://github.com/object-digital-passport/odp-mcp)** | AI integration and guided ODP passport lifecycle via MCP and WalletConnect | Public, planned implementation |
| **[swift-core](https://github.com/object-digital-passport/swift-core)** | Reusable Swift verification, canonicalization and wallet-crypto building blocks | Early reusable library |
| **[odp-profile-directory](https://github.com/object-digital-passport/odp-profile-directory)** | Open directory **format**, validator and re-check tooling; example entries are synthetic | Reference implementation, not an official identity authority |
| **[odp-directory-v0.6](https://github.com/object-digital-passport/odp-directory-v0.6)** | Independently curated real-profile directory for the **v0.6** generation | Generation-specific; not a v0.7 registry |
| **apple-app** *(private)* | Apple-platform client for passports, wallet and NFC integration | Pre-release; NFC hardware flow not yet validated as described in README |
| **android-verifier** *(private)* | Android NFC verifier and guided scan companion | Pre-release; documented v0.5-era integrations require review |
| **odp-sponsor-kit** *(private)* | Reference gas sponsorship service for institutions and universities | v0.1.1 reference; **not field-tested** |

Private repositories are accessible only to authorized collaborators. Their presence here does not mean they are released or audited.

## Roadmap and contributing

- **[ODP Product Roadmap](https://github.com/object-digital-passport/specifications/issues/181)** — cross-repository tracker for development, UX, physical labels, NFC, Tangem card skins and upcoming AI tools. Design-specific tasks live in [design-kit issues](https://github.com/object-digital-passport/design-kit/issues) and AI integration tasks in [odp-mcp issues](https://github.com/object-digital-passport/odp-mcp/issues).
- [Physical-object label design](https://github.com/object-digital-passport/specifications/issues/120) · [NFC seal research](https://github.com/object-digital-passport/specifications/issues/119).
- [Issues in the specification repository](https://github.com/object-digital-passport/specifications/issues) · [Discussions](https://github.com/object-digital-passport/specifications/discussions) · [Contributing](https://github.com/object-digital-passport/specifications/blob/main/docs/CONTRIBUTING.md).

We welcome independent review of the cryptography and client security, object documentation and conservation expertise, NFC device testing, translations, design and accessibility feedback. Issue and PR scope should follow each repository's contribution rules.

## Technical entry points

- **[Normative specification v0.7](https://github.com/object-digital-passport/specifications/blob/main/SPEC.md)** — including hashing, bundle rules, security and client obligations.
- **[Schemas, examples and test vectors](https://github.com/object-digital-passport/specifications/tree/main/schema)**.
- **[Contract ABIs](https://github.com/object-digital-passport/specifications/tree/main/chain/abi)** · **[approved chain generations](https://github.com/object-digital-passport/specifications/blob/main/chain/generations.json)**.
- **[Security model](https://github.com/object-digital-passport/specifications/blob/main/docs/SECURITY.md)** · **[v0.7 release notes](https://github.com/object-digital-passport/specifications/blob/main/docs/releases/v0.7.md)**.
- **[Detailed guide](https://github.com/object-digital-passport/specifications/blob/main/docs/GUIDE.md)** — **historical v0.6 guidance; not authoritative for v0.7**.

### Current v0.7 registry

- **Network:** Polygon PoS (`chainId 137`)
- **Generation:** `odp-0.7-redesign-8-polygon-20260925`
- **Core registry:** [`0x3281492981DCD492cc2F7c17398134e1D3B5CA1F`](https://polygonscan.com/address/0x3281492981DCD492cc2F7c17398134e1D3B5CA1F)
- **Satellites, runtime hashes and deployment evidence:** [`chain/generations.json`](https://github.com/object-digital-passport/specifications/blob/main/chain/generations.json)

---

<p align="center"><sub>Open-source under MIT · Verification is free · The protocol has no central authenticity authority</sub></p>
