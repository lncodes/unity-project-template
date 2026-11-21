# Unity Project Template

Git configuration template for new **Last Night Codes** Unity projects. Contains only repository setup files — no Unity project — so it works with any Unity version.

> GitHub templates cannot include Git LFS files, so this template ships configuration only. Create the Unity project inside the new repository after generating it.

## What's included

| File | Purpose |
|---|---|
| `.gitignore` | Official Unity ignore rules from [github/gitignore](https://github.com/github/gitignore) (`Library/`, `Temp/`, `Logs/`, `Obj/`, `Build/`, `UserSettings/`, IDE files) |
| `.gitattributes` | Line endings, **UnityYAMLMerge** smart merge for scenes/prefabs/assets/meta, and **Git LFS** for images, models, audio, video, fonts and archives |
| `.editorconfig` | Basic C# formatting |

## New project checklist

1. On GitHub: **Use this template → Create a new repository** (owner `lncodes`, usually **Private** for games).
2. Clone it, then create or move the Unity project into the repository root (`Assets/`, `Packages/`, `ProjectSettings/` next to `.gitignore`).
3. Enable Git LFS once per clone:
   ```bash
   git lfs install --local
   ```
4. Register Unity Smart Merge (adjust the Unity version path):
   ```bash
   git config merge.unityyamlmerge.name "Unity SmartMerge (UnityYAMLMerge)"
   git config merge.unityyamlmerge.driver "'C:/Program Files/Unity/Hub/Editor/<version>/Editor/Data/Tools/UnityYAMLMerge.exe' merge -h -p --force %O %B %A %A"
   git config merge.unityyamlmerge.recursive binary
   ```
5. In Unity: **Project Settings → Editor** → *Version Control: Visible Meta Files* and *Asset Serialization: Force Text*.
6. Commit `.meta` files together with their assets. Replace this README with the project's own and add a `LICENSE` if the project is not proprietary.

## Branches

`main` is the stable branch. Use short-lived `feature/<name>` branches and merge via pull requests.
