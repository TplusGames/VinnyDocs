# WidgetController (Simple Explanation)

> 🔗 **Related Pages:**  
> 👉 [VinnyUserWidget](VinnyUserWidgetDoc.md)  
> 👉 [VinnyHUD](VinnyHUDDoc.md)

---

## What is this?

**`WidgetController` is a helper object that tells widgets what is happening and what they should pay attention to.**

Think of it like:
> A teacher pointing and saying: “Look here now.”

Widgets listen. The controller talks.

---

## Why does this exist?

UI widgets should:
- Show information
- React to changes
- Not contain game logic

This class acts as a **middleman**:

- Game logic → WidgetController
- WidgetController → Widgets

---

## Big idea (important!)

The `WidgetController`:
- Knows **which player** it belongs to
- Sends **signals**
- Does **not** draw anything
- Exists only to talk to widgets

It’s a brain 🧠  
Widgets are the face 🙂

---

## Important signal

### `OnWidgetFocusChanged`

This is a **broadcast signal**.

Think of it like yelling:
> “Hey! The focus changed!”

Any widget that is listening will react.

---

### What does it send?

- An **Index** (a number) to tell widgets which one is focused

---

## Stored player info

### `PC` (Player Controller)

- Tells the controller which player owns this UI
- Widgets never talk to the player directly

---

## Setting it up

### `InitializeWidgetController(...)`

- Store the player controller
- Connect to game systems

❗ If not called, nothing works.

---

## Hooking into game logic

### `BindCallbacksToDependencies(...)`

This is a **Blueprint event**.

Where you:
- Listen for game events
- Listen for player changes
- React to gameplay

---

## Changing focus

### `SetFocusWidget(Index)`

- Sends a number
- Broadcasts `OnWidgetFocusChanged`
- Widgets react automatically

---

## One-sentence summary

> **`WidgetController` is a brain that sends messages so widgets know what to show and when to update.**
