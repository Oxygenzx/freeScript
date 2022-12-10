if game.PlaceId ~=155615604  then
    game.Players.LocalPlayer:Kick("This script only works on Prison Life!")
end
if getgenv().thunt_gui_executed then
    game.Players.LocalPlayer:Kick("GUI executed twice!")
end
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Prison Life)", "DarkTheme")
local Tab = Window:NewTab("Teleport")
local Section = Tab:NewSection("Teleport")
Section:NewButton("ThivesBase", "ButtonInfo", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-943.724854, 94.1287613, 2063.70142, -0.0698518828, -2.87379844e-08, -0.997557402, 4.3286037e-09, 1, -2.91114546e-08, 0.997557402, -6.35152064e-09, -0.0698518828)
end)
Section:NewButton("GunbasePolice", "ButtonInfo", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(823.648193, 99.9899826, 2255.10132, -0.96689409, 7.94051971e-08, -0.255177945, 7.50873994e-08, 1, 2.66623221e-08, 0.255177945, 6.61899424e-09, -0.96689409)
end)
local Tab = Window:NewTab("Misc")
local Section = Tab:NewSection("Misc")
Section:NewButton("ESP", "ButtonInfo", function()
    while wait() do
        pcall(function()
          for i,v in pairs(game.Players:GetChildren()) do
               if not v.Character.Head:FindFirstChild("ESP") then
                   local BillboardGui = Instance.new("BillboardGui")
                   local TextLabel = Instance.new("TextLabel")
                   BillboardGui.Parent = v.Character.Head
                   BillboardGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
                   BillboardGui.Active = true
                   BillboardGui.Name = "ESP"
                   BillboardGui.AlwaysOnTop = true
                   BillboardGui.LightInfluence = 1.000
                   BillboardGui.Size = UDim2.new(0, 200, 0, 50)
                   BillboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
                   TextLabel.Parent = BillboardGui
                   TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.BackgroundTransparency = 1.000
                   TextLabel.Size = UDim2.new(0, 200, 0, 50)
                   TextLabel.Font = Enum.Font.GothamBold
                   TextLabel.Text = v.Name
                   TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.TextScaled = true
                   TextLabel.TextSize = 14.000
                   TextLabel.TextStrokeTransparency = 0.000
                   TextLabel.TextWrapped = true
               end
           end
       end) 
   end
end)
Section:NewSlider("Speed player", "SliderInfo", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
local Section = Tab:NewSection("Spawn item")
Section:NewButton("Keycard(notwork)", "ButtonInfo", function()
    workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.single["Key card"].ITEMPICKUP)
end)
Section:NewButton("Remington870(notwork)", "ButtonInfo", function()
    workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.single["Remington870"].ITEMPICKUP)
end)
Section:NewButton("AK-47(notwork)", "ButtonInfo", function()
    workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.single["AK-47"].ITEMPICKUP)
end)
local Section = Tab:NewSection("morescript")
Section:NewButton("infadmin", "ButtonInfo", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)
Section:NewButton("Aimbot", "ButtonInfo", function()
    getgenv().AimbotInput = "\82\105\103\104\116\67\108\105\99\107"  getgenv().AimbotEasing = 1 getgenv().TeamCheck = false if getgenv().AlreadyRanItBroDanger then return end getgenv().AlreadyRanItBroDanger = "\73\116\39\115\32\116\104\101\32\78\117\116\115\104\97\99\107" local c = game:GetService("\85\115\101\114\73\110\112\117\116\83\101\114\118\105\99\101") local r = game:GetService("\80\108\97\121\101\114\115") local h = game:GetService("\84\101\97\109\115") local n = r.LocalPlayer local d = n:GetMouse() local b = workspace.CurrentCamera workspace:GetPropertyChangedSignal("\67\117\114\114\101\110\116\67\97\109\101\114\97"):Connect(function() b = workspace.CurrentCamera end) local q = false function l(t, k) local p = b.CFrame.Position local j, onscreen = b:WorldToViewportPoint(t.Position) if onscreen then local o = Ray.new(p, t.Position - p) local s = workspace:FindPartOnRayWithIgnoreList(o, n.Character:GetDescendants()) local j = false if s and s:IsDescendantOf(k) then j = true else j = false end return j else return false end end function g() local l_, distance = nil, math.huge for i, v in pairs(r:GetPlayers()) do if v ~= n then pcall(function() local tl = true if getgenv().TeamCheck then if n.TeamColor == v.TeamColor then tl = false end end if (d.Hit.Position - v.Character.PrimaryPart.Position).magnitude < distance and tl then if l(v.Character.Head, v.Character) and v.Character.Humanoid.Health > 0 then l_ = v distance = (d.Hit.Position - v.Character.PrimaryPart.Position).magnitude end end end) end end return l_, distance end c.InputBegan:Connect(function(i, m) if not m then if getgenv().AimbotInput == "\76\101\102\116\67\108\105\99\107" and i.UserInputType == Enum.UserInputType.MouseButton1 then q = true elseif getgenv().AimbotInput == "\82\105\103\104\116\67\108\105\99\107" and i.UserInputType == Enum.UserInputType.MouseButton2 then q = true elseif i.KeyCode.Name == getgenv().AimbotInput then q = true end end end) c.InputEnded:Connect(function(i, m) if not m then if getgenv().AimbotInput == "\76\101\102\116\67\108\105\99\107" and i.UserInputType == Enum.UserInputType.MouseButton1 then q = false elseif getgenv().AimbotInput == "\82\105\103\104\116\67\108\105\99\107" and i.UserInputType == Enum.UserInputType.MouseButton2 then q = false elseif i.KeyCode.Name == getgenv().AimbotInput then q = false end end end) while task.wait() do if q then local kt = g() if kt then local gk = workspace.CurrentCamera.CFrame workspace.CurrentCamera.CFrame = gk:Lerp(CFrame.new(gk.Position, kt.Character.Head.Position), getgenv().AimbotEasing) end end end
end)
