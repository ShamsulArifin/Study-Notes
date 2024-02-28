Implementing a custom viewport window to display and manipulate the imported mesh in real-time requires some understanding of Unreal Engine's Slate UI framework and rendering systems. Here's a basic guide on how you might approach this:

### 1. Create a Custom Slate Widget:
Create a new C++ class that derives from `SCompoundWidget` to represent your custom viewport.

```cpp
// CustomViewportWidget.h
#pragma once

#include "SlateBasics.h"

class SCustomViewportWidget : public SCompoundWidget
{
public:
    SLATE_BEGIN_ARGS(SCustomViewportWidget) {}
    SLATE_END_ARGS()

    void Construct(const FArguments& InArgs);

private:
    TSharedPtr<class SViewport> ViewportWidget;
};
```

```cpp
// CustomViewportWidget.cpp
#include "CustomViewportWidget.h"
#include "SViewport.h"

void SCustomViewportWidget::Construct(const FArguments& InArgs)
{
    // Create the SViewport widget
    ViewportWidget = SNew(SViewport)
        .RenderDirectlyToWindow(true)
        .EnableGammaCorrection(false)
        .ShowEffectWhenMoving(false)
        .EnableBlending(false);

    // Construct the UI
    ChildSlot
    [
        SNew(SOverlay)
        + SOverlay::Slot()
        .HAlign(HAlign_Fill)
        .VAlign(VAlign_Fill)
        [
            ViewportWidget.ToSharedRef()
        ]
    ];
}
```

### 2. Integrate into Your Main UI:
Use the custom viewport widget in your main UI class (could be a UUserWidget Blueprint in the editor).

```cpp
// YourMainUIWidget.h
#pragma once

#include "Blueprint/UserWidget.h"
#include "YourMainUIWidget.generated.h"

UCLASS()
class YOURPROJECT_API UYourMainUIWidget : public UUserWidget
{
    GENERATED_BODY()

public:
    UFUNCTION(BlueprintCallable)
    void OpenCustomViewport();

private:
    TSharedPtr<class SCustomViewportWidget> CustomViewportWidget;
};
```

```cpp
// YourMainUIWidget.cpp
#include "YourMainUIWidget.h"
#include "CustomViewportWidget.h"

void UYourMainUIWidget::OpenCustomViewport()
{
    // Create the custom viewport widget
    CustomViewportWidget = SNew(SCustomViewportWidget);

    // Add it to the UI
    AddViewportWidgetContent(CustomViewportWidget.ToSharedRef());
}
```

### 3. Handling Mesh Rendering in the Custom Viewport:
You would need to add logic to handle the rendering of your imported mesh within the `SCustomViewportWidget`. This might involve creating a custom scene manager, handling input events, and interacting with the 3D rendering system.

### 4. Binding the Custom Viewport to Your Imported Mesh:
You'll need to create functions in your `SCustomViewportWidget` that allow you to bind and update the displayed mesh based on user interactions.

### Additional Resources:
1. [Unreal Engine Slate UI Documentation](https://docs.unrealengine.com/en-US/API/Runtime/SlateCore/Widgets/SCompoundWidget/index.html)
2. [Unreal Engine 4 - Creating a Main Menu with UMG](https://www.tomlooman.com/create-main-menu-cpp/)

Creating a fully functional custom viewport involves quite a bit of work and might require in-depth knowledge of Unreal Engine internals. If you're new to Unreal Engine UI development, consider looking into more introductory resources and tutorials before attempting complex custom UI components.