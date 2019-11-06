# Fluent - Performance review request

**When will this ship?** It’s currently shipping.

**Review requested by:** Zibi Braniecki

**Engineering lead:** Zibi Braniecki

**Tracking Bug/Issue:** https://bugzilla.mozilla.org/show_bug.cgi?id=1365426

**Link to the code:** https://hg.mozilla.org/mozilla-central/file/tip/intl/l10n && https://hg.mozilla.org/mozilla-central/file/tip/dom/l10n 

**Design documents (e.g. UI spec, data flow diagrams, explainers):** 
* https://docs.google.com/document/d/1GE8TiCkI_2F29zNumgtsjdzv8G5uT5Ey6RSOn-q0tJ0/edit#heading=h.28eu2xksyi0j
* https://docs.google.com/document/d/1kZk6AUa4MyEVCYiQefwWbF82svUdd1ZVHQy1oNNV3Ds/edit
* https://docs.google.com/document/d/1GE8TiCkI_2F29zNumgtsjdzv8G5uT5Ey6RSOn-q0tJ0/edit#heading=h.28eu2xksyi0j
* https://docs.google.com/document/d/1A2wQI8tdEe0wIFK2KQZniBlQOjSrGoZglQUO_Xfvx2U/edit#
* https://docs.google.com/document/d/10Oplkz7fw0cwiwrn2RgBuddMzFtdgCsuu7wcy8KSR1g/edit#heading=h.77w12m845pav
* https://docs.google.com/document/d/1Ilfl1yrPNUrdnO_MFkYem1RrhqkER7_Noxe0Nk7oHzE/edit

**Relevant specifications and standards (W3C, etc):**
* https://github.com/projectfluent/fluent
* https://projectfluent.org/
* https://github.com/projectfluent/fluent/wiki
* https://github.com/projectfluent/fluent.js/wiki 

**User data or state saved locally by this feature, storage mechanism (prefs, sqlite, lmdb, JSON file, …) used for this data, and reasons for picking that storage mechanism:**
 FTL files in omni.ja + langpacks

**Actions that this feature takes during process startup or shutdown, and reasoning why they must happen at those times:**
* Language negotiation between preferred and available languages
* (potentially) Loading UI from cache
* Loading resources
* Parsing resources
* Formatting resources

**Please provide a link to a profile of your feature running. Please make sure the link selects a time period that highlights the feature’s impact, rather than a long profile where we have to look for the right timeslice:**
https://bugzilla.mozilla.org/show_bug.cgi?id=1441035#c44

**Web services used by this feature (e.g. FxA, kinto, SafeBrowsing, Pocket, etc.):**
 
 

## General: The questions below tell us about the performance concerns you had when designing the feature so we can focus on other areas you might not have considered.

**Describe the performance issues you considered while designing and implementing your feature and what steps you've taken to address them. Please include the ones you dismissed as non-problems so we don't waste your time re-considering them.**

I/O, FTL parsing performance, string formatting performance, DOM localization, layout, animation frames


**Describe areas of concern that you want the performance team to give special attention:**

Startup performance, non-en-US startup performance, memory use, fission compatibility (L10nRegistry is per-process), alignment between DOM/layout and Fluent, FFI between JS and C++/Rust

**Questions you have for the performance team:**
With Fluent enabled for all Firefox to use, we’d like to ensure that we understand if Fluent performance and memory profile is sufficient in all major scenarios, and what are the areas Gecko team should focus on to improve the impact of l10n layer on startup performance.
