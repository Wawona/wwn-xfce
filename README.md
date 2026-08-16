# wwn-xfce

Wawona's port of the **Xfce** Wayland session (labwc/wlroots-based Xfce Wayland)
to run under Wawona on the Apple ecosystem and Android, App Store compliant.

> **Status: SKELETON.** flake + `registryFragment` skeleton + port plan only.
> Build stubs fail intentionally; full port is downstream.

## Delivery model

Xfce's Wayland session runs **nested** (its compositor is a Wawona client), or
**remotely via waypipe / NixOS VM** for the full GTK desktop. Individual Xfce
GTK apps can also run as direct Wawona clients.

## Port plan

1. Toolchain via `wwn-toolchain`; GTK stack cross-built or delivered via VM.
2. Compliance: no external process spawning of unvetted binaries; bundled
   session config; sandbox-safe dirs.
3. Prefer per-app GTK clients (native) + nested session compositor for the full
   desktop.
4. Replace `dependencies/xfce/stub.nix` per platform; expose `xfce-*`; register.
5. Port plan lists `xfce` `status: planned` → `approved` post-review.

Convention: [wwn-* porting convention](https://github.com/Wawona/Wawona/blob/main/docs/2026-wwn-porting-convention.md).
