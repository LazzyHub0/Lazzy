local MainUI = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local Time_2 = Instance.new("TextLabel")
local BountyHunted = Instance.new("TextLabel")
local Logo = Instance.new("ImageLabel")
local UICorner = Instance.new("UICorner")
local UICorner_2 = Instance.new("UICorner")
local HUBname = Instance.new("TextLabel")
local T = Instance.new("TextLabel")
 
-- Properties
 
MainUI.Name = "MainUI"
 
MainUI.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
MainUI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
MainUI.ResetOnSpawn = false
 
Main.Name = "Main"
Main.Parent = MainUI
Main.BackgroundColor3 = Color3.new(1, 1, 1)
Main.BorderColor3 = Color3.new(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.402698278, 0, 0.274784476, 0)
Main.Size = UDim2.new(0, 200, 0, 250)
Main.Active = true
Main.Draggable = true
 
Time_2.Name = "Time"
Time_2.Parent = Main
Time_2.BackgroundColor3 = Color3.new(1, 1, 1)
Time_2.BackgroundTransparency = 1
Time_2.BorderColor3 = Color3.new(0, 0, 0)
Time_2.BorderSizePixel = 0
Time_2.Position = UDim2.new(0.0250000004, 0, 0.708000004, 0)
Time_2.Size = UDim2.new(0, 190, 0, 36)
Time_2.Font = Enum.Font.SourceSans
Time_2.Text = "Time Elapsed: 60H 60M 60S"
Time_2.TextColor3 = Color3.new(0, 0, 0)
Time_2.TextSize = 20
 
BountyHunted.Name = "BountyHunted"
BountyHunted.Parent = Main
BountyHunted.BackgroundColor3 = Color3.new(1, 1, 1)
BountyHunted.BackgroundTransparency = 1
BountyHunted.BorderColor3 = Color3.new(0, 0, 0)
BountyHunted.BorderSizePixel = 0
BountyHunted.Position = UDim2.new(-0.00131576543, 0, 0.850000024, 0)
BountyHunted.Size = UDim2.new(0, 200, 0, 36)
BountyHunted.Font = Enum.Font.SourceSans
BountyHunted.Text = "Bounty Hunted: 0000"
BountyHunted.TextColor3 = Color3.new(0, 0, 0)
BountyHunted.TextSize = 20
 
Logo.Name = "Logo"
Logo.Parent = Main
Logo.BackgroundColor3 = Color3.new(1, 1, 1)
Logo.BorderColor3 = Color3.new(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0, 0, -0.34799999, 0)
Logo.Size = UDim2.new(0, 200, 0, 200)
Logo.Image = "rbxassetid://14384647314"
 
UICorner.Parent = Logo
 
UICorner_2.Parent = Main
 
HUBname.Name = "HUBname"
HUBname.Parent = Main
HUBname.BackgroundColor3 = Color3.new(1, 1, 1)
HUBname.BackgroundTransparency = 1
HUBname.BorderColor3 = Color3.new(0, 0, 0)
HUBname.BorderSizePixel = 0
HUBname.Position = UDim2.new(-0.00131576543, 0, 0.451999992, 0)
HUBname.Size = UDim2.new(0, 200, 0, 30)
HUBname.Font = Enum.Font.SourceSans
HUBname.Text = "LAZZY HUB"
HUBname.TextColor3 = Color3.new(0, 0, 0)
HUBname.TextSize = 30
 
T.Name = "T"
T.Parent = Main
T.BackgroundColor3 = Color3.new(1, 1, 1)
T.BackgroundTransparency = 1
T.BorderColor3 = Color3.new(0, 0, 0)
T.BorderSizePixel = 0
T.Position = UDim2.new(-0.00131576543, 0, 0.572000027, 0)
T.Size = UDim2.new(0, 200, 0, 18)
T.Font = Enum.Font.SourceSans
T.Text = "Auto Bounty"
T.TextColor3 = Color3.new(0, 0, 0)
T.TextSize = 20
 
local s = 0
local m = 0
local h = 0
 
local plr = game:GetService("Players").LocalPlayer
local lastB = plr:WaitForChild("leaderstats")["Bounty/Honor"].Value
 
while wait(1) do
	s += 1
	if s >= 60 then
		s -= 60
		m += 1
	end
	if m >= 60 then
		m -= 60
		h += 1
	end
	Time_2.Text = "Time Elapsed: "..h.."H "..m.."M "..s.."S"
	local o = plr.leaderstats["Bounty/Honor"].Value - lastB
	if o >= 0 then
		BountyHunted.Text = "Bounty Hunted: "..o
	end
end
