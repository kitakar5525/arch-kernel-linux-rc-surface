# linux-surface for Arch Linux 5.0-rc kernel

- Currently kernel config is based on Arch Linux linux kernel 4.20.x, ported to 5.0-rcx

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`



## Issues for 5.0-rc

### IPTS is not working

```bash
Feb 12 09:34:39 localhost kernel: [drm:intel_guc_send_mmio [i915]] *ERROR* MMIO: GuC action 0x10 failed with error -5 0xf000f000
Feb 12 09:34:39 localhost kernel: [drm:intel_ipts_init [i915]] *ERROR* i915_guc_ipts_submission_enable failed : -5

Feb 12 09:34:40 localhost kernel: ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: open gpu error : -5
Feb 12 09:34:40 localhost kernel: ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: error in handling resp msg
```



## patch filename prefix

- 4416
	- Indicate that the patch is not from me (Hayataka@kitakar5525)
- 552?
	- Indicate that the patch is made by me
- 4416-*552?
	- Indicate that the patch is from another person and modified by me



## Changelog

2019-02-16
-  jakeday patchset: [updating 4.19 patches · jakeday/linux-surface@5b7dd5a](https://github.com/jakeday/linux-surface/commit/5b7dd5a7a9967c34f04c7108f5c7fbe326e261e2)