## Context

(!)Vendor:
* (Model) : (Links) : (Application) (Flash NAND) (Form Factor)-(size) : (Capacities)-(Variants)-FW_(Firmware) : (NVMe Protocol) : (PCIe Gen)x(Lanes) : (Flags)

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
* [NSS?](https://nvmexpress.org/resource/nvme-namespaces) = Namespace Support and how many
* [F4K](https://wiki.archlinux.org/title/Advanced_Format#NVMe_solid_state_drives) = Formatible 4 kilobyte sectors

## Data

!ADATA:
* XPG SX8200 Pro : [!1-reddit.com](https://www.reddit.com/r/hardware/comments/lk2f5i/breaking_news_adata_sx8200_pro_m2_ssd_performance) [techpowerup.com](https://www.techpowerup.com/ssd-specs/xpg-sx8200-pro-1-tb.d162) [pcpartpicker.com](https://pcpartpicker.com/product/zR3H99) : TLC? M.2-2280 : 1TB-32B3T8EA : 1.3 : 3x4 : FW2[R/W]

Corsair:
* Force MP510 : [techpowerup.com](https://www.techpowerup.com/ssd-specs/corsair-mp510-960-gb.d377) [pcpartpicker.com](https://pcpartpicker.com/product/BVbCmG) : TLC M.2-2280 : 960GB : 1.3 : 3x4 : FW[R/W] F4K

Crucial:
* P3 Plus : [techpowerup.com](https://www.techpowerup.com/ssd-specs/crucial-p3-plus-1-tb.d825) [pcpartpicker.com](https://pcpartpicker.com/product/chzhP6) : QLC M.2-2280 : 4TB : 1.4 : 4x4 : FW[R/W] F4K

Micron:
* 2400_MTFDKBA512QFM : [techpowerup.com](https://www.techpowerup.com/ssd-specs/micron-2400-512-gb.d804) : LTP-Ne QLC M.2-2280 : 512GB : 1.4 : 4x4 : FW2[R/W]

Phison:
* ESMP512GMB47C3 : [tech4gamers.com](https://tech4gamers.com/valve-steam-decks-slower-ssd) : SD-Ne TLC? M.2-2230 : 512GB-E13TS : 1.3 : 3x2-4 : FW[R/W] F4K

Samsung:
* PM951 MZVLV256HCHP-000L2 : : LTP-Ne MLC M.2-2280 : 256GB : 1.1a, reports 0 : 3x4 : FW3[R/W]
* PM9A3 MZQL21T9HCJR-00A07 : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-pm9a3-1-9-tb.d1258) : TLC U.2-2.5in : 1.92TB : 1.4 : 4x4 : FW3[R] NSS32 F4K
* 960 PRO : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-960-pro-1-tb.d68) [pcpartpicker.com](https://pcpartpicker.com/product/C3mxFT) : QLC M.2-2280 : 1TB : 1.2 : 3x4 : FW3[R/W]
* 970 EVO Plus : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-970-evo-plus-1-tb.d61) [pcpartpicker.com](https://pcpartpicker.com/product/Zxw7YJ) : QLC M.2-2280 : 1TB 2TB : 1.3 : 3x4 : FW3[R/W]
* 980 PRO : [techpowerup.com](https://www.techpowerup.com/ssd-specs/samsung-980-pro-2-tb.d52) [pcpartpicker.com](https://pcpartpicker.com/product/f3cRsY) : QLC M.2-2280 : 2TB : 1.3 : 4x4 : FW3[R/W]

WD_BLACK:
* SN850X : [techpowerup.com](https://www.techpowerup.com/ssd-specs/western-digital-sn850x-w-heatsink-4-tb.d860) [pcpartpicker.com](https://pcpartpicker.com/product/yBC48d) : TLC M.2-2280 : 4TB : 1.4 : 4x4 : FW2[R/W] F4K

## Vendor Commands

The following vendors have plugins in `nvme-cli` as of version 2.8:
  ymtc            Ymtc vendor specific extensions
  wdc             Western Digital vendor specific extensions
  virtium         Virtium vendor specific extensions
  transcend       Transcend vendor specific extensions
  toshiba         Toshiba NVME plugin
  solidigm        Solidigm vendor specific extensions
  shannon         Shannon vendor specific extensions
  seagate         Seagate vendor specific extensions
  sfx             ScaleFlux vendor specific extensions
  nvidia          NVIDIA vendor specific extensions
  netapp          NetApp vendor specific extensions
  nbft            ACPI NBFT table extensions
  micron          Micron vendor specific extensions
  memblaze        Memblaze vendor specific extensions
  intel           Intel vendor specific extensions
  inspur          Inspur vendor specific extensions
  innogrit        innogrit vendor specific extensions
  huawei          Huawei vendor specific extensions
  fdp             Manage Flexible Data Placement enabled devices
  dera            Dera vendor specific extensions
  dell            DELL vendor specific extensions
  amzn            Amazon vendor specific extensions
  
Use `nvme <plugin> --help` to see extra vendor commands.
