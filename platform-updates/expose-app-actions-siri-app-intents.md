# TIL: App Intents is now the only on-ramp to Siri — and SiriKit is deprecated

**Category:** platform-updates

---

## What I learned

WWDC 2026's new Siri runs on a Gemini layer with on-screen awareness and the ability to take actions across apps — but to act on your app, it needs a structured description of what your app can *do*, which is App Intents (introduced 2022, pure Swift, compiled into app-bundle metadata so the OS knows your capabilities without launching the app). SiriKit (2016, XML-based, IPC-heavy) is now deprecated with a multi-year migration window. The core unit is an `AppIntent` struct with typed `@Parameter`s and a `perform()` body; an `AppShortcutsProvider` exposes it to Siri via natural-language phrases; domain objects are modeled as `AppEntity` so Siri can reference "that task." One integration surfaces actions across Siri, Spotlight, Shortcuts, the Action Button, widgets, and controls. Separately, Apple's on-device Foundation Models (~3B params, Swift-native, free, offline) gained image input and `@Generable` typed structured output.

## Why it matters

For Flutter/React Native devs, App Intents must be defined in native Swift — the `flutter_app_intents` plugin bridges Siri/Shortcuts/Spotlight into Dart via generated Swift handlers + MethodChannel/Pigeon, but the native seam can't be avoided (FlutterFlow needs the Pro export plan + manual Xcode Intents extension). Practical next steps: audit your app's top 5 user actions as candidate intents, model core objects as `AppEntity`, start the SiriKit migration now (it's a clock, not a crisis), and prototype one on-device Foundation Models feature (summarize/extract/classify) with an availability gate and fallback. The throughline: you participate in the new Siri by describing what your app can do, not by redesigning screens.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/expose-your-app-s-actions-or-lose-them-to-siri-s-ai)
