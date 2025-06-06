# Plano de Testes

## Histórico de Revisões

| Data       | Versão | Descrição                | Autor  |
| ---------- | ------ | ------------------------ | ------ |
| DD/MM/AAAA | 1.0    | Versão inicial           | [Nome] |
| DD/MM/AAAA | 1.1    | [Descrição da alteração] | [Nome] |

## 1. Introdução

Este documento descreve o plano de testes para o aplicativo Unicar, cujo objetivo é conectar estudantes do campus universitário interessados em oferecer ou solicitar caronas. O plano visa garantir a qualidade e o funcionamento adequado do sistema antes de sua disponibilização para uso.

### 1.1 Objetivos

Verificar se o sistema reflete corretamente a oferta e solicitação de caronas
Validar a experiência do usuário em dispositivos móveis  
Testar a comunicação entre usuários através do chat interno
Avaliar a segurança básica do sistema

### 1.2 Escopo

O escopo dos testes inclui as funcionalidades principais do aplicativo, cadastro de usuários, criação de ofertas de carona, busca por caronas disponíveis, sistema de mensagens entre usuários.
Funcionalidades como gerenciamento administrativo, métricas de uso e histórico detalhado de caronas não serão abordadas nesta fase de testes.

### 1.3 Definições, Acrônimos e Abreviações

Ux: user experience(experiência do usuário)
Api: application programming interface
MVP: minimum viable product

## 2. Estratégia de Teste

### 2.1 Níveis de Teste

#### 2.1.1 Testes Unitários

Verificação da lógica da função, como cálculos de distancia e filtragem de caronas

#### 2.1.2 Testes de Integração

Validação de comunicação entre front end, back-end e banco de dados.

#### 2.1.3 Testes de Sistema

Teste de funcionamento da aplicação

#### 2.1.4 Testes de Aceitação

Simulação da experiência final do usuário

### 2.2 Tipos de Teste

#### 2.2.1 Testes Funcionais

[Descrição da abordagem para testes funcionais]

#### 2.2.2 Testes de Performance

[Descrição da abordagem para testes de performance]

#### 2.2.3 Testes de Segurança

Avaliar a segurança básica do sistema

#### 2.2.4 Testes de Usabilidade

[Descrição da abordagem para testes de usabilidade]

#### 2.2.5 Testes de Regressão

[Descrição da abordagem para testes de regressão]

## 3. Recursos


### 3.1 Ambientes de Teste

[Descrição dos ambientes de teste]

### 3.2 Ferramentas

Postman
react native
javascript
python

### 3.3 Equipe

[Descrição dos papéis e responsabilidades da equipe de teste]

## 4. Cronograma

[Cronograma de atividades de teste]

## 5. Critérios

### 5.1 Critérios de Entrada

Verificar se a funcionalidade implementada foi integrada ao sistema

### 5.2 Critérios de Saída

Visualizar se os testes foram realizados com sucesso, e se nenhum bug foi relatado no momento, ou se o aplicativo esteve rodando normalmente

### 5.3 Critérios de Suspensão e Retomada

[Critérios para suspensão e retomada dos testes]

## 6. Matriz de Risco e Contingência

| Risco     | Probabilidade      | Impacto            | Estratégia de Mitigação |
| --------- | ------------------ | ------------------ | ----------------------- |
| [Risco 1] | [Alta/Média/Baixa] | [Alto/Médio/Baixo] | [Estratégia]            |
| [Risco 2] | [Alta/Média/Baixa] | [Alto/Médio/Baixo] | [Estratégia]            |
| ...       | ...                | ...                | ...                     |

## 7. Casos de Teste

| ID   | Descrição   | Requisito | Pré-condições | Passos   | Resultado Esperado | Prioridade         |
| ---- | ----------- | --------- | ------------- | -------- | ------------------ | ------------------ |
| CT01 | [Descrição] | [Req]     | [Pré]         | [Passos] | [Resultado]        | [Alta/Média/Baixa] |
| CT02 | [Descrição] | [Req]     | [Pré]         | [Passos] | [Resultado]        | [Alta/Média/Baixa] |
| ...  | ...         | ...       | ...           | ...      | ...                | ...                |

## 8. Métricas

[Descrição das métricas a serem coletadas e analisadas]

## 9. Relatórios

[Descrição dos relatórios a serem gerados]

## 10. Aprovação

| Nome   | Papel   | Assinatura | Data       |
| ------ | ------- | ---------- | ---------- |
| [Nome] | [Papel] |            | DD/MM/AAAA |
| [Nome] | [Papel] |            | DD/MM/AAAA |

>[!WARNING]
>A execução completa do plano de testes é essencial para garantir a qualidade do software. Qualquer desvio do plano deve ser documentado e justificado.
