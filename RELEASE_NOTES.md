# ami.OLE — Release Notes

---

## Version 1.1.4 · 9 October 2026 · Test build

### What's New

**Settings now change how ami.OLE works**
In 1.1.3, only the placeholder wire heights and stagger followed the Settings window. Now almost every setting is used. Change a value, press **OK**, and the commands pick it up:
- **Add Structures**: default mast offset, height, boom length and T.O.F. for single masts, portals, two-track cantilevers, mounted structures and drop tubes. Also the "T.O.F. = High Rail Level − 350" rule, the footing projection, boom length rounding, plate thickness, the mounted mast offset and the input limits.
- **Brackets**: boom bracket distance, length to high rail level, which bracket types are ticked, and the orientation used when it can't be detected.
- **Wires**: span rounding for dropper lookup, the dropper lookup workbook layout and file, the dropper schedule template, cells and wire type descriptions, and the contact wire clearance diameter.
- **Documentation**: title blocks, the cross-section view template and size, dependent layout lengths, view and schedule names, tag offsets, and the Up/Down track keywords.
- **Compliance Check**: the template, cells, registration index table, span rounding and file name.
- **Alignment and imports**: chainage marker intervals, the alignment CSV and mast coordinate columns, import/export folders, and phase names.

**Fields not used yet are faded**
Some settings are kept for future features, such as gauge, conductors and clearances to earth. They appear faded in the Settings window, with a tooltip.

**Dropper lookup workbook**
If a dropper lookup workbook is set on the Project tab, ami.OLE uses it directly instead of asking for the file each time.

### Bug Fixes

**Portal: right mast offset now has a default**
When adding a portal, the right mast offset was left empty. It now gets the same default as the left mast.

---

## Version 1.1.3 · 9 October 2026 · Test build

### What's New

**Settings window**
The **Settings** button on the General panel now opens the ami.OLE Settings window. It has ten tabs: Project, Track & Alignment, Catenary System, Droppers, Structures, Cantilevers & Brackets, Clearances & Compliance, Documentation, Import / Export, and Company & Support. The tabs use the same diagrams as the Add Placeholder, Add Structures and Add Cantilevers windows, so you can enter wire heights and mast dimensions directly on the drawings.

**Design standards**
Pick a design standard at the top of the Settings window and its values fill every tab. *PTA (WA) - Standard* is built in. Your company can add its own standards as files in a shared folder. **Export standard...** saves the current values as a new standard, which is the quickest way to set one up for another authority.

**Settings saved with your project**
Press **OK** or **Apply** and your settings are saved inside the Revit model, so everyone working on the project uses the same values. Only the values you change from the standard are stored. The window shows how many there are, and **Reset tab to standard** removes them for one tab.

**Placeholder defaults follow your settings**
Add Placeholders (by Range, Single, Secondary and Based on Mast) and Overlap now take their wire heights, stagger and spacing from the project's settings instead of fixed values. With the PTA standard and no changes, they behave exactly as before.

---

## Version 1.1.2 · 7 October 2026 · Test build

### Bug Fixes

**Portal placeholders placed using the actual mast width**
Add Structures now reads the portal family's *Mast Width* when positioning placeholders, instead of working it out from the mast size name. This fixes placeholders being offset when the mast size name didn't start with the width.

---

## Version 1.1.1 · 29 June 2026

### Changes

**Production licensing**
ami.OLE now activates against the production licence. Use the licence key issued for ami.OLE.

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
