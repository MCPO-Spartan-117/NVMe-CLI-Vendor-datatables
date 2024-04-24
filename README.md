# NVMe-CLI Vendor datatables
# [OVERVIEW for NVMes](https://github.com/MCPO-Spartan-117/NVMe-CLI-Vendor-datatables/blob/master/OVERVIEW.md)

This repo documents the featuresets of NVMes as there doesn't seem to be any official documention on most NVMes as for what they support.  
Also consult [linux-hardware](https://linux-hardware.org) for more general purpose data or if this repo is lacking any NVMe data you're looking for.

## TODO:

* Learn to use the other `id-*` arguments, currently don't have a NVMe that supports the other subsets that the other arguments need.

## Contributions
You can make a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to add more NVMes to this list.

Linux:
1. Get the `nvme-cli` package, for most distros it's just `nvme-cli`, so usually no distro resolving needed, however version 2.8 was used, 2.6 has `--vendor-specific` and `--verbose` with the same shorthand `-v` which errors out and older versions like 2.4 may not have `--verbose` entirely.
2. Use `TEMPVAR="<Vendor>/<Model>/<Capacity>-<Variant>/<Firmware>" mkdir -p $TEMPVAR && cd $TEMPVAR` in the git repo (Omit `<Variant>` if there is none, you can get firmware from `sudo nvme id-ctrl /dev/nvme? | grep "fr  *:"`).
3. Use `sudo nvme id-ctrl -HVv /dev/nvme? > id-ctrl` for the controller.
4. Use `sudo nvme id-ns -HVv /dev/nvme?n? > id-ns?` for one or all namespaces.
5. (Optional) Use `sudo dmesg | grep -e nvme? | grep -v -e "nvme[0-9]n[0-9]" -e BTRFS > dmesg` to log dmesg quirks for the nvme.

Windows:
1. Currently i don't know any way to get the same information as `nvme-cli` doesn't have a Windows build.
