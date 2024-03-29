# NVMe-CLI Vendor datatables

This repo documents the featuresets of NVMes as there doesn't seem to be any official documention on most NVMes as for what they support.

## Currently has data for:

#### Context:

Vendor:
* (Model) : (Capacities)-(Variants) : (NVMe Protocol) : (PCIe Gen) : (Flags)

[NVMe Protocols](https://nvmexpress.org/specification/nvm-express-base-specification):
* 1.0-1.4
* 2.0

Flags:
* F4K = Formatible 4 kilobyte sectors

#### :Context

Corsair:
* [Force MP510](https://pcpartpicker.com/product/BVbCmG) : 960GB : 1.3 : 3 : F4K

Samsung:
* [960 PRO](https://pcpartpicker.com/product/C3mxFT): 1TB : 1.2 : 3
* [980 PRO](https://pcpartpicker.com/product/f3cRsY): 2TB : 1.3 : 4

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
