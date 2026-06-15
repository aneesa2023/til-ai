# TIL: Android is becoming an "intelligence layer" — design for tasks, not sessions

**Category:** platform-updates

---

## What I learned

Google I/O 2026 signals a shift: instead of "user opens app → taps through UI → done" (success = sessions/retention), the new flow is "user asks Gemini → Gemini calls the right function in the right app → done" (success = tasks fulfilled). Android **AppFunctions** let an app expose specific actions (create task, start workout, book ride) directly to Gemini — and if you don't define them, Google's UI-automation framework will navigate your app's screens on the user's behalf anyway. ASO effectively becomes "Gemini-optimization": your function descriptions matter more than your Play Store listing. **Gemini Nano** runs on-device via ML Kit, giving finance/health/productivity apps intelligent features without sending data to the cloud.

## Why it matters

The UI layer becomes optional for many tasks, which breaks "time-in-app" and ad-impression-based monetization models. AppFunctions currently requires flagship hardware (started on Galaxy S26), so for the next few years apps need two parallel experiences: an agentic one for capable devices, and a traditional UI for everyone else. The winning developers will treat their app as a set of well-described capabilities an AI can compose with other apps' capabilities — not just a set of screens.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/android-as-an-intelligence-layer-how-gemini-is-rewriting-app-design)
