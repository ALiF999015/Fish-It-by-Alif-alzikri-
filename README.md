local function createSplashScreen()
    local Players = game:GetService("Players")
    local player = Players.LocalPlayer
    local playerGui = player:WaitForChild("PlayerGui")
    
   
    local screenGui = Instance.new("ScreenGui")
    screenGui.Name = "SplashScreen"
    screenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    screenGui.ResetOnSpawn = false
    screenGui.Parent = playerGui
    
    
    local frame = Instance.new("Frame")
    frame.Size = UDim2.new(1, 0, 1, 0)
    frame.Position = UDim2.new(0, 0, 0, 0)
    frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    frame.BorderSizePixel = 0
    frame.Parent = screenGui
    
    
    local textLabel = Instance.new("TextLabel")
    textLabel.Size = UDim2.new(0.8, 0, 0.3, 0)
    textLabel.Position = UDim2.new(0.1, 0, 0.35, 0)
    textLabel.BackgroundTransparency = 1
    textLabel.Text = "Created by Alif alzikri"
    textLabel.TextColor3 = Color3.fromRGB(0, 255, 255)
    textLabel.Font = Enum.Font.GothamBold
    textLabel.TextScaled = true
    textLabel.TextTransparency = 1
    textLabel.Parent = frame
    
    
    local stroke = Instance.new("UIStroke")
    stroke.Color = Color3.fromRGB(255, 0, 255)
    stroke.Thickness = 3
    stroke.Transparency = 1
    stroke.Parent = textLabel
    
    
    local tweenService = game:GetService("TweenService")
    local fadeInInfo = TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
    local fadeInTween = tweenService:Create(textLabel, fadeInInfo, {TextTransparency = 0})
    local strokeFadeIn = tweenService:Create(stroke, fadeInInfo, {Transparency = 0})
    
    fadeInTween:Play()
    strokeFadeIn:Play()
    
    
    wait(1.5)
    
    -- Animasi fade out
    local fadeOutInfo = TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.In)
    local fadeOutTween = tweenService:Create(textLabel, fadeOutInfo, {TextTransparency = 1})
    local strokeFadeOut = tweenService:Create(stroke, fadeOutInfo, {Transparency = 1})
    local frameFadeOut = tweenService:Create(frame, fadeOutInfo, {BackgroundTransparency = 1})
    
    fadeOutTween:Play()
    strokeFadeOut:Play()
    frameFadeOut:Play()
    
    -- Hapus GUI setelah animasi selesai
    wait(0.5)
    screenGui:Destroy()
end


createSplashScreen()


wait(2)


loadstring(game:HttpGet("https://raw.githubusercontent.com/arcadeisreal/717exe---Fish-It/refs/heads/main/loader.lua"))()
