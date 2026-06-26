# ami.OLE — Release Notes

---

## Version 1.1.0 · 26 June 2026

### Bug Fixes

**Overlap tool — fully fixed on Revit 2025 & 2026**
The Overlap command was crashing Revit 2025 and 2026 on and off across several releases. After extensive investigation, the true root cause was found: an incompatibility between Revit 2025/2026's .NET 8 runtime and how certain internal WPF exceptions are handled during element selection and dialog display. The fix is transparent — the tool works exactly as it always has on all supported Revit versions: click Overlap, click on a placeholder, and the dialog opens.

**Export Droppers no longer shows an error after saving**
Exporting droppers to Excel now completes cleanly. The spreadsheet opens automatically without triggering a false error message.

---

## Version 1.0.702 · 13 June 2026

### What's New

**Release Notes now accessible from the About window**
You can now read the latest release notes directly from ami.OLE. Click **Release Notes** in the About dialog and it will open in your browser.

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
