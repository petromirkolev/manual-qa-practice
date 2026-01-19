# Odin Weather – Manual test cases

## Core flow

### TC-WE-001 – Search valid city shows weather

**Preconditions:** App loaded.
**Steps:**

1. In search input, enter "Plovdiv".
2. Submit (click Search or press Enter).

**Expected:**

- Loading indicator/message appears.
- Current weather section updates (temp + condition/wind/etc.).
- City label shows the searched city (or returned city name).
- No error message displayed.

### TC-WE-002 – Enter key submits search

**Steps:**

1. Click search input.
2. Type "Sofia".
3. Press Enter.

**Expected:** Same result as clicking Search.

---

## Input validation / edge cases

### TC-WE-003 – Empty input does not call APIs

**Steps:**

1. Clear input to empty string.
2. Submit.

**Expected:**

- App shows a validation message like “Enter a city” OR does nothing.
- No UI crashes, no console error.
- Existing weather display remains unchanged.

### TC-WE-004 – Whitespace-only input behaves like empty

**Steps:**

1. Type " " (spaces).
2. Submit.

**Expected:** Same as TC-WE-003.

### TC-WE-005 – City with spaces works

**Steps:**

1. Search "New York".

**Expected:**

- App returns results and displays weather (no URL/encoding issues).

### TC-WE-006 – Non-latin characters work (or fail gracefully)

**Steps:**

1. Search "Пловдив".

**Expected:**

- Either weather loads successfully OR a clear “no results” message appears.
- No crash / broken UI.

### TC-WE-007 – Garbage query returns “no results”

**Steps:**

1. Search "asdkjashdkjahsdkj".

**Expected:**

- App shows “No results found” / “City not found”.
- No crash. No stale/incorrect weather displayed as “success”.

---

## Geocoding specific behavior

### TC-WE-008 – Ambiguous city name gives a reasonable result

**Steps:**

1. Search "Springfield" (or another ambiguous city).

**Expected**

- No crash.

### TC-WE-009 – Country bias if supported

**Steps:**

1. Search a city name that exists in multiple countries (e.g. "Varna" is less ambiguous; pick one you know).

**Expected:**

- App still returns _some_ correct weather, no crash.

---

## Weather fetch behavior

### TC-WE-010 – Current weather fields render correctly

**Steps:**

1. Search a valid city.

**Expected:**

- Temperature is displayed (number + unit).
- Wind speed displayed (number + unit).
- No "undefined", "NaN", or empty placeholders.

### TC-WE-011 – Units toggle updates values consistently

**Preconditions:** Weather loaded for a city.
**Steps:**

1. Switch units from Metric → Imperial.
2. Switch back Imperial → Metric.

**Expected:**

- Temperatures convert correctly (C ↔ F) and update immediately.
- No duplicate UI elements or mixed units.

### TC-WE-012 – Refresh/research after unit switch keeps unit setting

**Preconditions:** Units set to Imperial.

**Steps:**

1. Search a new city.

**Expected:**

- New city weather loads and remains in Imperial.
- No unexpected reset to Metric.

---

## Error handling

### TC-WE-013 – Geocoding API failure handled gracefully

**Steps (choose one):**

- Disconnect internet OR block geocode.maps.co in devtools.

1. Try searching any city.

**Expected:**

- User-friendly error message (“Geocoding service unavailable”).
- No crash. UI stays usable.

### TC-WE-014 – Weather API failure handled gracefully

**Steps (choose one):**

- Disconnect internet OR block api.open-meteo.com in devtools.

1. Search any city.

**Expected:**

- User-friendly error message (“Weather service unavailable”).
- No crash. UI stays usable.

### TC-WE-015 – Rapid repeated searches do not break state

**Steps:**

1. Search "Sofia".
2. Immediately search "Plovdiv".
3. Immediately search "Burgas".

**Expected:**

- App ends up displaying the **last** search results.
- No UI glitches (half-updated city with wrong weather).
- No console errors.

---

## UI/UX

### TC-WE-016 – Loading indicator appears only during fetch

**Steps:**

1. Search a city.

**Expected:**

- Loading shows during request.
- Loading disappears after success/error.

### TC-WE-017 – App initial state is clean

**Steps:**

1. Load the page fresh (hard refresh).

**Expected:**

- No stale weather displayed.
- No errors shown by default.
