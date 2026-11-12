# Sistema de Controle de Estoque e Produção — Júlia Uniformes Ateliê
 
Projeto Interdisciplinar desenvolvido pela equipe **ABCLM** (2º semestre de Gestão da Tecnologia da Informação — FATEC Barueri) em parceria com o ateliê **Júlia Uniformes**.
 
## Visão Geral
 
O Júlia Uniformes é um ateliê de confecção e venda de vestuário que comercializa seus produtos principalmente pela **Shopee**, tanto peças de pronta-entrega (pré-prontas, retiradas do estoque) quanto peças personalizadas com bordado eletrônico.
 
Hoje, o controle de estoque e o acompanhamento da produção são feitos **manualmente**, o que gera falta de materiais descoberta tarde, atrasos, confusão entre pedidos personalizados e pré-prontos e erros de tamanho, cor ou modelo.
 
Este repositório documenta o **processo operacional (AS-IS e TO-BE, modelado em BPMN)** e a **proposta de um sistema informatizado** para controlar o estoque, identificar pedidos personalizados e organizar a produção, desde o pedido do cliente até a expedição e o pós-venda.
 
## Objetivos
 
- Padronizar e dar rastreabilidade ao fluxo operacional do ateliê.
- Controlar materiais (tecidos, linhas, botões, aviamentos e embalagens) e registrar o consumo na produção.
- Emitir alertas de reposição antes que a falta de insumo interrompa a produção.
- Identificar claramente os pedidos personalizados e organizar os pedidos por prioridade.
- Registrar devoluções, trocas e ocorrências.
- Oferecer uma ferramenta acessível, pensada para quem tem pouca familiaridade com tecnologia.
## Metodologia
 
O levantamento do processo atual foi feito por **questionário aplicado à proprietária do ateliê**, que descreveu o recebimento de pedidos, o gerenciamento de materiais, a produção e o envio. A partir disso, o fluxo foi modelado em BPMN (AS-IS) e a proposta de melhoria foi desenhada (TO-BE).
 
## Diagnóstico (AS-IS)
 
Quatro pontos críticos foram identificados no fluxo atual:
 
| # | Ponto crítico | Onde aparece |
|---|---------------|--------------|
| 1 | Controle manual do estoque | Consulta de estoque de peças/material |
| 2 | Falta de materiais | Decisão "peça/material disponível?" |
| 3 | Pedidos difíceis de diferenciar | Decisão "do zero / pré-pronta?" |
| 4 | Erros de tamanho, cor ou modelo | Pós-venda, quando o cliente abre contestação |
 
Os pontos 1, 2 e 3 estão no estoque e na decisão entre tipos de peça; o ponto 4 só aparece no fim do fluxo, quando o cliente abre uma contestação. É nessa parte que um sistema de estoque pode ajudar.
 
## Proposta (TO-BE)
 
Mudanças em relação ao AS-IS:
 
- O **cliente informa e escolhe a personalização** (cor, modelo e tamanho) já no momento do pedido; se o produto for personalizado, entra em contato com o ateliê via e-commerce.
- O ateliê passa a ter a tarefa **"Verifica personalização"** antes de consultar o estoque.
- Estoque, produção, qualidade, envio e pós-venda seguem como no AS-IS.
### Onde o sistema entra
 
| Ponto | Etapa do fluxo |
|-------|----------------|
| A | Consulta de estoque de peças/material pelo ateliê |
| B | Decisão: peça/material disponível? |
| C | Registro de baixa no estoque |
| D | Compra presencial, registro de entrada e armazenamento (quando não há disponibilidade) |
 
### Hoje vs. com o sistema
 
| Hoje | Com o sistema |
|------|---------------|
| Estoque controlado manualmente | Controle de materiais e registro do uso |
| Falta de insumo descoberta tarde | Alerta de reposição |
| Sem ordem clara de produção | Pedidos organizados por prioridade |
| Confusão entre personalizado e pré-pronto | Pedidos personalizados identificados |
| Devoluções sem acompanhamento | Registro de devoluções e ocorrências |
 
## Requisitos do Sistema
 
### Requisitos funcionais
 
| Código | Requisito | Descrição |
|--------|-----------|-----------|
| RF01 | Controle de estoque | Cadastro e acompanhamento da quantidade de tecidos, linhas, botões, aviamentos e embalagens. |
| RF02 | Registro de utilização | Registro do consumo de materiais na produção, atualizando automaticamente os saldos. |
| RF03 | Alerta de reposição | Avisos visuais quando o estoque de um insumo atingir o limite mínimo. |
| RF04 | Prioridade dos pedidos | Classificação dos pedidos por prioridade para definir a ordem de produção. |
| RF05 | Pedidos personalizados | Identificação clara dos pedidos que exigem customização, diferenciando-os dos itens de pronta-entrega. |
| RF06 | Devoluções e ocorrências | Registro e consulta de trocas, devoluções e problemas vinculados aos pedidos. |
 
### Requisitos não funcionais
 
| Código | Requisito | Descrição |
|--------|-----------|-----------|
| RNF01 | Usabilidade | Interface intuitiva e de fácil navegação, adequada à rotina do ateliê. |
| RNF02 | Linguagem | Desenvolvimento em **Java**. |
| RNF03 | Dados centralizados | Informações de pedidos, estoque e produção unificadas, facilitando acesso e consulta. |
 
## Acessibilidade
 
O sistema é pensado para quem hoje controla o estoque de forma manual e tem pouca familiaridade com tecnologia:
 
- **Letras grandes:** texto fácil de ler.
- **Alto contraste:** cores fortes entre texto e fundo.
- **Botões grandes:** fáceis de distinguir, com espaço entre eles.
- **Linguagem simples:** palavras do dia a dia, sem termos técnicos.
- **Alertas claros:** cor, ícone e palavra juntos.
- **Menos erros:** poucos passos por tela e confirmação antes de remover.
## Protótipos
 
- **Protótipo inicial:** tela de controle de estoque com cadastro de produtos, ajuste de quantidades, valor total e indicação de estoque baixo.
- **Protótipo de estoque (com foco em acessibilidade):** painel com total de produtos, itens em estoque e itens que precisam ser comprados, alerta em destaque (ex.: "Os botões estão acabando. Hora de comprar!"), situação de cada item ("Tem bastante" / "Comprar logo") e botões grandes de ajuste de quantidade.
## Impactos Esperados
 
**Organizacional**
- Centralização dos dados de estoque e produção em um único ambiente, com consulta de insumos e acompanhamento de cada pedido mais ágeis.
- Registro de consumo que permite antecipar a reposição e planejar compras antes que a falta de material pare a produção.
- Ordenação dos pedidos por prioridade, reduzindo atrasos.
**Social**
- Rotina da equipe mais simples, com menos consultas a registros separados e menos problemas causados por informação desatualizada.
- Para o cliente, entrega conforme as especificações da compra, com menos trocas e devoluções.
**Acessibilidade**
- Ferramenta adequada ao perfil de quem usa, com autonomia para o ateliê.
## Escopo do Processo (BPMN)
 
O diagrama BPMN representa as raias **Cliente, E-commerce (Shopee), Ateliê, Controle de qualidade e Estoque**. O processo contempla:
 
1. **Recebimento do pedido**
   - O cliente realiza a compra na Shopee (no TO-BE, já escolhendo cor, modelo, tamanho e personalização).
   - O pedido é recebido na plataforma e integrado ao sistema Bling.
2. **Análise e preparação**
   - Verificação da personalização (TO-BE) e conferência dos dados do pedido.
   - Consulta de estoque de peças/material.
   - Decisão entre produto feito **do zero** (personalizado) ou **pré-pronto** (retirado do estoque).
3. **Produção** (peças do zero)
   - Corte de tecido, costura da peça e personalização por bordadeira eletrônica.
4. **Estoque**
   - Peça/material disponível: registro de baixa.
   - Não disponível: compra presencial (ateliê), registro de entrada e armazenamento.
5. **Qualidade**
   - Inspeção de costura, bordado, medidas, acabamento, limpeza e conformidade.
   - Não conformidade: abertura de registro e descarte ou refação da peça pelo ateliê.
6. **Finalização**
   - Passadoria e embalagem.
   - Entrega no ponto de coleta.
7. **Logística**
   - Recebimento no ponto de coleta, geração de etiqueta/despacho e envio via transportadora.
   - Recebimento do produto pelo cliente.
8. **Pós-venda**
   - O cliente abre contestação ou relata o problema; a plataforma processa a contestação.
   - O ateliê orienta a devolução e decide entre **retorno** (cancelamento do pedido e logística reversa) ou **reembolso**.
   - Encerramento do atendimento.
## Participantes (raias do BPMN)
 
| Participante | Responsabilidade |
|--------------|------------------|
| Cliente | Realizar o pedido, receber o produto e abrir solicitações pós-venda |
| E-commerce (Shopee) | Receber o pedido, integrar ao Bling, gerar etiqueta, realizar o envio e processar contestações |
| Ateliê | Verificar personalização, consultar estoque, produzir, passar, embalar, levar ao ponto de coleta e conduzir devoluções/reembolsos |
| Controle de qualidade | Inspecionar, validar e tratar não conformidades |
| Estoque | Registrar baixas e entradas, armazenar e controlar a disponibilidade de peças e materiais |
 
## Fluxos Alternativos
 
- **Produto personalizado (do zero):** corte, costura e bordado eletrônico antes da inspeção de qualidade.
- **Produto pré-pronto:** o item é selecionado diretamente do estoque e segue para qualidade e preparação para expedição.
- **Ocorrências pós-venda:** devolução com logística reversa ou reembolso, seguidos do encerramento do atendimento.
## Equipe
 
**ABCLM Team** — 2º GTI, FATEC Barueri
 
- Ana Luisa Oliveira Andrade
- Bruno Bergamasco
- Livia Torres do Nascimento
- Maria Eduarda de Araújo

**Orientador:** Prof. Vander Ribeiro Elme
**Instituição:** FATEC Barueri — Padre Danilo José de Oliveira Ohl
**Curso:** Tecnologia em Gestão da Tecnologia da Informação — Disciplina AAP1 (2026)
**Cliente parceiro:** Júlia Uniformes Ateliê, que atestou a viabilidade prática do projeto em declaração de 11/11/2026.
 
## Conclusão
 
| Diagnóstico | Proposta | Resultado esperado |
|-------------|----------|--------------------|
| O controle manual dificulta a organização do estoque e dos pedidos, favorecendo falhas, atrasos e retrabalho. | Um sistema informatizado para auxiliar no controle de materiais, na identificação de pedidos e na organização da produção. | Mais organização, eficiência e autonomia, com uma ferramenta acessível e adequada às necessidades do ateliê. |
 
## Referências
 
- SEBRAE. *Como realizar o controle de estoque de mercadorias.*
- BALLOU, Ronald H. *Logística empresarial: transportes, administração de materiais e distribuição física.* São Paulo: Atlas, 2006.
- MARTINS, Petrônio G.; LAUGENI, Fernando P. *Administração da produção.* 2. ed. São Paulo: Saraiva, 2005.
- LAUDON, Kenneth C.; LAUDON, Jane P. *Sistemas de informação gerenciais.* 11. ed. São Paulo: Pearson Prentice Hall, 2014.
- ALBERTIN, Alberto Luiz. *Administração de informática na empresa.* 5. ed. São Paulo: Atlas, 2009.
---
 
**Versão:** 1.2
**Modelagem:** BPMN (AS-IS e TO-BE)
**Objetivo:** Documentação do processo operacional do ateliê e da proposta de sistema de controle de estoque e produção.
