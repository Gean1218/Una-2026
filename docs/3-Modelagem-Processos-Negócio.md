## 3. Modelagem dos Processos de Negócio


> **Links Úteis**:
> - [Modelagem de Processos AS-IS x TO-BE](https://dheka.com.br/modelagem-as-is-to-be/)
> - [20 Dicas Práticas de Modelagem de Processos](https://dheka.com.br/20-dicas-praticas-de-modelagem-de-processos/)

### 3.1. Modelagem da situação atual (Modelagem AS IS)

O projeto propõe o desenvolvimento de um aplicativo de gestão financeira e de estoque para Microempreendedores Individuais (MEIs), integrado ao WhatsApp Business para o envio automático de relatórios e alertas. A solução busca simplificar o controle das operações diárias, reduzir a desorganização financeira e evitar a perda de informações causada por registros manuais.

Os processos do negócio foram identificados com base nas observações realizadas em barbearias, manicures e pequenos mercados, nas entrevistas com empreendedores e nos requisitos levantados pelo grupo. Para compreender o funcionamento da solução, os processos foram classificados em primários, de suporte e gerenciais, conforme sua finalidade no atendimento às necessidades do empreendedor.

| Processo | Classificação | Descrição |
|---|---|---|
| Cadastro de produtos | Suporte | Permite cadastrar produtos e materiais, informando nome, categoria, preço de custo, preço de venda e quantidade inicial, estabelecendo a base para o controle do estoque. |
| Registro de vendas | Primário | Registra as vendas realizadas pelo MEI, atualiza automaticamente as quantidades em estoque e calcula o lucro de cada operação. |
| Registro de compras e reposição | Primário | Registra a aquisição de produtos e materiais junto aos fornecedores, atualizando o estoque disponível. |
| Geração de relatório semanal via WhatsApp | Gerencial | Consolida as informações da semana, incluindo vendas, faturamento, lucro e situação do estoque, enviando os resultados ao empreendedor pelo WhatsApp Business. |
| Alertas e notificações proativas | Gerencial | Identifica situações que exigem atenção, como estoque baixo, produtos sem movimentação e quedas relevantes no desempenho das vendas, notificando o empreendedor. |

####  Descrição macro dos processos

Os processos estão relacionados entre si. O cadastro de produtos estabelece os dados iniciais necessários para controlar o estoque. A partir desse cadastro, o empreendedor registra as vendas e as compras, permitindo que o sistema mantenha as quantidades atualizadas e reúna informações financeiras. Com base nesses registros, a solução calcula indicadores, identifica situações que exigem atenção e envia relatórios e alertas pelo WhatsApp Business.

Entradas, saídas, participantes e produtos de informação

| Processo | Entradas | Saídas | Onde acontece | Participantes | Produtos de informação |
|---|---|---|---|---|---|
| Cadastro de produtos | Nome, categoria, preço de custo, preço de venda e quantidade inicial | Produto cadastrado | Interface do aplicativo | MEI e sistema | Cadastro de produtos e estoque inicial |
| Registro de vendas | Produto vendido, quantidade e valor da venda | Venda registrada, estoque atualizado e lucro calculado | Interface do aplicativo | MEI, cliente final e sistema | Registro de venda, saldo de estoque e resultado da operação |
| Registro de compras e reposição | Produtos adquiridos, quantidades e dados da compra | Compra registrada e estoque atualizado | Interface do aplicativo | MEI, fornecedor e sistema | Registro de compra e saldo atualizado do estoque |
| Geração de relatório semanal via WhatsApp | Registros de vendas e compras, dados de estoque e indicadores calculados | Relatório semanal enviado ao empreendedor | Sistema e canal WhatsApp Business | Sistema, bot de WhatsApp e MEI | Relatório de faturamento, lucro, movimentação e situação do estoque |
| Alertas e notificações proativas | Dados de estoque, movimentações de produtos e indicadores de vendas | Notificações enviadas ao empreendedor | Sistema e canal WhatsApp Business | Sistema, bot de WhatsApp e MEI | Alertas de estoque baixo, produtos parados e queda nas vendas |

#### Participantes do processos
Os participantes identificados no levantamento são:

MEI/empreendedor: usuário principal, responsável por cadastrar produtos, registrar vendas e compras e acompanhar as informações do negócio.

Cliente final: participa das operações comerciais ao realizar compras, gerando os dados necessários para o registro das vendas.

Fornecedor: fornece produtos e materiais adquiridos pelo MEI, originando as informações de entrada e reposição de estoque.

Aplicativo/sistema: organiza os dados registrados, atualiza o estoque, calcula indicadores financeiros e identifica situações que exigem atenção.

Bot de WhatsApp Business: atua como canal de comunicação, enviando relatórios semanais e alertas proativos ao empreendedor.
Os processos produzem informações que precisam ser armazenadas e relacionadas para permitir o funcionamento integrado da solução. Entre os principais produtos de informação estão os cadastros de produtos, os registros de vendas e compras, os saldos de estoque, os indicadores financeiros, os relatórios semanais e as notificações.

#### Produtos de Informação e Relação com Arquitetura de softaware

Essas informações orientam a futura organização dos dados do sistema, incluindo entidades como Produto, Venda, Item de Venda, Compra, Item de Compra e Fornecedor, além dos dados necessários para gerar relatórios e alertas. Os relacionamentos definitivos e os atributos de cada entidade deverão ser estabelecidos conforme as regras de negócio e os requisitos funcionais do projeto.

A definição dos processos também permite identificar os usuários que interagem com o sistema e as informações que cada operação precisa receber e produzir. Como o projeto possui a restrição de não desenvolver um módulo de backend próprio, a implementação deverá respeitar o escopo acadêmico definido pelo grupo, sem pressupor uma arquitetura técnica que contrarie essa limitação.





### 3.2. Descrição geral da proposta (Modelagem TO BE)

A solução proposta é um aplicativo de gestão financeira e de estoque voltado a Microempreendedores Individuais (MEIs), integrado ao WhatsApp Business para o envio automático de relatórios e alertas sobre a situação do negócio.

Ela substitui registros manuais em cadernos, anotações dispersas no celular e controles feitos apenas de memória por processos digitais simples, rápidos e integrados. No aplicativo, o empreendedor cadastra produtos e materiais, registra vendas e compras e acompanha as movimentações. Com base nesses registros, o sistema atualiza o estoque, calcula indicadores financeiros e identifica situações que exigem atenção.

O bot de WhatsApp Business complementa o aplicativo com relatórios semanais e notificações proativas sobre estoque baixo, produtos sem movimentação e quedas relevantes nas vendas. Assim, o acompanhamento do negócio deixa de depender exclusivamente de o usuário abrir o aplicativo para consultar informações importantes.

#### Gargalos do AS IS e melhorias propostas no TO BE

No cenário atual (AS IS), o controle financeiro e de estoque é feito manualmente, em cadernos, anotações no celular ou de memória. Isso dificulta a consolidação das informações, aumenta o risco de erros e transforma o acompanhamento do negócio em mais uma tarefa na rotina. No modelo TO BE, esses controles passam a ser digitais e integrados, com atualização automática de dados, geração de indicadores e envio de notificações.

| Gargalo do cenário atual (AS IS) | Solução proposta (TO BE) | Oportunidade de melhoria |
|---|---|---|
| Cadastro e controle de produtos em anotações dispersas | Centralizar o cadastro de produtos e materiais no aplicativo | Facilitar a consulta e a organização dos produtos |
| Registro manual de vendas, sujeito a esquecimentos | Registro rápido de vendas com atualização automática do estoque | Reduzir retrabalho, erros de registro e divergências de quantidade |
| Compras e reposições sem controle sistemático | Registro de compras com atualização automática do estoque | Melhorar a visibilidade dos produtos disponíveis e das necessidades de reposição |
| Dificuldade para calcular faturamento e lucro | Consolidação dos registros e cálculo automático dos indicadores | Facilitar a compreensão dos resultados e apoiar decisões |
| Necessidade de abrir aplicativos ou conferir anotações para acompanhar o negócio | Envio de relatórios semanais pelo WhatsApp Business | Reduzir o esforço de acompanhamento do desempenho |
| Falta de percepção antecipada de problemas no estoque ou nas vendas | Alertas proativos sobre situações críticas | Permitir que o empreendedor identifique problemas e aja com antecedência |

#### Limites da Solução 
Apesar dos benefícios, a solução tem limites que precisam ser considerados no desenvolvimento e no uso do sistema:

 - Dependência dos registros realizados: a qualidade dos indicadores e das informações de estoque depende do cadastro correto dos produtos e do registro das vendas e compras. Operações não registradas podem gerar divergência entre o estoque real e o estoque informado pelo sistema.
 - Escopo funcional limitado: o produto mínimo viável (MVP) atende às três dores centrais identificadas no levantamento:        desorganização financeira, falta de controle de estoque e sobrecarga mental com registros manuais. Não se pretende cobrir todas as necessidades administrativas de uma empresa.
 - Dependência do WhatsApp Business: o envio de relatórios e alertas depende da disponibilidade do canal e das condições necessárias para a integração.
 - Necessidade de simplicidade: a interface deve priorizar operações rápidas e objetivas, evitando funcionalidades complexas que aumentem a curva de aprendizado do público-alvo.
 - Restrição técnica e acadêmica: por definição do grupo, o projeto não terá módulo de backend próprio, e a implementação deve se ater a essa limitação e às tecnologias disponíveis para a entrega acadêmica.
 - Limites dos indicadores: os resultados são calculados a partir dos dados registrados. Os relatórios não substituem uma análise contábil completa nem garantem, isoladamente, decisões comerciais corretas.



### 3.3. Modelagem dos processos

[PROCESSO 1 - Nome do Processo](./processos/processo-1-nome-do-processo.md "Detalhamento do Processo 1.")

[PROCESSO 2 - Nome do Processo](./processos/processo-2-nome-do-processo.md "Detalhamento do Processo 2.")

[PROCESSO 3 - Nome do Processo](./processos/processo-3-nome-do-processo.md "Detalhamento do Processo 3.")

[PROCESSO 4 - Nome do Processo](./processos/processo-4-nome-do-processo.md "Detalhamento do Processo 4.")
