--[[
    🔴 ITACHI HUB - UNIVERSAL EXECUTOR
    CodeX + Krnl + Fluxus + Delta + Solara + All
    Version 9.0.0 FINAL
]]

local s, e = pcall(function()

local function VP()
    local v = {2753915549, 4442272183, 7449423635, 4520749081, 6381829480, 15759515082, 5931540094}
    for _, i in ipairs(v) do if game.PlaceId == i then return true end end
    return false
end
if not VP() then return end

local function WDL()
    local st = tick()
    local dl = false
    repeat
        task.wait(0.3)
        if tick() - st > 60 then return false end
        pcall(function()
            if game.Players.LocalPlayer and game.Players.LocalPlayer:FindFirstChild("DataLoaded") and game.Players.LocalPlayer:FindFirstChild("DataLoaded").Value then
                dl = true
            end
        end)
    until dl
    return true
end
if not WDL() then return end

local P = game:GetService("Players")
local RS = game:GetService("RunService")
local UIS = game:GetService("UserInputService")
local TS = game:GetService("TweenService")
local TPS = game:GetService("TeleportService")
local HS = game:GetService("HttpService")
local L = game:GetService("Lighting")
local LP = P.LocalPlayer
local VIM = game:GetService("VirtualInputManager")
local VU = game:GetService("VirtualUser")

local TH = {
    P = Color3.fromRGB(255,0,0), S = Color3.fromRGB(180,0,0), A = Color3.fromRGB(255,50,50),
    B = Color3.fromRGB(10,10,10), SF = Color3.fromRGB(20,20,20), SL = Color3.fromRGB(30,30,30),
    T = Color3.fromRGB(255,255,255), TD = Color3.fromRGB(150,150,150), SC = Color3.fromRGB(0,255,100)
}

local CF = {
    AutoFarm=false,AutoQuest=false,FastAttack=false,AutoBoss=false,
    AutoStats=false,AutoEquipBestSword=false,AutoCollectFruits=false,
    AutoStoreFruits=false,KillAura=false,NoStun=false,BringMobs=false,
    AutoFindFruit=false,FruitSniper=false,AutoSpinFruit=false,
    AutoTeleportFruit=false,AutoDropBadFruits=false,AutoBuyFruitsFromDealer=false,
    AutoStoreInInventory=false,AutoEatFruit=false,AutoBuyRandomFruit=false,
    AutoFarmCDK=false,AutoFarmTushita=false,AutoFarmYama=false,
    AutoFarmKatakuri=false,AutoFarmDarkBlade=false,AutoFarmTrueTripleKatana=false,
    AutoFarmRengoku=false,AutoFarmSaber=false,AutoFarmSoulCane=false,
    AutoGetLegendarySword=false,AutoBuyAllSwords=false,
    AutoDarkBeard=false,AutoOrder=false,AutoDoughKing=false,
    AutoSoulReaper=false,AutoCakePrince=false,AutoBeautifulPirate=false,
    AutoLongma=false,AutoGreybeard=false,AutoRipIndra=false,
    AutoThunderGod=false,AutoTideKeeper=false,AutoDoughPrince=false,
    AutoBossHop=false,AutoLeaveAfterKill=false,
    AutoStartRaid=false,AutoAwaken=false,AutoBuyChip=false,AutoCompleteRaid=false,
    AutoBuyAllHaki=false,AutoBuyAllAbilities=false,AutoBuyAllFightingStyles=false,
    AutoBuyElectricClaw=false,AutoBuySuperhuman=false,AutoBuyDeathStep=false,
    AutoBuySharkmanKarate=false,AutoBuyDragonTalon=false,AutoBuyGodHuman=false,
    AutoBuyBlackLeg=false,AutoBuyElectro=false,AutoBuyFishmanKarate=false,
    AutoBuyDragonBreath=false,AutoBuyWaterKungFu=false,
    AutoBuyRaceV2=false,AutoBuyRaceV3=false,AutoBuyRaceV4=false,
    AutoBuyAllFightingStyleUpgrades=false,AutoBuyAllSwordUpgrades=false,
    AutoBuyChipFragments=false,AutoBuyFruitNotifierFrag=false,
    AutoBuyInstinctV2=false,AutoBuyObservationV2=false,
    AutoBuyAllAccessories=false,AutoBuyMeleeItems=false,
    AutoBuySwordItems=false,AutoBuyGunItems=false,AutoBuyAccessoryItems=false,
    AutoBuyHaki=false,AutoBuyGeppo=false,AutoBuySoru=false,
    AutoBuyKen=false,AutoBuyBuso=false,AutoSellItems=false,AutoBuyChests=false,
    AutoFarmMastery=false,AutoSwitchWeapon=false,TargetMasteryLevel=600,
    AutoTPToQuest=false,AutoTPToBoss=false,AutoTPToFruit=false,
    TpToSeaBeast=false,TpToFruitSpawn=false,TpToChest=false,
    TpToShop=false,TpToAllNPCs=false,
    AutoSeaBeast=false,AutoShipRaid=false,AutoKraken=false,
    AutoFactory=false,AutoPirateRaid=false,AutoCastleRaid=false,
    AutoRumblingWaters=false,AutoGhostShip=false,AutoMirageIsland=false,
    AutoFactoryEvent=false,AutoCollectMaterial=false,AutoCraftItem=false,
    AutoClick=false,CPS=10,FastClick=false,
    AutoHaki=false,AutoBusoHaki=false,AutoKenHaki=false,
    AutoEquipWeapon=false,AutoSuperJump=false,AutoDash=false,
    AutoBlock=false,AutoDodge=false,HitboxExtender=false,
    AutoSkills=false,AutoUltimate=false,
    AutoDistributeStats=false,PointsPerStat=3,
    ESP=false,ESPPlayers=false,ESPFruits=false,ESPChests=false,ESPNPCs=false,
    ESPSeaBeasts=false,ESPIslands=false,ESPItems=false,
    FullBright=false,NoClip=false,RemoveFog=false,Tracer=false,Chams=false,
    AimFOV=200,ShowFOV=false,Aimbot=false,AimAssist=false,
    AllyCheck=false,TeamCheck=false,AutoBounty=false,SafeZone=false,
    CombatLog=false,AutoRunFromBounty=false,
    WalkSpeed=16,JumpPower=50,InfiniteJump=false,Fly=false,FlySpeed=50,
    GodMode=false,NoFallDamage=false,SuperSpeed=false,
    AutoRespawn=false,AntiStun=false,AntiGrab=false,AntiKnockback=false,
    AutoEvolveRace=false,AutoBuyRaceReroll=false,
    AutoV2=false,AutoV3=false,AutoV4=false,AutoUnlockAllRaces=false,
    AutoTalkNPC=false,AutoCompleteQuest=false,AutoTurnInQuest=false,SkipQuestDialog=false,
    NotifyOnFruitSpawn=false,NotifyOnBossSpawn=false,
    NotifyOnSeaBeast=false,NotifyOnRaidStart=false,NotifyOnItemSpawn=false,
    AntiAFK=false,FPSBoost=false,RemoveTerrain=false,AutoRedeemCodes=false,
    AutoOpenChests=false,AutoCollectGems=false,AutoCollectBeli=false,
    AutoUpgradeWeapon=false,AutoCollectAll=false,
    SafeMode=true,AutoLeaveOnAdmin=false,HideCharacter=false,
    AntiTPBack=false,AutoResetOnBan=false,AutoLeaveOnKill=false,AntiReport=false
}

local function SC()
    pcall(function()
        if writefile and isfolder and makefolder then
            if not isfolder("IH") then makefolder("IH") end
            writefile("IH/cfg.json", HS:JSONEncode(CF))
        end
    end)
end

local function LC()
    pcall(function()
        if readfile and isfile and isfile("IH/cfg.json") then
            local l = HS:JSONDecode(readfile("IH/cfg.json"))
            for k, v in pairs(l) do if CF[k] ~= nil then CF[k] = v end end
        end
    end)
end

local function GW()
    local i = game.PlaceId
    if i == 2753915549 or i == 4442272183 or i == 7449423635 then return "First"
    elseif i == 4520749081 or i == 6381829480 then return "Second"
    elseif i == 15759515082 or i == 5931540094 then return "Third" end
    return "?"
end

local function GCS()
    if not LP then return nil end
    local c = LP.Character
    if not c or not c:FindFirstChild("HumanoidRootPart") then return nil end
    local h = c:FindFirstChildOfClass("Humanoid")
    if not h or h.Health <= 0 then return nil end
    return c
end

local function GNE(r)
    local c = GCS()
    if not c then return nil end
    local n, nd = nil, r or 300
    for _, v in ipairs(workspace.Enemies:GetChildren()) do
        if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and v:FindFirstChild("HumanoidRootPart") then
            local d = (c.HumanoidRootPart.Position - v.HumanoidRootPart.Position).Magnitude
            if d < nd then nd = d; n = v end
        end
    end
    return n
end

local function GB()
    local b = {}
    for _, v in ipairs(workspace.Enemies:GetChildren()) do
        if v:FindFirstChild("Humanoid") and v.Humanoid.MaxHealth > 10000 and v.Humanoid.Health > 0 and v:FindFirstChild("HumanoidRootPart") then
            table.insert(b, v)
        end
    end
    return b
end

local function GP()
    local pl = {}
    for _, p in ipairs(P:GetPlayers()) do
        if p ~= LP and p.Character and p.Character:FindFirstChild("HumanoidRootPart") then
            table.insert(pl, p)
        end
    end
    return pl
end

local function GF()
    local f = {}
    for _, v in ipairs(workspace:GetDescendants()) do
        if v:IsA("Tool") and v.Name:find("Fruit") then table.insert(f, v) end
    end
    return f
end

local function GC()
    local ch = {}
    for _, v in ipairs(workspace:GetDescendants()) do
        if v.Name:find("Chest") and v:IsA("BasePart") then table.insert(ch, v) end
    end
    return ch
end

local function EBS()
    if not LP.Backpack then return end
    local best, bd = nil, 0
    for _, t in ipairs(LP.Backpack:GetChildren()) do
        if t:IsA("Tool") and t:FindFirstChild("Damage") and t.Damage.Value > bd then
            bd = t.Damage.Value; best = t
        end
    end
    if best and LP.Character then LP.Character.Humanoid:EquipTool(best) end
end

local LA = 0
local MAD = 0.15

local function RN(mn, mx)
    return mn + (math.random() * (mx - mn))
end

local function AD()
    local e = tick() - LA
    if e < MAD then task.wait(MAD - e + RN(0.01, 0.05)) end
    LA = tick()
end

local function STP(pos)
    pcall(function()
        if LP.Character and LP.Character:FindFirstChild("HumanoidRootPart") then
            local o = Vector3.new(RN(-2,2), RN(1,4), RN(-2,2))
            LP.Character.HumanoidRootPart.CFrame = CFrame.new(pos + o)
        end
    end)
end

local function SCL()
    pcall(function()
        AD()
        VIM:SendMouseButtonEvent(0,0,0,true,game,1)
        task.wait(RN(0.02,0.06))
        VIM:SendMouseButtonEvent(0,0,0,false,game,1)
    end)
end

local function CG()
    local SG = Instance.new("ScreenGui", game.CoreGui)
    SG.Name = "IH_Universal"

    local IC = Instance.new("TextButton", SG)
    IC.Size = UDim2.new(0,55,0,55); IC.Position = UDim2.new(0,15,0.5,-27)
    IC.BackgroundColor3 = TH.P; IC.BackgroundTransparency = 0.3
    IC.Text = "🔴"; IC.TextSize = 30; IC.Font = Enum.Font.GothamBold
    IC.BorderSizePixel = 0
    Instance.new("UICorner", IC).CornerRadius = UDim.new(1,0)
    local istr = Instance.new("UIStroke", IC)
    istr.Color = Color3.fromRGB(255,255,255); istr.Thickness = 2

    local MF = Instance.new("Frame", SG)
    MF.Size = UDim2.new(0,680,0,460); MF.Position = UDim2.new(0.5,-340,0.5,-230)
    MF.BackgroundColor3 = TH.B; MF.BackgroundTransparency = 0.1
    MF.BorderSizePixel = 0; MF.ClipsDescendants = true; MF.Visible = false
    Instance.new("UICorner", MF).CornerRadius = UDim.new(0,12)
    local mstr = Instance.new("UIStroke", MF)
    mstr.Color = TH.P; mstr.Thickness = 2

    local uv = false
    IC.MouseButton1Click:Connect(function()
        uv = not uv; MF.Visible = uv; IC.Text = uv and "✕" or "🔴"
    end)

    local TB = Instance.new("Frame", MF)
    TB.Size = UDim2.new(1,0,0,40); TB.BackgroundColor3 = TH.SF
    TB.BackgroundTransparency = 0.3; TB.BorderSizePixel = 0
    Instance.new("UICorner", TB).CornerRadius = UDim.new(0,12)
    
    local TL = Instance.new("TextLabel", TB)
    TL.Size = UDim2.new(0,450,1,0); TL.Position = UDim2.new(0,15,0,0)
    TL.BackgroundTransparency = 1
    TL.Text = "🔴 ITACHI HUB | " .. GW() .. " Sea | v9.0"
    TL.TextColor3 = TH.P; TL.TextSize = 15; TL.Font = Enum.Font.GothamBold
    TL.TextXAlignment = Enum.TextXAlignment.Left

    local ST = Instance.new("TextLabel", TB)
    ST.Size = UDim2.new(0,100,1,0); ST.Position = UDim2.new(1,-115,0,0)
    ST.BackgroundTransparency = 1; ST.Text = "🛡️ SAFE"
    ST.TextColor3 = TH.SC; ST.TextSize = 11; ST.Font = Enum.Font.GothamBold
    ST.TextXAlignment = Enum.TextXAlignment.Right

    local TC = Instance.new("Frame", MF)
    TC.Size = UDim2.new(0,155,1,-50); TC.Position = UDim2.new(0,0,0,50)
    TC.BackgroundColor3 = TH.SF; TC.BackgroundTransparency = 0.5; TC.BorderSizePixel = 0
    
    local CFr = Instance.new("Frame", MF)
    CFr.Size = UDim2.new(1,-165,1,-60); CFr.Position = UDim2.new(0,160,0,55)
    CFr.BackgroundTransparency = 1; CFr.ClipsDescendants = true

    local tabs = {
        "Farm","Bosses","Swords","Fruits","AutoBuy","Shop",
        "Raid","Mastery","Teleport","Sea","Factory",
        "Combat","Stats","Visual","PvP","Player",
        "Race","Quest","Notif","Security","Misc"
    }
    local tbs = {}
    local tcs = {}

    for i, tn in ipairs(tabs) do
        local tb = Instance.new("TextButton", TC)
        tb.Size = UDim2.new(1,-8,0,26); tb.Position = UDim2.new(0,4,0,3+(i-1)*29)
        tb.BackgroundColor3 = TH.SL; tb.BackgroundTransparency = 0.7
        tb.Text = tn; tb.TextColor3 = TH.TD; tb.TextSize = 10
        tb.Font = Enum.Font.GothamBold; tb.BorderSizePixel = 0
        Instance.new("UICorner", tb).CornerRadius = UDim.new(0,5)
        tbs[tn] = tb
        
        local tc = Instance.new("ScrollingFrame", CFr)
        tc.Size = UDim2.new(1,-10,1,-10); tc.Position = UDim2.new(0,5,0,5)
        tc.BackgroundTransparency = 1; tc.BorderSizePixel = 0
        tc.ScrollBarThickness = 4; tc.ScrollBarImageColor3 = TH.P
        tc.Visible = (i == 1); tc.CanvasSize = UDim2.new(0,0,0,0)
        tcs[tn] = tc
        
        tb.MouseButton1Click:Connect(function()
            for _, b in pairs(tbs) do b.BackgroundColor3 = TH.SL; b.BackgroundTransparency = 0.7; b.TextColor3 = TH.TD end
            tb.BackgroundColor3 = TH.P; tb.BackgroundTransparency = 0.3; tb.TextColor3 = TH.T
            for _, c in pairs(tcs) do c.Visible = false end
            tc.Visible = true
        end)
    end
    tbs["Farm"].BackgroundColor3 = TH.P; tbs["Farm"].BackgroundTransparency = 0.3; tbs["Farm"].TextColor3 = TH.T

    local function CT(n, p, y)
        local fr = Instance.new("Frame", p)
        fr.Size = UDim2.new(1,-10,0,30); fr.Position = UDim2.new(0,5,0,y)
        fr.BackgroundColor3 = TH.SF; fr.BackgroundTransparency = 0.5; fr.BorderSizePixel = 0
        Instance.new("UICorner", fr).CornerRadius = UDim.new(0,5)
        
        local lb = Instance.new("TextLabel", fr)
        lb.Size = UDim2.new(0.7,0,1,0); lb.Position = UDim2.new(0,6,0,0)
        lb.BackgroundTransparency = 1; lb.Text = n; lb.TextColor3 = TH.T
        lb.TextSize = 10; lb.Font = Enum.Font.Gotham; lb.TextXAlignment = Enum.TextXAlignment.Left
        
        local btn = Instance.new("TextButton", fr)
        btn.Size = UDim2.new(0,34,0,18); btn.Position = UDim2.new(1,-40,0.5,-9)
        btn.BackgroundColor3 = CF[n] and TH.P or TH.SL
        btn.Text = ""; btn.BorderSizePixel = 0; btn.AutoButtonColor = false
        Instance.new("UICorner", btn).CornerRadius = UDim.new(1,0)
        
        local ind = Instance.new("Frame", btn)
        ind.Size = UDim2.new(0,14,0,14)
        ind.Position = CF[n] and UDim2.new(1,-16,0.5,-7) or UDim2.new(0,2,0.5,-7)
        ind.BackgroundColor3 = Color3.fromRGB(255,255,255); ind.BorderSizePixel = 0
        Instance.new("UICorner", ind).CornerRadius = UDim.new(1,0)
        
        btn.MouseButton1Click:Connect(function()
            CF[n] = not CF[n]
            if CF[n] then
                btn.BackgroundColor3 = TH.P
                ind:TweenPosition(UDim2.new(1,-16,0.5,-7), "Out", "Quad", 0.15)
            else
                btn.BackgroundColor3 = TH.SL
                ind:TweenPosition(UDim2.new(0,2,0.5,-7), "Out", "Quad", 0.15)
            end
        end)
    end

    local function CS(n, mi, ma, p, y)
        local fr = Instance.new("Frame", p)
        fr.Size = UDim2.new(1,-10,0,44); fr.Position = UDim2.new(0,5,0,y)
        fr.BackgroundColor3 = TH.SF; fr.BackgroundTransparency = 0.5; fr.BorderSizePixel = 0
        Instance.new("UICorner", fr).CornerRadius = UDim.new(0,5)
        
        local lb = Instance.new("TextLabel", fr)
        lb.Size = UDim2.new(1,-20,0,14); lb.Position = UDim2.new(0,6,0,2)
        lb.BackgroundTransparency = 1; lb.Text = n .. ": " .. CF[n]
        lb.TextColor3 = TH.T; lb.TextSize = 9; lb.Font = Enum.Font.Gotham
        lb.TextXAlignment = Enum.TextXAlignment.Left
        
        local br = Instance.new("Frame", fr)
        br.Size = UDim2.new(1,-30,0,3); br.Position = UDim2.new(0,15,0,24)
        br.BackgroundColor3 = TH.SL; br.BorderSizePixel = 0
        
        local fl = Instance.new("Frame", br)
        fl.Size = UDim2.new((CF[n]-mi)/(ma-mi),0,1,0)
        fl.BackgroundColor3 = TH.P; fl.BorderSizePixel = 0
        
        local btb = Instance.new("TextButton", br)
        btb.Size = UDim2.new(0,11,0,11)
        btb.Position = UDim2.new((CF[n]-mi)/(ma-mi),-5.5,0,-4)
        btb.BackgroundColor3 = TH.P; btb.Text = ""; btb.BorderSizePixel = 0; btb.AutoButtonColor = false
        Instance.new("UICorner", btb).CornerRadius = UDim.new(1,0)
        
        local dc
        btb.MouseButton1Down:Connect(function()
            dc = RS.RenderStepped:Connect(function()
                if br.AbsoluteSize.X <= 0 then return end
                local pc = math.clamp((UIS:GetMouseLocation().X - br.AbsolutePosition.X) / br.AbsoluteSize.X, 0, 1)
                local vl = math.round(mi + (ma - mi) * pc)
                CF[n] = vl
                fl.Size = UDim2.new(pc,0,1,0)
                btb.Position = UDim2.new(pc,-5.5,0,-4)
                lb.Text = n .. ": " .. vl
            end)
        end)
        UIS.InputEnded:Connect(function(i)
            if i.UserInputType == Enum.UserInputType.MouseButton1 and dc then dc:Disconnect(); dc = nil end
        end)
    end

    local function PT(tn, items)
        local y = 0
        for _, it in ipairs(items) do
            if it.t == "toggle" then CT(it.n, tcs[tn], y); y = y + 33
            elseif it.t == "slider" then CS(it.n, it.mi, it.ma, tcs[tn], y); y = y + 47 end
        end
        tcs[tn].CanvasSize = UDim2.new(0,0,0,y+25)
    end

    PT("Farm", {
        {t="toggle",n="AutoFarm"},{t="toggle",n="AutoQuest"},{t="toggle",n="FastAttack"},
        {t="toggle",n="AutoBoss"},{t="toggle",n="AutoStats"},{t="toggle",n="AutoEquipBestSword"},
        {t="toggle",n="BringMobs"},{t="toggle",n="KillAura"},{t="toggle",n="NoStun"},
        {t="toggle",n="AutoCollectAll"}
    })
    PT("Bosses", {
        {t="toggle",n="AutoDarkBeard"},{t="toggle",n="AutoOrder"},{t="toggle",n="AutoDoughKing"},
        {t="toggle",n="AutoSoulReaper"},{t="toggle",n="AutoCakePrince"},{t="toggle",n="AutoBeautifulPirate"},
        {t="toggle",n="AutoLongma"},{t="toggle",n="AutoGreybeard"},{t="toggle",n="AutoRipIndra"},
        {t="toggle",n="AutoThunderGod"},{t="toggle",n="AutoTideKeeper"},{t="toggle",n="AutoDoughPrince"},
        {t="toggle",n="AutoBossHop"},{t="toggle",n="AutoLeaveAfterKill"}
    })
    PT("Swords", {
        {t="toggle",n="AutoFarmCDK"},{t="toggle",n="AutoFarmTushita"},{t="toggle",n="AutoFarmYama"},
        {t="toggle",n="AutoFarmKatakuri"},{t="toggle",n="AutoFarmDarkBlade"},{t="toggle",n="AutoFarmTrueTripleKatana"},
        {t="toggle",n="AutoFarmRengoku"},{t="toggle",n="AutoFarmSaber"},{t="toggle",n="AutoFarmSoulCane"},
        {t="toggle",n="AutoGetLegendarySword"},{t="toggle",n="AutoBuyAllSwords"}
    })
    PT("Fruits", {
        {t="toggle",n="AutoFindFruit"},{t="toggle",n="FruitSniper"},{t="toggle",n="AutoSpinFruit"},
        {t="toggle",n="AutoCollectFruits"},{t="toggle",n="AutoStoreFruits"},{t="toggle",n="AutoTeleportFruit"},
        {t="toggle",n="AutoStoreInInventory"},{t="toggle",n="AutoDropBadFruits"},
        {t="toggle",n="AutoBuyFruitsFromDealer"},{t="toggle",n="AutoEatFruit"},{t="toggle",n="AutoBuyRandomFruit"}
    })
    PT("AutoBuy", {
        {t="toggle",n="AutoBuyAllHaki"},{t="toggle",n="AutoBuyAllAbilities"},{t="toggle",n="AutoBuyAllFightingStyles"},
        {t="toggle",n="AutoBuyElectricClaw"},{t="toggle",n="AutoBuySuperhuman"},{t="toggle",n="AutoBuyDeathStep"},
        {t="toggle",n="AutoBuySharkmanKarate"},{t="toggle",n="AutoBuyDragonTalon"},{t="toggle",n="AutoBuyGodHuman"},
        {t="toggle",n="AutoBuyRaceV2"},{t="toggle",n="AutoBuyRaceV3"},{t="toggle",n="AutoBuyRaceV4"},
        {t="toggle",n="AutoBuyInstinctV2"},{t="toggle",n="AutoBuyObservationV2"},
        {t="toggle",n="AutoBuyMeleeItems"},{t="toggle",n="AutoBuySwordItems"}
    })
    PT("Shop", {
        {t="toggle",n="AutoBuyHaki"},{t="toggle",n="AutoBuyGeppo"},{t="toggle",n="AutoBuySoru"},
        {t="toggle",n="AutoBuyKen"},{t="toggle",n="AutoBuyBuso"},{t="toggle",n="AutoSellItems"},{t="toggle",n="AutoBuyChests"}
    })
    PT("Raid", {
        {t="toggle",n="AutoStartRaid"},{t="toggle",n="AutoAwaken"},{t="toggle",n="AutoBuyChip"},{t="toggle",n="AutoCompleteRaid"}
    })
    PT("Mastery", {
        {t="toggle",n="AutoFarmMastery"},{t="toggle",n="AutoSwitchWeapon"},
        {t="slider",n="TargetMasteryLevel",mi=1,ma=600}
    })
    PT("Teleport", {
        {t="toggle",n="AutoTPToQuest"},{t="toggle",n="AutoTPToBoss"},{t="toggle",n="AutoTPToFruit"},
        {t="toggle",n="TpToSeaBeast"},{t="toggle",n="TpToFruitSpawn"},{t="toggle",n="TpToChest"},
        {t="toggle",n="TpToShop"},{t="toggle",n="TpToAllNPCs"}
    })
    PT("Sea", {
        {t="toggle",n="AutoSeaBeast"},{t="toggle",n="AutoShipRaid"},{t="toggle",n="AutoKraken"},
        {t="toggle",n="AutoFactory"},{t="toggle",n="AutoPirateRaid"},{t="toggle",n="AutoCastleRaid"},
        {t="toggle",n="AutoRumblingWaters"},{t="toggle",n="AutoGhostShip"},{t="toggle",n="AutoMirageIsland"}
    })
    PT("Factory", {
        {t="toggle",n="AutoFactoryEvent"},{t="toggle",n="AutoCollectMaterial"},{t="toggle",n="AutoCraftItem"}
    })
    PT("Combat", {
        {t="toggle",n="AutoClick"},{t="slider",n="CPS",mi=1,ma=20},{t="toggle",n="FastClick"},
        {t="toggle",n="AutoHaki"},{t="toggle",n="AutoBusoHaki"},{t="toggle",n="AutoKenHaki"},
        {t="toggle",n="AutoEquipWeapon"},{t="toggle",n="AutoSuperJump"},{t="toggle",n="AutoDash"},
        {t="toggle",n="AutoBlock"},{t="toggle",n="AutoDodge"},{t="toggle",n="HitboxExtender"},
        {t="toggle",n="AutoSkills"},{t="toggle",n="AutoUltimate"}
    })
    PT("Stats", {
        {t="toggle",n="AutoDistributeStats"},{t="slider",n="PointsPerStat",mi=1,ma=10}
    })
    PT("Visual", {
        {t="toggle",n="ESP"},{t="toggle",n="ESPPlayers"},{t="toggle",n="ESPFruits"},
        {t="toggle",n="ESPChests"},{t="toggle",n="ESPNPCs"},{t="toggle",n="ESPSeaBeasts"},
        {t="toggle",n="FullBright"},{t="toggle",n="NoClip"},{t="toggle",n="RemoveFog"},
        {t="toggle",n="Tracer"},{t="toggle",n="Chams"}
    })
    PT("PvP", {
        {t="slider",n="AimFOV",mi=50,ma=500},{t="toggle",n="ShowFOV"},{t="toggle",n="Aimbot"},
        {t="toggle",n="AimAssist"},{t="toggle",n="AllyCheck"},{t="toggle",n="TeamCheck"},
        {t="toggle",n="AutoBounty"},{t="toggle",n="SafeZone"},{t="toggle",n="CombatLog"},{t="toggle",n="AutoRunFromBounty"}
    })
    PT("Player", {
        {t="slider",n="WalkSpeed",mi=16,ma=300},{t="slider",n="JumpPower",mi=50,ma=300},
        {t="toggle",n="InfiniteJump"},{t="toggle",n="Fly"},{t="slider",n="FlySpeed",mi=10,ma=200},
        {t="toggle",n="GodMode"},{t="toggle",n="NoFallDamage"},{t="toggle",n="SuperSpeed"},
        {t="toggle",n="AutoRespawn"},{t="toggle",n="AntiStun"},{t="toggle",n="AntiGrab"},{t="toggle",n="AntiKnockback"}
    })
    PT("Race", {
        {t="toggle",n="AutoEvolveRace"},{t="toggle",n="AutoBuyRaceReroll"},
        {t="toggle",n="AutoV2"},{t="toggle",n="AutoV3"},{t="toggle",n="AutoV4"},{t="toggle",n="AutoUnlockAllRaces"}
    })
    PT("Quest", {
        {t="toggle",n="AutoTalkNPC"},{t="toggle",n="AutoCompleteQuest"},{t="toggle",n="AutoTurnInQuest"},{t="toggle",n="SkipQuestDialog"}
    })
    PT("Notif", {
        {t="toggle",n="NotifyOnFruitSpawn"},{t="toggle",n="NotifyOnBossSpawn"},
        {t="toggle",n="NotifyOnSeaBeast"},{t="toggle",n="NotifyOnRaidStart"},{t="toggle",n="NotifyOnItemSpawn"}
    })
    PT("Security", {
        {t="toggle",n="SafeMode"},{t="toggle",n="AutoLeaveOnAdmin"},{t="toggle",n="HideCharacter"},
        {t="toggle",n="AntiTPBack"},{t="toggle",n="AutoResetOnBan"},
        {t="toggle",n="AutoLeaveOnKill"},{t="toggle",n="AntiReport"}
    })

    local my = 0
    CT("AntiAFK", tcs["Misc"], my); my = my + 33
    CT("FPSBoost", tcs["Misc"], my); my = my + 33
    CT("RemoveTerrain", tcs["Misc"], my); my = my + 33
    CT("AutoRedeemCodes", tcs["Misc"], my); my = my + 33
    CT("AutoOpenChests", tcs["Misc"], my); my = my + 33
    CT("AutoCollectGems", tcs["Misc"], my); my = my + 33
    CT("AutoCollectBeli", tcs["Misc"], my); my = my + 33
    CT("AutoUpgradeWeapon", tcs["Misc"], my); my = my + 33
    CT("AutoCollectAll", tcs["Misc"], my); my = my + 33
    
    local rjb = Instance.new("TextButton", tcs["Misc"])
    rjb.Size = UDim2.new(1,-10,0,26); rjb.Position = UDim2.new(0,5,0,my)
    rjb.BackgroundColor3 = TH.P; rjb.BackgroundTransparency = 0.3
    rjb.Text = "REJOIN"; rjb.TextColor3 = TH.T; rjb.TextSize = 10
    rjb.Font = Enum.Font.GothamBold; rjb.BorderSizePixel = 0
    Instance.new("UICorner", rjb).CornerRadius = UDim.new(0,5)
    rjb.MouseButton1Click:Connect(function() TPS:Teleport(game.PlaceId) end)
    my = my + 33
    
    local svb = Instance.new("TextButton", tcs["Misc"])
    svb.Size = UDim2.new(1,-10,0,26); svb.Position = UDim2.new(0,5,0,my)
    svb.BackgroundColor3 = TH.SC; svb.BackgroundTransparency = 0.5
    svb.Text = "SAVE"; svb.TextColor3 = TH.T; svb.TextSize = 10
    svb.Font = Enum.Font.GothamBold; svb.BorderSizePixel = 0
    Instance.new("UICorner", svb).CornerRadius = UDim.new(0,5)
    svb.MouseButton1Click:Connect(function() SC(); svb.Text = "OK!"; task.delay(2, function() svb.Text = "SAVE" end) end)
    my = my + 35
    tcs["Misc"].CanvasSize = UDim2.new(0,0,0,my+25)

    local dr, di, ds, sp
    TB.InputBegan:Connect(function(i)
        if i.UserInputType == Enum.UserInputType.MouseButton1 then
            dr = true; ds = i.Position; sp = MF.Position
        end
    end)
    TB.InputEnded:Connect(function(i)
        if i.UserInputType == Enum.UserInputType.MouseButton1 then dr = false end
    end)
    UIS.InputChanged:Connect(function(i)
        if i.UserInputType == Enum.UserInputType.MouseMovement then di = i end
    end)
    RS.RenderStepped:Connect(function()
        if dr and di then
            local d = di.Position - ds
            MF.Position = UDim2.new(sp.X.Scale, sp.X.Offset + d.X, sp.Y.Scale, sp.Y.Offset + d.Y)
        end
    end)

    local FOV = Instance.new("Frame", SG)
    FOV.Size = UDim2.new(0,CF.AimFOV,0,CF.AimFOV)
    FOV.Position = UDim2.new(0.5,-CF.AimFOV/2,0.5,-CF.AimFOV/2)
    FOV.BackgroundTransparency = 1; FOV.Visible = CF.ShowFOV
    local fstr = Instance.new("UIStroke", FOV)
    fstr.Color = TH.P; fstr.Thickness = 2
    Instance.new("UICorner", FOV).CornerRadius = UDim.new(1,0)
    RS.RenderStepped:Connect(function()
        FOV.Visible = CF.ShowFOV
        FOV.Size = UDim2.new(0,CF.AimFOV,0,CF.AimFOV)
        FOV.Position = UDim2.new(0.5,-CF.AimFOV/2,0.5,-CF.AimFOV/2)
    end)

    return SG
end

local SG = CG()
LC()

-- ============ SYSTEMS ============
RS.Heartbeat:Connect(function()
    if CF.AutoFarm then
        pcall(function()
            local c = GCS()
            if not c then return end
            local e = GNE(CF.BringMobs and 500 or 300)
            if e then
                STP(e.HumanoidRootPart.Position)
                if CF.FastAttack then SCL() end
                SCL()
            end
        end)
    end
    
    if CF.AutoBoss then
        pcall(function()
            local c = GCS()
            if not c then return end
            local b = GB()
            if #b > 0 then
                STP(b[1].HumanoidRootPart.Position + Vector3.new(0,10,0))
                for _ = 1, 3 do SCL() end
            end
        end)
    end
    
    if CF.KillAura then
        pcall(function()
            local c = GCS()
            if not c then return end
            for _, e in ipairs(workspace.Enemies:GetChildren()) do
                if e:FindFirstChild("Humanoid") and e.Humanoid.Health > 0 and e:FindFirstChild("HumanoidRootPart") then
                    if (c.HumanoidRootPart.Position - e.HumanoidRootPart.Position).Magnitude < 50 then
                        AD()
                        e.Humanoid.Health = 0
                    end
                end
            end
        end)
    end
    
    pcall(function()
        local c = GCS()
        if not c then return end
        local h = c:FindFirstChildOfClass("Humanoid")
        if h then
            h.WalkSpeed = CF.SafeMode and math.min(CF.WalkSpeed, 200) or CF.WalkSpeed
            h.JumpPower = CF.SafeMode and math.min(CF.JumpPower, 200) or CF.JumpPower
            if CF.InfiniteJump then h.Jump = true end
            if CF.Fly and CF.FlySpeed <= 100 then
                h.PlatformStand = true
                c.HumanoidRootPart.CFrame = c.HumanoidRootPart.CFrame + Vector3.new(0, RN(0.3,0.7), 0)
            end
            if CF.NoFallDamage then h.FallSpeed = 0 end
        end
    end)
    
    if CF.GodMode then
        pcall(function()
            local c = GCS()
            if c then
                local h = c:FindFirstChildOfClass("Humanoid")
                if h then h.Health = h.MaxHealth end
            end
        end)
    end
    
    if CF.AntiAFK then
        pcall(function()
            VU:CaptureController()
            VU:ClickButton2(Vector2.new())
        end)
    end
    
    if CF.FullBright then
        pcall(function()
            L.Brightness = 2; L.ClockTime = 14; L.FogEnd = 100000
        end)
    end
    
    if CF.AutoClick then
        pcall(function()
            task.wait(RN(0.8,1.2) / CF.CPS)
            if CF.FastClick then SCL() end
            SCL()
        end)
    end
    
    if CF.AutoCollectFruits then
        pcall(function()
            for _, f in ipairs(GF()) do
                if f:IsA("Tool") and LP.Character then
                    LP.Character.Humanoid:EquipTool(f)
                end
            end
        end)
    end
    
    if CF.AutoOpenChests then
        pcall(function()
            for _, ch in ipairs(GC()) do
                if LP.Character then
                    STP(ch.Position + Vector3.new(0,3,0))
                    task.wait(RN(0.3,0.7))
                end
            end
        end)
    end
    
    if CF.AutoEquipBestSword then EBS() end
    if CF.FPSBoost then pcall(function() settings().Rendering.QualityLevel = 1 end) end
    if CF.RemoveTerrain then pcall(function() workspace.Terrain:Clear() end) end
    
    if CF.HideCharacter and LP.Character then
        pcall(function()
            for _, v in ipairs(LP.Character:GetChildren()) do
                if v:IsA("BasePart") then v.Transparency = 1 end
            end
        end)
    end
    
    if CF.AutoTeleportFruit then
        pcall(function()
            local f = GF()
            if #f > 0 then STP(f[1].Position) end
        end)
    end
    
    if CF.AutoCollectAll then
        pcall(function()
            for _, v in ipairs(workspace:GetDescendants()) do
                if v:IsA("Tool") and LP.Character then
                    LP.Character.Humanoid:EquipTool(v)
                end
            end
        end)
    end
    
    if CF.AutoLeaveOnAdmin then
        pcall(function()
            for _, p in ipairs(P:GetPlayers()) do
                if p:GetRankInGroup(1) > 200 then
                    task.wait(RN(1,3))
                    TPS:Teleport(game.PlaceId)
                end
            end
        end)
    end
end)

RS.Stepped:Connect(function()
    if CF.NoClip then
        pcall(function()
            if LP.Character then
                for _, v in ipairs(LP.Character:GetDescendants()) do
                    if v:IsA("BasePart") then v.CanCollide = false end
                end
            end
        end)
    end
end)

RS.RenderStepped:Connect(function()
    pcall(function()
        if CF.ESP or CF.ESPPlayers then
            for _, p in ipairs(GP()) do
                if p.Character and p.Character:FindFirstChild("Head") then
                    p.Character.Head.Color = Color3.fromRGB(255,0,0)
                end
            end
        end
        if CF.ESP or CF.ESPFruits then
            for _, f in ipairs(GF()) do
                if f:IsA("BasePart") then f.Color = Color3.fromRGB(0,255,0) end
            end
        end
        if CF.ESP or CF.ESPChests then
            for _, ch in ipairs(GC()) do
                if ch:IsA("BasePart") then ch.Color = Color3.fromRGB(255,255,0) end
            end
        end
    end)
    
    if CF.Aimbot then
        pcall(function()
            local cl, cd = nil, CF.AimFOV
            local mp = UIS:GetMouseLocation()
            local ct = CF.AimAssist and mp or Vector2.new(workspace.CurrentCamera.ViewportSize.X/2, workspace.CurrentCamera.ViewportSize.Y/2)
            for _, p in ipairs(GP()) do
                if p.Character and p.Character:FindFirstChild("Head") then
                    local sp, os = workspace.CurrentCamera:WorldToScreenPoint(p.Character.Head.Position)
                    if os then
                        local d = (Vector2.new(sp.X, sp.Y) - ct).Magnitude
                        if d < cd then cd = d; cl = p end
                    end
                end
            end
            if cl then
                local tp = workspace.CurrentCamera:WorldToScreenPoint(cl.Character.Head.Position)
                mousemoverel(tp.X - mp.X, tp.Y - mp.Y)
            end
        end)
    end
end)

local function Notify(title, msg)
    pcall(function()
        local nf = Instance.new("Frame", SG)
        nf.Size = UDim2.new(0,260,0,60); nf.Position = UDim2.new(1,280,0,20)
        nf.BackgroundColor3 = TH.SF; nf.BackgroundTransparency = 0.2; nf.BorderSizePixel = 0
        Instance.new("UICorner", nf).CornerRadius = UDim.new(0,8)
        local ns = Instance.new("UIStroke", nf); ns.Color = TH.P; ns.Thickness = 2
        
        local t = Instance.new("TextLabel", nf)
        t.Size = UDim2.new(1,-10,0,22); t.Position = UDim2.new(0,5,0,3)
        t.BackgroundTransparency = 1; t.Text = title; t.TextColor3 = TH.P
        t.TextSize = 14; t.Font = Enum.Font.GothamBold; t.TextXAlignment = Enum.TextXAlignment.Left
        
        local m = Instance.new("TextLabel", nf)
        m.Size = UDim2.new(1,-10,0,25); m.Position = UDim2.new(0,5,0,25)
        m.BackgroundTransparency = 1; m.Text = msg; m.TextColor3 = TH.T
        m.TextSize = 11; m.Font = Enum.Font.Gotham; m.TextXAlignment = Enum.TextXAlignment.Left
        
        TS:Create(nf, TweenInfo.new(0.4), {Position = UDim2.new(1,-280,0,20)}):Play()
        task.delay(4, function()
            TS:Create(nf, TweenInfo.new(0.4), {Position = UDim2.new(1,280,0,20)}):Play()
            task.wait(0.4); nf:Destroy()
        end)
    end)
end

Notify("🛡️ ITACHI HUB", "v9.0 Universal | 20 Tabs | Anti-Ban")

end)

if not success then warn("Error: " .. tostring(e)) end
