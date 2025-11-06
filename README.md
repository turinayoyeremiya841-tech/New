-- Crear el frame principal
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "Messi"
screenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
screenGui.ResetOnSpawn = false -- Evita que el ScreenGui se elimine al respawnear


-- Frame Principal (Estilo Infinity Ultron)
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 476, 0, 230)
mainFrame.Position = UDim2.new(0.31, 0, 0.322, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Fondo oscuro para resaltar el brillo metÃƒÂ¡lico
mainFrame.BorderSizePixel = 0
mainFrame.Visible = true
mainFrame.Parent = screenGui


-- Redondear las esquinas del frame principal
local uiCornerMain = Instance.new("UICorner")
uiCornerMain.CornerRadius = UDim.new(0.1, 0)
uiCornerMain.Parent = mainFrame


-- UIStroke metÃƒÂ¡lico para el frame principal
local uiStrokeMainFrame = Instance.new("UIStroke")
uiStrokeMainFrame.Color = Color3.fromRGB(255, 255, 255) -- Color metÃƒÂ¡lico (plata)
uiStrokeMainFrame.Thickness = 5 -- Grosor del trazo
uiStrokeMainFrame.Parent = mainFrame


-- Frame Secundario (Para los botones principales) (Estilo Infinity Ultron)
local secondaryFrame = Instance.new("Frame")
secondaryFrame.Size = UDim2.new(0, 138, 0, 214)
secondaryFrame.Position = UDim2.new(0.015, 0, 0.035, 0)
secondaryFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Gris oscuro metÃƒÂ¡lico
secondaryFrame.BorderSizePixel = 0
secondaryFrame.Visible = true
secondaryFrame.Parent = mainFrame


-- Redondear las esquinas del frame secundario
local uiCornerSecondary = Instance.new("UICorner")
uiCornerSecondary.CornerRadius = UDim.new(0.1, 0)
uiCornerSecondary.Parent = secondaryFrame


-- UIStroke metÃƒÂ¡lico para el frame secundario
local uiStrokeSecondaryFrame = Instance.new("UIStroke")
uiStrokeSecondaryFrame.Color = Color3.fromRGB(255, 255, 255) -- Plata metÃƒÂ¡lica
uiStrokeSecondaryFrame.Thickness = 3 -- Grosor del trazo
uiStrokeSecondaryFrame.Parent = secondaryFrame


-- Frame Tercero (Para mostrar los botones de cada pÃƒÂ¡gina) (Estilo Infinity Ultron)
local thirdFrame = Instance.new("Frame")
thirdFrame.Size = UDim2.new(0, 313, 0, 214)
thirdFrame.Position = UDim2.new(0.321, 0, 0.035, 0)
thirdFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Gris mÃƒÂ¡s oscuro, mÃƒÂ¡s acorde al tema de Ultron
thirdFrame.BorderSizePixel = 0
thirdFrame.Visible = true
thirdFrame.Parent = mainFrame


-- Redondear las esquinas del frame terciario
local uiCornerThird = Instance.new("UICorner")
uiCornerThird.CornerRadius = UDim.new(0.1, 0)
uiCornerThird.Parent = thirdFrame


-- UIStroke metÃƒÂ¡lico para el frame terciario
local uiStrokeThirdFrame = Instance.new("UIStroke")
uiStrokeThirdFrame.Color = Color3.fromRGB(255, 255, 255) -- Plata metÃƒÂ¡lica
uiStrokeThirdFrame.Thickness = 3 -- Grosor del trazo
uiStrokeThirdFrame.Parent = thirdFrame


-- TÃƒÂ­tulo de LD Hub estilo Infinity Ultron con fuente diferente, color blanco con borde negro
local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(0, 160, 0, 30) -- Ajustar tamaÃƒÂ±o del tÃƒÂ­tulo (mÃƒÂ¡s pequeÃƒÂ±o)
titleLabel.Position = UDim2.new(1, -480, 0.03, 0) -- Mover un poco mÃƒÂ¡s a la derecha (ajustado con un pequeÃƒÂ±o margen)
titleLabel.Text = "Wisp Hub" -- TÃƒÂ­tulo sin emoji
titleLabel.BackgroundTransparency = 1 -- Sin fondo
titleLabel.TextSize = 24 -- TamaÃƒÂ±o del texto mÃƒÂ¡s pequeÃƒÂ±o
titleLabel.Font = Enum.Font.Bangers -- Fuente GothamBold
titleLabel.TextScaled = true
titleLabel.TextStrokeTransparency = 0.5
titleLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0) -- Borde negro
titleLabel.TextColor3 = Color3.fromRGB(255, 170, 0) -- Blanco
titleLabel.Parent = mainFrame


-- AÃƒÂ±adir el contorno de texto (TextStroke) negro
titleLabel.TextStrokeTransparency = 0.1 -- MÃƒÂ¡s visible y grueso
titleLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0) -- Contorno negro


-- AnimaciÃƒÂ³n de cambio de color blanco y negro
local tweenService = game:GetService("TweenService")
local tweenInfo = TweenInfo.new(2, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut, -1, true)


-- Inicializa los colores para la animaciÃƒÂ³n (blanco y negro)
local goalWhite = {TextColor3 = Color3.fromRGB(255, 255, 255)} -- Blanco
local goalBlack = {TextColor3 = Color3.fromRGB(0, 0, 0)} -- Negro


-- Crear las transiciones de color
local tweenWhite = tweenService:Create(titleLabel, tweenInfo, goalWhite)
local tweenBlack = tweenService:Create(titleLabel, tweenInfo, goalBlack)


-- Iniciar la animaciÃƒÂ³n de color blanco
tweenWhite:Play()


-- Alternar entre los colores blanco y negro
tweenWhite.Completed:Connect(function()
        -- Cambiar al color negro
        tweenBlack:Play()


        -- DespuÃƒÂ©s de la animaciÃƒÂ³n negra, vuelve a empezar con el color blanco
        tweenBlack.Completed:Connect(function()
                tweenWhite:Play()
        end)
end)




-- Crear el botÃƒÂ³n circular de abrir/cerrar sin texto (solo imagen)
local toggleButton = Instance.new("TextButton")
toggleButton.Size = UDim2.new(0, 65, 0, 63) -- TamaÃƒÂ±o especificado (65x63)
toggleButton.Position = UDim2.new(0.5, -32, 0, -10) -- UbicaciÃƒÂ³n ajustada para centrar el botÃƒÂ³n
toggleButton.BackgroundColor3 = Color3.fromRGB(128, 128, 128) -- Gris metÃƒÂ¡lico
toggleButton.TextColor3 = Color3.fromRGB(0, 0, 0) -- Color negro para el texto (aunque no se usarÃƒÂ¡)
toggleButton.TextSize = 20
toggleButton.Font = Enum.Font.Garamond -- Fuente fuerte
toggleButton.Text = "" -- Eliminamos el texto (solo la imagen serÃƒÂ¡ visible)
toggleButton.Parent = screenGui


-- AÃƒÂ±adir el UICorner para hacer el botÃƒÂ³n circular
local uiCornerToggle = Instance.new("UICorner")
uiCornerToggle.CornerRadius = UDim.new(1, 0) -- Esto hace que el botÃƒÂ³n sea circular
uiCornerToggle.Parent = toggleButton


-- Crear la imagen del perfil que girarÃƒÂ¡ junto con el botÃƒÂ³n
local profileImageButton = Instance.new("ImageLabel")
profileImageButton.Size = UDim2.new(1, 0, 1, 0) -- Hacer que la imagen se ajuste al tamaÃƒÂ±o del botÃƒÂ³n (100% del tamaÃƒÂ±o del botÃƒÂ³n)
profileImageButton.Position = UDim2.new(0.5, 0, 0.5, 0) -- Centrar la imagen dentro del botÃƒÂ³n
profileImageButton.Image = "rbxassetid://101170400710228" -- Nueva imagen con el ID actualizado
profileImageButton.BackgroundTransparency = 1 -- Fondo transparente
profileImageButton.AnchorPoint = Vector2.new(0.5, 0.5) -- Centrado de la imagen
profileImageButton.Parent = toggleButton


-- FunciÃƒÂ³n para hacer girar la imagen
local function rotateImage()
        local rotation = 0
        while true do
                rotation = rotation + 1 -- Incrementar la rotaciÃƒÂ³n en grados
                if rotation >= 360 then
                        rotation = 0 -- Resetear la rotaciÃƒÂ³n despuÃƒÂ©s de 360 grados
                end
                profileImageButton.Rotation = rotation -- Aplicar la rotaciÃƒÂ³n a la imagen
                wait(0.01) -- Esperar un corto tiempo antes de la siguiente rotaciÃƒÂ³n
        end
end


-- Iniciar la rotaciÃƒÂ³n de la imagen
spawn(rotateImage)






-- FunciÃƒÂ³n para alternar la visibilidad del hub
local isVisible = false -- Inicialmente el hub estÃƒÂ¡ oculto
toggleButton.MouseButton1Click:Connect(function()
        isVisible = not isVisible
        mainFrame.Visible = isVisible
end)




-- **CÃƒÂ³digo para arrastrar el botÃƒÂ³n (toggleButton)**


local toggleDragging = false
local toggleDragStart = nil
local toggleStartPos = nil


-- FunciÃƒÂ³n para iniciar el arrastre del botÃƒÂ³n
local function startToggleDrag(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                toggleDragging = true
                toggleDragStart = input.Position
                toggleStartPos = toggleButton.Position
        end
end


-- FunciÃƒÂ³n para arrastrar el botÃƒÂ³n
local function updateToggleDrag(input)
        if toggleDragging then
                local delta = input.Position - toggleDragStart
                toggleButton.Position = UDim2.new(toggleStartPos.X.Scale, toggleStartPos.X.Offset + delta.X, toggleStartPos.Y.Scale, toggleStartPos.Y.Offset + delta.Y)
        end
end


-- FunciÃƒÂ³n para finalizar el arrastre del botÃƒÂ³n
local function stopToggleDrag()
        toggleDragging = false
end


-- Conectar los eventos de arrastre al botÃƒÂ³n
toggleButton.InputBegan:Connect(startToggleDrag)
toggleButton.InputChanged:Connect(updateToggleDrag)
toggleButton.InputEnded:Connect(stopToggleDrag)




-- **CÃƒÂ³digo para arrastrar el hub (mainFrame)**


local dragging = false
local dragStart = nil
local startPos = nil


-- FunciÃƒÂ³n para iniciar el arrastre del hub
local function startHubDrag(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                dragging = true
                dragStart = input.Position
                startPos = mainFrame.Position
        end
end


-- FunciÃƒÂ³n para arrastrar el hub
local function updateHubDrag(input)
        if dragging then
                local delta = input.Position - dragStart
                mainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
        end
end


-- FunciÃƒÂ³n para finalizar el arrastre del hub
local function stopHubDrag()
        dragging = false
end


-- Conectar los eventos de arrastre al hub
mainFrame.InputBegan:Connect(startHubDrag)
mainFrame.InputChanged:Connect(updateHubDrag)
mainFrame.InputEnded:Connect(stopHubDrag)


-- Crear la imagen de perfil con fondo transparente y en la parte inferior izquierda
local profileImage1 = Instance.new("ImageLabel")
profileImage1.Size = UDim2.new(0, 40, 0, 40) -- TamaÃƒÂ±o: 50x50
profileImage1.Position = UDim2.new(01, -60, 1, -10) -- MÃƒÂ¡s a la izquierda (antes estaba en X=85)
profileImage1.Image = "rbxassetid://101170400710228"
profileImage1.BackgroundTransparency = 1
profileImage1.AnchorPoint = Vector2.new(0, 1)
profileImage1.Parent = mainFrame


-- FunciÃƒÂ³n para hacer que la imagen gire usando un Tween
local function rotateImage(imageLabel)
        local tweenService = game:GetService("TweenService")
        local tweenInfo = TweenInfo.new(5, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut, -1, true)
        local goal = {Rotation = 360}


        local tween = tweenService:Create(imageLabel, tweenInfo, goal)
        tween:Play()
end


rotateImage(profileImage1)
-- Verifica que los frames existen
if not secondaryFrame or not thirdFrame then
        warn("Faltan 'secondaryFrame' o 'thirdFrame'. Verifica tu GUI.")
        return
end


-- FunciÃƒÂ³n para crear botones con estilo Akatsuki
local function createAkatsukiButton(text, position, parentFrame)
        local button = Instance.new("TextButton")
        button.Size = UDim2.new(0, 120, 0, 38)
        button.Position = position
        button.Text = text
        button.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        button.TextColor3 = Color3.fromRGB(0, 0, 0)
        button.TextSize = 18 -- Texto mÃƒÂ¡s pequeÃƒÂ±o
        button.Font = Enum.Font.Bangers
        button.Parent = parentFrame


        -- Esquinas redondeadas
        local uiCorner = Instance.new("UICorner")
        uiCorner.CornerRadius = UDim.new(0.2, 0)
        uiCorner.Parent = button


        -- Efecto de trazo de texto
        button.TextStrokeTransparency = 0.4
        button.TextStrokeColor3 = Color3.fromRGB(255, 0, 0)


        -- Contorno de borde en el botÃƒÂ³n
        local uiStroke = Instance.new("UIStroke")
        uiStroke.Color = Color3.fromRGB(255, 170, 0)
        uiStroke.Thickness = 3
        uiStroke.Parent = button


        -- Efecto hover para el botÃƒÂ³n
        button.MouseEnter:Connect(function()
                button.BackgroundColor3 = Color3.fromRGB(255, 0, 0) -- Rojo al pasar el ratÃƒÂ³n
                button.TextColor3 = Color3.fromRGB(255, 255, 255) -- Blanco cuando el ratÃƒÂ³n estÃƒÂ¡ sobre el botÃƒÂ³n
        end)


        button.MouseLeave:Connect(function()
                button.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Vuelve al color original
                button.TextColor3 = Color3.fromRGB(0, 0, 0) -- Vuelve al color original del texto
        end)


        return button
end




-- Crear los botones principales de la pÃƒÂ¡gina
local button1 = createAkatsukiButton("Main", UDim2.new(0.08, 0, 0.183, 0), secondaryFrame)
local button2 = createAkatsukiButton("Basic", UDim2.new(0.08, 0, 0.383, 0), secondaryFrame)
local button3 = createAkatsukiButton("Other", UDim2.new(0.08, 0, 0.583, 0), secondaryFrame)
local button4 = createAkatsukiButton("Normal", UDim2.new(0.08, 0, 0.783, 0), secondaryFrame)


-- FunciÃƒÂ³n para crear los botones de cada pÃƒÂ¡gina
local function createAkatsukiPageButtons(pageNumber)
        for _, child in pairs(thirdFrame:GetChildren()) do
                if child:IsA("TextButton") then
                        child:Destroy()
                end
        end


        local buttonsData = {}


        if pageNumber == 1 then
                buttonsData = {
                        {Text = "No-cooldown", ScriptLink = "https://pastebin.com/raw/DG6KuxsS", Position = UDim2.new(0.03, 0, 0.074, 0)},
                        {Text = "Auto Base", ScriptLink = "https://pastebin.com/raw/KeFcGRBg", Position = UDim2.new(0.51, 0, 0.074, 0)},
                        {Text = "Aura", ScriptLink = "https://pastebin.com/raw/9APMikh1", Position = UDim2.new(0.03, 0, 0.287, 0)},
                        {Text = "Respawn", ScriptLink = "https://pastefy.app/xEpDNPGE/raw", Position = UDim2.new(0.51, 0, 0.287, 0)},
                        {Text = "NHN", ScriptLink = "https://pastebin.com/raw/YXuAgsiQ", Position = UDim2.new(0.03, 0, 0.5, 0)},
                        {Text = "Usetools", ScriptLink = "https://pastebin.com/raw/ib2AtYeB", Position = UDim2.new(0.51, 0, 0.5, 0)},
                        {Text = "Get Tools(trap)", ScriptLink = "https://pastebin.com/raw/MHN7tVU8", Position = UDim2.new(0.03, 0, 0.7, 0)},
                        {Text = "Damage", ScriptLink = "https://pastefy.app/tEdYsz6N/raw", Position = UDim2.new(0.51, 0, 0.7, 0)}
                }
        elseif pageNumber == 2 then
                buttonsData = {
                        {Text = "Buy Base", ScriptLink = "https://pastebin.com/raw/eQNWCBme", Position = UDim2.new(0.03, 0, 0.074, 0)},
                        {Text = "Rejoin", ScriptLink = "https://pastebin.com/raw/r2UgvFat", Position = UDim2.new(0.51, 0, 0.074, 0)},
                        {Text = "Infinity", ScriptLink = "https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source", Position = UDim2.new(0.03, 0, 0.287, 0)},
                        {Text = "Ghost Hub", ScriptLink = "https://raw.githubusercontent.com/GhostPlayer352/Test4/main/GhostHub", Position = UDim2.new(0.51, 0, 0.287, 0)},
                        {Text = "Spy Chat", ScriptLink = "https://pastebin.com/raw/u0eJBiH9", Position = UDim2.new(0.03, 0, 0.5, 0)},
                        {Text = "Anti Spy", ScriptLink = "https://pastebin.com/raw/ECZP85Ud", Position = UDim2.new(0.51, 0, 0.5, 0)},
                        {Text = "kill without noco", ScriptLink = "https://pastebin.com/raw/Tm0Zdj3h", Position = UDim2.new(0.03, 0, 0.7, 0)},
                        {Text = "Kill Counter", ScriptLink = "https://pastebin.com/raw/CeVeuKFb", Position = UDim2.new(0.51, 0, 0.7, 0)}
                }
        elseif pageNumber == 3 then
                buttonsData = {
                        {Text = "Float Tools", ScriptLink = "https://pastebin.com/raw/czJjPEYa", Position = UDim2.new(0.03, 0, 0.074, 0)},
                        {Text = "Multi Base", ScriptLink = "https://pastebin.com/raw/4u6C1YwW", Position = UDim2.new(0.51, 0, 0.074, 0)},
                        {Text = "Hitbox", ScriptLink = "https://pastebin.com/raw/8pXQKjnh", Position = UDim2.new(0.03, 0, 0.287, 0)},
                        {Text = "Anti Lag", ScriptLink = "https://pastebin.com/raw/u5KgwBeD", Position = UDim2.new(0.51, 0, 0.287, 0)},
                        {Text = "Get (Mega)", ScriptLink = "https://pastebin.com/raw/KE6bLMyV", Position = UDim2.new(0.03, 0, 0.5, 0)},
                        {Text = "Script 22", ScriptLink = "https://example.com/script22", Position = UDim2.new(0.51, 0, 0.5, 0)},
                        {Text = "Script 23", ScriptLink = "https://example.com/script23", Position = UDim2.new(0.03, 0, 0.7, 0)},
                        {Text = "Script 24", ScriptLink = "https://example.com/script24", Position = UDim2.new(0.51, 0, 0.7, 0)}
                }
        elseif pageNumber == 4 then
                buttonsData = {
                        {Text = "Script 25", ScriptLink = "https://pastebin.com/raw/example1", Position = UDim2.new(0.03, 0, 0.074, 0)},
                        {Text = "Script 26", ScriptLink = "https://pastebin.com/raw/example2", Position = UDim2.new(0.51, 0, 0.074, 0)},
                        {Text = "Script 27", ScriptLink = "https://pastebin.com/raw/example3", Position = UDim2.new(0.03, 0, 0.287, 0)},
                        {Text = "Script 27", ScriptLink = "https://pastebin.com/raw/example4", Position = UDim2.new(0.51, 0, 0.287, 0)},
                        {Text = "Script 28", ScriptLink = "https://pastebin.com/raw/example5", Position = UDim2.new(0.03, 0, 0.5, 0)},
                        {Text = "Script 29", ScriptLink = "https://pastebin.com/raw/example6", Position = UDim2.new(0.51, 0, 0.5, 0)},
                        {Text = "Script 30", ScriptLink = "https://pastebin.com/raw/example7", Position = UDim2.new(0.03, 0, 0.7, 0)},
                        {Text = "Script 31", ScriptLink = "https://pastebin.com/raw/example8", Position = UDim2.new(0.51, 0, 0.7, 0)}
                }
        end


        for _, buttonData in ipairs(buttonsData) do
                local button = createAkatsukiButton(buttonData.Text, buttonData.Position, thirdFrame)
                button.Size = UDim2.new(0.45, 0, 0.18, 0)


                button.MouseButton1Click:Connect(function()
                        local success, result = pcall(function()
                                loadstring(game:HttpGet(buttonData.ScriptLink))()
                        end)
                        if not success then
                                warn("Error al cargar el script: " .. result)
                        end
                end)
        end
end


-- Conectar los botones principales a las pÃƒÂ¡ginas
button1.MouseButton1Click:Connect(function() createAkatsukiPageButtons(1) end)
button2.MouseButton1Click:Connect(function() createAkatsukiPageButtons(2) end)
button3.MouseButton1Click:Connect(function() createAkatsukiPageButtons(3) end)
button4.MouseButton1Click:Connect(function() createAkatsukiPageButtons(4) end)


-- Mostrar la pÃƒÂ¡gina 1 por defecto
createAkatsukiPageButtons(1)
