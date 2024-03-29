# NVMe-CLI Vendor datatables

This repo documents the featuresets of NVMes as there doesn't seem to be any official documention on most NVMes as for what they support.  
Also consult [linux-hardware](https://linux-hardware.org) for more general purpose data or if this repo is lacking any NVMe data you're looking for.

## Currently has data for:

#### Context:

Vendor:
* (Model) : (Links) : (Application) (Form Factor)-(size) : (Capacities)-(Variants) : (NVMe Protocol) : (PCIe Gen)x(Lanes) : (Flags)

Links:
* pcpartpicker.com(shopping)
* www.techpowerup.com(wiki)
* tech4gamers.com(news)

Application:
* LTP-Ne = Laptop NVMe
* SD-Ne = Steam Deck NVMe

[NVMe Protocols](https://nvmexpress.org/specification/nvm-express-base-specification):
* 1.0-1.4
* 2.0

Flags:
* [F4K](https://wiki.archlinux.org/title/Advanced_Format#NVMe_solid_state_drives) = Formatible 4 kilobyte sectors

#### :Context

Corsair:
* Force MP510 : [pcpartpicker.com](https://pcpartpicker.com/product/BVbCmG) : M.2-2280 : 960GB : 1.3 : 3x4 : F4K

Micron:
* 2400_MTFDKBA512QFM : [www.techpowerup.com](https://www.techpowerup.com/ssd-specs/micron-2400-512-gb.d804)  : LTP-Ne M.2-2280 : 512GB : 1.4 : 4x4

Phison:
* ESMP512GMB47C3 : [tech4gamers.com](https://tech4gamers.com/valve-steam-decks-slower-ssd) : SD-Ne M.2-2230 : 512GB-E13TS : 1.3 : 3x2-4 : F4K

Samsung:
* 960 PRO : [pcpartpicker.com](https://pcpartpicker.com/product/C3mxFT) : M.2-2280 : 1TB : 1.2 : 3x4
* 980 PRO : [pcpartpicker.com](https://pcpartpicker.com/product/f3cRsY) : M.2-2280 : 2TB : 1.3 : 4x4

## TODO:

* Learn to use the other `id-*` arguments, currently don't have a NVMe that supports the other subsets that the other arguments need.

## Contributions
You can make a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to add more NVMes to this list.

Linux:
1. Get the `nvme-cli` package, for most distros it's just `nvme-cli`, so usually no distro resolving needed, however version 2.8 was used, 2.6 has `--vendor-specific` and `--verbose` with the same shorthand `-v` which errors out and older versions like 2.4 may not have `--verbose` entirely.
2. Use `TEMPVAR="<Vendor>/<Model>/<Capacity>-<Variant>" mkdir -p $TEMPVAR && cd $TEMPVAR` in the git repo (Omit `<Variant>` if there is none).
3. Use `sudo nvme id-ctrl -HVv /dev/nvme? > id-ctrl` for the controller.
4. Use `sudo nvme id-ns -HVv /dev/nvme?n? > id-ns?` for one or all namespaces.

Windows:
1. Currently i don't know any way to get the same information as `nvme-cli` doesn't have a Windows build.
