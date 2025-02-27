-- Mod Menu Simples em Lua
local menu = {}
menu.isOpen = false

function menu.toggle()
    menu.isOpen = not menu.isOpen
    if menu.isOpen then
        menu.draw()
    end
end

function menu.draw()
    print("\n==== MOD MENU ====")
    print("1. Ativar Modo Deus")
    print("2. Aumentar Velocidade")
    print("3. Sair do Menu")
    print("Escolha uma opção:")
end

function menu.handleInput(input)
    if input == "1" then
        print("Modo Deus Ativado!")
    elseif input == "2" then
        print("Velocidade Aumentada!")
    elseif input == "3" then
        menu.toggle()
    else
        print("Opção Inválida! Tente novamente.")
    end
end

-- Loop de teste (simulando entrada do usuário)
while true do
    print("\nPressione 'M' para abrir/fechar o menu")
    local key = io.read()

    if key == "M" or key == "m" then
        menu.toggle()
    end

    while menu.isOpen do
        local choice = io.read()
        menu.handleInput(choice)
        if menu.isOpen then
            menu.draw()
        end
    end
end
