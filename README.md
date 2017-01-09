# Linux Kernel Patches for Loongson Platform

All patches are `git format-patch`'ed from [Loongnix official repository](http://www.loongnix.org/cgit/linux-4.4/), and are ported from Linux 4.4 to Linux 4.9.

Patches are currently under development (**in a mess**, but appliable (I didn't mean usable)). Use at your own risk.

## Structure

- `drivers`: Out-of-tree drivers for the use of several Loongson platforms.
- `features`: Support of Loongson processors.
- `platform`: Platform-specific supports. Contains support codes of several Loongson platforms.
  - Different from `drivers`, these patches are often essential for some Loongson platforms (that is, lack of these drivers may cause problems).
- `misc`: Misc...
- `pending`: TBD, often contains to-be-tested codes.

## Usage

Patches have dependencies of each other. To apply the patches correctly, use the [series](series) file:

```bash
export PATCHES=/path/to/loongson-patches

for i in `cat $PATCHES/series`; do
  patch -Np1 -i $PATCHES/$i;
done
```

That is, sequentially,

1. `drivers/`.
2. `platform/0028-MIPS-Loongson-Add-suspend-support-for-Loongson-3-Lap.patch`. Several patches depends on this patch.
3. `feature/`.
4. `platform/`. **Remember not to apply `0028-MIPS-Loongson-Add-suspend-support-for-Loongson-3-Lap.patch` again.**

Note on `pending/`: Loongson 3B support is a little bit dirty.
