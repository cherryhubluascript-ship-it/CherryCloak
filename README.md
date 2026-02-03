local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local backpack = player:WaitForChild("Backpack")

local toolName = "Invisibility Cloak"

local tool = backpack:FindFirstChild(toolName) or character:FindFirstChild(toolName)

if tool then
	humanoid:EquipTool(tool)
	task.wait(0.1)
	if tool.Activate then
		tool:Activate()
	end
	task.wait(0.5)
	if tool.Deactivate then
		tool:Deactivate()
	end
else
	warn("No se encontró la Invisibility Cloak")
end
