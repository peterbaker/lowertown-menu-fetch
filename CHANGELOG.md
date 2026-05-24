# Changelog

## 2026-05-24

### Added
- **Per-item `image` field in the bar/cafe consumer JSON.** `build_bar_menu` /
  `build_cafe_menu` now carry the Toast image URL (or `null`) so downstream
  consumers (the Framer menu sync) can use Toast images. Wall-display consumers
  ignore the new field.
- **Nested subgroup support.** `process_group` now recurses into nested Toast
  `menuGroups`, emitting `Parent — Sub` sections (e.g. `Spirits — Whisk(e)y`,
  `Spirits — Tequila`). Toast nests the Spirits group's bottles under
  Whisk(e)y/Tequila subgroups with no direct items on the parent, so without
  recursion they were dropped entirely.
