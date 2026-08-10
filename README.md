# FreeCut provider releases

This repository publishes immutable binary providers and shared runtimes for
[FreeCut Native](https://github.com/walterlow/freecut-native).

Large ZIP files live on GitHub Releases rather than in git. `catalog-v1.json` is the machine-readable
index consumed by FreeCut. Every package entry pins its byte size and SHA-256; FreeCut verifies both
before atomically installing the archive.

Package roles:

- **providers** contain one out-of-process inference adapter and its ABI-sensitive backend DLLs;
- **runtimes** contain large redistributable dependencies shared by compatible providers;
- **models** remain separately downloaded from their manifest-pinned Hugging Face repositories.

CUDA runtime archives contain only files NVIDIA identifies as redistributable with applications and
include the applicable NVIDIA notices. The NVIDIA display driver is not included.

Do not replace assets attached to an existing catalog tag. Publish a new semantic package version,
update the catalog, and create a new catalog release instead.
