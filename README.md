mob = ""
Distance = -9
weapon = ""
-- anti afk
local VirtualUser=game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
    VirtualUser:CaptureController()
    VirtualUser:ClickButton2(Vector2.new())
end)



local VIM = game:GetService("VirtualInputManager")
local chars = game.Players.LocalPlayer.Character or game.Players.LocalPlayer.CharacterAdded:Wait()
local player = game.Players.LocalPlayer
local function sellurn()
    game:GetService("ReplicatedStorage").RemoteEvents.ItemRemote:FireServer()

end
local function hidename()
if game.Players.LocalPlayer.Character.Head:FindFirstChild("Overhead") then
game.Players.LocalPlayer.Character.Head:FindFirstChild("Overhead"):Destroy()
end
end
local function quets()
local quest = game:GetService("Players").LocalPlayer.PlayerValues.CurrentQuest.Value
if quest == "" and currentquests == "Defeat 10 Wood Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest1)

local function sellurn()
game:GetService("ReplicatedStorage").RemoteEvents.ItemRemote:FireServer()

end    
    
else    
if quest == "" and currentquests == "Defeat 9 Ice Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest2)
else
if quest == "" and currentquests == "Defeat 8 Rock Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest3)
 else
if quest == "" and currentquests == "Defeat 7 Iron Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest4)
else
if quest == "" and currentquests == "Defeat 6 Metal Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest5)
else
    if quest == "" and currentquests == "Defeat 5 Steel Dummies"  then
   
game:GetService("ReplicatedStorage").RemoteEvents.ChangeQuestRemote:FireServer(quest6)

else
print("no quest")
  
 
 
     
 
 
 
  end    
 end   
end
end
end     
end
end







currentquests = "Defeat 10 Wood Dummies"
quest1 = game:GetService("ReplicatedStorage").Quests["Defeat 10 Wood Dummies"]
quest2 = game:GetService("ReplicatedStorage").Quests["Defeat 9 Ice Dummies"]
quest3 = game:GetService("ReplicatedStorage").Quests["Defeat 8 Rock Dummies"]
quest4 = game:GetService("ReplicatedStorage").Quests["Defeat 7 Iron Dummies"]
quest5 = game:GetService("ReplicatedStorage").Quests["Defeat 6 Metal Dummies"]
quest6 = game:GetService("ReplicatedStorage").Quests["Defeat 5 Steel Dummies"]









function enemy()
    while wait(0) do
    if workspace.Live then
        local shit = workspace.Live:GetDescendants(mob)
        for i = 1, #shit do local v = shit[i]
            if v.Name == mob and v:IsA("Model") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                print(v)
                return v
            end
        end
    end
end
end
local function damage()
local args = {
    [1] = false,
    [2] = Vector3.new(3128.7421875, -3170.0270996094, -8373.1376953125),
    [3] = CFrame.new(Vector3.new(3128.7421875, -3170.0270996094, -8373.1376953125), Vector3.new(0.38824120163918, -0.32355213165283, -0.86289215087891))
}

game:GetService("ReplicatedStorage").RemoteEvents.BladeCombatRemote:FireServer(unpack(args))
    
end
local function damage2()
local args = {
    [1] = false,
    [2] = Vector3.new(198.79348754883, 62.253589630127, 636.21868896484),
    [3] = CFrame.new(Vector3.new(198.79348754883, 62.253589630127, 636.21868896484), Vector3.new(0.87055194377899, -0.42890161275864, 0.24121090769768)),
    [4] = 1,
    [5] = Vector3.new(0.92324495315552, -0.36570227146149, 0.11781609803438)
}

game:GetService("ReplicatedStorage").RemoteEvents.WhiteBlowRemote:FireServer(unpack(args))
    

end
local lib = loadstring(game:HttpGet"https://raw.githubusercontent.com/Recovery-coder/ui/main/Vape")()

local win = lib:Window("Project Porn",Color3.fromRGB(44, 120, 224), Enum.KeyCode.RightControl)
local tab = win:Tab("AutoFarm")
local tab2 = win:Tab("Skills")
local tab3 = win:Tab("Item Tp")
local tab4 = win:Tab("Misc")

tab:Toggle("AutoFarm",false, function(t)
_G.Farm = t

while true do 
if not _G.Farm then return end








repeat
local v = enemy()
damage()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(v.HumanoidRootPart.Position) * CFrame.Angles(math.rad(Distance < 0 and 0 or 0), 0, 0) + Vector3.new(0, Distance, 0)
wait()
until not _G.Farm or enemy ~= v.Name or not v.Parent or not v:FindFirstChild("Humanoid") or v.Humanoid.Health <= 0
end
end)
tab:Toggle("AutoQuest",false, function(t)
_G.quest = t    
if not _G.quest then return end     
   
repeat    
wait(0)
quets()
until  not _G.quest
end)    



tab:Dropdown("Quest",{"Defeat 10 Wood Dummies","Defeat 9 Ice Dummies","Defeat 8 Rock Dummies","Defeat 7 Iron Dummies","Defeat 6 Metal Dummies","Defeat 5 Steel Dummies"}, function(t)


currentquests = t

end)
tab:Slider("Slider",-15,15,5, function(t)
Distance = t
end)

tab:Dropdown("Mobs",{"Wood Dummy","Ice Dummy","Rock Dummy","Iron Dummy","Metal Dummy","Steel Dummy"}, function(t)
mob = t
end)
tab:Dropdown("Weapons",{"Moku Moku no mi","Goro Goro no mi","Electrification","Mera Mera no mi","Kage Kage no mi","Pika Pika no mi","Ittoryu; Shusui"}, function(t)
weapon = t
end)
tab:Toggle("Auto Equip",false, function(t)
_G.equip = t    
while true do 
wait(0.5)
if not _G.equip then return end 

for _, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
if v.Name == weapon then     
v.Parent = game.Players.LocalPlayer.Character
end
end   
end   
end)
--tab 2
tab2:Toggle("Skill E",false, function(t)
_G.skillE = t    
while true do 
if not _G.skillE then return end
VIM:SendKeyEvent(true, Enum.KeyCode.E, false, game)
wait(0.1)

end    
end)   
tab2:Toggle("Skill R",false, function(t)
_G.skillR = t      
while true do 
if not _G.skillR then return end
VIM:SendKeyEvent(true, Enum.KeyCode.R, false, game)
wait(0.1)
end   
end)   
tab2:Toggle("Skill C",false, function(t)
_G.skillC = t
while true do 
if not _G.skillC then return end
 VIM:SendKeyEvent(true, Enum.KeyCode.C, false, game)   
wait(0.1)

end
end)
tab2:Toggle("Skill X",false, function(t)
_G.skillX = t    
while true do 
if not _G.skillX then return end   
VIM:SendKeyEvent(true, Enum.KeyCode.X, false, game)
wait(0.1)

end
end)
--tab3
tab3:Toggle("Item Tp",false, function(t)
_G.tp = t
while true do
if not _G.tp then return end
for _, v in pairs(game:GetService("Workspace"):GetDescendants()) do
if  v.Name == "TouchInterest"  then
  
firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent,0)
end    
end    
wait(0.30)
end 
end)


tab3:Toggle("Remove Useless Items",false, function(t)
_G.ew = t
while true do
if not _G.ew then return end
wait(4)
for i,fr in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if fr.Name == "Scripts" or fr.Name == "Bag" or fr.Name == "Moku Moku no mi" or fr.Name == "Pika Pika no mi" or fr.Name == "Kage Kage no mi" or fr.Name == "Mera Mera no mi" or fr.Name == "Electrification" or fr.Name == "Goro Goro no mi" or fr.Name == "Heart" or fr.Name == "Eyeball" or fr.Name == "Brain" or fr.Name == "Fire Stone" or fr.Name == "Lightning Stone" or fr.Name == "Gem of the Aspect" or fr.Name == "Doa Doa no mi v1" or fr.Name == "Danger Sense v1" or fr.Name == "Danger Sense v2" or fr.Name == "Hirenkyaku" or fr.Name == "Sonido" or fr.Name == "Flashstep" or fr.Name == "Bag"  then 
    
    
    
    
    
    else
        fr:Destroy()
    end


end
end
end)   

tab4:Button("Better Dao Visuals", function()
local doacolor = game:GetService("Lighting").DoaColorCorrection


doacolor.TintColor =  Color3.fromRGB(25, 255, 100)
doacolor.Saturation = 3
doacolor.Brightness = 0.30000001192093
doacolor.Contrast = 1
end)

tab4:Button("Hide Name", function()
hidename()
end)
tab4:Button("Equip all Items", function()
for _, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
v.Parent = game.Players.LocalPlayer.Character
end
end)

tab4:Button("Sell Urn", function()
for _, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
if v.Name == "Urn" then
v.Parent = game.Players.LocalPlayer.Character
end
end
wait(0.50)
sellurn()

end)
tab4:Toggle("Kill Aura",false, function(t)
_G.aura = t    
while wait(0.20) do
if not _G.aura then return end
damage()

end
end)

tab4:Button("Spoof Name", function()
game:GetService("Players").LocalPlayer.PlayerGui.Menu:FindFirstChild("Name").Text = "Nigga-Kun"
end)
