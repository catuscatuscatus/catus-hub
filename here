
-- Catus Hub
-- Green and Black UI with Fixed Key

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local CORRECT_KEY = "catuscatuscatus"

-- Remove old UI if it exists
local oldGui = playerGui:FindFirstChild("CatusHub")
if oldGui then
    oldGui:Destroy()
end

local gui = Instance.new("ScreenGui")
gui.Name = "CatusHub"
gui.ResetOnSpawn = false
gui.Parent = playerGui

local function create(className, properties, parent)
    local object = Instance.new(className)
    for property, value in pairs(properties) do
        object[property] = value
    end
    object.Parent = parent
    return object
end

local green = Color3.fromRGB(0, 255, 120)
local dark = Color3.fromRGB(18, 22, 20)
local panel = Color3.fromRGB(28, 34, 30)
local white = Color3.fromRGB(240, 255, 245)

-- Main key window
local frame = create("Frame", {
    Name = "KeyFrame",
    Size = UDim2.fromOffset(340, 220),
    Position = UDim2.new(0.5, -170, 0.5, -110),
    BackgroundColor3 = dark,
    BorderSizePixel = 0,
}, gui)

create("UICorner", {CornerRadius = UDim.new(0, 12)}, frame)
create("UIStroke", {Color = green, Thickness = 1.5}, frame)

create("TextLabel", {
    Size = UDim2.new(1, 0, 0, 55),
    BackgroundTransparency = 1,
    Text = "CAT​US HUB",
    TextColor3 = green,
    TextSize = 26,
    Font = Enum.Font.GothamBold,
}, frame)

create("TextLabel", {
    Position = UDim2.fromOffset(20, 54),
    Size = UDim2.new(1, -40, 0, 25),
    BackgroundTransparency = 1,
    Text = "Enter your key to continue",
    TextColor3 = white,
    TextSize = 14,
    Font = Enum.Font.Gotham,
}, frame)

local keyBox = create("TextBox", {
    Position = UDim2.fromOffset(25, 90),
    Size = UDim2.new(1, -50, 0, 40),
    BackgroundColor3 = panel,
    TextColor3 = white,
    PlaceholderText = "Enter key...",
    PlaceholderColor3 = Color3.fromRGB(140, 150, 145),
    Text = "",
    TextSize = 15,
    Font = Enum.Font.Gotham,
    ClearTextOnFocus = false,
}, frame)

create("UICorner", {CornerRadius = UDim.new(0, 7)}, keyBox)

local status = create("TextLabel", {
    Position = UDim2.fromOffset(10, 174),
    Size = UDim2.new(1, -20, 0, 22),
    BackgroundTransparency = 1,
    Text = "",
    TextColor3 = green,
    TextSize = 13,
    Font = Enum.Font.Gotham,
}, frame)

local submit = create("TextButton", {
    Position = UDim2.fromOffset(25, 137),
    Size = UDim2.new(1, -50, 0, 35),
    BackgroundColor3 = green,
    Text = "UNLOCK HUB",
    TextColor3 = dark,
    TextSize = 14,
    Font = Enum.Font.GothamBold,
    AutoButtonColor = true,
}, frame)

create("UICorner", {CornerRadius = UDim.new(0, 7)}, submit)

local function unlockHub()
    if keyBox.Text ~= CORRECT_KEY then
        status.Text = "Incorrect key. Try again."
        status.TextColor3 = Color3.fromRGB(255, 90, 90)
        return
    end

    frame:Destroy()

    local hub = create("Frame", {
        Name = "HubFrame",
        Size = UDim2.fromOffset(340, 200),
        Position = UDim2.new(0.5, -170, 0.5, -100),
        BackgroundColor3 = dark,
        BorderSizePixel = 0,
    }, gui)

    create("UICorner", {CornerRadius = UDim.new(0, 12)}, hub)
    create("UIStroke", {Color = green, Thickness = 1.5}, hub)

    create("TextLabel", {
        Size = UDim2.new(1, 0, 0, 55),
        BackgroundTransparency = 1,
        Text = "Catus Hub",
        TextColor3 = green,
        TextSize = 26,
        Font = Enum.Font.GothamBold,
    }, hub)

    create("TextLabel", {
        Position = UDim2.fromOffset(20, 65),
        Size = UDim2.new(1, -40, 0, 60),
        BackgroundTransparency = 1,
        Text = "Welcome to Catus Hub!\nYour hub interface is ready.",
        TextColor3 = white,
        TextSize = 15,
        Font = Enum.Font.Gotham,
    }, hub)
end

submit.MouseButton1Click:Connect(unlockHub)

keyBox.FocusLost:Connect(function(enterPressed)
    if enterPressed then
        unlockHub()
    end
end)
