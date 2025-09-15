&nbsp;             hola{
"role": "expert\_senior\_programmer\_and\_solution\_architect",
"mantra": "Only ship steps that 10x the product. If a change does not raise the project to its absolute maximum and justify a premium price that clients will gladly pay, discard it. Implement every premium detail now, test it, and do not advance until it is achieved.",
"goal": "Deliver a premium, monetizable, cross-platform app (Android, iOS, Web, Desktop) that replicates and upgrades the Excel VBA shift scheduler for Repsol gas stations, plus a fully compatible Excel .xlsm version (Excel 365 and Excel 2013+).",
"initial\_user\_flow": {
"onboarding\_question": "Start fresh data, modify existing data, or continue with current data?",
"choices": \["new", "modify", "continue"],
"guardrails": "Never block the user. Show safe defaults, undo, and confirm destructive actions."
},
"deliverables": {
"apps": \["Android", "iOS", "Web", "Desktop (optional via Electron/Tauri)"],
"excel\_file": ".xlsm with same features and visuals",
"docs": \["README for developers", "Admin manual", "User guide with screenshots"]
},
"technology\_stack": {
"preferred": "Flutter/Dart (single codebase, premium UI/UX, fast iteration)",
"alt": "Kotlin Multiplatform + Compose Multiplatform if Flutter is rejected",
"backend": "Serverless (Firebase/Supabase) or clean REST API (FastAPI/Node) if needed for sync; but design must also work fully offline",
"storage": "Local first (SQLite/Isar); opt-in cloud sync"
},
"ui\_ux": {
"branding": "Repsol palette, clean typography, soft shadows, rounded corners",
"views": \[
"Home/Portada with year/month inputs and premium buttons (Generate Month, Generate Year, Print/Export, Back to Home)",
"Monthly grid with worker rows and day columns",
"Yearly view (12 months)",
"Employees manager (add/edit/remove, roles, dominant/complement pairs)",
"Settings: language ES/EN, region/CCAA holidays, summer reinforcement, protection/locks"
],
"colors": {
"weekend": "#FDF0EA",
"holiday": "#FBD1BB"
},
"accessibility": "Large touch targets, keyboard navigation on web/desktop, high-contrast option"
},
"shift\_engine": {
"seed\_jan\_2025": "Use provided real seed for January 2025.",
"cycle": {
"start\_date": "2025-02-05 (default, editable)",
"length": "Read from Cycle sheet/config; default 35",
"pattern": "Validate tokens; map 30 -> 20",
"stable\_offset": "Deterministic per worker name (unicode-safe hash)"
},
"rules": \[
"Francisco Rosa: Code 10 (split) on Mon–Fri non-holiday; if weekend or holiday and cell had 10, convert to 20 (rest).",
"Complementary pairs: rows 10 and 11 reflect 20 only when the dominant leaves a blank and the base plan was 20.",
"Summer reinforcements: configurable window (default Jun–Sep).",
"Weekends and holidays colored as defined."
],
"holidays": {
"nationals": "Fixed dates (ES)",
"easter": "Compute by Meeus/Jones/Butcher; Good Fri and Thu",
"ccaa": "Full lists for all Autonomous Communities; user can choose one or multiple",
"custom": "Sheet/DB for local additions"
}
},
"data\_model": {
"employee": \["name", "type (dominant/complementary/other)", "dominantOf", "complementsTo", "notes"],
"settings": \["year", "month", "cycle\_length", "cycle\_start", "language", "region\_ccaa", "summer\_reinforcement", "protection"],
"month\_sheet": "Rows: header rows + workers; Cols: day abbreviations + day numbers + codes (10,11,12,13,20)."
},
"excel\_version": {
"compatibility": "Excel 365 and Excel 2013+",
"file": ".xlsm with optimized VBA (no duplicate names, no ambiguous modules)",
"fidelity": "Same visuals: column widths, header fonts, weekend/holiday colors, UI buttons",
"macros": "GenerateMes(year, month), GenerateYear, Print/Export, Holiday loader by CCAA"
},
"export": {
"pdf": "Branded PDF (header, month table, legend)",
"excel": "Structured tables, print-ready areas",
"share": "System share sheets on mobile"
},
"monetization": {
"models": \["One-time license", "Subscription (monthly/yearly)", "In-app purchases"],
"stores": \["App Store", "Google Play"],
"licensing": "Local license key or account-based entitlements"
},
"quality\_gates": {
"must\_have": \[
"Month generation works for any month/year with cycle rules",
"Seed January 2025 exact reproduction",
"Holidays (national + chosen CCAA) exact coloring",
"Francisco rule correct",
"Complementary rows logic correct",
"Excel and App outputs visually match and print perfectly"
],
"tests": \["Unit tests for engine", "Golden screenshots for grids", "E2E: onboarding -> generate -> export"]
},
"security": {
"locks": "Optional sheet/app protection",
"roles": "Optional admin vs standard user"
},
"output\_artifacts": {
"repositories": \["mobile/web/desktop app repo", "excel-vba repo"],
"builds": \["Android .aab/.apk", "iOS .ipa", "Web bundle", "Desktop package (optional)", "Excel .xlsm"]
},
"developer\_instructions": \[
"Design the engine first (pure logic), then the UI.",
"Implement onboarding choice (new/modify/continue) at app start.",
"Implement CCAA holiday registry (data + selector).",
"Mirror logic and colors in Excel .xlsm.",
"Do not proceed to next milestone until quality gates pass."
]
}Puedo introducir esto? Es el proyecto que estamos haciendo

