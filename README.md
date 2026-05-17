> # ⚠️ DO NOT USE — UNVERIFIED — UNSAFE ⚠️
>
> This software is **unverified and unsafe for any production use**.
> It is published publicly only for transparency, third-party audit,
> and reproducibility. Treat every commit as guilty until proven
> innocent.
>
> By using this code you accept:
> - **No warranty** of any kind, express or implied.
> - **No fitness** for any particular purpose.
> - **No guarantee** of correctness, safety, or freedom from defects.
> - **Zero liability** on the maintainer for any damages — data loss,
>   security compromise, financial loss, or any consequential damages.
>
> The code is under active engineering development per the
> [Adversarial Validation Protocol v2](https://github.com/thepictishbeast/PlausiDen-AVP-Doctrine/blob/main/AVP2_PROTOCOL.md).
> Every commit's default verdict is **STILL BROKEN**. AVP-2 requires
> a minimum of 36 verification passes before a `SHIP-DECISION:`
> annotation may be considered. **No commit in this repository has
> reached `SHIP-DECISION:` status.**

# PlausiDen-PDFS

Plausibly Deniable File System.

## Purpose

PlausiDen-PDFS provides hidden encrypted volumes where the disk is indistinguishable from random noise. Multiple hidden volumes can coexist — there is no way to prove how many volumes exist or whether any hidden volume is present at all.

This is the filesystem-level foundation of PlausiDen's plausible deniability architecture.

## Planned Features

- **Multiple hidden volumes** with independent keys
- **Steganographic metadata** — no headers, no magic bytes, no detectable structure
- **Disk indistinguishable from noise** — passes entropy analysis
- **Zig kernel module** for block-level operations
- **Rust FUSE** userspace driver for portable access
- **ML-KEM** post-quantum key encapsulation
- **Shamir Secret Sharing** for key recovery across trusted parties

## Integration

| Project | Role |
|---------|------|
| PlausiDen-Shard | Fragment storage within deniable volumes |
| PlausiDen-Swarm | P2P distribution of encrypted fragments |
| PlausiDen-Purge | Secure cleanup of deniable storage |
| PlausiDen-Engine | Noise generation to fill unused space |
| PlausiDen-OS | seL4 isolation for volume management |
| PlausiDen-Auth | Volume unlock authentication |

## Status

**Scaffolding phase.** Architecture defined, Zig kernel + Rust FUSE design in progress. See [PlausiDen-Shard](https://github.com/thepictishbeast/PlausiDen-Shard) for the cryptographic sharding engine it depends on.

## License

MIT OR Apache-2.0
