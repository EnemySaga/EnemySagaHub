# Example Use EnemySagaLib
## -- Load the UI library (replace the URL if you use a local or different version)
### Load Library

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/EnemySaga/EnemySagaHub/refs/heads/main/EnemySagaHubLib"))()
```

### Configuration for the window
```lua
local Config = {
    WindowName = "Example EnemySaga Hub UI",
    Color = Color3.fromRGB(255,128,64),
    Keybind = Enum.KeyCode.RightControl
}
```

### Create the main window

```lua
local Window = Library:CreateWindow(Config, game:GetService("CoreGui"))
```

### Create a tab and a section

```lua
local MainTab = Window:CreateTab("Main Features")
local MainSection = MainTab:CreateSection("Demo Controls")
```

### Add a toggle

```lua
local ExampleToggle = MainSection:CreateToggle("Example Toggle", false, function(state)
    print("Toggle state:", state)
end)
ExampleToggle:AddToolTip("This is a simple toggle example.")
```

### Add a button

```lua
local ExampleButton = MainSection:CreateButton("Example Button", function()
    print("Button clicked!")
end)
```

### Add a dropdown

```lua
local ExampleDropdown = MainSection:CreateDropdown("Example Dropdown", {"Option 1", "Option 2", "Option 3"}, function(selected)
    print("Selected option:", selected)
end)
```

### Add a label

```lua
MainSection:CreateLabel("This is a label for demonstration.")
```
### Add a color picker

```lua
local ExampleColorPicker = MainSection:CreateColorpicker("Pick a Color", function(color)
    print("Color picked:", color)
end)
ExampleColorPicker:UpdateColor(Color3.fromRGB(255,128,64))
```
### Add a slider

```lua
local ExampleSlider = MainSection:CreateSlider("Example Slider", 0, 100, 50, false, function(value)
    print("Slider value:", value)
end)
ExampleSlider:SetValue(50)
```
### UI toggle (show/hide)

```lua
local UIToggle = MainSection:CreateToggle("UI Toggle", true, function(state)
    Window:Toggle(state)
end)

UIToggle:CreateKeybind("RightControl", function(key)
    print("UI keybind pressed:", key)
end)
UIToggle:SetState(true)
```
