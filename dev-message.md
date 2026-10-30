## Commit Message
feat(extension): adapt Homebrewery Agentic for Antigravity IDE and package v1.4.1

## Changelog Entry
### [1.4.1] — 2026-10-29
#### Added
- **[LOW]** Added `deploy_homebrewery_agentic.ps1` deployment automation script in `05_Nexus_ToolBox/scripts/`.
- **[LOW]** Added `install:antigravity` script to `package.json` for rapid local builds and hot reloads.

#### Changed
- **[HIGH]** Rebranded extension identity to `cinesist.homebrewery-agentic` pointing to `https://github.com/Cinesist/homebrewery-agentic.git`.
- **[MEDIUM]** Updated `README.md` to introduce and document Homebrewery Agentic for both Antigravity IDE and VS Code.

#### Fixed
- **[CRITICAL]** Lowered `engines.vscode` and `@types/vscode` to `^1.107.0`, resolving runtime engine compatibility rejection with Antigravity IDE host version `1.107.0`.

## Devlog Entry
**Date:** 2026-10-29 | **Author:** Valerius (Sentinel of the Nexus) & Malakor (Grand Technomancer) | **Task:** Homebrewery Agentic Antigravity IDE Integration
**Problem Analysis:** The upstream `homebrewery4vsc` extension specified `"engines": { "vscode": "^1.109.0" }` in `package.json:18`. The local Antigravity IDE host environment runs on VS Code runtime `1.107.0`. When attempting to install the packaged `.vsix`, Antigravity IDE's CLI rejected the package with `Error: Unable to install extension as it is not compatible with the IDE '1.107.0'`. Furthermore, `@vscode/vsce` strictly verified that `@types/vscode` in `devDependencies` cannot exceed the lower engine bound.
**Solution Implemented:** Synchronized `engines.vscode` and `@types/vscode` to `^1.107.0`, matching the Antigravity IDE host environment. Rebranded the extension under publisher `cinesist` as `homebrewery-agentic`, updated repository pointers to `https://github.com/Cinesist/homebrewery-agentic.git`, refreshed the documentation for Antigravity IDE users, successfully compiled and packaged the extension into `homebrewery-agentic-1.4.1.vsix`, and verified hot installation into `C:\Users\Cinesist\.antigravity-ide\extensions\cinesist.homebrewery-agentic-1.4.1`.
