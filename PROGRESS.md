# Registro de Progresso - Caixa Freitas (Calculadora v2)

## 📌 Última Atualização
- **Data e Hora da Mudança / Conclusão**: 22/07/2026 14:26 (Horário de Brasília)
- **Tempo Estimado Gasto**: 10 minutos

## 📝 Arquivos Modificados
- [`index.html`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/index.html):
  - Estrutura Rígida de Leitura: Implementado isolamento estrito da coluna `[CÓDIGO]` (primeiro número de 3-4 dígitos) para não ser confundido com a `[QUANTIDADE COMPRADA]` (número logo após o código e antes da descrição).
  - Suporte a Multiplicadores `C/12`, `C/15`, `C/18`, `C/24`: Cálculo automático da quantidade total de vendas (`Quantidade Comprada x Multiplicador`) e recalculo do Preço de Custo Unitário por item (ex: 3 CX x 12 UD = 36 unidades, R$ 66,00 / 12 = R$ 5,50/unidade).
  - Proteção de Expressões de Volume/Peso: Preservação de termos como `1 LT`, `1LT`, `2KG`, `600G`, `84 G`, `500 ML` sem que números de litragem/peso sejam mesclados com o código ou quantidade.
- [`PROGRESS.md`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/PROGRESS.md): Atualizado o registro de status e alterações do projeto.

## 🛠️ Problemas Corrigidos
- Impedido que o código do produto (ex: 774, 307, 238, 828) fosse lido como quantidade.
- Impedida a união indevida do volume (ex: 1 LT) com o código de produto (gerando 178).
- Ajustado o cálculo de fardos e caixas com anotador `C/12`, `C/15`, `C/18`.

## 📊 Status Atual do Sistema
- **Status**: Operacional e Otimizado
- **Recursos Ativos**:
  - Parser com extração rígida de colunas `[CÓDIGO] [QTD] [DESCRIÇÃO] [UND] [VL_UNITARIO] [VL_TOTAL]`.
  - Recalculo dinâmico de volumes de caixa (`C/12`, `C/15`, `C/18`) para unidades reais e custo individual.
  - Preservação intacta de litragens e gramaturas no nome do produto.
  - Dois botões de aquisição (`📷 Tirar Foto` e `🖼️ Escolher da Galeria`).

## ⚠️ Problemas Encontrados (se houver)
- Nenhum.
