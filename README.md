# qbr-menu
Menu System for the QBCore Framework

This is a modified version of **[NH Context](https://forum.cfx.re/t/no-longer-supported-standalone-nerohiro-s-context-menu-dynamic-event-firing-menu/2564083)** by **[NeroHiro](https://github.com/nerohiro)**

This is also modified version of **[QB Menu](https://github.com/qbcore-framework/qb-menu)** by **[Kakarot](https://github.com/GhzGarage)**

Original Repository **[QB Menu](https://github.com/qbcore-framework/qb-menu)**

Preview :

<img alt="Preview" height = "500" src="https://cdn.discordapp.com/attachments/898298633101918278/941789278260834374/unknown.png">


--[[
EXAMPLE MENU
--]]

```
RegisterCommand("qbrmenutest", function(source, args, raw)
    openMenu({
        {
            header = "Main Title",
            isMenuHeader = true, -- Set to true to make a nonclickable title
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            params = {
                event = "qbr-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
    })
end)
```
```
RegisterNetEvent('qbr-menu:client:testMenu2', function(data)
    local number = data.number
    openMenu({
        {
            header = "< Go Back",
        },
        {
            header = "Number: "..number,
            txt = "Other",
            params = {
                event = "qbr-menu:client:testButton",
                args = {
                    message = "This was called by clicking this button"
                }
            }
        },
    })
end)
```

# License

    QBCore Framework
    Copyright (C) 2021 Joshua Eger

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>
