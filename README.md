# conda-forge

Community-led conda package channel providing over 33,000 open-source packages for scientific computing, data science, and general Python development.

## Overview

conda-forge is a GitHub organization and community effort that maintains conda package recipes and provides a free, open-source package channel. Packages are built through automated CI infrastructure and distributed via the Anaconda.org hosting platform.

## APIs

### Anaconda.org REST API

Base URL: `https://api.anaconda.org`

| Endpoint | Description |
|----------|-------------|
| `GET /package/conda-forge/{name}` | Full metadata for a conda-forge package including versions, platforms, license, and download stats |
| `GET /user/conda-forge` | conda-forge organization profile |
| `GET /search?name={term}` | Search packages across all Anaconda.org channels by name |

Example:

```bash
curl https://api.anaconda.org/package/conda-forge/numpy
```

### conda Channel Repodata

Base URL: `https://conda.anaconda.org/conda-forge`

| Resource | Description |
|----------|-------------|
| `/{subdir}/repodata.json.zst` | Compressed package index for a platform (e.g., linux-64, osx-64, win-64) |
| `/{subdir}/repodata.json` | Uncompressed package index |
| `/channeldata.json` | Cross-platform index of all 33,000+ packages with docs, license, and subdir info |

Example:

```bash
# Channel-wide package index
curl https://conda.anaconda.org/conda-forge/channeldata.json

# Platform-specific package index (compressed)
curl https://conda.anaconda.org/conda-forge/linux-64/repodata.json.zst
```

## Access

All conda-forge APIs are publicly accessible with no authentication required for read operations. No API key or subscription is needed.

## Resources

- Website: https://conda-forge.org/
- Documentation: https://conda-forge.org/docs/
- GitHub: https://github.com/conda-forge
- Packages: https://anaconda.org/conda-forge
- Community Chat: https://conda-forge.zulipchat.com/
- Status: https://conda-forge.org/status/

## APIs.json

This repository contains an [APIs.json 0.19](apis.yml) profile cataloging the conda-forge public APIs.
