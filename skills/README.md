# Reusable drawing skills

[human-readable-analog-schematics](human-readable-analog-schematics/SKILL.md)
contains the placement, routing, label and verification rules used for
transistor-level OTA/LDO schematics. Its references include the inspected
Analog Canvas gallery examples and version-specific native export limitations.

Copy the complete skill directory, including `references/` and `agents/`, to
the skill directory used by your agent. For Codex with its default location:

```sh
mkdir -p ~/.codex/skills
cp -R skills/human-readable-analog-schematics ~/.codex/skills/
```

PowerShell:

```powershell
$skillDirectory = Join-Path $env:USERPROFILE '.codex/skills'
New-Item -ItemType Directory -Force -Path $skillDirectory | Out-Null
Copy-Item -Recurse -LiteralPath 'skills/human-readable-analog-schematics' -Destination $skillDirectory
```

If a skill with that name already exists, review its differences before replacing
it. Use your configured skills location when it differs from the default.
Invoke `human-readable-analog-schematics` in the destination environment, or have
another agent read its `SKILL.md` and linked references directly.

These are drawing instructions, not a bundled Analog Canvas runtime or universal
automatic placement algorithm. Draw from the actual source netlist and verify
the saved/reopened native project's ordered pins, models, values and interface.
The skill does not authorize changes to recorded benchmark evidence or website
publication. Visual `M` means mega; SPICE parameters retain `meg`.
