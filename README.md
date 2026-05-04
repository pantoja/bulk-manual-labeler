# YOLO Label Corrector

Uma ferramenta simples, baseada em navegador, para aplicar correções de deslocamento (offset) em lote para anotações de bounding box no formato YOLO.

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
    *   No painel direito "Offset Correction", insira os valores de deslocamento em pixels (`Δx` e `Δy`).
    *   Clique em **"Apply to This Image"** para corrigir apenas a imagem atual ou **"Apply to All Images"** para aplicar o deslocamento em todo o conjunto de dados.
    *   Você também pode ajustar caixas individualmente arrastando-as ou desenhar novas caixas arrastando o mouse sobre a imagem.

4.  **Exporte os Resultados**:
    *   Após fazer as correções, clique no botão **"Export ZIP"**.
    *   Isso fará o download de um arquivo `.zip` contendo todos os arquivos de anotação `.txt` atualizados.

## Funcionalidades

*   Carregamento de imagens e anotações via arrastar e soltar ou seletor de arquivos.
*   Suporte para carregamento em lote via arquivo `.zip`.
*   Aplicação de deslocamento (offset) em pixels para uma ou todas as imagens.
*   Visualização e ajuste manual de bounding boxes.
*   Criação e exclusão de bounding boxes.
*   Exportação das anotações corrigidas em um arquivo `.zip`.
