-- Script para conceder acesso premium no jogo CARROSEL com GUI e botão

-- Função para conceder acesso premium ao jogador
local function concederAcessoPremium(jogador)
    -- Conceder acesso a todos os recursos premium
    print(jogador.Name .. " tem acesso premium!")
    -- Adicione aqui os recursos premium que você deseja conceder
    -- Exemplo: jogador:GiveTool(game.ServerStorage.PremiumTool)
    
    -- Criar uma GUI para indicar acesso premium
    local screenGui = Instance.new("ScreenGui")
    screenGui.Name = "PremiumGui"
    screenGui.Parent = jogador:WaitForChild("PlayerGui")
    
    local textLabel = Instance.new("TextLabel")
    textLabel.Size = UDim2.new(0, 200, 0, 50)
    textLabel.Position = UDim2.new(0.5, -100, 0.4, -25)
    textLabel.Text = "Clique para ativar Premium"
    textLabel.TextColor3 = Color3.new(1, 1, 1)
    textLabel.BackgroundColor3 = Color3.new(0, 0, 0)
    textLabel.Parent = screenGui
    
    local button = Instance.new("TextButton")
    button.Size = UDim2.new(0, 200, 0, 50)
    button.Position = UDim2.new(0.5, -100, 0.5, -25)
    button.Text = "Ativar Premium"
    button.TextColor3 = Color3.new(1, 1, 1)
    button.BackgroundColor3 = Color3.new(0, 0.5, 0)
    button.Parent = screenGui
    
    button.MouseButton1Click:Connect(function()
        jogador.MembershipType = Enum.MembershipType.Premium
        textLabel.Text = "Você tem acesso premium!"
        button:Destroy()
    end)
end

-- Simular que o jogador tem assinatura premium
local jogador = game.Players.LocalPlayer
concederAcessoPremium(jogador)
