# Jon's Ui Documentation

## Getting My Library
```lua
local Library = loadstring(game:HttpGet('https://raw.githubusercontent.com/Jonatanortiz2/Johnny-Test/master/Ui-Lib.lua'))();
```

## Creating Window
I Don't Recommend Changing This.
```lua
local Window = Library:CreateWindow('Hub Name', false)
```

```text
1.) <String> Name of the UI.
2.) <Bool> if true, themes will be disabled, if false, themes will be enabled (this setting is to increase performance)
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
