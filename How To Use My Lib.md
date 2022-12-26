# Jonathan's Ui Documentation


## Getting My Library
```lua
local Library = loadstring(game:HttpGet('https://raw.githubusercontent.com/Jonatanortiz2/Johnny-Test/master/Ui-Lib.lua'))();
```

## Creating Window

```lua
local Window = Library:CreateWindow('Hub Name', false)
```

```text
1.) <String> Name of the UI.
2.) <Bool> if true, themes will be disabled, if false, themes will be enabled (this setting is to increase performance)
```

## Creating Tabs
```lua
local Tab = Window:CreateTab('Tab', true, 'rbxassetid://4483362458', Vector2.new(0, 0), Vector2.new(0, 0))
```

```text
1.) <String> Name of the tab.
2.) <Bool> Tab visibility.
    2).a When the GUI loads, just the enabled tab will be visible if all other tabs are disabled.
3.) <String> Tab Image URL.
4.) <Vector2> Tab Image RectOffset.
5.) <Vector2> Tab Image RectSize.
```
## Creating Sections
```lua
local Section = Tab:CreateSection('Section')
```

```text
1.) <String> Name of the section.
```

## Creating Labels
```lua
local Label = Section:CreateLabel('Label')
```

```text
1.) <String> Label text.
```

## Updating Labels
```lua
Label:UpdateLabel('New Text')
```

```text
1.) <String> New label text.
```

## Creating Paragraphs
```lua
local Paragraph = Section:CreateParagraph('Paragraph', 'Content')
```

```text
1.) <String> Title of the paragraph.
2.) <String> Content of the paragraph.
```

## Updating Paragraphs
```lua
Paragraph:UpdateParagraph('New Title', 'New Text')
```

```text
1.) <String> New title of the paragraph.
2.) <String> New content of the paragraph.
```

## Creating Buttons
```lua
Section:CreateButton('Button', function()
    print('Button Pressed')
end)
```

```text
1.) <String> Name of the button.
2.) <Function> Function / Callback of the button.
```

## Creating Sliders
```lua
Section:CreateSlider('Slider', 1, 100, 50, Color3.fromRGB(0, 146, 214), function(Value)
    print(Value)
end)
```
```text
1.) <String> Name of the slider.
2.) <Number> Minimum value of the slider.
3.) <Number> Maximum value of the slider.
4.) <Number> Default value of the slider.
5.) <Color3> Color of the slider.
6.) <Function> Function / Callback of the slider.
```

## Creating Textboxes
```lua
Section:CreateTextbox('Textbox', 'TextGoesHere', function(Value)
    print(Value)
end)
```
```text
1.) <String> Name of the textbox.
2.) <String> placeholder of the textbox.
3.) <Function> Function / Callback of the textbox.
```

## Creating Keybinds
```lua
Section:CreateKeybind('Keybind', 'A', function()
    print('Key Pressed')
end)
```
```text
1.) <String> Name of the keybind.
2.) <String> Default KeyCode.
    2).a Find all KeyCodes here: https://developer.roblox.com/en-us/api-reference/enum/KeyCode
3.) <Function> Function / Callback of the keybind.
```

## Creating Toggles
```lua
Section:CreateToggle('Toggle', true, Color3.fromRGB(0, 146, 214), 0.25, function(Value)
    print(Value)
end)
```
```text
1.) <String> Name of the toggle.
2.) <Bool> Default value of the toggle.
3.) <Color3> Color of the toggle.
4.) <Number> Debounce of the toggle.
5.) <Function> Function / Callback of the toggle.
```

## Creating Dropdowns
```lua
Section:CreateDropdown('Dropdown', {'Bread', 'Kitten', 'ROBLOX', 'JohnDoe', '5'}, 'Kitten', 0.25, function(Value)
    print(Value)
end)
```
```text
1.) <String> Name of the dropdown.
2.) <Table> Dropdown options.
3.) <Any> Put nil for none in the dropdown's default option. If it is not zero, it must be of the same type as the table's item; for instance, the drop-down menu is {'Kitten'}, so the Default should be 'Kitten', both strings.
4.) <Number> Debounce of the dropdown opening and closing.
5.) <Function> Function / Callback of the dropdown.
```

## Updating Dropdowns
```lua
Dropdown:UpdateDropdown({'Filter', 'Spoon', 'Fork'})
```
```text
1.) <Table> New list of dropdown options.
```

## Creating Colorpickers
```lua
local Colorpicker = Section:CreateColorpicker('Colorpicker', Color3.fromRGB(0, 146, 214), 0.25, function(Value)
    print(Value)
end)
```
```text
1.) <String> Name of the colorpicker.
2.) <Color3> Default color of the colorpicker.
3.) <Number> Debounce of the colorpicker opening and closing.
4.) <Function> Function / Callback of the colorpicker.
```

## Creating Images
```lua
local Image = Section:CreateImage('Name', 'rbxassetid://11912754017', UDim2.new(0, 250, 0, 250))
```
```text
Show an image.
1.) <String> Name of the Image.
2.) <String> Asset ID.
3.) <UDim2> The size that the image should be.
```

## Updating Images
```lua
Image:UpdateImage('rbxassetid://11912754017', UDim2.new(0, 200, 0, 200))
```
```text
1.) <String> New Asset ID.
2.) <UDim2> The size that the image should be changed to.
```

## Creating Notifications
creates a variety of Notifications on the side of the screen.
```lua
Library:CreateNotification('Notification Title', 'Notification Text', 5)
```
```text
1.) <String> Title of the notification.
2.) <String> The text of the notification.
3.) <Number> The time the notification is on-screen for.
```

## Creating Prompts
creates a Notification with several types inside the UI.

# Just Text
```lua
Library:CreatePrompt('Text', 'Prompt Title', 'Prompt Text', 'Okay')
```
```text
1.) <String> The type of prompt, 'Text'. Nothing Special
2.) <String> The title of the prompt.
3.) <String> The text of the prompt.
4.) <String> The name of the prompt button, button has no callback.
```

# One Button
```lua
Library:CreatePrompt('OneButton', 'Prompt Title', 'Prompt Text', {
    'Okay',
    function()
        print('Prompt Button Pressed')
    end
})
```
```text
1.) <String> The type of prompt => 'OneButton'. Button's text and callback.
2.) <String> The title of the prompt.
3.) <String> The text of the prompt.
4.) <Table> {
    1.) <String> The name of the button.
    2.) <Function> The callback of the button.
}
```

# Two Buttons
```lua
UIFunctions:CreateButton('Create Two Button Prompt', function()
    Library:CreatePrompt('TwoButton', 'Prompt Title', 'Prompt Text', {
        'Button 1',
        function()
            print('Button 1')
        end,
        'Button 2',
        function()
            print('Button 2')
        end
    })
end)
```
```text
1.) <String> The type of prompt, 'TwoButton', for text and two buttons with different callbacks.
2.) <String> The title of the prompt.
3.) <String> The text of the prompt.
4.) <Table> {
    1.) <String> The name of the first button.
    2.) <Function> The callback of the first button.
    3.) <String> The name of the second button.
    4.) <Function> The callback of the second button.
}
```

## Update UI Transparency
```lua
Library:SetTransparency(0.5, true)
```
```text
1.) <Number> The new background transparency of the UI.
2.) <Bool> If true, alerts' background transparency will change; if false, it won't.
```
## Creating / Saving Configs
```lua
Library:SaveConfig('Config')
```
```text
1.) <String> The name of the configuration; if it doesn't exist, it will create one; otherwise, it will overwrite it.
```

## Getting All Configs
```lua
Library:GetConfigs()
```

## Deleting Configs
```lua
Library:DeleteConfig('Config')
```
```text
1.) <String> The name of the config to delete.
```

## Loading Configs
```lua
Library:LoadConfig('Config')
```
```text
1.) <String> The name of the config to load.
```

## Themes

## Changing Themes
```lua
Library:ChangeTheme('Default')
```
```text
1.) <String or Table> a custom theme or the name of the theme you want to switch to.
```

## Getting All Themes
```lua
Library:GetThemes()
```

## Changing Theme Colors
Add this code to your UI in a section if you want to create a custom theme from within the user interface.
```lua
for Index, CurrentColor in next, Library:ReturnTheme() do
    ColorSection:CreateColorpicker(Index, CurrentColor, 0.25, function(Color)
        Library:ChangeColor(Index, Color)
    end, {true})
end
```

# Example Script

```lua
No```
