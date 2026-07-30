# Changelog

## Bug Fixes

- Fixed unquoted variable `$PHONE_IP` in `pi-launch_phone.sh`
- Fixed unescaped regex dot in `pkill -9 -f "termux.x11"` across setup script
- Replaced non-portable `grep -oP` with `awk` for IP detection
- Replaced hardcoded `wlan0` interface with `ip route get` for reliable IP detection

## RuusianP Rebrand

- Project rebranded as an independent build by RuusianP
- All URLs updated to point to RuusianP/TermuxDroid
- Rebranded project attribution to RuusianP
- Added project governance documentation (CONTRIBUTING.md, SECURITY.md, CODE_OF_CONDUCT.md)
- Updated setup script completion banner with RuusianP branding
- Updated LICENSE with RuusianP copyright notice

## Prior History

The original work was done by the community. All commits have been rebased under RuusianP as the project owner.