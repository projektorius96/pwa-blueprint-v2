# Title: pwa-blueprint

### Remarks

---

#### Window state management heuristics

Depending on situation, iff:

A. `window.opener === null` - it means "you're in the very top (PARENT) window":
- subsequently, iff you need to get reference to "nth" child, you must implement custom window tracking solution, _e.g. using Sets (see - `./src/apis/window-manager.js`)_;

B. `window.opener !== null` - it means "you're currently referring to particular nth child window": 
- subsequently, iff you need to get reference to the PARENT (top window), you can simply refer it with `window.opener` call;

> **NOTE**: In either cases, i.e. **A.** or **B.** discussed earlier on, iff you need to get reference to itself (_either parent or "nth" child respectively_) you can refer it with `window || window.parent` call;

### Current limitations

##### Children window focusing

As per description of [this comment](https://github.com/projektorius96/pwa-blueprint-v2/pull/1#issuecomment-4054516881), citing: "...due to Chromium-internal behaviour preventing malicious background windows from popping up unexpectedly, meaning (at best) only the very recent popup and its parent will be focused!"

---



