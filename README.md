# minisforum-v3se-dsdt

Arch Linux (AUR) package that patches the ACPI DSDT on the **Minisforum V3 SE** tablet so that the built-in accelerometer (ST LSM6DS3TR-C, HID `SMO8B30`) is recognised by the kernel and screen-rotation works under Linux.

The package extracts the firmware DSDT, applies [fix-dsdt.patch](fix-dsdt.patch) to correct the accelerometer's ACPI definition, recompiles it with `iasl`, and installs the resulting `.aml` to `/etc/initcpio/acpi_override/` for `mkinitcpio` to bake into the initramfs as an ACPI override.

## Credits

This package is based on prior work by:

- **Thomas Rijpstra (@trijpstra-fourlights)** — original Minisforum V3 DSDT patch and PKGBUILD that this package is derived from.
- **Bartosz Sławianowski (@eplightning)** — original DSDT fix for the accelerometer, posted at [mudkipme/awesome-minisforum-v3#2 (comment)](https://github.com/mudkipme/awesome-minisforum-v3/issues/2#issuecomment-2279282784).

The V3 SE variant differs from the base V3 in the accelerometer's ACPI HID, so this package supersedes the generic `minisforum-v3-dsdt` (declared via `conflicts=`).

## License

[MIT](LICENSE).
