# Registro de Progresso - Caixa Freitas (Calculadora v2)

## 📌 Última Atualização
- **Data e Hora da Mudança / Conclusão**: 22/07/2026 14:15 (Horário de Brasília)
- **Tempo Estimado Gasto**: 15 minutos

## 📝 Arquivos Modificados
- [`index.html`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/index.html):
  - Interface: Adicionados dois botões distintos (`📷 Tirar Foto` com `capture="environment"` e `🖼️ Escolher da Galeria` sem `capture`).
  - Parser OCR: Suporte avançado a cupons térmicos de distribuidora com estrutura em duas linhas (Linha 1: Descrição, Linha 2: Fórmula `QTD UN x VL_UNITARIO`).
  - Formatos Numéricos: Tratamento de numeração brasileira e americana (ex: `8.000 UN x 2.75` ou `8,000 UN x 2,75`).
  - Regra de Fardos/Multiplicadores: Suporte a `10X120G`, `10X100G`, `10X62G`, `24X350ML` na descrição para recalcular quantidade total de unidades e o preço de custo unitário.
  - Filtro de Cabeçalhos/Rodapés: Filtro ampliado para ignorar termos de distribuidoras (`BUZIM DISTRIBUIDORA`, `VENDA SIMPLES`, `NAO E DOCUMENTO FISCAL`, `SUBTOTAL`, `TOTAL`, `DINHEIRO`, `DADOS PARA ENTREGA`, `TRIBUTOS`).
- [`PROGRESS.md`](file:///Users/thiagoviniciusdefreitas/Documents/calculadora-v2/PROGRESS.md): Atualizado o registro de status e alterações do projeto.

## 🛠️ Problemas Corrigidos
- Adicionada opção explícita de escolher foto da galeria do celular.
- Leitura e conversão perfeita de cupons térmicos em duas linhas típicos de distribuidoras alimentícias.

## 📊 Status Atual do Sistema
- **Status**: Operacional e Atualizado
- **Recursos Ativos**:
  - Dois botões nativos na interface (`📷 Tirar Foto` e `🖼️ Escolher da Galeria`).
  - Parser inteligente para cupons térmicos de distribuidora (estrutura de 2 linhas).
  - Normalização automática de números PT-BR e EN (vírgulas e pontos decimais).
  - Decomposição de fardos e pacotes promocionais (`10X120G`, etc.).
  - Preenchimento e seletor rápido de itens lidos.

## ⚠️ Problemas Encontrados (se houver)
- Nenhum.
