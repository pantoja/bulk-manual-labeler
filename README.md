# YOLO Label Corrector

Uma ferramenta simples, baseada em navegador, para corrigir e revisar anotações de bounding box no formato YOLO. Suporta o formato padrão (`class cx cy w h`) e o formato OBB/polígono do Roboflow (`class x1 y1 x2 y2 x3 y3 x4 y4`), convertendo automaticamente para bbox alinhado ao eixo.

## Como Usar

1.  **Abra a Ferramenta**:
    *   Abra o arquivo `yolo-label-corrector.html` em seu navegador web.

2.  **Carregue seus Dados**:
    *   **Opção 1 (Recomendado)**: Arraste e solte um arquivo `.zip` que contenha as pastas `images/` e `labels/`.
    *   **Opção 2**: Arraste e solte múltiplos arquivos de imagem (`.jpg`, `.png`) e de anotação (`.txt`) diretamente na janela.
    *   **Opção 3**: Clique em "Load Files" para selecionar os arquivos.

    A ferramenta irá parear automaticamente as imagens e as anotações pelos nomes dos arquivos.

3.  **Corrija as Anotações**:
    *   Selecione uma imagem na lista à esquerda para visualizá-la.
    *   **Offset em lote**: No painel direito, insira os valores de deslocamento em pixels (`Δx` e `Δy`) e clique em **"Apply to This Image"** ou **"Apply to All Images"**.
    *   **Ajuste manual**: Arraste caixas existentes para reposicioná-las. Mantenha `S` pressionado e arraste para selecionar várias caixas ao mesmo tempo.
    *   **Nova caixa manual**: Arraste o mouse sobre uma área vazia da imagem para desenhar uma nova caixa.
    *   **Smart Select**: Ative o modo `✦ Smart` (botão no cabeçalho ou tecla `F`) e clique sobre um objeto para criar uma caixa automaticamente via flood fill. Use o slider **Tolerance** para ajustar a sensibilidade.

4.  **Exporte os Resultados**:
    *   Clique no botão **"Export ZIP"** para baixar todas as anotações corrigidas em um arquivo `.zip`.

## Funcionalidades

*   Carregamento via arrastar e soltar ou seletor de arquivos, com suporte a `.zip`.
*   Conversão automática do formato OBB/polígono do Roboflow para bbox alinhado ao eixo.
*   Arquivos de metadados do macOS (`._*`) ignorados automaticamente.
*   Aplicação de deslocamento em pixels para uma ou todas as imagens.
*   Ajuste manual de caixas por arrastar, seleção múltipla e exclusão.
*   **Smart Select**: flood fill a partir do pixel clicado para estimar uma bounding box automaticamente — ideal para objetos escuros sobre fundo claro.
*   **Checkpoints automáticos**: cada alteração é salva no `localStorage`. Ao reabrir a ferramenta e carregar os mesmos arquivos, o progresso é restaurado automaticamente (indicado pela tag `checkpoint` no painel de status). O botão "Clear All Checkpoints" apaga todo o progresso salvo.
*   Desfazer por imagem (histórico de 30 estados).
*   Exportação das anotações corrigidas em `.zip` (formato YOLO bbox padrão).

## Atalhos do Teclado

| Tecla(s) | Ação |
| :--- | :--- |
| `←` `→` `↑` `↓` / `j` `k` | Navegar para a imagem anterior/seguinte. |
| `F` | Ativar/desativar o modo Smart Select. |
| `S` (manter pressionado) | Ativar o modo de seleção em área (arraste para selecionar várias caixas). |
| `A` ou `Ctrl/Cmd + A` | Selecionar todas as caixas na imagem atual. |
| `Delete` / `Backspace` | Excluir a(s) caixa(s) selecionada(s). |
| `Enter` | Aplicar o offset à imagem atual. |
| `Z` | Desfazer a última alteração. |
| `Esc` | Cancelar seleção em área ou deselecionar caixas. |
