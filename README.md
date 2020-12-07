# TESTES AUTOMATIZADOS COM JMETER & ELASTICSEARCH

[![Me pague um ☕ ](https://img.shields.io/badge/Buy%20me%20a%20%E2%98%95%20-%20Patreon%20-yellowgreen)](https://paypal.me/ciberninjas "Paga um café para nos")
[![Github](https://img.shields.io/badge/creator-alexyucra-red)](https://github.com/diggleweb)
[![Data de documentação no Github](https://img.shields.io/badge/created-November%202020-orange)]()

**inicio**
```
┈┈┈╲┈┈┈┈╱┈┈┈┈
┈┈┈╱▔▔▔▔╲┈┈┈┈
┈┈┃┈▇┈┈▇┈┃┈┈┈
╭╮┣━━━━━━┫╭╮┈
┃┃┃lexdev┃┃┃┈
╰╯┃┈┈┈┈┈┈┃╰╯┈
┈┈╰┓┏━━┓┏╯┈┈┈
┈┈┈╰╯┈┈╰╯┈┈┈┈
```
___
## Histórico de revisões
| Versão | Author | Descrição | Data |
| --- | --- | --- | --- |
| 1.0.0 | Alex Yucra | Base de conhecimento sobre elasticsearch e Apache Jmeter | Novembro 2020 |
| ... |
| ... |
| ... |
| ... |
| ... |
| ... |

___

## Índice

1. [Introdução](#introdução)

    1.1 [Objetivos](#objetivos) 

    1.2 [Guia de informação](#guia-de-informação)

    1.3 [Escopo](#escopo)

    1.4 [Identificação do Projeto](#identificação-do-projeto)

2. [Requisitos a Testar](#requisitos_a_testar)

    2.1 [Teste de Banco de Dados](#teste-de-banco-de-dados)

    2.2 [Teste Funcional](#teste-funcional)

    2.3 [Teste do Ciclo de Negócios](#teste-do-ciclo-de-negócios)

    2.4 [Teste de Interface de usuário](#teste-de-interface-de-usuário)

    2.5 [Perfil da Performance](#perfil-da-performance)

    2.6 [Teste de Carga](#teste-de-carga)

    2.7 [Teste de Stress](#teste-de-stress)

    2.8 [Teste de Volume](#teste-de-volume)
    
    2.9 [Teste de Segurança e de Controle de Acesso](#teste-de-segurança-e-de-controle-de-acesso)

    2.10 [Teste de Falla/Recuperação](#teste-de-falla/recuperação)
    
    2.11 [Teste de instalação](#teste-de-instalação)

3. [Estratégia de Teste](#estratégia-de-teste)

    3.1 [Tipos de Teste](#tipos-de-teste)

    * [Teste de Integridade de banco de Dados](#teste-de-integridade-de-banco-de-dados)

    * [Teste de Performance](#teste-de-carga)

    * [Teste de Carga](#teste-de-carga)

    3.2 [Ferramentas](#ferramentas)

4. [Recursos](#recursos)

    4.1 [Trabalhadores](#trabalhadores)

    4.2 [Sistema](#sistema)

5. [Cronograma](#cronograma)
6. [Evidências e paso a paso dos teste](#evidencias-de-teste)
7. [Conclusão](#conclusão)
8. [Bibliografía](#bibliografía)


<!-- + [Páginas de Programación](/readme.md#histórico) -->
___

## Introdução

#### Objetivos
Este projeto tem os seguintes objetivos:
+ Recopilar e documentar informações para realizar teste automatizados nos servidores `ElasticSearch` com a ferramenta open source `Apache JMETER`.
+ Listar os requisitos a testar.
+ recomendar e descrever as estratégias de teste a serem empregadas.
+ Identificar os recursos necessários e prever uma estimativa dos esforços de teste.
+ Listar os elementos resultantes do projeto de testes.

#### Guia de Informação
Informações uteis: [Guía de informação](guia_informacao.md#Teste-de-performance)

#### Escopo

Os servidor ElasticSearch passará pelos teste de performance e stress, os testes de performance vao lidar com a qualidade das bases de dados dos logs da `Sac Digital`.

Os testes de performance serão realizadas num servidor ElasticSearch virtual localmente montado em ambiente Docker, para criação dos scripts de performance e stress, posteriormente estos scripts poderão ser usados nos testes reais dos servidores ElasticSearch. 

As funções que serão testadas:

+ Teste de indexação de dados [ Indexação de dados em elastic ](paso-a-paso.md#indexação-de-dados-em-elastic)

+ Teste de buscas com diferentes dados [ Busca e Filtros de dados em elastic ](paso-a-paso.md#buscas-de-dados-em-elasticsearch)


<!-- fin objetivo do artigo -->
[🔝 Voltar ao Inicio](#índice)
___
#### Identificação do Projeto
| Documento | Criado ou Disponível | Recebido ou Revisado
| --- | --- | --- |
| Especificação de requisitos | `[X] Sim` `[] Não` | `[] Sim` `[] Não` |
| Plano de Projeto | `[X] Sim` `[] Não` | `[] Sim` `[] Não` |
| Modelo de Análise | `[X] Sim` `[] Não` | `[] Sim` `[] Não` |
| Modelo de Projeto | `[X] Sim` `[] Não` | `[] Sim` `[] Não` |
| Documento de Arquitetura | `[X] Sim` `[] Não` | `[] Sim` `[] Não` |
| Protótipo | `[] Sim` `[X] Não` | `[] Sim` `[] Não` |
| Manual do usuário | `[] Sim` `[X] Não` | `[] Sim` `[] Não` |
| Lista de Riscos | `[] Sim` `[X] Não` | `[] Sim` `[] Não` |

<!-- fin objetivo do artigo -->
[🔝 Voltar ao Inicio](#índice)
___
# Requisitos a Testar
A lista abaixo identifica os items que serão testados.

#### Teste de Banco de Dados
+ Verifique que as informações do contato podem ser cadastrados e buscados.

#### Teste Funcional
Nenhum

#### Teste do Ciclo de Negócios
Nenhum

#### Teste de Interface de usuário
Nenhum

#### Perfil da Performance
+ Verifique o tempo de resposta da rede interna, do servidor em relação aos terminais.
+ Verifique o tempo de consulta/atualização do subsistema de informações úteis.
+ Verifique que o tempo de resposta para operações que envolvam dados multimídia (imagens, videos, etc.) não ultrapassam 30 segundos.

#### Teste de Carga
+ Verificar a resposta do sistema com 10 usuários.
+ Verificar a resposta do sistema com 100 usuários.
+ Verificar a resposta do sistema com 400 usuários.
+ Verificar a resposta do sistema com 500 usuários.
+ Verificar a resposta do sistema com 700 usuários.
+ verificar a resposta do sistema com 1000 usuários.

#### Teste de Stress
+ Verificar taxa de erros para indexar 1000 requisições em 10 segundos com 
+ Verificar taxa de erros para indexar 700 requisições em

#### Teste de Volume
Nenhum

#### Teste de Segurança e de Controle de Acesso
Nenhum

#### Teste de Falla/Recuperação
Nenhum

#### Teste de instalação
Nenhum

<!-- fin objetivo do artigo -->
[🔝 Voltar ao Inicio](#índice)
___
# Estratégia de Teste
## Tipos de Teste

    Nota: as transações abaixo se referem ás "transações lógicas de negócio".
    Essas transações são definidas como funções especificas que um usuário final do sistema 
    é suposto de executar ao usar a aplicação, tais como indexar ou buscar uma informação.


### Teste de Integridade de banco de Dados
|  | |
| --- | --- |
| `Objetivo do Teste:` | Garantir que ós métodos e processos de acesso ao banco de dados funcionam apropriadamente e sem corrupção dos dados. |
| `Técnica:` | <p> Invocar cada método e processo de acesso ao banco de dados, alimentando cada um com dados ou requisições de dados validos e inválidos. </p> <p> Inspecionar o banco de dados para garantir que os dados foram populados como pretendido, que todos os eventos do banco de dados ocorreram apropriadamente, ou revisar os dados retornados para garantir que os dados corretos foram recuperados pelas razões corretas. </p> |
| `Critério de finalização:` | Todos os métodos e processos de acesso á base de dados funcionam como projetados e sem nenhuma corrupção de dados. |
| `Considerações Especiais:` | <p> </p> |

### Teste de Performance

| | |
| --- | --- |
| `Objetivo de Teste:` | |
| `Técnica:` | |
| `Critério de Finalização:` | |
| `Considerações Especiais:` | | 

### Teste de Carga

| | |
| --- | --- |
| `Objetivo de Teste:` | Verifique o tempo de resposta para as transações designadas ou casos de negócio sob condições variantes de carga de trabalho. |
| `Técnica:` | Implementar script de teste para as funções de indexar e buscar dados no servidor ElasticSearch |
| `Critério de Finalização:` |  |
| `Considerações Especiais:` | <p> * O teste de carga debe ser executado em um máquina dedicada para mesuração precisa. <br> * O servidor ElastiSearch debe ser dedicado para teste real e disponibilizar  um porta teste de carga. </p>|

## Ferramentas
As seguintes ferramentas serão empregadas para esse projeto:

| Ferramentas | Uso |
| --- | --- |
| Apache JMeter 5.3 | Ferramenta para realizar teste de desempenho|
| Cerebro | Monitorar servidor ElasticSearch
| ElasticSearch Head | Extensão crome para monitor ElasticSearch 

<!-- fin objetivo do artigo -->
[🔝 Voltar ao Inicio](#índice)
___
# Recursos
#### Trabalhadores

| Trabalhador | Recursos mínimos recomendados | Responsabilidades Especificas ou Comentários |
| --- | --- | --- |
| Test Designer | Alex Yucra | <p>Identifica, prioriza, e implementa os casos de teste.</p> `Responsabilidades:` <p> * gera o plano de teste <br> * cria o modelo de teste <br> * avalia efetividade do esforço de teste </p> |
| Testador | Alex Yucra | <p> Executa os testes. </p> `Responsabilidades:` <p> * executar os testes <br> * registrar os resultados <br> * restabelecer-se dos erros <br> * documentar solicitações de mudança </p> |

#### Sistema
A tabela seguinte expõe os recursos do sistema para o projeto de teste.

| Recursos do Sistema |
| --- |
| <p> Servidor de Banco de Dados <br> `ElasticSearch 1.10 in docker` </p> |
| <p> Terminais Clientes <br> `macOS 10.14` </p> |
| <p> Repositório de Testes <br> `Nenhum` </p> |


<!-- fin recursos -->
[🔝 Voltar ao Inicio](#índice)
___
# Cronograma
| | Data de inicio | Data de término |
| --- | :---: | :---: |
| Planear Teste | 30/11/2020 | 30/11/2020 |
| Projetar Teste |  |  |
| Implementar Teste |  |  |
| Executar Teste |  |  |
| Avaliar Teste |  |  |

<!-- fin cronograma -->
[🔝 Voltar ao Inicio](#índice)
___
# Evidências de teste

[ Indexação de dados em elastic ](paso-a-paso.md#indexação-de-dados-em-elastic)

<!-- fin evidencias de teste -->
[🔝 Voltar ao Inicio](#índice)
___
## Conclusão

Este artigo apresentou um padrão de documentação de teste de software, que pode ser aplicado em um processo de software já existente, ou utilizado no desenvolvimento de um processo próprio, o padrão de documentação foca nos items de implementação de ferramentas de testes  para monitorar e testar um servidor com ElasticSearch em ambiente virtual local, a fim de conseguirmos nosso conhecimento com a performance do ElasticSearch.

<!-- fin conclusão -->
[🔝 Voltar ao Inicio](#índice)
___

## Bibliografía

- Tag de documentação [https://shields.io](https://shields.io/)
- Testes de  performance com JMeter [-->link](https://medium.com/@samuellucas/primeiros-passos-com-testes-de-performance-e-jmeter-a96b4db360ab)
- Install JMeter on MAC [--> link](https://psychowhiz.medium.com/install-jmeter-on-mac-25531bc2b2ad)
- Rally [https://github.com/openstack/rally](https://github.com/openstack/rally)
- Gerador csv [https://github.com/dominictarr/random-name](https://github.com/dominictarr/random-name)

- Ajuda em documentação [link](http://www.linhadecodigo.com.br/artigo/1807/uma-abordagem-para-documentacao-de-testes-de-software-baseado-no-ieee-829-1998.aspx)

- Mapas de tipos de teste [link](http://apoema.inf.ufg.br/pts-mpe/pts-mpe/f48a1066-d42e-424e-9307-5de14e6401df.htm)


<!-- fin bibliografia -->
[🔝 Índice](#índice) | [🔝 Ferramentas de Teste](#ferramentas-de-teste)  | [🔝 Guía de informação](guia_informacao.md#Teste-de-performance) | [ Indexação de dados em elastic ](paso-a-paso.md#indexação-de-dados-em-elastic)
___
