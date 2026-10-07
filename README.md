# AMPGameServer

Custom [CubeCoders AMP](https://cubecoders.com/AMP) GenericModule templates.

## Quake II - Q2PRO

Linux-first Quake II dedicated server template using Q2PRO.

### Features

- Q2PRO dedicated server built from current upstream source
- Vanilla `baseq2`
- AMP web UI mod selector with classic Quake II presets
- One-click Weapons of Destruction Linux build/install
- Custom/legacy mod directory support
- RCON
- Deathmatch / co-op settings
- Frag limit / time limit / dmflags
- Public master listing
- Client downloads and FastDL URL
- Editable map rotation
- Optional Tastyspleen community map download modes

### AMP repository

Add this repository in AMP:

```text
hypercube33/AMPGameServer:main
```

Then use **ADS -> Configuration -> Instance Deployment -> Configuration Repositories -> Fetch Latest**.

### Required retail data

This repository does not contain copyrighted Quake II retail game data.

After creating the instance, place your legally-owned Quake II data in:

```text
q2pro/server/baseq2/
```

At minimum, supply the appropriate `pak*.pak` files from your Quake II installation.

### Linux build

Q2PRO does not publish Linux binaries. The AMP update stage clones Q2PRO and builds the dedicated server from source with Meson. The template declares the required build packages for AMP's Linux container.

### Map packs

Set **Community Map Pack** before running **Update**:

- `None` - no community maps
- `ClassicDM` - a curated classic DM selection
- `TastyspleenAll` - downloads all BSP files linked from Tastyspleen's Quake II baseq2 map index

Downloaded maps are installed into `baseq2/maps/`. Map rotation remains explicitly controlled by AMP's **Map Rotation** setting so the giant archive does not try to cram thousands of names into one ancient Quake II CVAR.

The Tastyspleen option is intentionally enormous. Storage has been warned. Humanity has not.


### Quake II mod presets

The **Game / Mod** setting now selects the value passed to Q2PRO as `+set game`.

Current presets include Vanilla, Weapons of Destruction, Action Quake II/AQtion, ThreeWave CTF, 4-Team CTF, Freeze Tag, Catch the Chicken, Rocket Arena 2, Chaos Deathmatch, Jailbreak, Red Rover, QPong, Weapons Factory CTF, LMCTF, Holy Wars II, Lithium II, Gloom and Vortex.

**Weapons of Destruction** is currently a verified one-click installer: select it, run **Update**, then start the server. AMP builds the maintained Linux source and installs its original resources into `server/weapons/`.

The remaining legacy presets currently select their canonical game directory. Their automatic installers are being added only as each original package/source is recovered and verified. This keeps the AMP UI useful without presenting a fake install button that produces a dead server.

Gloom and Vortex remain external/manual-only by project policy; this repository will not rehost their packages.

See `mods/catalog.json` for preservation/install status.
