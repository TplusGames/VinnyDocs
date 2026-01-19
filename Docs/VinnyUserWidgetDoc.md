# VinnyUserWidget (Simple Explanation)

> 🔗 **Related Pages:**  
> 👉 [What is a WidgetController?](WidgetControllerDoc.md)  
> 👉 [What is VinnyHUD?](VinnyHUDDoc.md)

---

## What is this?

**`VinnyUserWidget` is a screen thing that can slowly fade in and fade out.**

Think of it like:
> A message that appears on the screen, stays for a bit, then disappears nicely instead of popping away.

---

## Why does this exist?

We want UI things (like popups, notifications, or messages) to:

- Show up smoothly
- Go away smoothly
- Not disappear instantly
- Be easy to control from Blueprints

This class handles **all of that automatically**.

---

## Big idea (important!)

This widget:

- Can **fade in**
- Can **fade out**
- Can **wait a few seconds**
- Can **fade out by itself**
- Is controlled by a **Widget Controller**

👉 If you don’t know what that is, click here:  
**[WidgetController explained](WidgetControllerDoc.md)**

---

## Imagine it like this 🧸

Imagine a picture on the screen:

- **Opacity** = how see-through it is
    - `1.0` = fully visible
    - `0.0` = invisible

This class slowly changes that number over time.

---

## Things you can change (the knobs)

### `bShouldFade`

> “Should this widget fade at all?”

- `true` → fade logic runs
- `false` → no fading happens

---

### `bShouldAutoFadeOut`

> “Should this widget disappear by itself?”

- `true` → it fades out after waiting
- `false` → it stays forever until told otherwise

---

### `DisplayTimeLength`

> “How long should the widget stay visible?”

- Measured in **seconds**
- Example: `5.0` = wait 5 seconds before fading out

---

### `FadeInSpeed`

> “How fast does the fade happen?”

- Bigger number = faster fade
- Smaller number = slower fade

---

## Important hidden stuff (you don’t touch this)

- `CurrentFadeAlpha` → How far along is the fade
- `TargetOpacity` → Where the fade is going
- `FadeInTimerHandle` → Timer that waits before fading out

---

## Controller connection

### `SetWidgetController(...)`

This function:

1. Saves the controller
2. Tells Blueprints the controller is ready
3. Starts the fade timer (if fading is enabled)

Think of it like:
> “The widget just got its brain.”

👉 That brain is explained here:  
**[WidgetController](WidgetControllerDoc.md)**

---

## Blueprint hook (very important)

### `OnWidgetControllerSet`

This is a **Blueprint event**.

This is where you:
- Bind data
- Update text
- Connect UI elements

---

## Automatic fade in/out

- `FadeInWidget()` → Start fading in
- `ToggleFadeIn(true)` → Fade in
- `ToggleFadeIn(false)` → Fade out

All fading happens smoothly in the background using `NativeTick(...)`.

---

## One-sentence summary

> **`VinnyUserWidget` is a smart UI widget that fades in/out and listens to a WidgetController for instructions.**
