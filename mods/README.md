# Quake II Mod Catalog

This directory tracks the Quake II mods we want to support as first-class AMP presets.

## Preservation rules

- Keep the original README/documentation with every recovered package.
- Preserve original author/team credits.
- Prefer source builds on Linux/x86_64 where source survives.
- Preserve original package names and version numbers where possible.
- Do not silently modify a historical package; patched builds should be clearly labeled.
- Keep provenance for every recovered archive: original site, mirror, filename, version and checksum.

## Target mods

1. Weapons of Destruction
2. ThreeWave / Quake II CTF
3. 4-Team CTF
4. Lithium II
5. Action Quake II / AQtion
6. Freeze Tag
7. Catch the Chicken
8. Rocket Arena 2
9. Chaos Deathmatch
10. Gloom
11. Jailbreak
12. Red Rover
13. QPong
14. Weapons Factory CTF
15. LMCTF
16. Holy Wars II
17. Vortex

See `catalog.json` for install/build status and source/archive references.

## Packaging layout

When we recover and verify a distributable package, use:

```text
mods/
  <mod-id>/
    README-original.txt
    provenance.json
    source/
    package/
```

For mods with preserved source, the preferred AMP installer path is to fetch/build from source rather than depend on a 25-year-old binary.
