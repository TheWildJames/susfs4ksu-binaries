# susfs4ksu universal binary
universal binary for susfs4ksu v1.5.2+

## This fork

`TheWildJames/susfs4ksu-binaries`, `universal-binary` branch.

- adds `set_sus_path_uid_filter` (susfs kernel tree after v2.4.0) alongside
  `set_priority_uid_filter`
- fixes the `--help <cmd>` dispatch for `set_priority_uid_filter`: the
  `strcmp()` check was missing `== 0`, so it acted as a catch-all and printed
  its own help for every unmatched command
- `ksu_susfs_arm64` is built by `.github/workflows/build.yml` (zig cc + NDK
  r27d sysroot, `-static`), then `upx --ultra-brute` + `sstrip`, and committed
  back to this branch
