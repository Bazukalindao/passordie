-- By Bazuka_yt

if game.CoreGui:FindFirstChild("CheatPanel") then
    game.CoreGui:FindFirstChild("CheatPanel"):Destroy()
end

local function _10(_11, _12)
    local _13 = Instance.new("UICorner")
    _13.CornerRadius = UDim.new(0, _11)
    _13.Parent = _12
end

local _14 = Instance.new("ScreenGui")
_14.Name = "CheatPanel"
_14.Parent = game.CoreGui

local _15 = Instance.new("Frame")
_15.Size = UDim2.new(0, 175, 0, 200)
_15.Position = UDim2.new(0.5, 0, 0.5, 0)
_15.AnchorPoint = Vector2.new(0.5, 0.5)
_15.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
_15.BorderSizePixel = 1
_15.Active = true
_15.Draggable = true
_15.Parent = _14

local _16 = Instance.new("TextLabel")
_16.Size = UDim2.new(1, 0, 0, 40)
_16.BackgroundColor3 = Color3.fromRGB(125, 125, 125)
_16.BorderSizePixel = 1
_16.Text = "Bazuka Hub | Pass Or Die"
_16.TextSize = 15
_16.TextColor3 = Color3.new(1, 1, 1)
_16.Font = Enum.Font.Code
_16.Parent = _15

local _17 = Instance.new("TextLabel")
_17.Size = UDim2.new(1, 0, 0.5, 0)
_17.Position = UDim2.new(0, 0, 0.5, -50)
_17.BackgroundColor3 = Color3.fromRGB(150, 150, 150)
_17.BorderSizePixel = 1
_17.Text = "Wait Until The Bomb Spawns"
_17.TextScaled = true
_17.TextColor3 = Color3.new(1, 1, 1)
_17.Font = Enum.Font.Code
_17.Parent = _15

_10(20, _15)
_10(20, _16)
_10(30, _17)

workspace.Bombs.ChildAdded:Connect(function(_18)
    if _18:FindFirstChild("Highlight") then
        while _18.Parent do
            local _19 = _18:FindFirstChild("Highlight")
            if _19 then
                _17.Text = tostring(_19.FillTransparency)
                if _19.FillTransparency <= 0.51 then game:GetService("ReplicatedStorage"):WaitForChild("Rounds"):WaitForChild("Core"):WaitForChild("Default"):WaitForChild("Remotes"):WaitForChild("Pass"):InvokeServer("Forward")
                end
            end
            task.wait()
        end
    end
end)
