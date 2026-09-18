# Personal experimentation checkout

All repositories in this tree are forked under `Ehaic` on GitHub.
The experiment branch is `experiment-galaxies-reborn` in the root and every submodule.
The original source revisions were preserved; setup commits only change fork wiring and this guide.

## Clone this experiment

```bash
git clone --recurse-submodules --branch experiment-galaxies-reborn https://github.com/Ehaic/galaxies-reborn.git
```

A fresh recursive clone checks out submodules at detached pinned revisions. Before editing a submodule,
run `git switch experiment-galaxies-reborn` inside it (or create a new feature branch).

## Working with changes

Commit and push changes inside the deepest modified submodule first. Then commit its updated
submodule pointer in its parent and push that parent. Repeat up to the root repository.
Plain `git submodule update --init --recursive` restores the committed pins;
`git submodule update --remote` deliberately advances to the configured experiment branches.

The prepared local checkouts use your fork as `origin`, default pushes to `origin`, and retain
the original as `upstream` with its push URL set to `disabled://upstream`.
These local Git settings are not inherited by new clones. Fetching from upstream remains available;
merging upstream updates is an explicit operation. Do not open upstream pull requests unless intended.

## Original revision inventory

| Path | Fork | Original revision |
| --- | --- | --- |
| `.` | [Ehaic/galaxies-reborn](https://github.com/Ehaic/galaxies-reborn) | `7916d5d7ee7e857083a92fcd996f7856c4aadd7a` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main` | [Ehaic/swg-main](https://github.com/Ehaic/swg-main) | `44b866a68fc6319a6a9ccf709aee9f0570f14e93` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main/stationapi` | [Ehaic/stationapi](https://github.com/Ehaic/stationapi) | `4c067908ad32af662f464ec0405650f47a586722` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main/dsrc` | [Ehaic/dsrc](https://github.com/Ehaic/dsrc) | `5b878b956b6e420b6d9283e6eef158fcf8ec535f` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main/src` | [Ehaic/src](https://github.com/Ehaic/src) | `cd33f379d003d982f031293fe843b469b5edd662` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main/serverdata` | [Ehaic/serverdata](https://github.com/Ehaic/serverdata) | `72e7507e24fecb3716cee94a296bd6ad286cabb6` |
| `galaxies-reborn/nge/x64-dx11-vanilla/swg-main/exe` | [Ehaic/configs](https://github.com/Ehaic/configs) | `90b1f6d6ab23d5df314ae7602af275c32e1bfc1f` |
| `galaxies-reborn/nge/x64-dx11-vanilla/client-assets` | [Ehaic/client-assets](https://github.com/Ehaic/client-assets) | `accd54ba15db72adbd156f1b3859eda08ce69cac` |
| `galaxies-reborn/nge/x64-dx11-vanilla/client-tools` | [Ehaic/client-tools](https://github.com/Ehaic/client-tools) | `ec6217fa4eae1d8c7638ec01b71a2521daa848c3` |
| `galaxies-reborn/nge/x64-dx11-vanilla/client-tools/tools-payload` | [Ehaic/legacy-tools-payload](https://github.com/Ehaic/legacy-tools-payload) | `cf53acca41e1747eed57e102851db9a8bfc81019` |
| `swgemu/core3/Core3` | [Ehaic/Core3](https://github.com/Ehaic/Core3) | `3f294c7027dde69647bc0461224041551ee55f2b` |
| `swgemu/core3/Core3/MMOCoreORB/utils/engine3` | [Ehaic/engine3](https://github.com/Ehaic/engine3) | `7012c03145cc2ad7aa4e652933e9af460d4dd8b8` |

This setup does not build or deploy the server. Retail client assets and external SDKs/services
remain separate requirements. Historical documentation and third-party download links retain
their original attribution.
