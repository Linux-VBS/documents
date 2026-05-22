# Linux Virtualization-Based Security (LVBS) — Resource Links

A curated set of links covering the LVBS umbrella project and its constituent
efforts: the Hyper-V VTL backend (LVBS-HyperV), the KVM/Heki backend
(LVBS-KVM), Paolo Bonzini's KVM VM Planes patch series (the common in-kernel
substrate planned to support both VTLs and AMD VMPLs), and the Microsoft
Litebox secure-kernel library OS that runs in the higher-privileged
environment.

---

## 1. Project home pages & code

- **LVBS umbrella org (docs/discussions):** https://github.com/Linux-VBS
- **Heki / LVBS-KVM (PoC code, history):** https://github.com/heki-linux
  - LVBS Hyper-V tree (VTL0 + VTL1 guest kernel changes): https://github.com/heki-linux/lvbs-linux
- **Litebox (Rust secure-kernel library OS, MIT):** https://github.com/microsoft/litebox

## 2. Slides & conference presentations

- **LPC 2023 — Linux Virtualization Based Security (LVBS)** (umbrella architecture intro)
  - Session page: https://lpc.events/event/17/contributions/1515/
  - Slides (PDF): https://lpc.events/event/17/contributions/1515/attachments/1353/2717/LPC_2023_LVBS.pdf
- **LPC 2023 — Heki companion session:** https://lpc.events/event/17/contributions/1486/
- **SCaLE 22x (2025) — Linux Virtualization Based Security:** https://www.socallinuxexpo.org/scale/22x/presentations/linux-virtualization-based-security-lvbs/
- **Kernel Recipes 2025 — Linux Virtualization Based Security – Why, What and How?** (Thara Gopinath): https://kernel-recipes.org/en/2025/schedule/linux-virtualization-based-security-why-what-and-how/
- **Speaker Deck — LVBS slides** (covers Hyper-V VTL / AMD VMPL / Intel TD Partition / Arm CCA mapping to the "plane" abstraction): https://speakerdeck.com/ennael/linux-virtualization-based-security
- **Open Source Summit 2024 — *Booting a Linux Kernel in a Higher Privilege Level*** (VTL1 secure-kernel boot): referenced from https://github.com/heki-linux
- **Linux Security Summit 2024 — Linux Virtualization Based Security:** referenced from https://github.com/heki-linux

## 3. Upstream patch postings — Heki / LVBS-KVM

Posted by Mickaël Salaün (`mic@digikod.net`) and Madhavan T. Venkataraman
(`madvenka@linux.microsoft.com`).

- **v1 — RFC: Hypervisor-Enforced Kernel Integrity** (May 2023): https://lore.kernel.org/all/20230505152046.6575-1-mic@digikod.net/
- **v2 — RFC PATCH v2 00/19** (Nov 2023): https://lore.kernel.org/r/20231113022326.24388-1-mic@digikod.net
  - LWN coverage: https://lwn.net/Articles/951240/
- **v3 — RFC PATCH v3 0/5: Heki – CR pinning** (May 2024): https://lore.kernel.org/r/20240503131910.307630-1-mic@digikod.net
  - LWN coverage: https://lwn.net/Articles/972318/

## 4. Upstream patch postings — KVM VM Planes (Paolo Bonzini)

The common KVM-side mechanism for "privilege levels within a guest" that
underlies VTLs and VMPLs.

- **RFC v0 — Documentation cleanup + "VM planes" concept** (Oct 2024): https://lore.kernel.org/lkml/20241023124507.280382-1-pbonzini@redhat.com/
  - LWN coverage: https://lwn.net/Articles/995318/
- **Full series — KVM: VM planes (29 patches)** (Apr 2025): https://lore.kernel.org/lkml/20250401161118.790588-1-pbonzini@redhat.com/
  - LWN coverage: https://lwn.net/Articles/1016113/
  - Tree: `git://git.kernel.org/pub/scm/virt/kvm/kvm.git`, branch `planes-20250401`

## 5. Litebox — secure-kernel library OS

Litebox is the Rust-based library OS being developed in collaboration with
LVBS to play the role of "secure kernel" running at the higher privilege level
(VTL1 / equivalent), protecting the normal guest kernel through virtualization
hardware.

- **Repo:** https://github.com/microsoft/litebox
- **James Morris announcement (social.kernel.org):** https://social.kernel.org/notice/B2xBkzWsBX0NerohSC
- **Phoronix writeup:** https://www.phoronix.com/news/Microsoft-LiteBox
- **Help Net Security writeup:** https://www.helpnetsecurity.com/2026/02/05/microsoft-litebox-security-focused-open-source-library-os/

## 6. Background / explainers

- **Medium — *The Linux Security Journey: LVBS*** (Shlomi Boutnaru): https://medium.com/@boutnaru/the-linux-security-journey-lvbs-linux-virtualization-based-security-e80e8c15e186
- **Microsoft Hyper-V TLFS — Virtual Secure Mode** (the VTL model LVBS-HyperV builds on): https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/tlfs/vsm
