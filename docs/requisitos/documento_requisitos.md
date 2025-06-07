# Documento de Requisitos

## Histórico de Revisões Deste Arquivo

| Data       | Versão | Descrição                | Autor  |
| ---------- | ------ | ------------------------ | ------ |
| DD/MM/AAAA | 1.0    | Versão inicial           | [Nome] |
| DD/MM/AAAA | 1.1    | [Descrição da alteração] | [Nome] |

## 1. Introdução

### 1.1 Propósito

Este documento descreve os requisitos funcionais e não funcionais do unicar, um aplicativo, que visa a conexão dem otoristas, que oferecem caronas a passageiros que precisam de transporte, otimizando rotas e dividindo custos. O objetivo é proporcionar uma alternativa de transporte mais acessível, sustentável e socialmente integrada, o mesmo serve para usuarios que desejam carona.

### 1.2 Escopo

[Descrição do escopo do sistema]

### 1.3 Definições, Acrônimos e Abreviações

Usuário: Qualquer pessoa cadastrada no aplicativo.
Motorista: Usuário que oferece caronas.
Passageiro: Usuário que busca e solicita caronas.
Carona: Trajeto oferecido por um motorista com vagas para passageiros.
GPS: Global Positioning System.
API: Application Programming Interface.

## 2. Descrição Geral

### 2.1 Perspectiva do Produto

O unicarride é um sistema autônomo que se integrará com APIs de mapas (e.g., Google Maps, OpenStreetMap) para cálculo de rotas e geolocalização, Ele se posiciona como uma solução de transporte alternativa, mais barata e ecologicamente correta que táxis/aplicativos de transporte tradicionais, e mais flexível que o transporte público.

### 2.2 Funcionalidades do Produto

Cadastro e gerenciamento de perfil de usuário (motorista/passageiro).
Oferta de caronas por motoristas.
Busca e solicitação de caronas por passageiros.
Gerenciamento de caronas (aceitar/recusar solicitações, cancelar caronas).
Comunicação entre motorista e passageiro.

### 2.3 Características dos Usuários

Motorista:
Possui CNH válida e veículo próprio.
Deseja ajudar os usuarios que necessitam de carona, por morarem longe do campus, ou não possuirem condições de utilizar transporte publico ou privado.
Precisa de controle sobre as caronas ofertadas aos passageiros.

Passageiro:
Busca transporte acessível e conveniente.
Deseja opções de caronas que se encaixem em sua rota e horário.
Precisa de segurança e comunicação com o motorista.

### 2.4 Restrições

Necessita de conexão à internet (dados móveis ou Wi-Fi) para operar.
Disponível apenas para smartphones (iOS e Android).
Integração com APIs de terceiros para mapas e pagamentos.
Conformidade com leis locais de transporte e privacidade de dados (LGPD no Brasil).

## 3. Requisitos Específicos

### 3.1 Requisitos Funcionais

| ID   | Descrição                | Prioridade         |
| ---- | ------------------------ | ------------------ |
| RF01 | [Descrição do requisito] | [Alta/Média/Baixa] |
| RF02 | [Descrição do requisito] | [Alta/Média/Baixa] |
| ...  | ...                      | ...                |

### 3.2 Requisitos Não Funcionais

| ID    | Categoria   | Descrição                | Prioridade         |
| ----- | ----------- | ------------------------ | ------------------ |
| RNF01 | Usabilidade | [Descrição do requisito] | [Alta/Média/Baixa] |
| RNF02 | Performance | [Descrição do requisito] | [Alta/Média/Baixa] |
| RNF03 | Segurança   | [Descrição do requisito] | [Alta/Média/Baixa] |
| ...   | ...         | ...                      | ...                |

## 4. Visão Geral do Sistema

O unicarride, é um sistema de software móvel projetado para conectar motoristas que oferecem vagas em seus veículos com passageiros que precisam de transporte, com foco na otimização de rotas Nosso objetivo principal é criar uma plataforma intuitiva e segura que fomente o uso de caronas compartilhadas, promovendo a sustentabilidade, a economia de recursos e a interação social entre os usuários.

## 5. Casos de Uso

[Diagrama de casos de uso ou referência para o documento específico]

## 6. Priorização de Requisitos

O documento de requisitos do unicaride é um guia essencial para o desenvolvimento de um aplicativo que conecta motoristas e passageiros para caronas compartilhadas.

Ele começa com uma Introdução que define o propósito do documento e o escopo do projeto: criar uma alternativa de transporte mais acessível, sustentável e socialmente integrada.

A Visão Geral do Sistema descreve o unicaride como uma solução móvel que se integra com APIs de mapas, seu objetivo é beneficiar motoristas, que buscam reduzir custos e  e passageiros, que procuram transporte acessível e conveniente. As funcionalidades principais incluem cadastro, oferta e busca de caronas, gerenciamento de viagens e pagamentos.

Os Requisitos Funcionais detalham as ações que o sistema deve realizar. Isso engloba desde o cadastro e login de usuários, a capacidade de motoristas ofertarem caronas (com pontos de partida, destino, horário e valor), até a funcionalidade para passageiros buscarem e solicitarem vagas. Abrange também o gerenciamento das solicitações por parte dos motoristas, o acompanhamento da viagem em tempo real, o processamento de pagamentos e o sistema de avaliação mútua entre usuários.

Já os Requisitos Não Funcionais especificam como o sistema deve funcionar, focando em suas qualidades. Destacam-se o desempenho (telas rápidas e buscas eficientes), a segurança (criptografia de dados e autenticação forte), a usabilidade (interface intuitiva), a confiabilidade (alta disponibilidade) e a manutenibilidade (código bem documentado).

A seção de Casos de Uso aprofunda as interações. Cada caso descreve uma ação específica que um ator (como um "Passageiro" ou "Motorista") realiza no sistema, detalhando o passo a passo. Exemplos incluem o "Cadastrar Usuário", o "Ofertar Carona" e o "Realizar Pagamento da Carona".

## 7. Aprovação

| Nome   | Papel   | Assinatura | Data       |
| ------ | ------- | ---------- | ---------- |
| [Nome] | [Papel] |            | DD/MM/AAAA |
| [Nome] | [Papel] |            | DD/MM/AAAA |

>[!NOTE]
>Este documento será atualizado incrementalmente ao longo do desenvolvimento do projeto.
