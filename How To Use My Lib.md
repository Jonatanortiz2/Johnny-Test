# Jon's Ui Documentation

## Getting Loadstring
```lua
local Library = loadstring(game:HttpGet('https://raw.githubusercontent.com/Jonatanortiz2/Johnny-Test/master/Ui-Lib.lua'))()
```

## Creating Window
```lua
local Window = Library:CreateWindow('Hub Name', 'Game Name', 'Visual UI Library', 'rbxassetid://10618928818', false, 'VisualUIConfigs', 'Default')
```
```text
1.) <String> Name of the UI.
2.) <String> Name of the Game.
3.) <String> Text that shows in the intro screen.
4.) <String> URL of the icon that shows in the intro screen.
5.) <Bool> if true, themes will be disabled, if false, themes will be enabled (this setting is to increase performance)
6.) <String> the path that the config folder should be in your exploits workspace folder.
7.) <String or Table> The name of a pre-made theme or a table with your custom theme (Find more in Themes.md).
```

## Creating Tabs
```lua
local Tab = Window:CreateTab('Tab', true, 'rbxassetid://3926305904', Vector2.new(484, 44), Vector2.new(36, 36))
```
```text
1.) <String> Name of the tab.
2.) <Bool> Tab visibility.
3.) <String> Tab Image URL.
4.) <Vector2> Tab Image RectOffset.
5.) <Vector2> Tab Image RectSize.
```

## Creating Sections
```lua
local Section = Tab:CreateSection('Section')
```
