# NVMe-CLI Vendor datatables

This repo documents the featuresets of NVMes as there doesn't seem to be any official documention on most NVMes as for what they support.

## Currently has data for:

#### Context:
Vendor:
* (Model):(Capacities)-(Variants):(NVMe Protocol)

Corsair:
* [Force MP510](https://pcpartpicker.com/product/BVbCmG/corsair-mp510-960-gb-m2-2280-nvme-solid-state-drive-cssd-f960gbmp510b): 960GB : 1.3

## TODO:

* Add Samsung 970/80 EVO(Have one of them somewhere inaccessible atm, don't remember which though)
* Learn to use the other `id-*` arguments, currently don't have a NVMe that supports the other subsets that the other arguments need.

## Contributions
You can make a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to add more NVMes to this list.

1. Use `TEMPVAR="<Vendor>/<Model>/<Capacity>-<Variant>" mkdir -p $TEMPVAR && cd $TEMPVAR` in the git repo (Omit `<Variant>` if there is none).
2. Use `sudo nvme id-ctrl -HVv /dev/nvme? > id-ctrl` for the controller.
3. Use `sudo nvme id-ns -HVv /dev/nvme?n? > id-ns` for one or all namespaces.
