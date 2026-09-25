# Especificações do Projeto

Esta parte do documento apresenta a especificação do problema e da solução sob a perspectiva do
usuário, a partir dos dados de contextualização levantados na Sprint 1 (observações de campo em
barbearias, manicures e pequenos mercados, entrevistas e pesquisa Sebrae 2025). Foram utilizadas
as seguintes técnicas:

• Personas, para representar de forma concreta os perfis de MEI identificados na pesquisa;

• Histórias de Usuário, para traduzir as dores e objetivos das personas em necessidades funcionais do sistema, agrupadas por contexto;

• Levantamento de Requisitos Funcionais (RF) e Não Funcionais (RNF), derivados diretamente
das histórias de usuário e dos 5 processos de negócio já mapeados na Sprint 1;

• Técnica de priorização MoSCoW, adaptada
para as categorias ALTA, MÉDIA e BAIXA, usada para classificar cada requisito conforme seu impacto
direto nas três dores centrais do projeto;

• Restrições do projeto, delimitando o escopo viável dentro do contexto acadêmico e do público-alvo.

## Personas

## Persona 1 — Carlos Eduardo (dono de barbearia)

Carlos tem 34 anos e é MEI há 3 anos, dono de uma barbearia de bairro onde atende sozinho.
Trabalha das 9h às 20h, sem tempo para "sentar e organizar planilha". Anota os cortes do dia em um
caderno e controla os produtos (pomadas, lâminas, toalhas) de memória. Já perdeu vendas por falta
de produto em estoque e não sabe dizer, com certeza, quanto lucrou no mês passado. Usa o
WhatsApp o dia inteiro para marcar horários com clientes, mas nunca usou nenhum aplicativo de
gestão porque "são complicados demais para quem trabalha sozinho".

## Persona 2 — Marcela Silva (manicure autônoma

Marcela tem 29 anos, é manicure MEI e atende em um salão compartilhado e também em domicílio.
Compra esmaltes, lixas e produtos descartáveis com frequência, mas não tem noção clara de quanto
gasta em material por mês nem de qual produto está "parado". Registra os agendamentos no
WhatsApp Business, mas o controle financeiro é feito, quando é feito, em anotações soltas no celular.
Se sente sobrecarregada tentando lembrar de anotar tudo entre um atendimento e outro.

## Persona 3 — Sebastião Almeida (dono de pequeno mercado)

Sebastião tem 52 anos, é MEI há 10 anos e administra um pequeno mercado de bairro com a ajuda
ocasional da esposa. Tem baixa familiaridade com tecnologia e desconfia de aplicativos "cheios de
telas". Sofre com produtos parados na prateleira e com rupturas de itens que vendem bem, pois não
tem nenhum sistema de controle de estoque — apenas a experiência para "sentir" o que está faltando.
Já tentou usar uma planilha, mas abandonou por achar trabalhoso demais no dia a dia.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|EU COMO... | QUERO/PRECISO ...  |PARA ...                  |
|--------------------|------------------------------------|----------------------------------------|
|MEI  | cadastrar meus produtos/materiais com nome, categoria, preço de custo, preço devenda e quantidade inicial           | ter meu estoque organizado desde o início               |
|MEI       | registrar uma venda em poucos segundos                 | não abandonar o registro no meio da correria do dia |
|MEI       | que o estoque seja atualizado automaticamente após uma venda                 | não precisar contar os produtos manualmente |
|MEI       | registrar a compra/reposição de produtos vindos de um fornecedor                 | manter meu estoque sempre atualizado |
|MEI       | que o sistema calcule automaticamente o lucro de cada venda                 | saber se estou lucrando sem precisar fazer conta |
|MEI       | receber um relatório semanal automático pelo WhatsApp                 | saber meu desempenho sem precisar abrir um aplicativo |
|MEI sem conhecimento técnico       | cadastrar um produto de forma simples e rápida                 | não perder tempo nem desistir do sistema |

## Requisitos

Os requisitos foram priorizados segundo o critério MoSCoW: requisitos que atacam diretamente uma
das três dores centrais (desorganização financeira, falta de controle de estoque, sobrecarga mental)
e/ou viabilizam a proposta de valor central ("relatório proativo sem abrir o app") foram classificados
como ALTA; requisitos que agregam valor mas não são indispensáveis ao MVP foram classificados
como MÉDIA; e requisitos de conveniência, adiáveis para versões futuras, como BAIXA.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir o cadastro de produtos/materiais (nome, categoria, preço de custo,preço de venda, quantidade inicial) | ALTA | 
|RF-002| Permitir o registro de vendas, com baixa automática no estoque e cálculo do lucro da operação   | ALTA |
|RF-003| Permitir o registro de compras/reposição de produtos junto a fornecedores, atualizando o estoque   | ALTA |
|RF-004| Calcular automaticamente indicadores financeiros (lucro, faturamento, produtos parados)   | ALTA |
|RF-005| Gerar e enviar automaticamente um relatório semanal consolidado via WhatsAppo   | ALTA |
|RF-006| Emitir alertas proativos de estoque crítico/baixo   | ALTA |
|RF-007| Emitir alertas sobre produtos parados/sem giro   | MÉDIA |
|RF-008| Emitir alertas sobre quedas relevantes no desempenho de vendas   | MÉDIA |
|RF-009| Permitir a consulta do estoque atual diretamente pelo WhatsApp   | MÉDIA |
|RF-0010| Permitir o cadastro de fornecedores associados aos produtos   | BAIXA |



### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| A interface deve ser simples, intuitiva e de baixa curva de aprendizado, acessível a MEIs sem conhecimento técnico (usabilidade) | ALTA | 
|RNF-002| Os relatórios e alertas devem ser entregues via WhatsApp Business, sem exigir que o usuário abra um aplicativo separado (interoperabilidade) |  ALTA |
|RNF-003| O registro de uma venda ou compra deve poder ser concluído em poucos segundos (usabilidade/desempenho) |  ALTA | 
|RNF-004| O sistema deve ser responsivo, funcionando corretamente em dispositivos móveis |  MÉDIA | 
|RNF-005| Os dados financeiros e de estoque do MEI devem ser armazenados de forma segura (segurança) |  MÉDIA | 
|RNF-006| O sistema deve processar as requisições do usuário em no máximo 3 segundos (desempenho) |  BAIXA | 

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend, conforme diretriz do trabalho interdisciplinar        |
|03| O canal principal de comunicação com o usuário deve ser o WhatsApp Business, já utilizado no dia a dia do MEI        |
|04| A solução deve manter baixa complexidade técnica, sendo utilizável por empreendedores sem conhecimento em tecnologia        |
|05| O escopo do MVP deve se restringir às três dores centrais identificadas na pesquisa (financeiro, estoque, sobrecarga mental de registro)        |

