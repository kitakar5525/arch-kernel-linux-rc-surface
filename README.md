# linux-surface for Arch Linux 5.0-rc kernel

- Currently kernel config is based on Arch Linux linux kernel 4.20.x, ported to 5.0-rcx

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`

See also:
- [kitakar5525/note-linux-on-surface-book-1: Notes to use Linux on Surface Book 1 with Performance Base](https://github.com/kitakar5525/note-linux-on-surface-book-1)
- [kitakar5525/note-linux-on-surface-3: Notes to use Linux on Surface 3](https://github.com/kitakar5525/note-linux-on-surface-3)



## How to build

```bash
git clone --depth 1 https://github.com/kitakar5525/arch-kernel-linux-rc50-surface
cd arch-kernel-linux-surface
makepkg -sC
```



## Issues for 5.0-rc

### IPTS is not working

```
kern  :info  : [Mon Feb 18 20:32:38 2019] i915 0000:00:02.0: GuC firmware version 9.33
kern  :info  : [Mon Feb 18 20:32:38 2019] i915 0000:00:02.0: GuC submission enabled
kern  :info  : [Mon Feb 18 20:32:38 2019] i915 0000:00:02.0: HuC enabled
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:gen8_init_common_ring [i915]] Applied 5 rcs0 workarounds
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:gen9_init_render_ring [i915]] Applied 4 whitelist workarounds
kern  :info  : [Mon Feb 18 20:32:38 2019] ipts: initializing ipts
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:guc_client_alloc [i915]] client 2 (high prio=no) reserved doorbell: 1
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:guc_client_alloc [i915]] reserved cacheline 0x80, next 0xc0, linesize 64
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:guc_client_alloc [i915]] new priority 3 client 00000000c7fb370a for engine(s) 0x47: stage_id 2
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:guc_client_alloc [i915]] doorbell id 1, cacheline offset 0x80
kern  :err   : [Mon Feb 18 20:32:38 2019] [drm:intel_guc_send_mmio [i915]] *ERROR* MMIO: GuC action 0x10 failed with error -5 0xf000f000
kern  :debug : [Mon Feb 18 20:32:38 2019] [drm:create_doorbell [i915]] Couldn't create client 2 doorbell: -5
kern  :err   : [Mon Feb 18 20:32:38 2019] [drm:intel_ipts_init [i915]] *ERROR* i915_guc_ipts_submission_enable failed : -5
kern  :info  : [Mon Feb 18 20:32:38 2019] [drm] Initialized i915 1.6.0 20181204 for 0000:00:02.0 on minor 0

kern  :info  : [Mon Feb 18 20:32:39 2019] IPTS ipts_mei_cl_init() is called
kern  :info  : [Mon Feb 18 20:32:39 2019] probing Intel Precise Touch & Stylus
kern  :info  : [Mon Feb 18 20:32:39 2019] IPTS using DMA_BIT_MASK(64)
kern  :err   : [Mon Feb 18 20:32:39 2019] ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: open gpu error : -5
kern  :err   : [Mon Feb 18 20:32:39 2019] ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: error in handling resp msg
```



## patch filename prefix

- 4416
	- Indicate that the patch is not from me (Hayataka@kitakar5525)
- 552?
	- Indicate that the patch is made by me
- 4416-*552?
	- Indicate that the patch is from another person and modified by me



## Changelog

2019-02-18 5.0.0-rc7-1-rc50-surface
- 5.0-rc7, [The Linux Kernel Archives](https://www.kernel.org/)

2019-02-18 5.0.0-rc6-2-rc50-surface
- [updating 4.19 patches · jakeday/linux-surface@2f1570d](https://github.com/jakeday/linux-surface/commit/2f1570d509eb7de8330ad4bc01b725c501ab9a8c)

2019-02-16 5.0.0-rc6-1-rc50-surface
-  jakeday patchset: [updating 4.19 patches · jakeday/linux-surface@5b7dd5a](https://github.com/jakeday/linux-surface/commit/5b7dd5a7a9967c34f04c7108f5c7fbe326e261e2)