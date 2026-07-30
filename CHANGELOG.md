# Changelog

## Production Readiness

- Resolved all shellcheck warnings across both scripts (zero warnings)
- Replaced fragile `bash -c "..."` quoting in proot user setup with temp script file
- Removed dead code: `install_pkg_checked()`, `BLUE`, `BOLD`, `CPU_ABI`, `GPU_VENDOR`, `HAS_ROOT`, `PROOT_BIN`
- Fixed overly broad `pkill -9 -f "dbus"` → `pkill -9 -f "dbus-daemon"` (safer process targeting)
- Graceful pulseaudio shutdown: SIGTERM first, fallback to SIGKILL
- VNC password no longer hardcoded in generated `start-vnc.sh` (references passwd file)
- Added `trap cleanup EXIT` for temp file cleanup on script exit
- Added `# shellcheck disable=SC1090` directive for dynamic source path
- Removed unused color variables and dead code paths

## Code Quality & Bug Fixes

- Fixed unquoted variable `$PHONE_IP` in `pi-launch_phone.sh`
- Fixed unescaped regex dot in `pkill -9 -f "termux.x11"` across setup script
- Replaced non-portable `grep -oP` with `awk` for IP detection
- Replaced hardcoded `wlan0` interface with `ip route get` for reliable IP detection
- Fixed unquoted `$pid`, `$pkg`, `${VNC_DISPLAY}`, `${VNC_GEOMETRY}` (word splitting)
- Fixed `printf` format string safety (SC2059) — variables no longer used as format args
- Switched color definitions to `$'...'` ANSI-C quoting for proper escape handling
- Fixed ImageMagick gradient syntax (removed spurious quotes)
- Added `-r` flag to all `read` commands (preserve backslashes)
- Removed dead code: `CPU_ABI`, `GPU_VENDOR`, `HAS_ROOT`, `PROOT_BIN` unused variables
- Fixed PS1 prompt line to use `printf` instead of `echo` (SC2028)

## RuusianP Rebrand

- Project rebranded as an independent build by RuusianP
- All URLs updated to point to RuusianP/TermuxDroid
- Rebranded project attribution to RuusianP
- Added project governance documentation (CONTRIBUTING.md, SECURITY.md, CODE_OF_CONDUCT.md)
- Updated setup script completion banner with RuusianP branding
- Updated LICENSE with RuusianP copyright notice

## Prior History

The original work was done by the community. All commits have been rebased under RuusianP as the project owner.