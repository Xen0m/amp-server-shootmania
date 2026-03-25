# AMP ShootMania Elite Template

Generic AMP template for the ManiaPlanet / ShootMania Storm dedicated server, focused on `SMStormElite@nadeolabs`.

What this package gives you:
- a `GenericModule` app template for AMP
- automatic download of the official dedicated server archive
- automatic download of the base `SMStorm` and `SMStormElite@nadeolabs` title packs
- bootstrap config files for `dedicated_cfg.txt` and `elite-test.txt`

What it does not solve automatically:
- AMP cannot invent a valid Elite map pool for you
- you must add at least one `.Map.Gbx` yourself before first successful start

## Files

- `AMPMetadata.json`: repository metadata file used by AMPTemplates-style repositories
- `shootmania-elite.kvp`: main GenericModule template
- `shootmania-eliteconfig.json`: settings exposed in AMP
- `shootmania-elitemetaconfig.json`: metaconfig manifest placeholder
- `shootmania-eliteports.json`: reserved ports
- `shootmania-eliteupdates.json`: update/install stages
- `bootstrap/UserData/Config/dedicated_cfg.txt`: starter dedicated config
- `bootstrap/UserData/Maps/MatchSettings/elite-test.txt`: starter Elite matchsettings

## Before importing into AMP

1. Put these files in their own GitHub repository.
2. Edit `shootmania-eliteupdates.json` if you want AMP to fetch bootstrap files directly from your raw GitHub URLs.
   - This package currently installs the server and title packs only.
   - The two bootstrap files are included here for manual copy into the instance if you prefer.

## Import into AMP

1. In AMP, go to `Configuration -> Instance Deployment`.
2. Add a configuration repository in the format `user/repo:branch`.
3. Fetch the repository.
4. Create a new instance from the `xen0m-shootmania-elite` template.

## First start checklist

1. Install/update the instance in AMP.
2. Copy `bootstrap/UserData/Config/dedicated_cfg.txt` into the instance at:
   `UserData/Config/dedicated_cfg.txt`
3. Copy `bootstrap/UserData/Maps/MatchSettings/elite-test.txt` into the instance at:
   `UserData/Maps/MatchSettings/elite-test.txt`
4. Upload at least one Elite-compatible `.Map.Gbx` into:
   `UserData/Maps/My Maps/Elite/`
5. Edit `elite-test.txt` so the `<map><file>...</file></map>` entries match the uploaded map paths.
6. Start the instance.

## Notes

- The official dedicated server archive URL currently used is:
  `http://files.v04.maniaplanet.com/server/ManiaplanetServer_Latest.zip`
- The title packs currently used are:
  - `https://v4.live.maniaplanet.com/ingame/public/titles/download/SMStorm@nadeo.Title.Pack.gbx`
  - `https://v4.live.maniaplanet.com/ingame/public/titles/download/SMStormElite@nadeolabs.Title.Pack.gbx`
- The template targets both Windows and Linux.
- On Linux, the server executable is `./ManiaPlanetServer`.
- On Windows, the server executable is `ManiaPlanetServer.exe`.
