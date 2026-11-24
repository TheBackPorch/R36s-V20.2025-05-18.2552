# 🔮 R36S `6S-V20 2025-05-18 (2552)` — The BackPorch Field Grimoire & Interactive Blueprint

> *"It’s dangerous to solder alone! Take this."*  
> Welcome to **The BackPorch** workshop archive—a community-built hardware compendium, CAD inspection suite, and modder's spellbook dedicated to unlocking the hidden potential of the **R36S `6S-V20 2025-05-18 (2552)`** clone mainboard.

---

### 🌐 Launch the Live Interactive CAD Blueprint
**[✨ Click Here to Open the Interactive R36S 6S-V20 Blueprint App ✨](https://thebackporch.github.io/R36s-V20.2025-05-18.2552/)**

* Works straight in **Safari, Chrome, Firefox, and mobile browsers** with zero installation required.
* **Pro Tip (Mobile App Mode):** Open the link on iOS or Android and tap **Share → Add to Home Screen** to summon the custom **Hyrule Triforce × Atomic Purple R36S** launcher icon directly onto your device.

<p align="center">
  <img src="R36S_V20_Blueprint_QR.png" alt="Scan to Launch R36S 6S-V20 Interactive Blueprint" width="240"/>
</p>

---

### 📜 What's Inside This Scroll Archive?

| File in Repo | Artifact Type | What It Unlocks |
| :--- | :--- | :--- |
| **`index.html`** | Interactive Web App | Full-height vertical PCB CAD blueprint (`68.5 × 112.0 mm` PCB / `73.0 × 118.0 mm` shell) with translucent shell & battery door opacity sliders, stock matte-black rear triggers (`L2/L1/R1/R2`), dual **Metric (`mm`) / US Imperial (`in`)** unit switcher, two-point **Caliper Ruler**, and **Original vs. Mod Loadout** comparator. |
| **`HyruleHeroMasterFieldGuide_R36S(2552V20)_ZeldaEdition(VerifiedBuild).pdf`** | Master Field Guide | Verified setup, firmware (`ArkOS4Clone` / `dArkOS4Clone`), `rf3536k3ka.dtb` display locking, and *Ship of Harkinian* tuning walkthrough. |
| **`Hardware_Mod_Guide.pdf`** | Technical Mod Manual | Complete hardware teardown notes, thermal shim sizing, BMS battery safety rules, and drop-in upgrades. |
| **`foldable1.pdf`** | Zero-Cut Pocket Booklet | Single-sheet duplex printable booklet—print double-sided (flip on short edge) and fold once down the middle with zero scissors needed. |
| **`CodeFeatures1.pdf`** | Visual Dev & CAD Guide | Side-by-side architectural breakdown pairing the app's coordinate math, SVG layer stack, and CTM caliper engine with visual diagrams. |
| **`Code2.pdf`** | Unabridged Source Monograph | Full-stack engineering reference documenting the state store, telemetry formulas, and standalone HTML5/SVG starter code for anyone who wants to fork or build their own hardware tool. |

---

### 🧬 Hardware Anatomy: `6S-V20 2025-05-18 (2552)`
If you peek through a translucent shell or pop open the back cover and spot **`R36S-V20 2025-05-18`** silkscreened on the PCB with a **`2552`** stamp, you are holding a specific single-RAM-chip variant—**not** a standard dual-chip unit and **not** the 4-inch R36S MAX:

* **SoC:** Rockchip **RK3326-S (PX30S)** Quad-Core ARM Cortex-A35 (stock-capped at `1.3 GHz`, unlockable via OPP table edits)
* **Memory:** Single **XINYUWEI 1GB DDR3** IC (`~717 MB` usable out of the box; second RAM footprint unpopulated)
* **Display Panel:** 3.5-inch `640 × 480` IPS — **strictly requires `rf3536k3ka.dtb`** (standard DTBs result in a black screen)
* **Stock Power Cell:** `3500mAh` `804068` Li-ion (`JST-XH 2-pin`, **no onboard BMS protection** — stick strictly to **5V 1A–1.5A USB-A to USB-C** charging on the DC port!)
* **Chassis & Bay Dimensions:** `73.0 × 118.0 mm` outer shell (`2.87" × 4.65"`), `68.5 × 112.0 mm` mainboard (`2.70" × 4.41"`), `68.5 × 40.5 × 9.2 mm` rear battery bay

---

### ⚡ Arcane Upgrades & Workarounds
Even without traces on the second RAM footprint, there is plenty of magic left in this board:
1. **512 MB LZ4 ZRAM Pool:** Instant kernel-level memory compression that eliminates out-of-memory crashes in heavy PortMaster titles (*Ship of Harkinian*, *Vice City*) with near-zero latency.
2. **DDR3 & SoC OPP Clock Unlocking:** Decompiling `rf3536k3ka.dtb` via `dtc` to push RAM clocks from **`328 MHz` → `528 MHz` (+61% bandwidth)** and CPU/GPU clocks up to **`1512 MHz` / `600 MHz`** (paired with a `15 × 15 × 2 mm` copper heatsink shim).
3. **Single-Footprint 2GB DDR3L BGA Swap:** Hot-air rework replacement of the single XINYUWEI chip with a pin-compatible `2GB (16Gbit)` DDR3L IC + `ddrbin` loader update.
4. **Board-Level Soldering Mods:**
   * **Internal Wi-Fi:** Micro `RTL8188FTV` / `MT7601U` module wired to the `USB-OTG` pads (`D+`, `D-`, `3.3V/5V`, `GND`).
   * **Haptic Rumble:** `3.7V` coin vibration motor across `M+` / `M-` with a mandatory **M7 flyback diode** (stripe to `+`).
   * **Speaker Overvolt Shield:** `10Ω–22Ω` inline resistor on the `+` speaker lead to protect upgraded iPhone/Switch drivers from clone amp spikes.
   * **UART Debug Header:** `TX / RX / GND` test pads (`1.5 Mbps` baud) for live U-Boot and Linux kernel logs.
   * **BMS Battery & Hall Sticks:** Protected `804068`/`904068` (`3500–4000mAh`) cell + Switch-compatible Hall effect joysticks.

---

### 🛠️ Built Together on The BackPorch
Crafted iteratively on a headless M1 MacBook setup alongside **Gemini** to help fellow tinkerers, repair techs, and retro handheld adventurers visualize, measure, and push their `6S-V20` hardware safely. Feel free to download, print, fork, or submit pull requests to expand the archive!
