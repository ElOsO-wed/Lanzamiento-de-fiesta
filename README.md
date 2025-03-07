local player = game.Players.LocalPlayer
local playerGui = player:FindFirstChild("PlayerGui")

-- Crear la GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = playerGui

local videoFrame = Instance.new("VideoFrame")
videoFrame.Size = UDim2.new(1, 0, 1, 0) -- Pantalla completa
videoFrame.Position = UDim2.new(0, 0, 0, 0)
videoFrame.BackgroundTransparency = 1
videoFrame.Video = "rbxassetid://5608292559" -- Reemplaza con tu ID de video
videoFrame.Parent = screenGui
videoFrame.Looped = false
videoFrame.Volume = 5
videoFrame.Playing = true

-- Esperar 15 segundos (duración del video)
wait(15)

-- Eliminar la animación de video
screenGui:Destroy()

-- EJECUTAR EL SCRIPT PRINCIPAL
local mainGui = Instance.new("ScreenGui")
mainGui.Parent = game.CoreGui
mainGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
mainGui.ResetOnSpawn = false

local frame = Instance.new("Frame")
frame.Parent = mainGui
frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
frame.Size = UDim2.new(0, 186, 0, 256)
frame.Active = true
frame.Draggable = true

local textLabel1 = Instance.new("TextLabel")
textLabel1.Parent = frame
textLabel1.Size = UDim2.new(0, 186, 0, 45)
textLabel1.Font = Enum.Font.LuckiestGuy
textLabel1.Text = "Lanzamiento de fiesta"
textLabel1.TextColor3 = Color3.fromRGB(255, 255, 255)
textLabel1.TextScaled = true
textLabel1.TextWrapped = true

local textLabel2 = Instance.new("TextLabel")
textLabel2.Parent = frame
textLabel2.Position = UDim2.new(0, 0, 0.82421875, 0)
textLabel2.Size = UDim2.new(0, 186, 0, 45)
textLabel2.Font = Enum.Font.LuckiestGuy
textLabel2.Text = "Made By: YANSER_EXPLOIT"
textLabel2.TextColor3 = Color3.fromRGB(255, 255, 255)
textLabel2.TextScaled = true
textLabel2.TextWrapped = true

local button = Instance.new("TextButton")
button.Parent = frame
button.Position = UDim2.new(0, 0, 0.31640625, 0)
button.Size = UDim2.new(0, 186, 0, 55)
button.Font = Enum.Font.LuckiestGuy
button.Text = "Auto punto"
button.TextColor3 = Color3.fromRGB(255, 255, 255)
button.TextScaled = true
button.TextWrapped = true

button.MouseButton1Click:Connect(function()
	local character = player.Character or player.CharacterAdded:Wait()
	local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

	-- Crear mensaje de ejecución
	local executeGui = Instance.new("ScreenGui")
	executeGui.Parent = player.PlayerGui

	local executeLabel = Instance.new("TextLabel")
	executeLabel.Parent = executeGui
	executeLabel.Size = UDim2.new(0.4, 0, 0.1, 0)
	executeLabel.Position = UDim2.new(0.3, 0, 0.05, 0)
	executeLabel.BackgroundTransparency = 0.3
	executeLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	executeLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
	executeLabel.TextScaled = true
	executeLabel.Font = Enum.Font.SourceSansBold
	executeLabel.Text = "EXECUTANDO!!!.... Made BY: YANSER_EXPLOIT"

	wait(5) -- Esperar 5 segundos

	task.delay(1, function()
		executeGui:Destroy()
	end)

	while true do
		character.Parent = nil
		humanoidRootPart.CFrame = CFrame.new(267, 0, 14)
		wait(0.1)
		character.Parent = game.Workspace
		wait(0.1)
		character.Parent = nil
		humanoidRootPart.CFrame = CFrame.new(271, 233, -6)
		wait(0.1)
		character.Parent = game.Workspace
		wait(0.1)
	end
end)
