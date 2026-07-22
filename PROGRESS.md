# Registro de Progresso - Caixa Freitas (Calculadora v2)

## 📌 Última Atualização
- **Data e Hora da Mudança / Conclusão**: 22/07/2026 16:05 (Horário de Brasília)
- **Tempo Estimado Gasto**: 10 minutos

## 📝 Arquivos Modificados
- [`index.html`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/index.html):
  - **Correção da Dupla Divisão**: `calcularPrecoVenda()` não divide mais o preço pela quantidade. O `Custo Unitário` (ex: R$ 5,50) é usado diretamente para calcular o preço de venda.
  - **Limpeza de Lixo OCR**: `limparNomeProduto()` agora remove traços/hífens iniciais (ex: `— LEITE`, `—— BISCRECH`) e outros artefatos de imagem.
  - **Heurística de Código Corrigida**: O parser de tabela de orçamento agora usa regex com `[A-Z]` para garantir que quando dois números precedem texto com letra, o 1º é sempre o código e o 2º a quantidade (funciona com códigos pequenos como `55`).
  - **Atalho Duplo Clique**: Chips OCR agora suportam `onclick` (preencher campos) e `ondblclick` (preencher + adicionar direto na lista).
- [`PROGRESS.md`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/PROGRESS.md): Atualizado com o registro desta alteração.

## 🛠️ Problemas Corrigidos
- **Dupla Divisão do Custo Unitário**: `calcularPrecoVenda()` não dividia pelo parâmetro `quantidade` que foi removido. O preço de custo preenchido pelo OCR (ex: R$ 5,50) agora é usado diretamente, sem nenhuma nova divisão.
- **Lixo OCR no nome do produto**: `limparNomeProduto()` remove traços (`—`, `-`, `–`) no início do nome.
- **Código de 1-2 dígitos lido como quantidade**: Nova regex `^\s*(\d{1,6})\s+(\d{1,4})\s+([A-ZÀ-Ú].*)$/i` garante que quando há dois números antes de texto com letra, o 1º é sempre o código (funciona com `55 3 IBITURUNA`).
- **Primeiro item da nota ignorado**: O filtro de linhas de cabeçalho não afeta mais os primeiros itens da tabela.

## 📊 Status Atual do Sistema
- **Status**: Operacional e Otimizado
- **Recursos Ativos**:
  - Parser OCR com 3 modos de leitura: Tabela de Orçamento, Cupom Térmico (2 linhas) e Notas de Loja.
  - Distinção automática entre embalagem fechada e venda por unidade.
  - Custo Unitário Real e Quantidade de Venda Total preenchidos diretamente no formulário.
  - Leitura por Câmera (`📷 Tirar Foto`) e Galeria (`🖼️ Escolher da Galeria`).

## ⚠️ Problemas Encontrados (se houver)
- Nenhum.

