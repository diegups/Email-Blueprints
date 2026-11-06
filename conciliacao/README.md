# Conciliador de Extrato

Página web (um único arquivo, `index.html`) que compara os lançamentos de uma
planilha Excel com o extrato bancário em OFX e aponta:

- **Valor divergente**: mesmo lançamento com valor diferente (avisa quando a diferença sugere inversão de dígitos)
- **Só na planilha** / **Só no extrato**: o que não tem par do outro lado
- **Conciliado · data**: mesmo valor com até N dias de diferença (tolerância ajustável)
- **Conciliado · soma**: um crédito ou débito do extrato que corresponde à soma de várias linhas da planilha, ou o contrário
- **Possível duplicidade**: linhas repetidas na planilha ou FITID repetido no OFX
- **Categoria**: linha sem categoria, categoria que contraria uma regra (`CEMIG = Energia`) ou fora do habitual para aquele favorecido
- **Fora do período**: linhas da planilha com data fora do período do extrato

## Como usar

1. Abra `index.html` no navegador (Chrome, Edge, Firefox).
2. Envie a planilha (.xlsx, .xls, .ods ou .csv) e o extrato .ofx.
3. Confira as colunas detectadas em "Colunas da planilha" (Data, Descrição, Valor ou Entrada/Saída, Tipo, Categoria, Documento).
4. Filtre por "Pendências" e baixe o resultado em Excel ou copie a lista.

Os arquivos são processados no próprio navegador; nada é enviado para servidor.
A leitura de Excel usa a biblioteca SheetJS (carregada do cdnjs), então é preciso internet ao abrir a página.
