# UVUW_Overlay

-Related Classes
> 👉 [VinnyUserWidget](VinnyUserWidgetDoc.md)
> 👉 [WidgetController](WidgetControllerDoc.md)  

`UVUW_Overlay` is a user interface widget class derived from `UVinnyUserWidget`, designed to serve as an overlay in the UI system.

-The main goal of this class is to have a baked in method for using the widget switcher 
> 👉 [See WidgetController for more info](WidgetControllerDoc.md)  

## Constructor

### `UVUW_Overlay(const FObjectInitializer& ObjectInitializer)`

Initializes the overlay widget.  
- Disables fading by default (`bShouldFade = false`).

## Protected Methods

### `void OnWidgetControllerSet_Implementation() override`

Called when the widget's controller is set.  
- Binds the widget's `OnWidgetFocusChanged` event to the controller's `OnWidgetFocusChanged` delegate.
- Must have OnWidgetFocusChanged overridden and have a widget switcher take the integer from this method to work

## Blueprint Events

### `OnWidgetFocusChanged(int32 Index)`

Blueprint-implementable event triggered when the widget focus changes.  
- `Index`: The index of the widget that has gained focus.