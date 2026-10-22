# ADR-0004: Brand theme A "Pure Intelligence" + English-first website
- Status: accepted
- Date: 2026-10-22
- Options considered: banks/options/brand-theme.md

**Simple matlab:** International launch ke liye saaf safed + navy design, emerald (kheti) aur indigo→cyan (AI). Website English me, app me English/Urdu switch.

## Decision
Tokens (Figma "VSN Tokens"): bg #FAFAF9, surface #FFFFFF, ink #0B1220, muted #5B6472, line #E6E8EC,
primary emerald #059669 / #10B981 / #ECFDF5, AI indigo #4F46E5 → cyan #06B6D4 (/ #818CF8 / #EEF2FF),
accent amber #F59E0B, danger rose #E11D48. Font: Plus Jakarta Sans + Noto Nastaliq Urdu.
Token names kept (e.g. `color/leaf-700` = primary) so code maps 1:1.
## Consequences
Light theme reads well outdoors on cheap phones; dark-mode can be added later as a second variable mode.
