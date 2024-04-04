# NVMe-CLI Vendor datatables

This repo documents the featuresets of NVMes as there doesn't seem to be any official documention on most NVMes as for what they support.  
Also consult [linux-hardware](https://linux-hardware.org) for more general purpose data or if this repo is lacking any NVMe data you're looking for.

## Currently has data for:

#### Context:

(!)Vendor:
* (Model) : (Links) : (Application) (Flash NAND) (Form Factor)-(size) : (Capacities)-(Variants) : (NVMe Protocol) : (PCIe Gen)x(Lanes) : (Flags)

!:
* This Manufactor is flagged for bad company practices such as bad/lack of customer support, false advertisement or sliently changing component parts, see their warning file regarding their practices

Links:
* !?-**(Points to where one of the flags came from)
* techpowerup.com(wiki)
* pcpartpicker.com(shopping)
* tech4gamers.com(news)
* reddit.com(forum)

Application:
* LTP-Ne = Laptop NVMe
* SD-Ne = Steam Deck NVMe

[NVMe Protocols](https://nvmexpress.org/specification/nvm-express-base-specification):
* 1.0-1.4
* 2.0

Flags:
* FW?[R/W] = Number of firmware slots and if firmware is readable and/or writable, this doesn't mean it's safe to update the firmware even if writeable though, check wikis like [this one for arch linux](https://wiki.archlinux.org/title/Solid_state_drive/NVMe) for special instructions
* [NSS](https://nvmexpress.org/resource/nvme-namespaces) = Namespace Support
* [F4K](https://wiki.archlinux.org/title/Advanced_Format#NVMe_solid_state_drives) = Formatible 4 kilobyte sectors

#### :Context

!ADATA:
* XPG SX8200 Pro : [!1-reddit.com](https://www.reddit.com/r/hardware/comments/lk2f5i/breaking_news_adata_sx8200_pro_m2_ssd_performance) [techpowerup.com](https://www.techpowerup.com/ssd-specs/xpg-sx8200-pro-1-tb.d162) [pcpartpicker.com](https://pcpartpicker.com/product/zR3H99) : TLC? M.2-2280 : 1TB-32B3T8EA : 1.3 : 3x4 : FW2[R/W]

Corsair:
* Force MP510 : [techpowerup.com](https://www.techpowerup.com/ssd-specs/corsair-mp510-960-gb.d377) [pcpartpicker.com](https://pcpartpicker.com/product/BVbCmG) : TLC M.2-2280 : 960GB : 1.3 : 3x4 : FW[R/W] F4K

Micron:
* 2400_MTFDKBA512QFM : [techpowerup.com](https://www.techpowerup.com/ssd-specs/micron-2400-512-gb.d804) : LTP-Ne QLC M.2-2280 : 512GB : 1.4 : 4x4 : FW2[R/W]

Phison:
* ESMP512GMB47C3 : [tech4gamers.com](https://tech4gamers.com/valve-steam-decks-slower-ssd) : SD-Ne TLC? M.2-2230 : 512GB-E13TS : 1.3 : 3x2-4 : FW[R/W] F4K

Samsung:
* PM951 MZVLV256HCHP-000L2 : : LTP-Ne MLC M.2-2280 : 256GB : 1.1a, reports 0 : 3x4 : FW3[R/W]
* PM9A3 MZQL21T9HCJR-00A07 : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-pm9a3-1-9-tb.d1258) : TLC U.2-2.5in : 1.92TB : 1.4 : 4x4 : FW3[R] NSS F4K
* 960 PRO : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-960-pro-1-tb.d68) [pcpartpicker.com](https://pcpartpicker.com/product/C3mxFT) : QLC M.2-2280 : 1TB : 1.2 : 3x4 : FW3[R/W]
* 980 PRO : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-980-pro-2-tb.d52) [pcpartpicker.com](https://pcpartpicker.com/product/f3cRsY) : QLC M.2-2280 : 2TB : 1.3 : 4x4 : FW3[R/W]

## TODO:

* Learn to use the other `id-*` arguments, currently don't have a NVMe that supports the other subsets that the other arguments need.

## Contributions
You can send NVMe data files in a archive(preferably in ZSTD or XZ) to github contributors or make a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to add more NVMes to this list.

Linux:
1. Get the `nvme-cli` package, for most distros it's just `nvme-cli`, so usually no distro resolving needed, however version 2.8 was used, 2.6 has `--vendor-specific` and `--verbose` with the same shorthand `-v` which errors out and older versions like 2.4 may not have `--verbose` entirely.
2. Use `TEMPVAR="<Vendor>/<Model>/<Capacity>-<Variant>" mkdir -p $TEMPVAR && cd $TEMPVAR` in the git repo (Omit `<Variant>` if there is none).
3. Use `sudo nvme id-ctrl -HVv /dev/nvme? > id-ctrl` for the controller.
4. Use `sudo nvme id-ns -HVv /dev/nvme?n? > id-ns?` for one or all namespaces.

Windows:
1. Currently i don't know any way to get the same information as `nvme-cli` doesn't have a Windows build.
