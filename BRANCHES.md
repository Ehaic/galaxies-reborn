# Branch policy

`main` is the primary x64 / DirectX 11 branch. Server main starts from the validated x64-dx11-vanilla source; client main starts from x64-dx11-integration and incorporates the Qt editor tools.

Maintained efforts:

- `entertainer-reborn`: preserves the entertainer MIDI work. The preserved client branch originated on DX9 and still requires a separate DX11 port and runtime validation; renaming it does not change its renderer.
- `pre-cu-reborn`: preserves the Pre-CU gameplay line and its repository-specific dependencies.
- `web-dashboard`: preserves src's web-admin console work. It contains Pre-CU gameplay changes and must not be merged wholesale into the NGE mainline.

Other client work remains available on its existing branches: x64-dx11-vanilla (independent renderer), x64-dx11-steamdeck-reborn, x64-dx11-tcg-reborn, and econ-sim. These are not interchangeable with main. Merge individual compatible changes only after comparison and build/runtime validation. The independent renderer has extensive add/add conflicts with integration.

The x64-dx9 branch names are retired after their original tips are preserved under archive/branch-cleanup-20260911 tags and entertainer-reborn branches. This retires branch names, not history or DX9 compatibility code.

Submodules remain pinned to exact commits. Changing a default branch does not upgrade an existing checkout or running server. Rebase or merge deliberately; do not reset dirty workspaces to follow main.