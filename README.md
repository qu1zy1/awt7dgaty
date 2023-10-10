local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "NightHub | Blade Ball",
   LoadingTitle = "NightHub",
   LoadingSubtitle = "by qu1zy and chase",
   ConfigurationSaving = {
      Enabled = False,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "NightHub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = True, -- Set this to true to use our key system
   KeySettings = {
      Title = "Blade Ball| Keys",
      Subtitle = "Key In Discord Server",
      Note = "Join Discord From Misc Tab",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = True, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"https://pastebin.com/raw/FGK1BmCC"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("⚔Combat", nil) -- Title, Image
local MainSection = MainTab:CreateSection("Combat")

Rayfield:Notify({
   Title = "successfully Executed NightHub",
   Content = "Enjoy Thanks For Using NightHub",
   Duration = 5,
   Image = nil,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("The user tapped Okay!")
      end
   },
},
})

local Button = MainTab:CreateButton({
   Name = "RageParry",
   Callback = function()
        while wait() do
for i, v in pairs(game.Workspace.Balls:GetChildren()) do
if v:GetAttribute("realBall") == true then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
if game.Players.LocalPlayer.Character:FindFirstChild("Highlight") then
game:GetService("ReplicatedStorage").Remotes.ParryButtonPress:Fire()
end
end
end
end
   end,
})

local Toggle = MainTab:CreateToggle({
   Name = "AutoParry",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        --[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
getgenv().config = getgenv().config or {
	hit_time = 0.5, -- // recommended 0.25 to 0.75 \\ --
	
	mode = 'Always', -- // Hold , Toggle , Always \\ --
	deflect_type = 'Remote', -- // Key Press , Remote \\ --
	notifications = true,
	keybind = Enum.KeyCode.X
}

loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/Refinement/main/MC%3ABlade%20Ball%20Parry%20V4.0.0",true))()
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})

local Slider = MainTab:CreateSlider({
   Name = "WalkSpeed",
   Range = {0, 350},
   Increment = 10,
   Suffix = "Speed",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
   end,
})

local Button = MainTab:CreateButton({
   Name = "Infinite Jump",
   Callback = function()
        local notification = Instance.new("Hint")
notification.Text = "Script by qu1zy"
notification.Parent = game.StarterGui
 
local player = game.Players.LocalPlayer
 
local infiniteJumpPower = 100
local defaultJumpPower = 50
 
local gui = Instance.new("ScreenGui")
gui.Name = "InfiniteJumpGUI"
gui.Parent = player.PlayerGui
 
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 200, 0, 50)
mainFrame.Position = UDim2.new(1, -220, 1, -60) -- Position at the bottom-right corner
mainFrame.BackgroundTransparency = 0.3
mainFrame.BackgroundColor3 = Color3.new(0.2, 0.8, 0.8) -- Teal background color
mainFrame.BorderSizePixel = 0
mainFrame.Parent = gui
 
 
local turnOnButton = Instance.new("TextButton")
turnOnButton.Name = "TurnOnButton"
turnOnButton.Text = "Infinite Jump"
turnOnButton.Size = UDim2.new(0, 200, 0, 50)
turnOnButton.Position = UDim2.new(0, 0, 0, 0)
turnOnButton.BackgroundTransparency = 0.3
turnOnButton.BackgroundColor3 = Color3.new(0.4, 0.9, 0.4) -- Light green background color
turnOnButton.Parent = mainFrame
 
local minimizeButton = Instance.new("TextButton")
minimizeButton.Name = "MinimizeButton"
minimizeButton.Text = "_"
minimizeButton.Size = UDim2.new(0, 30, 0, 30)
minimizeButton.Position = UDim2.new(1, -35, 0, 5) -- Position at the top-right corner
minimizeButton.BackgroundTransparency = 0.3
minimizeButton.BackgroundColor3 = Color3.new(0.8, 0.2, 0.2) -- Red background color
minimizeButton.TextColor3 = Color3.new(1, 1, 1)
minimizeButton.Parent = mainFrame
 
local function handleJump()
    
    if player.Character and player.Character:FindFirstChildOfClass("Humanoid") then
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        
 
        humanoid.JumpPower = infiniteJumpPower
        
        humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end
 
local function turnOnInfiniteJump()
    handleJump()
    turnOnButton.Visible = true
end
 
local function minimizeGUI()
    mainFrame.Visible = false
    minimizeButton.Visible = false
end
 
turnOnButton.MouseButton1Click:Connect(turnOnInfiniteJump)
minimizeButton.MouseButton1Click:Connect(minimizeGUI)
 
local UserInputService = game:GetService("UserInputService")
UserInputService.InputBegan:Connect(function(input, isProcessed)
    if not isProcessed and input.KeyCode == Enum.KeyCode.Space then
        turnOnInfiniteJump()
    end
end)
 game:GetService("StarterGui"):SetCore("SendNotification", { 
        Title = "Script By";
        Text  = "qu1zy";
        Icon  = "rbxthumb://type=Asset&id=5107182114&w=150&h=150"})
    Duration = 16;
   end,
})

local MiscTab = Window:CreateTab("✨Misc", nil) -- Title, Image
local Section = MiscTab:CreateSection("Misc")

local Button = MiscTab:CreateButton({
   Name = "AntiAfk",
   Callback = function()
        wait(0.5)local ba=Instance.new("ScreenGui")
local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,370,0,52)
ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk"ca.TextColor3=Color3.new(0,1,1)
ca.TextSize=22;da.Parent=ca
da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
da.Size=UDim2.new(0,370,0,107)_b.Parent=da
_b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
_b.Size=UDim2.new(0,370,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by qu1zy"
_b.TextColor3=Color3.new(0,1,1)_b.TextSize=20;ab.Parent=da
ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377,0)
ab.Size=UDim2.new(0,370,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Active"
ab.TextColor3=Color3.new(0,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
bb:CaptureController()bb:ClickButton2(Vector2.new())
ab.Text="Roblox tried kicking you buy I didnt let them!"wait(2)ab.Text="Status : Active"end)
   end,
})

local Input = MiscTab:CreateInput({
   Name = "Jump Power",
   PlaceholderText = "1-200",
   RemoveTextAfterFocusLost = True,
   Callback = function(Text)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = (Text)
   end,
})

local Button = MiscTab:CreateButton({
   Name = "FpsBoost",
   Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/xfarzad/Sources/main/UWP%20fps%20boost.lua", true))()
   end,
})
