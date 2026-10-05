# scoop-wiradesk

> **Cakupan Playbook:** Repositori bucket paket distribusi Windows ini berada di luar cakupan aplikasi WDI Coding Playbook (Packaging Manifest).

A [Scoop](https://scoop.sh) bucket for [Wira Desk](https://github.com/wiradeltaid/wira-desk).

This dedicated bucket distributes Wira Desk as a portable application package from official
GitHub release archives (`WiraDesk-<version>-x64-portable.zip`), licensed under GPL-3.0-only.

## Install

```powershell
scoop bucket add wiradesk https://github.com/wiradeltaid/scoop-wiradesk
scoop install wiradesk
```

## Update

```powershell
scoop update wiradesk
```

## How this bucket stays current

`bucket/wiradesk.json` carries `checkver`/`autoupdate` fields pointing at wira-desk's own GitHub
releases. `.github/workflows/excavator.yml` runs on a schedule (every four hours) and bumps the
manifest automatically the moment a new tag's release is published there - nothing needs to be
pushed from the wira-desk repository itself for this to happen.

Manual regeneration, if ever needed: bump `version` and `url` by hand, or trigger the
`Excavator` workflow's `workflow_dispatch` from the Actions tab.

## Source of truth

The staged content of this bucket lives at `packaging/scoop-bucket/` in the
[wira-desk](https://github.com/wiradeltaid/wira-desk) repository, and this repository is a
plain copy of it. If the two ever disagree, wira-desk's copy is correct; push its content here
again to fix the drift.
