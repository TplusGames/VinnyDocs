# Vinny and Glitch Documentation

Welcome to the **Vinny and Glitch** project documentation.  
This README is the **entry point** to all technical docs, written in simple language so anyone on the team can understand it.

---

## Table of Contents

- [UI](#ui)

---

## UI

The UI section explains how our widgets, controllers, and HUD work together in **Vinny and Glitch**.

- **[VinnyUserWidget](VinnyUserWidgetDoc.md)**
  > The visual screen widget that can fade in/out and listens to a controller.

- **[WidgetController](WidgetControllerDoc.md)**
  > The “brain” that sends messages to widgets, telling them what to do.

- **[VinnyHUD](VinnyHUDDoc.md)**
  > The stage manager that creates widgets and controllers, and sets up the UI for the player.

- **[VUW_Overlay](VUW_OverlayDoc.md)**
  > Overlay class that links into WidgetControllers callback for switching widget focus (Easy toggling of active widget)
