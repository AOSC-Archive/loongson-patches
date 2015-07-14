# loongson-patches
Patches (originally from Biergaizi) for Loongson-2F(Lemote) Platform.

## Rationale
The device running on Loongson-2F processor platform, (arguably) retailed as the Yeelong 8089 series, has a graphics chip namely ```Silicon Motion LynxEM+ (SM712)``` which has a (very) slow framebuffer driver shipped with the Linux Kernel.

## What is in here?
* 'base' contains base line patches for the goal explained in the ```Rationale``` section.
* 'additional' contains patches which is think valuable by AOSC, or much rather the "chick blood" part of things.
* 'tricks' contains some tricks to simplify the build process on AOSC OS (only).
