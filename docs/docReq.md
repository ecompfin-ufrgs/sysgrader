# SysGrader - sistema de avaliação e recomendação de equipamentos de informática do TCE-SC

## Documento de Requisitos

## 1. Introdução

Diz-se que uma configuração de hardware de um sistema computacional é **adequada** a um sistema de informação se ela é capaz de dar o suporte necessário e suficiente à execução sem falhas (inclusive no tempo de processamento) ou interrupções dos sistemas de software e aplicativos que compõem o mencionado sistema computacional bem como a evolução esperada destes nos próximos dois anos. Alternativamente, a configuração de hardware se diz **subdimensionada** se é insuficiente para as tarefas de uma configuração adequada e **superdimensionada** se superior à configuração adequada.  Nesse sentido, dada uma lista de sistemas de software e de aplicativos, pode-se determinar a adequação ou não de uma determinada configuração de hardware.

No contexto de auditoria externa, TCE-SC propôs um Desafio com a demanda de uma proposta técnica de Prova de Conceito (PoC) para determinar a adequação de configurações de hardware definidas por seus auditados em licitações.  Adicionalmente, o aplicativo poderia em versões futuras determinar superfaturamento na compra de uma dada configuração e mensurar o risco de superfaturamento em uma dada licitação em curso.

O objetivo deste trabalho é apresentar os requisitos elicitados pela Bulzai Inteligência Artificial por meio de reuniões realizadas com as equipes do TCE-SC e do LinkLab para um aplicativo partir de agora denominado **SysGrader** cuja tarefa precípúa consiste em avaliar e recomendar configurações de hardware para o [Tribunal de Contas do Estado de Santa Catarina](https://www.tcesc.tc.br/) e para seus auditados.

A organização do texto é a seguinte.  A seção 2 apresenta a definição do sistema, a seção 3 mostra os requisitos de usuário e do sistema definido ao passo que a seção 4 revela os requisitos de software para o **SysGrader**.  A seção 5 tece as considerações finais, encerrando o trabalho.

## 2. Definição de sistema

A avaliação de uma configuração de hardware tal como realizada atualmente pelo TCE-SC consiste em verificar se este atende às exigências mínimas dos fabricantes dos sistemas de software e aplicativos que deverão ser executados pelo hardware em questão.  Tal tarefa pode ser dividida em:

- determinar a lista de sistemas de software e aplicativos que deverão ser executados;
- buscar a exigência mínima recomendada pelo fabricante de cada sistema ou aplicativo requerido para cada tipo de hardware (cpu, memória, hd etc), e
- escolher como configuração exigida a configuração mais exigente entre todos os sistemas e aplicativos.

Este processo requer a entrada da lista de softwares, a consulta a uma base de dados de hardware mínimo exigido para cada software e a escolha, para cada software, da especificação de hardware mais poderosa por tipo de hardware.  Por exemplo, se o aplicativo A exige um processador com clock mínimo de 3,6 GHz e memória RAM mínima de 32GB e o aplicativo B exige um processador com clock mínimo de 3,3 GHz e memória RAM minima de 64GB, então a configuração adequada requer um processador com clock mínimo de 3,6 GHz e memória RAM mínima de 64GB, isto é, o mínimo exigido por cada software para cada tipo de hardware.

Observe-se também que, por vezes, os fabricantes de software incluem, além da configuração mínima, uma configuração recomendada.  Neste caso, a avaliação deve ser feita com base na configuração recomendada para evitar falhas decorrentes tanto da interação entre os softwares quanto do desempenho esperado dos mesmos.

Por fim, tem-se que os principais usuários do aplicativo são os auditores do TCE-SC e também as prefeituras do município de Santa Catarina

## 3. Especificação de requisitos de sistema

Em vista da definição realizada na seção anterior, listamos a seguir os requisitos do usuário e do sistema.

### 3.1. Requisitos de usuário

#### Requisito RU1 - avaliação de configurações de hardware

O *SysGrader* deverá ser capaz de avaliar configurações de hardware com base em softwares de prateleira.

#### Requisito RU2 - recomendação de configurações de hardware

O *SysGrader* deverá ser capaz de recomendar configurações de hardware com base em softwares de prateleira.

#### Requisito RU3 - adequação do hardware

O *SysGrader* deverá informar se uma configuração de hardware avaliada está subdimensionada, adequada ou superdimensionada.

### 3.2. Requisitos de sistema

#### Requisitio RS1 - acesso ao *SysGrader*

O acesso ao *SysGrader* deverá ser feito por meio da Web.

#### Requisito RS2 - opções de avaliar ou recomendar configurações de hardware

O *SysGrader* deverá possuir um menu para determinar se o usuário deseja avaliar uma configuração de hardware ou obter uma recomendação para configuração adequada de hardware.

#### Requisito RS3 - avaliação de configuração de hardware

A avaliação de configuração de hardware deverá apresentar um menu com as especificações dos tipos de hardware, tipos de software e informar se a configuração de hardware está subdimensionada, adequada ou superdimensionada.

#### Requisitio RS4 - recomendação de configuração de hardware

A recomendação de configuração de hardware deverá apresentar um menu com os tipos de softwares que deverão ser executados e informar a configuração de hardware adequada.


#### Requisitio RS5 - base de dados de tipos de software

O *SysGrader* deverá possuir uma base de dados atualizada de tipos de software a serem executados.

#### Requisitio RS6 - base de dados de especificações de tipos de hardware

O *SysGrader* deverá possuir uma base de dados atualizada com especificações para diferentes tipos de hardware.

## 4. Especificação de requisitos de software

### 4.1. Requisitos funcionais

### 4.2. Requisitos não funcionais

#### Requisito RNF1 - sistema web

O *SysGrader* deverá ser executado em plataforma web.

#### Requisito RNF2 - hospedagem externa à infra-estrutura TCE-SC

O *SysGrader* deverá ser executado fora da infra-estrutura TCE-SC.

## 5. Considerações finais
