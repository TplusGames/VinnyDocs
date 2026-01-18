# VinnyHUD (Simple Explanation)

> 🔗 **Related Pages:**  
> 👉 [VinnyUserWidget](VinnyUserWidgetDoc.md)  
> 👉 [WidgetController](WidgetControllerDoc.md)

---

## What is this?

**`VinnyHUD` is the main boss that sets up all the UI widgets and their controllers.**

Think of it like:
> A stage manager that creates actors (widgets) and tells them who their director (controller) is.

---

## Why does this exist?

- Game logic doesn’t create widgets one by one
- HUD makes sure all UI appears on screen
- HUD connects widgets to their controllers automatically

---

## Big idea (important!)

The `VinnyHUD`:

1. Loops through **UI groups**
2. Creates a **WidgetController** for each group
3. Creates a **VinnyUserWidget** for each group
4. Adds the widget to the viewport
5. Connects widget to its controller

All automatically. No extra setup needed.

---

## Imagine it like this 🧸

- `VinnyHUD` → Stage manager
- `WidgetController` → Director
- `VinnyUserWidget` → Actor on stage

The manager creates the actors and directors and tells them to start the show.

---

## Important struct

### `FUIGroup`

- `WidgetClass` → Which widget to create
- `WidgetControllerClass` → Which controller to create

Each UI group is one “actor + director” combo.

---

## How it works (simple steps)

### `InitializeHUD(PlayerController)`

For each `FUIGroup`:

1. Create a `WidgetController`
2. Initialize it with the player controller
3. Create a `VinnyUserWidget`
4. Add it to the screen
5. Connect it to the `WidgetController`

After this, everything is ready and widgets automatically respond to the controller.

---

## One-sentence summary

> **`VinnyHUD` is the stage manager that sets up all UI widgets and their controllers so they work together automatically.**
~~~~