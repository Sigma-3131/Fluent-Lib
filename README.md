
# Lib Source
```
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()
```

# Create Window
```
local Window = Fluent:CreateWindow({
    Title = "Fluent " .. Fluent.Version,
    SubTitle = "by dawid",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true, -- The blur may be detectable, setting this to false disables blur entirely
    Theme = "Dark",
    MinimizeKey = Enum.KeyCode.LeftControl -- Used when theres no MinimizeKeybind
})
```


# Create Tab

```
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}
```

# Notify

```
Fluent:Notify({
     Title = "Notification",
     Content = "This is a notification",
    SubContent = "SubContent", -- Optional
     Duration = 5 -- Set to nil to make the notification not disappear
   })
```


# Create Paragraph

```
Tabs.Main:AddParagraph({
    Title = "Paragraph",
  Content = "This is a paragraph.\nSecond line!"
  })
```

# Create Button

```
Tabs.Main:AddButton({
        Title = "Button",
        Description = "Very important button",
        Callback = function()
            Window:Dialog({
                Title = "Title",
                Content = "This is a dialog",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()
                            print("Confirmed the dialog.")
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            print("Cancelled the dialog.")
                        end
                    }
                }
            })
        end
    })
```

```
Tabs.Main:AddButton({
        Title = "Button",
        Description = "Very important button",
        Callback = function()
            print('clicked')
        end
    })
```

# Create Toggle

```
local Toggle = Tabs.Main:AddToggle("MyToggle", {Title = "Toggle", Default = false })

   Toggle:OnChanged(function()
    print("Toggle changed:", Options.MyToggle.Value)
  end)
```

# Change Toggle Value

```
Options.MyToggle:SetValue(false)
```


# Create Slider

```
local Slider = Tabs.Main:AddSlider("Slider", {
   Title = "Slider",
   Description = "This is a slider",
    Default = 2,
    Min = 0,
  Max = 5,
   Rounding = 1,
   Callback = function(Value)
     print("Slider was changed:", Value)
    end
   })

  Slider:OnChanged(function(Value)
   print("Slider changed:", Value)
  end)

```

# Update Slider Value

```
Slider:SetValue(3)
```

