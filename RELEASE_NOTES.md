# ami.OLE — Release Notes

---

## Version 1.1.0 · 26 June 2026

### Bug Fixes

**Overlap tool — fully fixed on Revit 2025 & 2026**
After extensive investigation across many releases, the true root cause of the Overlap crash has been found and fixed. The crash was caused by an incompatibility between Revit 2025/2026's .NET 8 runtime and how certain internal WPF exceptions are handled during element selection and dialog display. The fix is transparent — the tool works exactly as it always has on Revit 2022, 2023, and 2024: click Overlap, click on a placeholder, and the dialog opens.

---

## Version 1.0.707 · 26 June 2026

### Bug Fixes

**Overlap tool — fully fixed on Revit 2025 & 2026**
After extensive investigation across multiple releases, we identified the root cause: a fundamental incompatibility between Revit 2025/2026's .NET 8 runtime and the way Revit internally processes element selection for this type of element. The Overlap button was crashing Revit during the selection step itself — not in any of the surrounding code — and no amount of code restructuring could change that.

The fix changes how you use the tool on Revit 2025 and 2026: **select the placeholder first** (click on it in the model), **then click the Overlap button**. This avoids the problematic selection step entirely. On Revit 2022, 2023, and 2024, nothing changes — the button still prompts you to select as before.

---

## Version 1.0.706 · 26 June 2026

### Bug Fixes

**Overlap tool — root cause found and fixed**
After several targeted fixes, journal analysis finally pinpointed the exact crash location: the element selection filter that runs while you move your cursor over the model. In Revit 2026, this filter is called on a restricted background thread, and the filter was reading a property (`Symbol.FamilyName`) that requires a database lookup — something that isn't allowed on that thread. The filter has been simplified to use only a safe category check, matching the pattern of every other working filter in the addin.

---

## Version 1.0.705 · 26 June 2026

### Bug Fixes

**Overlap tool crash on Revit 2025 & 2026 — resolved (again)**
The previous fix (1.0.704) eliminated the database scans and geometry calls after element selection, but Revit 2026 turned out to be stricter than expected: even routine parameter reads on a single element crash the process in the brief moment after you click to confirm your selection. The command now pre-loads all placeholder data before the selection prompt appears, so by the time you click, there is nothing left to read from Revit — the dialog opens from fully in-memory data.

---

## Version 1.0.704 · 26 June 2026

### Bug Fixes

**Overlap tool crash on Revit 2025 & 2026 — fully resolved**
The Overlap command was still crashing Revit 2025 and 2026 despite earlier fixes. The root cause has now been identified and eliminated: Revit 2026's new execution model (NOBLE) does not allow certain heavy database operations — scanning for elements or reading geometry — in the brief window immediately after a user clicks to select an element. The command now performs all of that work upfront before the selection prompt appears, so nothing heavy runs after you click. The Overlap tool should now work reliably on all supported Revit versions.

---

## Version 1.0.702 · 13 June 2026

### What's New

**Release Notes now accessible from the About window**
You can now read the latest release notes directly from ami.OLE. Click **Release Notes** in the About dialog and it will open in your browser.

---

## Version 1.0.700 · 13 June 2026

### Bug Fixes

**Overlap tool is now fully stable on Revit 2025 & 2026**
The Overlap command was crashing Revit under various conditions on Revit 2025 and 2026 — including when clicking the button, when selecting the first or last placeholder on a line, and in certain follow-up scenarios. All of these have been resolved. The tool now works reliably across all supported Revit versions.

**Export Droppers no longer shows an error after saving**
Exporting droppers to Excel now completes cleanly. The spreadsheet opens automatically without triggering a false error message.

---

## Version 1.0.696 · 13 June 2026

### Bug Fixes

**Licence key is now fully visible when entering it**
The licence key input field was cutting off part of the key, making it hard to read or verify. The field is now taller and displays your full key clearly.

---

## Version 1.0.695 · 13 June 2026

### What's New

**Change your licence key from the About window**
You can now update your licence key at any time directly from the About dialog. No more manually deleting files — just open About, click *Change Licence Key*, enter your new key, and you're done.

---

## Version 1.0.694 · 12 June 2026

### What's New

**Revit 2026 support**
ami.OLE now supports Revit 2026 alongside Revit 2022, 2023, 2024, and 2025.

**Floating licence keys**
Licence keys are no longer hardcoded per user. On first run, ami.OLE will prompt you to enter your Cryptolens licence key. The key is saved securely and you won't be asked again unless it becomes invalid or is removed.
