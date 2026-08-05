<h1 align="center">
  <a name="logo" href="https://www.vCloudInfo.com/tag/iot"><img src="https://raw.githubusercontent.com/CCOSTAN/Home-AssistantConfig/master/x_profile.png" alt="Bear Stone Smart Home" width="200"></a>
  <br>
  Bear Stone Smart Home Documentation
</h1>
<h4 align="center">Be sure to :star: my configuration repo so you can keep up to date on any daily progress!</h4>

<div align="center">

[![X Follow](https://img.shields.io/static/v1?label=talk&message=3k&color=blue&logo=twitter&style=for-the-badge)](https://x.com/ccostan)
[![YouTube Subscribe](https://img.shields.io/badge/VIEW-6.8K-FF0000&logo=Youtube&logoColor=%23DF5D44&style=for-the-badge)](https://www.youtube.com/vCloudInfo?sub_confirmation=1)
[![GitHub Stars](https://img.shields.io/github/stars/CCOSTAN/Home-AssistantConfig.svg?label=STARS&logo=github&style=for-the-badge)](https://github.com/CCOSTAN/Home-AssistantConfig?tab=stargazers) <br>
[![HA Version Badge](https://raw.githubusercontent.com/ccostan/home-assistantconfig/master/ha-version-badge.svg)](https://github.com/CCOSTAN/Home-AssistantConfig/blob/master/config/.HA_VERSION)
[![Last Commit](https://img.shields.io/github/last-commit/CCOSTAN/Home-AssistantConfig/master?style=plastic)](https://github.com/CCOSTAN/Home-AssistantConfig/commits/master)
[![Commit Activity](https://img.shields.io/github/commit-activity/y/CCOSTAN/Home-AssistantConfig.svg?style=plastic)](https://github.com/CCOSTAN/Home-AssistantConfig/commits/master)

</div>

# Home Assistant Codex Skills

[![Tests](https://github.com/CCOSTAN/Home-Assistant-Codex-Skills/actions/workflows/tests.yml/badge.svg)](https://github.com/CCOSTAN/Home-Assistant-Codex-Skills/actions/workflows/tests.yml)
[![GitHub stars](https://img.shields.io/github/stars/CCOSTAN/Home-Assistant-Codex-Skills?logo=github)](https://github.com/CCOSTAN/Home-Assistant-Codex-Skills/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Reusable [Codex skills](https://learn.chatgpt.com/docs/build-skills) for designing, validating, documenting, and diagramming Home Assistant and self-hosted infrastructure.

These skills grew out of the public [Bear Stone Home Assistant configuration](https://github.com/CCOSTAN/Home-AssistantConfig). They are maintained separately so people can install only the automation guidance they need, report issues, and contribute improvements without cloning a full Home Assistant configuration.

## Included skills

| Skill | Purpose |
| --- | --- |
| [`homeassistant-dashboard-designer`](homeassistant-dashboard-designer/SKILL.md) | Design and refactor Lovelace YAML with constrained layouts, reusable templates, and validation. |
| [`homeassistant-yaml-dry-verifier`](homeassistant-yaml-dry-verifier/SKILL.md) | Detect duplicated Home Assistant triggers, conditions, actions, sequences, and misplaced shared scripts. |
| [`infrastructure-doc-sync`](infrastructure-doc-sync/SKILL.md) | Keep infrastructure instructions, README files, runbooks, dashboards, and inventory snapshots aligned. |
| [`network-architecture-diagrammer`](network-architecture-diagrammer/SKILL.md) | Create Mermaid-first Home Assistant and homelab diagrams that import cleanly into Excalidraw. |

## Install

Clone the repository:

```sh
git clone https://github.com/CCOSTAN/Home-Assistant-Codex-Skills.git
```

Copy the skill folders you want into a Codex skills directory:

- User-wide on Linux/macOS: `$HOME/.agents/skills/<skill-name>/`
- User-wide on Windows: `%USERPROFILE%\.agents\skills\<skill-name>\`
- Repository-scoped: `<repo>/.agents/skills/<skill-name>/`

Each installed folder must contain its own `SKILL.md`. Restart Codex or begin a new session after installing so the skill catalog is refreshed.

Example for Linux/macOS:

```sh
cp -R Home-Assistant-Codex-Skills/homeassistant-yaml-dry-verifier "$HOME/.agents/skills/"
```

Example for PowerShell:

```powershell
Copy-Item -Recurse Home-Assistant-Codex-Skills\homeassistant-yaml-dry-verifier "$env:USERPROFILE\.agents\skills\"
```

You can also invoke `$skill-installer` and ask it to install one or more skill folders from this GitHub repository.

## Use

Invoke an installed skill by name, for example:

```text
$homeassistant-yaml-dry-verifier check the packages I changed and report duplicated automation logic
```

Read the selected skill's `SKILL.md` for its workflow and optional tooling. The Python validators use the standard library plus PyYAML where noted.

## Validator CLI examples

Validate a Lovelace view:

```sh
python homeassistant-dashboard-designer/scripts/validate_lovelace_view.py /path/to/changed-view.yaml
```

Scan Home Assistant YAML for duplicated logic:

```sh
python homeassistant-yaml-dry-verifier/scripts/verify_ha_yaml_dry.py /path/to/config/packages --strict
```

Validate Mermaid before importing it into Excalidraw:

```sh
python network-architecture-diagrammer/scripts/validate_mermaid_excalidraw.py /path/to/diagram.mmd
```

## Walkthroughs and related projects

- Dashboard design walkthrough: [![Watch on YouTube](https://img.shields.io/badge/Watch-YouTube-FF0000?logo=youtube&logoColor=white)](https://youtu.be/aFis2YPeSuY)
- Dashboard design companion post: [![vCloudInfo Blog Post](https://img.shields.io/static/v1?label=vCloudInfo&message=Blog%20Post&color=21759B&logo=wordpress&logoColor=white)](https://www.vcloudinfo.com/2026/02/home-assistant-dashboard-design-system-button-card.html)
- Example Home Assistant configuration: [CCOSTAN/Home-AssistantConfig](https://github.com/CCOSTAN/Home-AssistantConfig)
- More Home Assistant articles: [vCloudInfo Home Assistant](https://www.vcloudinfo.com/search/label/Home%20Assistant)
- Videos: [vCloudInfo on YouTube](https://www.youtube.com/vCloudInfo)

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for validation and public-content requirements.

This repository intentionally excludes personal runtime data, credentials, internal hostnames, private infrastructure addresses, and machine-specific agent instruction files.

## License

Released under the [MIT License](LICENSE).
