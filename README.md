local repo = 'https://raw.githubusercontent.com/violin-suzutsuki/LinoriaLib/main/'

local Library = loadstring(game:HttpGet(repo .. 'Library.lua'))()
local ThemeManager = loadstring(game:HttpGet(repo .. 'addons/ThemeManager.lua'))()
local SaveManager = loadstring(game:HttpGet(repo .. 'addons/SaveManager.lua'))()

local hacks = Library:CreateWindow({
    Title = 'walmart ps99 hacks lul',
    Center = true,
    AutoShow = true,
    TabPadding = 8,
    MenuFadeTime = 0.2
})

local Tabs = {
    home = hacks:AddTab('home'),
    gemsauto = hacks:AddTab('gems auto'),
	dealsniper = hacks:AddTab('good deal sniper'),
    ['UI Settings'] = hacks:AddTab('UI Settings'),
}

local auto_snipe = Tabs.dealsniper:AddLeftGroupbox('sniping')
local auto_snipe_modes = Tabs.dealsniper:AddRightGroupbox('autosnipe settings')

local autofarm_gems = Tabs.gemsauto:AddLeftGroupbox('autofarm')
local mode = Tabs.gemsauto:AddRightGroupbox('autofarm settings')

auto_snipe_modes:AddDropdown('modes', {
	Values = {'Legit', 'Blatant (risky)'},
	Default = 1,
	Multi = false,
	Text = 'modes',
	Tooltip = 'modes',
	Callback = function(Value)
		print('[cb] dropdown changed:', Value)
	end
})

mode:AddDropdown('modes', {
	Values = {'Legit', 'Blatant (risky)'},
	Default = 1,
	Multi = false,
	Text = 'modes',
	Tooltip = 'modes',
	Callback = function(Value)
		print('[cb] dropdown changed:', Value)
	end
})

auto_snipe:AddToggle('deal sniper', {
    Text = 'autosnipe deals toggle',
    Default = false,
    Tooltip = 'makes the player teleport to the trading plaza when a good deal is found',

    Callback = function(Value)
        
    end
})

autofarm_gems:AddToggle('autofarm', {
    Text = 'autofarm toggle',
    Default = false,
    Tooltip = 'makes the player teleport above every gem in the game and breaks it at light speed',

    Callback = function(Value)
        
    end
})

Toggles.autofarm:OnChanged(function()
    if Toggles.autofarm.Value == true then
		
    else

	end
end)

local MenuGroup = Tabs['UI Settings']:AddLeftGroupbox('Menu')

MenuGroup:AddButton('Unload', function() Library:Unload() end)
MenuGroup:AddLabel('Menu bind'):AddKeyPicker('MenuKeybind', { Default = 'End', NoUI = true, Text = 'Menu keybind' })

local homegroup = Tabs.home:AddLeftGroupbox('main')

homegroup:AddLabel('thank you for using walmart ps99 hacks <3')
