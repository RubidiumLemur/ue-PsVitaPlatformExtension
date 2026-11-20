# Unreal Engine PS Vita Platform Extension

A highly experimental PlayStation Vita platform extension for the Vite Unreal Engine 4.27 fork. It adds Vita platform integration, a native runtime and renderer, asset cooking and VPK packaging tools.

**Status: pre-pre-pre-alpha.** This is just the extension, not a stock Unreal Engine fork. More testing, natural edge cases, and ports are still needed.

## Installation

1. Place this directory at `Engine/Platforms/Vita` in the matching engine checkout.
2. Integrate the required shared Engine changes at their normal `Engine/Source` paths. See [Shared Engine integration](Docs/SharedEngineIntegration.md) for the file list, baseline and patch instructions.
3. Follow the [Windows setup and packaging guide](Docs/VITA-WINDOWS.md) for engine setup, VitaSDK, build dependencies and packaging.

The shared changes are already present in the development checkout. The included [integration patch](Build/SharedEngineIntegration.patch) is intended for a separate checkout at the documented baseline; review it and check that it applies before using it. Other fork-specific changes may also be required.

## Project setup

The current native game profile expects a C++ runtime module, a corresponding editor target, and a saved game default map. Enable the Python Editor Script Plugin for the Vita cook audit. Configure additional maps and assets loaded dynamically in `Config/VitaCook.ini`; see [Vita cook selection](Docs/VitaCookSelection.md).

Blueprint gameplay is restricted by the Vita runtime. Use native C++ gameplay and audit the actual project assets and references before removing Blueprints. Material graphs are processed through Vita's supported material path; see [material expression support](Source/Runtime/Engine/Private/Vita/MaterialExpressions.md) for supported inputs and limitations.

## Documentation

- [Windows setup and packaging](Docs/VITA-WINDOWS.md)
- [Shared Engine integration and file locations](Docs/SharedEngineIntegration.md)
- [Cook selection and auditing](Docs/VitaCookSelection.md)
- [Material expressions, Fresnel and world-aligned textures](Source/Runtime/Engine/Private/Vita/MaterialExpressions.md)
- [Vita particles plugin](Plugins/VitaParticles/README.md)

## AI Usage/Contributing
I mean, I hand coded this for a few months now, and I got codex to write comments/docs(if it touches the vita code I fear something will break).
Because I technically used AI in this project, ai protestors won't touch this.
If you want to contribute, go right ahead and submit a pr if you did something.
And if you want to contribute and its fully vibe coded, as long as its functional i guess its fine.
