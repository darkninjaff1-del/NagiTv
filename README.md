-- [[ NOVA SEÇÃO DA INTERFACE DO USUÁRIO (UI) - ESTILO ITACHI UCHIHA ]] --
-- ITACHI HUB - Blox Fruits

local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/download/latest/main.lua"))()
local Window = Fluent:CreateWindow({
    Title = "🍥 ITACHI HUB | Sharingan Mode 🍥", 
    SubTitle = "| By: caveira | Tema: Itachi Uchiha",
    TabWidth = 180,
    Size = UDim2.fromOffset(660, 440),
    Acrylic = false,
    Theme = "Rose",
    MinimizeKey = Enum.KeyCode.End
})

-- Tenta modificar o tema da janela para preto e vermelho
pcall(function()
    Window:SetTheme("Dark")
end)

-- Cria um estilo CSS global para forçar as bordas vermelhas e fundo preto
local StyleSheet = Instance.new("StyleSheet")
StyleSheet.Source = [[
    /* Força o fundo da janela principal e das abas para preto */
    .Frame, .TabFrame, .Tab, .TabContainer, .Window, .Main, .Content, .Left {
        background-color: #0a0a0a !important;
        border-color: #ff0000 !important;
    }
    /* Adiciona uma borda vermelha brilhante em toda a janela */
    .Window {
        border: 2px solid #ff0000 !important;
        box-shadow: 0 0 15px rgba(255, 0, 0, 0.3) !important;
    }
    /* Estiliza as abas selecionadas com uma cor vermelha escura */
    .Tab.Active {
        background-color: #2a0000 !important;
        border-left: 3px solid #ff0000 !important;
    }
    /* Texto das abas */
    .Tab .Text {
        color: #cccccc !important;
    }
    .Tab.Active .Text {
        color: #ff4d4d !important;
        text-shadow: 0 0 5px rgba(255, 0, 0, 0.5) !important;
    }
    /* Bordas e textos dos elementos internos */
    .Toggle, .Button, .Dropdown, .Slider, .Input {
        border: 1px solid #660000 !important;
        background-color: #111111 !important;
    }
    .Toggle.Active {
        background-color: #990000 !important;
        border-color: #ff0000 !important;
    }
    .Button:hover {
        background-color: #2a0000 !important;
        border-color: #ff3333 !important;
    }
    .Paragraph .Title, .Paragraph .Content {
        color: #cccccc !important;
    }
]]
StyleSheet.Parent = game:GetService("CoreGui")

-- Cria um ScreenGui separado para o ícone flutuante do Itachi
local CoreGui = game:GetService("CoreGui")
local ItachiIconGui = Instance.new("ScreenGui")
ItachiIconGui.Name = "ItachiHubIcon"
ItachiIconGui.Parent = CoreGui
ItachiIconGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ItachiIconGui.ResetOnSpawn = false

-- Função para adicionar bordas arredondadas e linha vermelha ao ícone
local function addStyleToIcon(button)
    local corners = Instance.new("UICorner")
    corners.CornerRadius = UDim.new(1, 0)
    corners.Parent = button

    local stroke = Instance.new("UIStroke")
    stroke.Color = Color3.fromRGB(255, 0, 0)
    stroke.Thickness = 2
    stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
    stroke.Parent = button
end

-- Cria o botão flutuante com a imagem do Itachi
local ItachiButton = Instance.new("ImageButton")
ItachiButton.Size = UDim2.new(0, 60, 0, 60)
ItachiButton.Position = UDim2.new(0.85, 0, 0.80, 0)
ItachiButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ItachiButton.BackgroundTransparency = 0.2
-- IMAGEM DO ITACHI COM SHARINGAN (substitua o ID se quiser outra imagem)
ItachiButton.Image = "rbxassetid://7143313059"
ItachiButton.ImageColor3 = Color3.fromRGB(255, 255, 255)
ItachiButton.Parent = ItachiIconGui

-- Aplica as bordas arredondadas e a linha vermelha no ícone
addStyleToIcon(ItachiButton)

-- Efeito de brilho vermelho ao passar o mouse
local hoverTween = game:GetService("TweenService")
local glowIn = hoverTween:Create(ItachiButton, TweenInfo.new(0.2), {
    ImageColor3 = Color3.fromRGB(255, 100, 100),
    BackgroundTransparency = 0
})
local glowOut = hoverTween:Create(ItachiButton, TweenInfo.new(0.2), {
    ImageColor3 = Color3.fromRGB(255, 255, 255),
    BackgroundTransparency = 0.2
})
ItachiButton.MouseEnter:Connect(function() glowIn:Play() end)
ItachiButton.MouseLeave:Connect(function() glowOut:Play() end)

-- Funcionalidade do botão: Envia a tecla "End" para abrir/fechar o menu
ItachiButton.MouseButton1Click:Connect(function()
    local VirtualInputManager = game:GetService("VirtualInputManager")
    VirtualInputManager:SendKeyEvent(true, "End", false, game)
    task.wait(0.05)
    VirtualInputManager:SendKeyEvent(false, "End", false, game)
end)

-- Funcionalidade de arrastar o ícone
local dragging = false
local dragInput, dragStart, startPos
local UserInputService = game:GetService("UserInputService")

local function update(input)
    local delta = input.Position - dragStart
    ItachiButton.Position = UDim2.new(
        startPos.X.Scale,
        startPos.X.Offset + delta.X,
        startPos.Y.Scale,
        startPos.Y.Offset + delta.Y
    )
end

ItachiButton.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        dragging = true
        dragStart = input.Position
        startPos = ItachiButton.Position

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

ItachiButton.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInput = input
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if dragging and input == dragInput then
        update(input)
    end
end)

-- MENSAGEM DE CONFIRMAÇÃO
print("Itachi Hub carregado com sucesso! Tema: Sharingan Mode")

-- ===================================================== --
-- COLE AQUI O RESTO DO SEU SCRIPT ORIGINAL (TABS, TOGGLES, FUNÇÕES DE FARM)
-- ===================================================== --

-- Exemplo das Tabs (substitua pelo seu código original):
local Tabs = {
    Settings = Window:AddTab({Title = "⚙️ Setting Farm", Icon = ""}),
    Main = Window:AddTab({Title = "🚀 Farm", Icon = ""}),
    Melee = Window:AddTab({Title = "🥊 Fighting Style", Icon = ""}),
    Quests = Window:AddTab({Title = "💎 Items Farm", Icon = ""}),
    Valentine = Window:AddTab({Title = "❤️ Valentine", Icon = ""}),
    SeaEvent = Window:AddTab({Title = "🌊 Sea Events", Icon = ""}),
    Mirage = Window:AddTab({Title = "🌴 Mirage + Race V4", Icon = ""}),
    Drago = Window:AddTab({Title = "🐉 Drago Dojo", Icon = ""}),
    Prehistoric = Window:AddTab({Title = "🦕 Prehistoric", Icon = ""}),
    Raids = Window:AddTab({Title = "🌀 Raid", Icon = ""}),
    Combat = Window:AddTab({Title = "⚔️ Combat PVP", Icon = ""}),
    Travel = Window:AddTab({Title = "🗺️ Travel", Icon = ""}),
    Fruit = Window:AddTab({Title = "🍎 Fruits", Icon = ""}),
    Shop = Window:AddTab({Title = "🛒 Shop", Icon = ""}),
    Misc = Window:AddTab({Title = "⚡ Misc", Icon = ""})
}

-- ===================================================== --
-- O RESTO DAS FUNÇÕES DO SEU SCRIPT CONTINUA AQUI
-- (FarmLevel, AutoFarm, BringEnemy, Useskills, etc...)
-- ===================================================== --

-- Finaliza selecionando a primeira aba
Window:SelectTab(1)
