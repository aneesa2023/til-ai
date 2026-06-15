Blog 9) Title- 90 minutes, not a day: how MCPs — not the model — sped up my mobile dev workflow
Subtitle- MCPs for Mobile Devs: Build Faster with Xcode MCP, Flutter MCP, Expo & Firebase
Link- https://aneesas.hashnode.dev/90-minutes-not-a-day-how-mcps-not-the-model-sped-up-my-mobile-dev-workflow
Last week I built a feature in 90 minutes that would have taken me a full day 6 months ago. The difference wasn't the AI model. It was the MCPs.

For anyone unfamiliar: MCP (Model Context Protocol) is an open standard that lets AI assistants connect to real tools - your Xcode, your simulator, your Figma file, your Crashlytics dashboard. The AI isn't guessing anymore. It's reading the actual data.

What I learned going deep on this matters for mobile devs specifically:

1.  The platform vendors are all in. Apple shipped a built-in MCP server in Xcode. Flutter's official MCP is stable. Expo and Firebase both went GA. This isn't experimental anymore. → 𝗫𝗰𝗼𝗱𝗲 𝗠𝗖𝗣: https://lnkd.in/esDdm6CG → 𝗙𝗹𝘂𝘁𝘁𝗲𝗿 𝗠𝗖𝗣: https://lnkd.in/e5-7j4tM → 𝗘𝘅𝗽𝗼 𝗠𝗖𝗣: https://lnkd.in/eEigKfyU → 𝗙𝗶𝗿𝗲𝗯𝗮𝘀𝗲 𝗠𝗖𝗣: https://lnkd.in/ekr34qNQ
    
2.  The Figma Dev Mode MCP : AI reads your actual design, variables, components, layout instead of squinting at a screenshot. Design-to-Flutter or design-to-SwiftUI becomes a 15-minute review job instead of a half-day translation. → https://lnkd.in/eD4sMzty
    
3.  Crash triage changes completely. With the Firebase Crashlytics MCP, you ask "what's the top new crash this week and which commit likely caused it?" and get an actionable answer with stack traces. No more dashboard tab-switching. → https://lnkd.in/ejqGaF9Y
    
4.  Cross-platform device control is solved. Mobile MCP (mobile-next) abstracts iOS and Android into one interface. Build once, drive both. XcodeBuildMCP by Sentry is the deeper option for iOS-only with LLDB debugging built in. → Mobile MCP: https://lnkd.in/e87wJsv7 → XcodeBuildMCP: https://lnkd.in/eyNeVTiy
    
5.  The 𝘀𝗺𝗮𝗿𝘁𝗲𝘀𝘁 𝗺𝗼𝘃𝗲 is building 1-2 𝗰𝘂𝘀𝘁𝗼𝗺 𝗠𝗖𝗣𝘀 for your 𝘁𝗲𝗮𝗺'𝘀 𝘀𝗽𝗲𝗰𝗶𝗳𝗶𝗰 𝘄𝗼𝗿𝗸𝗳𝗹𝗼𝘄 — internal design system, proprietary backend, custom CI. Off-the-shelf gets you 80%. Custom MCPs get you the last 20% that actually matches how your team works.
    

Before building your own, check if it already exists. The MCP ecosystem is growing fast. I found this directory with categories spanning Deployment & DevOps, Security & Testing, Web Scraping & Data Collection, Collaboration tools, and official MCPs from major vendors. You can also submit your own MCP. → https://lnkd.in/e5FBFade

hashtag#AIAgents hashtag#DeveloperTools hashtag#ModelContextProtocol hashtag#MCP hashtag#AICodingAssistant hashtag#AgenticAI hashtag#DevProductivity



Blog 10) Title- Preventing Merge Nightmares: Claude + FlutterFlow Done Right
Subtitle- A practical guide to using the CLI + MCP approach so Claude’s edits respect FlutterFlow patterns and conflicts are detected, not silently merged.
Link- https://aneesas.hashnode.dev/preventing-merge-nightmares-claude-flutterflow-done-right
"If you mix FlutterFlow-generated code with Claude-generated code, won't you end up with unreadable, hard-to-maintain code?"

100% fair concern. And the FlutterFlow documentation actually explains how to avoid exactly that problem.

This is a nightmare if If you Design in FlutterFlow → Export → Edit with Claude → Re-import → Repeat. FlutterFlow patterns clash with Claude patterns. Code becomes a mess.

The CLI + MCP Solution is actually different.

Claude doesn't generate separate files competing with FlutterFlow's code. Claude injects changes into FlutterFlow's project structure. FlutterFlow's patterns stay intact. You extend within the system, not on top of it.

𝗛𝗲𝗿𝗲'𝘀 𝗵𝗼𝘄 𝘁𝗵𝗲 𝘀𝘆𝘀𝘁𝗲𝗺 𝗽𝗿𝗲𝘃𝗲𝗻𝘁𝘀 𝘁𝗵𝗲 𝗺𝗲𝗿𝗴𝗲 𝗺𝗲𝘀𝘀:

𝟭) 𝗢𝗽𝘁𝗶𝗺𝗶𝘀𝘁𝗶𝗰 𝗖𝗼𝗻𝗰𝘂𝗿𝗿𝗲𝗻𝗰𝘆 (𝗕𝘂𝗶𝗹𝘁-𝗶𝗻 𝗦𝗮𝗳𝗲𝘁𝘆)

From FlutterFlow docs: "When the agent pushes, the server checks the project's last-modified timestamp against the agent's snapshot. If anyone else modified the project in between, the push is rejected. The agent will re-read the latest state and retry. 𝗡𝗼𝘁𝗵𝗶𝗻𝗴 𝗴𝗲𝘁𝘀 𝘀𝗶𝗹𝗲𝗻𝘁𝗹𝘆 𝗼𝘃𝗲𝗿𝘄𝗿𝗶𝘁𝘁𝗲𝗻."

Conflicts are detected automatically. Not silently merged. Not a nightmare.

𝟮️) 𝗖𝗼𝗻𝘁𝗲𝘅𝘁 𝗥𝗲𝗳𝗿𝗲𝘀𝗵 (𝗣𝗿𝗲𝘃𝗲𝗻𝘁𝘀 𝗦𝘁𝗮𝗹𝗲 𝗦𝘁𝗮𝘁𝗲)

If you make visual edits, you run `𝗳𝗹𝘂𝘁𝘁𝗲𝗿𝗳𝗹𝗼𝘄 𝗮𝗶 𝗿𝗲𝗳𝗿𝗲𝘀𝗵-𝗰𝗼𝗻𝘁𝗲𝘅𝘁`. Claude reads the latest state before planning the next change. No stale snapshots fighting.

𝟯) .𝗳𝗹𝘂𝘁𝘁𝗲𝗿𝗳𝗹𝗼𝘄𝗶𝗴𝗻𝗼𝗿𝗲 (𝗣𝗿𝗼𝘁𝗲𝗰𝘁𝘀 𝗖𝘂𝘀𝘁𝗼𝗺 𝗖𝗼𝗱𝗲)

If you export locally for heavy customization: create a `.flutterflowignore` file. Your custom Dart files won't be overwritten on re-export.

𝟰) 𝗕𝗿𝗮𝗻𝗰𝗵𝗲𝘀 (𝗦𝗮𝗳𝗲 𝗘𝘅𝗽𝗲𝗿𝗶𝗺𝗲𝗻𝘁𝗮𝘁𝗶𝗼𝗻)

Each branch has its own project ID. Work with Claude on a feature branch, test it, merge back. No risk to main.

𝗧𝗵𝗲 𝗥𝗶𝗴𝗵𝘁 𝗪𝗼𝗿𝗸𝗳𝗹𝗼𝘄:

1.  `flutterflow ai init --project [your-id]`
    
2.  `claude`
    
3.  Describe changes: "add a profile screen", "wire up Firebase Auth"
    
4.  Claude reads current state → plans change → pushes through MCP
    
5.  You verify in the visual editor
    
6.  If you make visual changes, refresh context
    
7.  Repeat
    

What This ISN'T: ❌ Stacking Claude on top of FlutterFlow's code ❌ Exporting and re-importing repeatedly ❌ Mixing competing code patterns ❌ Silent merge nightmare

What This IS: ✅ Claude works within FlutterFlow's structure ✅ Respecting FlutterFlow's patterns ✅ Conflict detection built in ✅ Frequent context refresh keeps things in sync

They work beside each other, not on top of each other.

If you've had bad experiences mixing low-code tools and AI, you were likely using the export-and-re-import approach. The CLI + MCP flow is specifically designed to avoid that mess.

Docs: https://lnkd.in/e-vTTXKr

#FlutterFlow #ClaudeAI #AppDevelopment #AI #DeveloperTools #Flutter #BuildingTogether


Blog 11) Title- Why Dentists Are Building Their Own Scheduling Software (and What It Means for Healthcare Tech)
Subtitle- Why Industry-Specific Software Is Coming from the Shop Floor, Not Silicon Valley
Link- https://aneesas.hashnode.dev/why-dentists-are-building-their-own-scheduling-software-and-what-it-means-for-healthcare-tech
Over the long weekend, my cousin who is dentist built his own scheduling software.  
  
People inside real industries like clinics, law firms, logistics teams, farms, are now building working software for problems their software vendors never bothered to solve.  
  
Software and non-technical fields are merging. And 𝘁𝗵𝗲 𝗺𝗲𝗿𝗴𝗲𝗿 𝗶𝘀 𝗵𝗮𝗽𝗽𝗲𝗻𝗶𝗻𝗴 𝗳𝗿𝗼𝗺 𝘁𝗵𝗲 𝗻𝗼𝗻-𝘁𝗲𝗰𝗵𝗻𝗶𝗰𝗮𝗹 𝘀𝗶𝗱𝗲.  
  
Here's why a dentist had to build his own software:  
  
 • The platforms most clinics use treat a dentist's day like a flat calendar. In reality, the dentist is hands-on for only 50–60% of any procedure. The rest of the time, the patient is with a hygienist or going through insurance paperwork and the dentist should be seeing another patients.  
  
 • Each procedure has a different active-time ratio. Each dentist works at a different speed. Hygienist availability fluctuates. Even experienced receptionists default to safe, wasteful blocks. The clinic loses hours eventually harming their revenue and patient experience.  
  
 • No software company is building for this, the market is too fragmented, the variables too specific to each clinic.  
  
So my cousin opened 𝗖𝗹𝗮𝘂𝗱𝗲, fed it the workflow, the variables, the constraints unique to his practice and over one long weekend, walked away with a working prototype tuned to his exact rhythm.  
  
He's now using that prototype to retrain his receptionists. They can finally see why the schedule should look one way instead of another. A tool he built to solve scheduling turned out to be 𝗺𝗼𝗿𝗲 𝘃𝗮𝗹𝘂𝗮𝗯𝗹𝗲 𝗮𝘀 𝗮 𝘁𝗲𝗮𝗰𝗵𝗶𝗻𝗴 𝘁𝗼𝗼𝗹.  
  
𝗛𝗲𝗿𝗲 𝗮𝗿𝗲 𝗺𝘆 𝘁𝗮𝗸𝗲𝗮𝘄𝗮𝘆𝘀 𝗳𝗼𝗿 𝗯𝘂𝘀𝗶𝗻𝗲𝘀𝘀 𝗼𝘄𝗻𝗲𝗿𝘀:  
  
The era of "build it once and ride it" is gone. 𝗗𝗶𝘀𝗿𝘂𝗽𝘁𝗶𝗼𝗻 𝗶𝘀 𝗲𝗮𝘀𝘆 𝗻𝗼𝘄. If you don't keep iterating, someone else will and they'll be 6 months ahead of you.  
  
Your customers are no longer comparing your product to your competitors. They're comparing it to the optimised, personalised workflow they could build themselves.  
  
Eagle Soft and its peers won the dental scheduling market years ago and then stopped solving the underlying workflow problem. That gap is exactly what made my cousin pick up Claude.  
  
Your customers can now build the features you skipped. They won't replace you tomorrow. But they'll train their staff on the workflows you should have shipped and eventually, one of them, or a developer working with one of them, will build the version that does.  
  
You don't get to coast on a good product anymore. The product has to keep getting more specific, more efficient, more aligned with the workflows your customers actually run.  
  
The hard part is no longer the building. The hard part is paying attention to 𝘄𝗵𝗮𝘁 𝘆𝗼𝘂𝗿 𝗰𝘂𝘀𝘁𝗼𝗺𝗲𝗿𝘀 𝗵𝗮𝘃𝗲 𝗮𝗹𝗿𝗲𝗮𝗱𝘆 𝘀𝘁𝗮𝗿𝘁𝗲𝗱 𝗯𝘂𝗶𝗹𝗱𝗶𝗻𝗴 𝘄𝗶𝘁𝗵𝗼𝘂𝘁 𝘆𝗼𝘂.  
  
[**#AI**](https://www.linkedin.com/search/results/all/?keywords=%23ai&origin=HASH_TAG_FROM_FEED) [**#Entrepreneurship**](https://www.linkedin.com/search/results/all/?keywords=%23entrepreneurship&origin=HASH_TAG_FROM_FEED) [**#FutureOfWork**](https://www.linkedin.com/search/results/all/?keywords=%23futureofwork&origin=HASH_TAG_FROM_FEED) [**#Innovation**](https://www.linkedin.com/search/results/all/?keywords=%23innovation&origin=HASH_TAG_FROM_FEED) [**#HealthTech**](https://www.linkedin.com/search/results/all/?keywords=%23healthtech&origin=HASH_TAG_FROM_FEED)

Blog 12) Title- Lightbuild: Making Android build configs agent-friendly
Subtitle- How Google's Lightbuild compiles YAML to Gradle and removes brittle, hard-to-maintain build logic
Link- https://aneesas.hashnode.dev/lightbuild-making-android-build-configs-agent-friendly

Google just put out something worth paying attention to: 𝗟𝗶𝗴𝗵𝘁𝗯𝘂𝗶𝗹𝗱.  
If you've done any 𝗔𝗻𝗱𝗿𝗼𝗶𝗱 𝗱𝗲𝘃, you already know the build files are where the pain lives.  
  
𝗚𝗿𝗮𝗱𝗹𝗲 config in 𝗞𝗼𝘁𝗹𝗶𝗻 𝗼𝗿 𝗚𝗿𝗼𝗼𝘃𝘆 𝗗𝗦𝗟 is real code. You're writing logic, conditionals, custom tasks. It's powerful, but it's also messy, easy to break, and hard to reason about six months later when you've forgotten why that one closure exists. And then there's the ritual everyone dreads: 𝗔𝗚𝗣 𝘃𝗲𝗿𝘀𝗶𝗼𝗻 𝘂𝗽𝗴𝗿𝗮𝗱𝗲𝘀 and the slow project syncs that come with them.  
  
Google's new Lightbuild (in limited testing right now) is taking a swing at this. Instead of writing build logic, you 𝗱𝗲𝗰𝗹𝗮𝗿𝗲 𝘄𝗵𝗮𝘁 𝘆𝗼𝘂 𝘄𝗮𝗻𝘁 𝗶𝗻 𝗬𝗔𝗠𝗟, and it compiles down to Gradle underneath. Gradle still runs the build, you just stop writing scripts to drive it.  
  
The part that actually got my attention is the agents.  
  
When an 𝗔𝗜 𝗮𝗴𝗲𝗻𝘁 tries to edit an imperative Gradle script, it has to understand arbitrary logic to change anything safely, which is exactly as risky and error-prone as it sounds. 𝗗𝗲𝗰𝗹𝗮𝗿𝗮𝘁𝗶𝘃𝗲 𝗬𝗔𝗠𝗟 is structured and predictable, so an agent can bump a dependency or edit a module without guessing what the rest of the file is doing.  
  
We're starting to see 𝘁𝗼𝗼𝗹𝗶𝗻𝗴 𝗱𝗲𝘀𝗶𝗴𝗻𝗲𝗱 𝗳𝗼𝗿 𝘁𝗵𝗲 𝗮𝗴𝗲𝗻𝘁𝘀 working alongside us, not just for us. Build config is a smart place to start.  
  
Reference: [**https://lnkd.in/e7Nr9sjK**](https://lnkd.in/e7Nr9sjK)  
  
[**#Android**](https://www.linkedin.com/search/results/all/?keywords=%23android&origin=HASH_TAG_FROM_FEED) [**#DeveloperTools**](https://www.linkedin.com/search/results/all/?keywords=%23developertools&origin=HASH_TAG_FROM_FEED) [**#AI**](https://www.linkedin.com/search/results/all/?keywords=%23ai&origin=HASH_TAG_FROM_FEED) [**#LightBuild**](https://www.linkedin.com/search/results/all/?keywords=%23lightbuild&origin=HASH_TAG_FROM_FEED)

