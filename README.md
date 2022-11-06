local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "⭐ Star's Hub ⭐", HidePremium = false, SaveConfig = true, ConfigFolder = "Save"})
local Player = game.Players.LocalPlayer

-- Values

ForLoop = true

OrionLib:MakeNotification({
	Name = "Welcome",
	Content = "Welcome, " ..Player.Name.."!",
	Image = "rbxassetid://4483345998",
	Time = 5
})

-- Functions

function OHGCatEgg8()
    while ForLoop == true do
        wait()
local args = {
    [1] = {
        [1] = "Golden Cat Egg",
        [2] = true,
        [3] = true
    }
}

workspace.__THINGS.__REMOTES["buy egg"]:InvokeServer(unpack(args))

   end
end

function OHGCatEgg3()
    while ForLoop == true do
local args = {
    [1] = {
        [1] = "Golden Cat Egg",
        [2] = true,
        [3] = false
    }
}

workspace.__THINGS.__REMOTES["buy egg"]:InvokeServer(unpack(args))

   end
end

function LootBagsNotification()
    OrionLib:MakeNotification({
        Name = "Success!",
        Content = "Auto Collect Loot Bags has been enabled!",
        Image = "rbxassetid://4483345998",
        Time = 5
    })
end


-- Tabs & GUI

local Tab = Window:MakeTab({
    Name = "Cat Egg",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

Tab:AddToggle({
    Name = "Octuple Hatch",
    Default = false,
    Callback = function(Value)
    ForLoop = Value 
    OHGCatEgg8()
    end
})

Tab:AddToggle({
    Name = "Triple Hatch",
    Default = false,
    Callback = function(Value)
    ForLoop = Value
    OHGCatEgg3()
    end
})

local MiscTab = Window:MakeTab({
    Name = "Miscelaneous",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

MiscTab:AddButton({
    Name = "Auto Collect Lootbags",
    Callback = function()
    LootBagsNotification()
    while _G.Toggle do wait()
    for i,v in pairs(game:GetService("Workspace")["__THINGS"].Lootbags:GetChildren()) do
    v.CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.Position)
       end
   end
end
})

local InformationTab = Window:MakeTab({
    Name = "Information",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

InformationTab:AddParagraph("Read Me", "This HUB is going to be updated adding such as new functions or simply updating the script to the newest version of the game.")

InformationTab:AddParagraph("Current Version", "The current version of this HUB is v1.0.")
OrionLib:Init()
