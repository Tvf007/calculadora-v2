# Registro de Progresso - Caixa Freitas (Calculadora v2)

## 📌 Última Atualização
- **Data e Hora da Mudança / Conclusão**: 22/07/2026 15:50 (Horário de Brasília)
- **Tempo Estimado Gasto**: 20 minutos

## 📝 Arquivos Modificados
- [`index.html`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/index.html):
  - **Reescrita completa do parser OCR** com suporte a 3 tipos de documentos:
    - **Tipo 1 — Orçamento em Tabela** (`CÓDIGO QTD PRODUTO UND VL_UNIT VL_TOTAL`):
      * Heurística de 2 números iniciais: se `n1 >= 100` ou `n1 > n2*3`, então `n1=código` e `n2=qtd`. Nunca usa o código como quantidade.
      * Embalagem fechada (`CX`, `FD`, `BL`, `PC`, `PT`, `PCT`) com multiplicador (`C/12 UD`, `C/15`, `10X120G`): `qtd_venda = qtd_comprada × mult`, `custo = vlUnit / mult`.
      * Venda direta (`UN`, `KG`, `M2`, `L`, etc.): sem subdivição de custo.
    - **Tipo 2 — Cupom Térmico de Distribuidora** (2 linhas):
      * Linha 1 = descrição do produto (ex: `GULAO QUEIJO SUICO 10X120G`).
      * Linha 2 = `QTD UND x VL_UNIT` (ex: `1 FD x 39,49`).
      * Multiplicador (`10X120G`) aplicado: custo por unidade = `39,49 / 10 = R$ 3,95`; qtd venda = `1 × 10 = 10`.
    - **Tipo 3 — Notas de Construção / Lojas** (Agrizzi e similares):
      * Filtro expandido de linhas de cabeçalho e rodapé (CNPJ, CPF, telefone, endereço, totais, carimbos, etc.).
      * Detecção por regex de linhas de CNPJ (`\d{2}\.\d{3}\.\d{3}\/...`), telefone e data.
  - Novas funções adicionadas: `deveIgnorarLinha()`, `parseLinhaTabelaOrcamento()`, `tentarParseCupomDuasLinhas()`.
  - Função `limparNomeProduto()` refatorada para remover artefatos OCR (`|`, `<`, `>`, `{}`, `[]`).
  - Array de controle `usada[]` para evitar que linhas sejam re-processadas.
- [`PROGRESS.md`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/PROGRESS.md): Atualizado com o registro desta alteração.

## 🛠️ Problemas Corrigidos
- **Código do produto sendo lido como Quantidade**: Heurística `n1 >= 100 || n1 > n2 * 3` garante que o número grande inicial seja sempre tratado como código, e o segundo como a quantidade real.
- **Multiplicador ignorado em cupons térmicos**: O parse de 2 linhas agora extrai corretamente o multiplicador da descrição (ex: `10X120G`) e divide o valor da embalagem por ele.
- **Linhas de cabeçalho / rodapé capturadas incorretamente**: Lista de filtros expandida com CNPJ, CPF, telefone, endereço, tributos, fatura, comprovante, etc.

## 📊 Status Atual do Sistema
- **Status**: Operacional e Otimizado
- **Recursos Ativos**:
  - Parser OCR com 3 modos de leitura: Tabela de Orçamento, Cupom Térmico (2 linhas) e Notas de Loja.
  - Distinção automática entre embalagem fechada e venda por unidade.
  - Custo Unitário Real e Quantidade de Venda Total preenchidos diretamente no formulário.
  - Leitura por Câmera (`📷 Tirar Foto`) e Galeria (`🖼️ Escolher da Galeria`).

## ⚠️ Problemas Encontrados (se houver)
- Nenhum.

