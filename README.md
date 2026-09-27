# Tool Pocket Generator V134

## Release Notes

### V134 — Allow any outline point to be Curve

**Source and provenance:** Built directly from the supplied `Tool_Pocket_Generator_V133_FINAL(1).zip` archive. The V133 archive was opened and its `index.html`, `README.md`, and supporting files were inspected. This is a controlled rebuild from that immediate preceding ZIP; no older build was substituted.

**Problem:** V133's `setPointType()` blocked changing a point to Curve whenever either adjacent point was already Curve. This prevented users from freely choosing curve points and deciding which surrounding points should remain Straight.

**Fix:** Removed only that neighbour-based restriction. Any eligible outline point can now be set to Curve even when adjacent points are also Curve. The existing curve-generation and drag behaviour was left intact.

**Process/order:** Import or create the profile → edit point types → choose which points are Curve or Straight → confirm profile editing → close profile → Geometry Check → export JSON/STL.

**What was not changed:** Curve geometry/math, point identity, JSON import/export mapping, photo loading, physical-grid confirmation, outline detection, workspace, point add/insert/delete/undo, profile closure, geometry checking, STL construction, and export logic. Version labels were updated to V134.

**Verification performed:** Confirmed the exact V133 neighbour-restriction code existed and removed that condition from `setPointType()`. Checked that V134 version labels are present in the HTML and supporting metadata where applicable. JavaScript syntax and ZIP integrity checks are recorded below.

**Verification not performed:** No browser or iPad/Safari interaction test was performed. In particular, adjacent Curve-point rendering and export still require user retest.
