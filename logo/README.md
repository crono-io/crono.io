# Crono Brand Identity & Logo Specification

The Crono brand identity is designed to reflect a modern, cloud-native infrastructure scheduler and execution control plane: precise, predictable, and built for distributed systems. Rather than relying on literal clock imagery, every visual element—from the geometry of the mark to the typography and color system—represents how the software operates under the hood.

## 1. The Concept & Symbolism

The mark combines a segmented timeline with an orchestration graph to visualize discrete, coordinated execution rather than passive timekeeping:

- **Concentric Arcs (Execution Windows):** The broken, layered rings represent parallel job queues, intervals, and scheduled execution windows. Leaving strategic gaps in the outer rings forms a subtle, open `"C"` silhouette.
- **Connected Nodes (The Control Plane):** The linked dots anchored at the center represent distributed worker nodes, tasks, and dependencies being coordinated from a single control plane.
- **Radial Vectors (Triggers & Dispatch):** The angled lines intersecting the concentric arcs symbolize deterministic triggers—events firing at exact intervals across different layers of the schedule.

### Visual Hierarchy (Stroke Weights in `200×200` Mark)

The vector mark uses deliberate stroke-weight contrast so structure, dispatch origin, and worker dependencies remain distinct at any size:

- **Execution Windows (`9`):** Outer (`r = 76`), middle (`r = 54`), and inner (`r = 32`) concentric arcs carry the heaviest structural weight.
- **Primary Control-Plane Dispatch (`6.5`):** The diagonal teal vector from the central control node `(100, 100)` to the outer `1:30` node `(153.7, 46.3)` is bolder than downstream links to convey directionality from the control plane outward.
- **Orchestration Edges (`4.5`):** Secondary teal links (the upper-right curved edge and `3:00` horizontal worker branch) use a lighter stroke so they read as node-to-node dependencies rather than timeline rings.
- **Trigger Vector (`5.5`):** The lower-left off-white ray entering from outside the outer ring into `(73.1, 126.9)` represents cron schedules and manual runs firing into the system.

---

## 2. Color System

The palette separates **system structure** from **active execution state** using a high-contrast, dark-mode-first color scheme:

- **Teal / Mint (`#1CC8B4`) — Active Execution:** Applied to the central control node, dependency graph, and active ring segments. In developer and observability tooling, vibrant teal signals healthy throughput, live telemetry, and active signal flow—echoing the visual language of cloud-native ecosystems like NATS without harsh neon glare.
- **Warm Off-White (`#F2F2ED`) — Structural Framework & Wordmark:** Used for the outer timeline arcs, trigger vector, and typography. A slightly warm off-white eliminates harsh eye strain against dark terminals and documentation themes while maintaining crisp contrast.
- **Deep Obsidian (`#0E1116`) — Canvas Ground:** A neutral dark slate background that allows both foreground tones to read clearly without visual vibration. For light-mode contexts (such as light GitHub READMEs or print), `#F2F2ED` swaps cleanly to `#0E1116` while `#1CC8B4` shifts slightly deeper (`#0F9D8E`) to preserve contrast.

| Role | Token | Dark Mode (Primary) | Light Mode | Monochrome |
| --- | --- | --- | --- | --- |
| **Active Execution / Accent** | `--crono-accent` | `#1CC8B4` (Teal / Mint) | `#0F9D8E` | `currentColor` |
| **Structure & Wordmark** | `--crono-primary` | `#F2F2ED` (Warm Off-White) | `#0E1116` | `currentColor` |
| **Background / Ground** | `--crono-bg` | `#0E1116` (Deep Obsidian) | `#FFFFFF` | `transparent` |

---

## 3. Typography

The wordmark sets **`crono`** in a clean, lowercase geometric sans-serif (**Plus Jakarta Sans** SemiBold `600` or Bold `700`, with fallback to **Inter** or `system-ui, sans-serif`) at `-0.03em` letter spacing:

- **Lowercase Form:** Mirrors the command-line ergonomics and UNIX heritage of `cron`, making the name feel approachable, developer-native, and unpretentious.
- **Geometric Construction:** The circular counters of the `c`, `o`, and `o` directly echo the concentric rings and circular nodes of the symbol, creating visual harmony between the icon and text.
- **Balanced Weight & Tracking:** Medium-bold stroke thickness ensures the wordmark holds its visual weight alongside the multi-layered mark across documentation headers, CLI splash screens, and repository badges.

---

## 4. Assets in This Directory

| File | Purpose |
| --- | --- |
| `crono-mark.svg` | Standalone `200x200` icon mark for avatars, app icons, and badges. Uses `--crono-primary` and `--crono-accent` CSS custom properties. |
| `crono-logo.svg` | Horizontal `562x200` geometric vector lockup (`icon + crono`) optically centered on the `3 o'clock` node (`y = 100`) for headers, navbars, and README banners. |
| `crono-favicon.svg` | Simplified high-legibility `32x32` favicon (`stroke-width="12"`, inner ring omitted) on a `#0E1116` rounded square. |
| `crono-avatar.png` | Clean `512x512` avatar PNG rendered from `crono-mark.svg` on `#0E1116` with circle-safe padding for GitHub organizations. |
| `crono.png` | Standalone icon mark reference PNG. |
| `crono.jpg` | Original horizontal lockup prototype reference. |

---

## 5. Implementation & Usage Guidelines

- **Theming:** Define `--crono-primary` and `--crono-accent` in `:root` (dark mode) and `[data-theme="light"]` (light mode) so inline SVGs adapt automatically.
- **Small Sizes (`16x16` / `32x32`):** Use `crono-favicon.svg` rather than the detailed mark to preserve ring separation at browser-tab resolution.
- **Minimum Clear Space:** Maintain padding around the mark equal to at least `25%` of the icon's diameter.
