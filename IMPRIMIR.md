## Impressão do Relatório (Modo Paisagem)

* Ao clicar no botão 'IMPRIMIR' (definido em '010-Tela.md'), imprimir o arquivo de relatório gerado pela etapa 'GERAR' (arquivo 'GERAR.md') na impressora padrão do Windows, obrigatoriamente em **modo paisagem (orientação horizontal)** — independente da orientação salva como padrão na impressora.

* **Origem do arquivo:** o relatório é gravado em **texto (.txt)** no diretório `C:\Windows\Temp`, com nome `STETSON-` seguido da data de geração (formato `dd-mm-aaaa` definido em 'GERAR.md'). O comando abaixo localiza automaticamente o arquivo `STETSON-*.txt` mais recente nesse diretório, em vez de fixar um nome — assim continua funcionando qualquer que seja a data usada.

### Comando (PowerShell) — localiza o relatório mais recente e imprime em paisagem

```powershell
$diretorioRelatorio = "C:\Windows\Temp"
$padraoNome = "STETSON-*.txt"

$arquivoRelatorio = Get-ChildItem -Path $diretorioRelatorio -Filter $padraoNome -File |
    Sort-Object LastWriteTime -Descending |
    Select-Object -First 1

if (-not $arquivoRelatorio) {
    Write-Error "Nenhum arquivo '$padraoNome' encontrado em '$diretorioRelatorio'. Rode o GERAR antes de imprimir."
    exit 1
}

Add-Type -AssemblyName System.Drawing

$conteudo = Get-Content -Path $arquivoRelatorio.FullName -Encoding UTF8

$doc = New-Object System.Drawing.Printing.PrintDocument
# Sem definir PrinterName, o .NET já usa a impressora padrão do Windows
$doc.DefaultPageSettings.Landscape = $true
$doc.DefaultPageSettings.Margins = New-Object System.Drawing.Printing.Margins(40, 40, 40, 40)

$fonte = New-Object System.Drawing.Font("Consolas", 8)
$script:linha = 0

$doc.add_PrintPage({
    param($sender, $e)
    $y = $e.MarginBounds.Top
    $alturaLinha = $fonte.GetHeight($e.Graphics)
    while ($script:linha -lt $conteudo.Count -and $y -lt $e.MarginBounds.Bottom) {
        $e.Graphics.DrawString($conteudo[$script:linha], $fonte, [System.Drawing.Brushes]::Black, $e.MarginBounds.Left, $y)
        $y += $alturaLinha
        $script:linha++
    }
    $e.HasMorePages = $script:linha -lt $conteudo.Count
})

$doc.Print()
```

* Para executar a partir de linha de comando (cmd/batch) ou chamado por outra aplicação (Python `subprocess`, Node `child_process`, etc.), salve o script acima como `imprimir_paisagem.ps1` e rode:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -File "imprimir_paisagem.ps1"
```

### Alternativas mais simples (não garantem o modo paisagem)

Só usar se a impressora padrão já estiver configurada em paisagem, e substituindo `<data>` pela data real do relatório:

* Via Notepad: `notepad /p "C:\Windows\Temp\STETSON-<data>.txt"`
* Via PowerShell: `Get-Content "C:\Windows\Temp\STETSON-<data>.txt" | Out-Printer`

### Sobre a largura do relatório

O `Relatorio.txt` deste projeto tem linhas de ~133 colunas. Em modo paisagem, com a fonte Consolas 8pt e margens de 40pt definidas acima, o relatório cabe confortavelmente em A4/Carta — diferente do modo retrato, aqui não é necessário reduzir a fonte para evitar corte de colunas.

## Fim da Impressão do Relatório
