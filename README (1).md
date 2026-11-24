# 🗡️ R36S 6S-V20 (2025-05-18 / Batch 2552) — Interactive Hardware Blueprint & Mod Grimoire

> *"It's dangerous to mod a clone board alone! Take this."*

Welcome to **TheBackPorch** hardware workshop repository for the **R36S 6S-V20 `2025-05-18` (`2552`)** handheld revision. This repository houses an interactive, browser-based CAD blueprint, Progressive Web App (PWA) icons, and printable field manuals engineered specifically around this board's **Rockchip RK3326-S (PX30S)** SoC, single-chip **XINYUWEI 1GB DDR3** memory layout, and **`rf3536k3ka.dtb`** panel requirement.

---

## 🚀 Launch the Interactive Blueprint App

* **Live Web App (GitHub Pages):** **[https://thebackporch.github.io/R36s-V20.2025-05-18.2552/](https://thebackporch.github.io/R36s-V20.2025-05-18.2552/)**
* **Install as a Standalone App (Chrome / Safari / Mobile):**
  1. Open the live link above in **Chrome** (Mac/Windows/Android) or **Safari** (iPhone/iPad).
  2. Click **Install page as app...** (Chrome `⋮ → Cast, save, and share`) or **Share → Add to Home Screen** (iOS/Android).
  3. The custom **Atomic Purple & Gold Triforce R36S icon** (`icon-512.png` + `manifest.json`) installs straight to your Dock or Home Screen.

---

## 📦 Repository Contents

| File | Purpose & Format |
| :--- | :--- |
| **`index.html`** | Interactive CAD Blueprint (`Rev 1.6`) with translucent shell & battery door opacity sliders, matte black/custom triggers, Metric (`mm`) / US Imperial (`in`) toggle, two-point caliper ruler, and live mod telemetry. |
| **`manifest.json`** | Progressive Web App manifest enabling standalone desktop & mobile installation with custom app branding. |
| **`icon-512.png`** | `512×512` custom Atomic Purple R36S & Triforce app icon used by Chrome, Android, and iOS home screens. |
| **`Hardware_Mod_Guide.pdf`** | Core hardware breakdown, non-upgradable limits, and step-by-step installation specs for drop-in and soldered upgrades. |
| **`HyruleHeroMasterFieldGuide_R36S(2552V20)_ZeldaEdition(VerifiedBuild).pdf`** | Illustrated Hyrule-themed master walkthrough covering firmware setup, DTB panel verification, and *Ship of Harkinian* tuning. |
| **`foldable1.pdf`** | Single-sheet duplex printable pocket booklet designed to fold cleanly with zero cutting required. |
| **`CodeFeatures1.pdf`** | Visual side-by-side code and architectural breakdown of the interactive CAD blueprint. |
| **`Code2.pdf`** | Unabridged full-stack source & systems architecture monograph covering coordinate math, SVG layer occlusion, and Linux `dtc` patching. |

---

## 🔬 6S-V20 `2025-05-18 (2552)` Hardware Profile & Survival Rules

* **SoC:** Rockchip **RK3326-S (PX30S)** Quad-Core ARM Cortex-A35 @ `1.3 GHz` (unlockable to `1512 MHz` CPU / `600 MHz` Mali-G31 GPU via OPP table edits).
* **Memory:** Single **XINYUWEI 1GB DDR3** chip (`~717 MB` usable). *Note: Empty `U2` pads lack PCB traces—use **512 MB LZ4 ZRAM**, **528 MHz DDR3 overclocking**, or a **single-chip 2GB DDR3L FBGA-96 BGA swap**.*
* **Display Panel:** 3.5-inch `640×480` IPS panel — **strictly requires `rf3536k3ka.dtb`** (standard R36S DTBs will boot to a black screen).
* **Battery & Charging:** `3500mAh 804068` Li-Ion cell (`JST-XH` 2-pin) with **no onboard BMS protection circuit**. Charge strictly via **5V 1A–1.5A USB-A to USB-C** on the `DC` port.

---

## 🛠️ Key Hardware & Kernel Mods Covered

1. **Memory & Silicon Tuning:** `512 MB LZ4 ZRAM`, `528 MHz` DDR3 clock unlock (`+61%` bandwidth), `1512 MHz` CPU / `600 MHz` GPU OPP override, and `15 × 15 × 2 mm` copper heatsink shim.
2. **Power & Audio Safety:** Upgrade to a **BMS-protected `804068` or `904068` (`3500–4000mAh`)** Li-Po battery and wire a **10Ω–22Ω inline resistor** on the positive speaker lead to prevent clone amp overvolting.
3. **Internal Wireless & Haptics:** Solder a stripped **RTL8188FTV / MT7601U** USB Wi-Fi module to the `USB-OTG` pads (`D+`, `D-`, `3.3V/5V`, `GND`) and add a **3.7V coin rumble motor** with an **M7 flyback diode** across `M+ / M-`.
4. **Controls & Debug:** Drop-in **Nintendo Switch Hall Effect joysticks** and **`1.5 Mbps` UART serial debug** header (`TX / RX / GND`) for live kernel boot logs on macOS.
