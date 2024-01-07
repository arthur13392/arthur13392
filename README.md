-- Importe a biblioteca IMGui (deve ter a biblioteca instalada)
local imgui = require("imgui")

-- FunÃ§Ã£o para criar a GUI
function criarGUI()
    imgui.Begin("ConfiguraÃ§Ãµes do Script")
    local _, scriptAtivadoChanged = imgui.Checkbox("Ativar Script", scriptAtivado)
    local _, visaoAtivadaChanged = imgui.Checkbox("Ativar VisÃ£o AtrÃ¡s das Paredes", visaoAtrasDasParedesAtivada)
    imgui.End()

    -- Atualiza as variÃ¡veis com base nas mudanÃ§as na GUI
    if scriptAtivadoChanged then
        scriptAtivado = not scriptAtivado
    end

    if visaoAtivadaChanged then
        alternarVisaoAtrasDasParedes()
    end
end

-- FunÃ§Ã£o principal para renderizar cena e GUI
function love.draw()
    renderizarCena()
    criarGUI()
end

-- Restante do seu cÃ³digo aqui...
