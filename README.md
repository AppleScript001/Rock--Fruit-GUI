local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()
local Mobs_Table = {}
for _, v in ipairs(workspace.Mob:GetDescendants()) do
    if v:IsA("Model") and v:FindFirstChild("HumanoidRootPart") and not table.find(Mobs_Table, v.Name) then
        table.insert(Mobs_Table, v.Name)
        table.sort(Mobs_Table)
    end
end

local PlayerTP1
local TweenService = game:GetService("TweenService")

Npcs = {}
for i,v in pairs(workspace.npcClick:GetChildren()) do
    table.insert(Npcs,v.Name) 
end

local X = Material.Load({
	Title = "🍀 Rock Fruit 🍀 | AppleScript001",
	Style = 2,
	SizeX = 400,
	SizeY = 320,
	Theme = "Dark",
	ColorOverrides = {
		MainFrame = Color3.fromRGB(0,9,55)
	}
})

local Y = X.New({
	Title = "Main"
})
local ii = Y.Dropdown({
	Text = "Select Mobs!",
	Callback = function(t)
        PlayerTP1 = t
	end,
	Options = Mobs_Table
})
Y.Button(
    {
        Text = "Refresh/Mobs",
        Callback = function()
            table.clear(Mobs_Table)
            for i, v in pairs(workspace.Mob:GetDescendants()) do
                if v:IsA "Model" and v:FindFirstChild("HumanoidRootPart") then
                    if not table.find(Mobs_Table, tostring(v)) then
                        table.insert(Mobs_Table, tostring(v))
                        ii:SetOptions(Mobs_Table)
                    end
                end
            end
        end
    }
)
Y.Dropdown({
Text = "Select Weapon!",
Callback = function(t)
Weapon = t
	end,
Options = {
        "Combat",
        "Muaythai",
        "David",
        "Megumin",
        "Shikono",
        "Katana",
        "KatanaWooden",
        "HeavenKatana",
        "Shisui",
        "Wado",
        "Yoru",
        "DarkKatana",
        "Gryphon",
},
})
Y.Toggle({
Text = "Auto Farm/Mobs",
Callback = function(Value)
_G.Attack = Value
while _G.Attack do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == PlayerTP1 then
if v.Humanoid.Health > 0 then
repeat
local toolName = Weapon -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
    v.Parent = LocalPlayer.Character
    break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Attack or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
local T = X.New({
	Title = "Items"
})
T.Toggle({
Text = "Farm - [Bacon 15%]",
Callback = function(Value)
_G.Bacon = Value
while _G.Bacon do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Bacon" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Bacon or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Red 10%]",
Callback = function(Value)
_G.Red = Value
while _G.Red do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Bacon Red" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Red or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Clown Mask 5%]",
Callback = function(Value)
_G.Clown = Value
while _G.Clown do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Buggy" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Clown or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Blue 10%]",
Callback = function(Value)
_G.Blue = Value
while _G.Blue do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Bacon Blue" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Blue or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Cat 1%]",
Callback = function(Value)
_G.cat = Value
while _G.cat do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Cat" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.cat or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Rot Banana 5%]",
Callback = function(Value)
_G.rot = Value
while _G.rot do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Gorilla" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.rot or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Shiny Banana 1%]",
Callback = function(Value)
_G.Shiny = Value
while _G.Shiny do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Gorilla Power" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Shiny or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Skull Mask 4%]",
Callback = function(Value)
_G.skull = Value
while _G.skull do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Koma Man" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.skull or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Rock 1%]",
Callback = function(Value)
_G.rock = Value
while _G.rock do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Moai" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.rock or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Banana 1%]",
Callback = function(Value)
_G.banana = Value
while _G.banana do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Monkey" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.banana or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb White 5%]",
Callback = function(Value)
_G.white = Value
while _G.white do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Pirate" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.white or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Sand 5%]",
Callback = function(Value)
_G.sand = Value
while _G.sand do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Sand Man" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.sand or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Banana Stem 1%]",
Callback = function(Value)
_G.stem = Value
while _G.stem do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Tani Man" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.stem or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Dark 2%]",
Callback = function(Value)
_G.dark = Value
while _G.dark do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Zombie Smile" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.dark or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Scarf 4%]",
Callback = function(Value)
_G.scarf = Value
while _G.scarf do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Zombie Speed" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.scarf or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Black 5%]",
Callback = function(Value)
_G.black = Value
while _G.black do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "ZombieXD" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.black or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Tissue 5%]",
Callback = function(Value)
_G.black = Value
while _G.black do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Bacon Marine" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.black or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
Text = "Farm - [Orb Purple 4%]",
Callback = function(Value)
_G.black = Value
while _G.black do
task.wait(0.1)
pcall(function()
for i,v in pairs(workspace.Mob:GetDescendants()) do
if v.Name == "Marine Strong" then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
LocalPlayer.Character:FindFirstChild(toolName):Activate()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.black or v.Humanoid.Health <= 0
end
end
end
end)
end
end,
Enabled = false
})
T.Toggle({
    Text = "Farm - [Orb Demon 1%]",
    Callback = function(Value)
    _G.Demon = Value
    while _G.Demon do
    task.wait(0.1)
    pcall(function()
    for i,v in pairs(workspace.Mob:GetDescendants()) do
    if v.Name == "Demon Man" then
    if v.Humanoid.Health > 0 then
    repeat
    local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
    local LocalPlayer = game:GetService("Players").LocalPlayer
    for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
    if v:IsA('Tool') and v.Name == toolName then
    v.Parent = LocalPlayer.Character
    break -- Stop the loop after picking up the tool
    end
    end
    LocalPlayer.Character:FindFirstChild(toolName):Activate()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
    wait()  -- Wait a short time before checking again
    until not _G.Demon or v.Humanoid.Health <= 0
    end
    end
    end
    end)
    end
    end,
    Enabled = false
})
T.Toggle({
    Text = "Farm - [Orb Dragon 1%]",
    Callback = function(Value)
    _G.Dragon = Value
    while _G.Dragon do
    task.wait(0.1)
    pcall(function()
    for i,v in pairs(workspace.Mob:GetDescendants()) do
    if v.Name == "Dragon Man" then
    if v.Humanoid.Health > 0 then
    repeat
    local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool 
    local LocalPlayer = game:GetService("Players").LocalPlayer
    for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
    if v:IsA('Tool') and v.Name == toolName then
    v.Parent = LocalPlayer.Character
    break -- Stop the loop after picking up the tool
    end
    end
    LocalPlayer.Character:FindFirstChild(toolName):Activate()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
    wait()  -- Wait a short time before checking again
    until not _G.Dragon or v.Humanoid.Health <= 0
    end
    end
    end
    end)
    end
    end,
    Enabled = false
})

local S = X.New({
    Title = "Stats"
})
S.Toggle({
Text = "Melee",
Callback = function(Value)
_G.melee = Value
while _G.melee do
wait()
game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer("UpStats", "Melee", 100)
end
end,
Enabled = false
})
S.Toggle({
Text = "Sword",
Callback = function(Value)
_G.sword = Value
while _G.sword do
wait()
game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer("UpStats", "Sword", 100)
end
end,
Enabled = false
})
S.Toggle({
Text = "Devil-Fruits",
Callback = function(Value)
_G.fruit = Value
while _G.fruit do
wait()
game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer("UpStats", "DevilFruit", 100)
end
end,
Enabled = false
})
S.Toggle({
Text = "Special",
Callback = function(Value)
_G.magic = Value
while _G.magic do
wait()
game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer("UpStats", "Special", 100)
end
end,
Enabled = false
})
S.Toggle({
Text = "Defense",
Callback = function(Value)
_G.Health = Value
while _G.Health do
wait()
game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer("UpStats", "Defense", 100)
end
end,
Enabled = false
})
local R = X.New({
	Title = "NPC"
})
local uu = R.Dropdown({
	Text = "Select NPC!",
	Callback = function(Value)
        Npc = Value
	end,
	Options = Npcs
})
R.Button(
    {
        Text = "Refresh/NPC",
        Callback = function()
            table.clear(Npcs)
            for i, v in pairs(workspace.npcClick:GetDescendants()) do
                if v:IsA "Model" and v:FindFirstChild("HumanoidRootPart") then
                    if not table.find(Npcs, tostring(v)) then
                        table.insert(Npcs, tostring(v))
                        uu:SetOptions(Npcs)
                    end
                end
            end
        end
    }
)
R.Button({
Text = "Tp",
Callback = function()
for i,v in pairs(workspace.npcClick[Npc]:GetDescendants()) do
if v.Name == "HumanoidRootPart" then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
end,
})
local I = X.New({
	Title = "Island"
})
I.Button({
Text = "Starter Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(91.0101547, 95.3697205, -920.771179, -0.998822331, 6.20104501e-09, 0.0485174991, 5.77855142e-09, 1, -8.84833096e-09, -0.0485174991, -8.55755022e-09, -0.998822331)
end,
})
I.Button({
Text = "Skull Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-932.757446, 22.2691574, 166.437866, 0.120102331, 3.6117811e-08, 0.992761493, 2.54782684e-08, 1, -3.94634654e-08, -0.992761493, 3.00334975e-08, 0.120102331)
end,
})
I.Button({
Text = "Coconut Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1353.11523, 18.4210606, -1192.56982, 0.153942347, 1.25322259e-08, -0.988079846, -1.07434957e-07, 1, -4.05489819e-09, 0.988079846, 1.06778529e-07, 0.153942347)
end,
})
I.Button({
Text = "Buggy Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1192.25305, 16.9509182, 101.26046, 0.0179014821, -6.38557935e-08, -0.999839783, 6.00907768e-08, 1, -6.27901429e-08, 0.999839783, -5.8957113e-08, 0.0179014821)
end,
})
I.Button({
Text = "Sand Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(108.563576, 22.751915, 1044.93811, -0.997287512, -7.29497884e-08, 0.0736048073, -7.89143115e-08, 1, -7.81262557e-08, -0.0736048073, -8.372281e-08, -0.997287512)
end,
})
I.Button({
Text = "Pirate Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-953.485413, 26.838707, -1197.76123, 0.646016896, 4.23648743e-08, 0.763323128, 3.06679873e-08, 1, -8.14555605e-08, -0.763323128, 7.60312489e-08, 0.646016896)
end,
})
I.Button({
Text = "Rock Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1222.85059, 25.6455154, 1552.65491, -0.518102407, 8.60653202e-08, -0.855318606, 7.82970577e-09, 1, 9.58809139e-08, 0.855318606, 4.29792379e-08, -0.518102407)
end,
})
I.Button({
Text = "Monkey Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(185.737122, 13.0266523, -1721.12341, 0.999867439, -6.15261231e-10, 0.0162821803, 5.354861e-10, 1, 4.9038964e-09, -0.0162821803, -4.89452745e-09, 0.999867439)
end,
})
I.Button({
Text = "Zomebie Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-799.199707, 75.6590118, 1253.22314, -0.0977619588, 1.65685432e-09, 0.995209813, -3.34438166e-09, 1, -1.99335615e-09, -0.995209813, -3.52323593e-09, -0.0977619588)
end,
})
I.Button({
Text = "Event Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2.51008773, 19.3622723, 0.998785615, -0.997371972, -1.81395805e-08, 0.07245069, -9.58642588e-09, 1, 1.18402568e-07, -0.07245069, 1.17396858e-07, -0.997371972)
end,
})
I.Button({
Text = "Marine Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(77.1779404, 51.5903358, 2291.68311, -0.999949753, -2.0541591e-11, 0.0100267194, -1.20574618e-11, 1, 8.46212544e-10, -0.0100267194, 8.4604912e-10, -0.999949753)
end,
})
I.Button({
Text = "Boss Island",
Callback = function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1953.4054, 15.9745502, -461.09671, 0.0952273831, -1.55894533e-08, 0.995455563, -4.84080276e-10, 1, 1.57069309e-08, -0.995455563, -1.9776103e-09, 0.0952273831)
end,
})
I.Button({
    Text = "Demon Island",
    Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1277.09583, 17.3987808, -2118.93921, 0.738377094, -1.1523861e-08, -0.674388051, -6.52020162e-08, 1, -8.84765612e-08, 0.674388051, 1.0930053e-07, 0.738377094)
    end,
})
I.Button({
    Text = "Dragon Island",
    Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2104.74731, 12.3522291, 827.102722, -0.581708133, -7.08551329e-10, 0.813397586, 5.95031002e-09, 1, 5.12651521e-09, -0.813397586, 7.82210385e-09, -0.581708133)
    end,
})

local Z = X.New({
    Title = "LocalPlayer"
})
Z.Slider({
	Text = "WalkSpeed",
	Callback = function(Value)
		getgenv().bool = Value
	end,
	Min = 50,
	Max = 500,
	Def = 50
})
Z.Button({
Text = "Change-WalkSpeed",
Callback = function()
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = bool
end,
})
local E = X.New({
	Title = "Extra"
})
E.Toggle({
Text = "Collect Fruit [Items]",
Callback = function(Value)
_G.bring = Value
while _G.bring do
wait(1)
for _,v in pairs(workspace.Fruits:GetDescendants()) do
if v:IsA("TouchTransmitter") then
firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
end
end
end
end,
Enabled = false
})
E.Toggle({
Text = "Auto Random-Fruit",
Callback = function(Value)
_G.buy = Value
while _G.buy do
wait(0.1)
local args = {
    [1] = "Random"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("RandomFruit"):FireServer(unpack(args))
wait(0.1)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(131.559616, 37.8697586, -915.78833, 0.00800570473, 1.13077157e-08, -0.999967933, -5.6414895e-09, 1, 1.12629133e-08, 0.999967933, 5.55114132e-09, 0.00800570473)
end
end,
Enabled = false
})
for i,v in pairs(getconnections(game.Players.LocalPlayer.Idled)) do
    v:Disable()
end
