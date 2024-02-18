
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({Name = "mwing8 Hub", HidePremium = false, SaveConfig = true, ConfigFolder = "mwing8 Hub"})

FarmTab = Window:MakeTab({
	Name = "Farm",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local Section = FarmTab:AddSection({
	Name = "Farm"
})

FarmTab:AddButton({
	Name = "Farm",
	Callback = function()
      		print("haha")
  	end    
})

FarmTab:AddToggle({
	Name = "Farm",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})

FarmTab:AddBind({
	Name = "ngu",
	Default = Enum.KeyCode.E,
	Hold = false,
	Callback = function()
		print("oke")
	end    
})

FarmTab:AddDropdown({
	Name = "twen",
	Default = "2",
	Options = {"mainson", "turtle"},
	Callback = function(Value)
		print(Value)
	end    
})

local tween_s = game:service "TweenService"
local info = TweenInfo.new(
    (RealTarget.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position)
    .Magnitude / Speed, Enum.EasingStyle.Linear)
local tweenw, err = pcall(function()
    tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, { CFrame = RealTarget })
    tween:Play()
end)

function tweenfunc:Stop()
    tween:Cancel()
end

function tweenfunc:Wait()
    tween.Completed:Wait()
end

return tweenfunc
end
