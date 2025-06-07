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

Nome: unicaride
Propósito: Conectar motoristas que farão uma rota com passageiros que precisam de carona para o mesmo destino, otimizando viagens e reduzindo custos e tráfego.
Público-Alvo: Pessoas que buscam transporte econômico e sustentável, e motoristas que desejam ajudar os universitarios a chegarem a seu destino.

Funcionalidades Essenciais (MVP - Produto Mínimo Viável)
Para o Passageiro:
Cadastro e Login
Busca de Caronas: Inserir origem, destino, data e hora. Visualizar caronas disponíveis com detalhes básicos (motorista, veículo)
Solicitação e Confirmação: Enviar solicitação de carona e receber confirmação.
Comunicação: Chat básico com o motorista após a confirmação.

Para o Motorista:
Cadastro e Login:
Oferecer Carona: Informar origem, destino, data, hora, vagas disponíveis por passageiro.
Gerenciar Solicitações: Aceitar ou recusar solicitações de passageiros.
Comunicação: Chat básico com passageiros confirmados.

Requisitos Técnicos e de Segurança (Básicos)
Plataformas: Aplicativo mobile (iOS e Android).
Segurança: Autenticação de usuários, criptografia de dados básicos, e um processo de verificação de motoristas.
Usabilidade: Interface intuitiva e fácil de usar.


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

Para Todos os Usuários (Passageiro e Motorista)
Autenticação: Permitir que o usuário crie uma conta (e-mail, redes sociais) e faça login.
Perfil: Possibilitar a visualização e edição de informações pessoais do usuário.

Para o Passageiro
Busca de Caronas: Permitir a pesquisa de caronas informando origem, destino, data e hora.
Solicitação: Habilitar o envio de solicitações para caronas disponíveis e a recepção de notificações sobre o status.
 Comunicação: Fornecer um chat para contato direto com o motorista após a solicitação.

Para o Motorista
Cadastro e Verificação: Oferecer a opção de cadastrar veículo e exigir verificação de documentos (CNH, documento do veículo, antecedentes).
Oferta de Caronas: Permitir a criação de ofertas de carona, definindo rota, data, hora, vagas e preço.
Gerenciamento de Solicitações: Possibilitar a aceitação ou recusa de solicitações de passageiros.
 Comunicação: Fornecer um chat para contato direto com o passageiro.



### 3.2 Requisitos Não Funcionais

Performance:

Rapidez: O aplicativo deve ser rápido, com buscas e ações respondendo em poucos segundos.
Escalabilidade: Deve conseguir lidar com um grande número de usuários sem ficar lento.
Segurança:

Proteção de Dados: Todas as informações (pagamentos, dados pessoais) precisam ser seguras e criptografadas.
Autenticação: O login e a verificação de motoristas devem ser robustos e à prova de fraudes.
Usabilidade:

Intuitividade: Ser fácil de usar e navegar, mesmo para quem nunca usou.
Consistência: Ter um visual e fluxo consistentes em todas as telas.
Confiabilidade:

Disponibilidade: O aplicativo deve estar sempre funcionando (com alta disponibilidade).
Estabilidade: Deve lidar bem com erros e se recuperar rapidamente de falhas.
Compatibilidade:

Mobile: Funcionar perfeitamente nas versões mais recentes de iOS e Android.
Manutenção: O código deve ser organizado para facilitar futuras atualizações.

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

Para garantir a segurança e a confiança na plataforma, o aplicativo implementará um rigoroso processo de aprovação para todos os motoristas:

Coleta de Dados: O sistema solicitará que o motorista envie cópias digitais da CNH (Carteira Nacional de Habilitação) e do CRLV (documento do veículo).
Verificações Essenciais:
CNH: Validade, categoria e histórico de infrações.
Veículo: Situação do veículo e restrições.
Análise e Aprovação: Todos os dados e documentos passarão por uma análise.
O motorista só será aprovado e poderá oferecer caronas após a conclusão bem-sucedida de todas as verificações.
O status (pendente, aprovado, reprovado) será comunicado ao motorista.
Critérios Mínimos: O veículo e o motorista devem atender a requisitos mínimos de idade e condições de segurança para serem aceitos na plataforma.


>[!NOTE]
>Este documento será atualizado incrementalmente ao longo do desenvolvimento do projeto.
