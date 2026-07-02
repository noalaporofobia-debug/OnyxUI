# OnyxUI

A modern, lightweight, and safe UI library for Roblox. Built with clean code, smooth animations, and a professional dark aesthetic. Designed for developers who want a reliable foundation without bloat or detectable patterns.

## ✨ Features

- 🎨 **Modern Dark Theme** with smooth easing animations
- 📊 **Dynamic Info Panel** showing User, Executor, and live Time/Date
- 🧩 **Modular Components**: Cards, Checkboxes, Sliders, Color Pickers
- 🔄 **Tab & Sidebar Navigation** with active state tracking
- 🖱️ **Draggable Window** & `RightShift` toggle
- 🛡️ **100% Safe & Undetectable** (Uses only official Roblox services)
- ⚡ **Optimized** (`task.spawn`, proper instance cleanup, no memory leaks)

---

## 📥 Installation

Execute this single line to load the library:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/noalaporofobia-debug/OnyxUI/refs/heads/main/library"))()
```

---

## 🚀 Quick Start

```lua
local UI = _G.OnyxUI

-- Create a new tab page
local settingsPage = UI.CreateTabPage("Settings")

-- Create a card inside the page
local card = UI.CreateSectionCard(
    settingsPage, 
    "Display", 
    UDim2.new(0, 0, 0, 0), 
    UDim2.new(1, 0, 0, 200)
)

-- Add components
UI.CreateCheckbox(card, "Enable Shadows", UDim2.new(0, 0, 0, 38), true)
UI.CreateSlider(card, "Brightness", UDim2.new(0, 0, 0, 70), 0, 100, 50)
UI.CreateColorPicker(card, "Accent Color", UDim2.new(0, 0, 0, 102), Color3.fromRGB(59, 130, 246))
```

---

## 📖 API Reference

### `_G.OnyxUI`

| Method | Description | Returns |
|--------|-------------|---------|
| `CreateTabPage(name)` | Creates a new tab page | `Frame` |
| `CreateSectionCard(page, title, position, size)` | Creates a styled section card | `Frame` |
| `CreateCheckbox(parent, text, position, default)` | Adds a toggle checkbox | `Frame` |
| `CreateSlider(parent, text, position, min, max, default)` | Adds a draggable slider | `Frame` |
| `CreateColorPicker(parent, text, position, defaultColor)` | Adds a color picker with presets | `Frame` |
| `Toggle()` | Shows/Hides the UI | `nil` |
| `Visible()` | Returns current visibility state | `boolean` |

### `_G.OnyxUI.Theme`

Modify the theme table **before** loading components to customize colors:

```lua
_G.OnyxUI.Theme.Accent = Color3.fromRGB(255, 100, 100)
_G.OnyxUI.Theme.Bg = Color3.fromRGB(20, 20, 25)
```

| Key | Default | Description |
|-----|---------|-------------|
| `Bg` | `Color3.fromRGB(10,10,12)` | Main background |
| `Sidebar` | `Color3.fromRGB(14,14,16)` | Sidebar background |
| `Card` | `Color3.fromRGB(22,22,26)` | Card background |
| `Accent` | `Color3.fromRGB(59,130,246)` | Primary highlight color |
| `Text` | `Color3.fromRGB(245,245,247)` | Main text color |

---

## 🎮 Controls

- **RightShift** → Toggle UI visibility
- **Left Click & Drag** → Move window
- **Click components** → Interact with checkboxes, sliders, and color pickers

---

## 🛡️ Safety & Compatibility

- ✅ Uses only standard `game:GetService()` calls
- ✅ No `require()`, `getgenv()`, or external dependencies
- ✅ Clean instance hierarchy with proper cleanup
- ✅ Compatible with all major executors supporting standard Lua

---

## 📝 Notes

- The library exports all functions under `_G.OnyxUI` for easy access
- Color picker popups are automatically parented to the active tab to prevent clipping
- Time/Date updates every second via `task.spawn`
- All animations use `TweenService` with `Quad` easing for smooth performance

---

## 🤝 Contributing

Found a bug or want a feature? Open an issue or submit a PR. All contributions are welcome.

---

## 📜 License

MIT License. Use freely in personal or commercial projects. Attribution is appreciated but not required.

---

Made with 💙 for the Roblox scripting community.
