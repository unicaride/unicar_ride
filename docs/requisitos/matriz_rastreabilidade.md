# Matriz de Rastreabilidade - App Carona Universitária

## Histórico de Revisões
| Data       | Versão | Descrição               | Autor       |
|------------|--------|-------------------------|-------------|
| 12/06/2025 | 1.0    | Versão inicial          | Product Owner |

## 1. Requisitos x Histórias de Usuário
| ID   | História                          | Critérios de Aceitação Relacionados | Prioridade |
|------|-----------------------------------|-------------------------------------|------------|
| RF01 | Buscar Caronas Disponíveis        | 1, 2                                | Must       |
| RF02 | Pagamento Integrado               | 1, 2, 3                            | Must       |
| RF03 | Perfil Visível                    | 1, 2, 3                            | Should     |
| RF04 | Verificação de Identidade         | 1                                   | Must       |
| RF05 | Oferta de Carona                  | 1, 2                                | Could      |
| RF06 | Aceitar/Recusar Vagas             | 1, 2                                | Must       |
| RF07 | Avaliar Usuário                   | 1, 2, 3                            | Should     |
| RF08 | Cancelar Carona                   | 1, 2, 3                            | Could      |

## 2. Requisitos x Componentes do Sistema
| ID   | Módulo de Busca | Gateway Pagamento | Perfil Usuário | Autenticação | Gestão Caronas | Notificações |
|------|-----------------|--------------------|----------------|--------------|----------------|--------------|
| RF01 | X               |                    |                |              | X              |              |
| RF02 |                 | X                  |                |              |                | X            |
| RF03 |                 |                    | X              |              |                |              |
| RF04 |                 |                    |                | X            |                |              |
| RF05 |                 |                    |                |              | X              | X            |
| RF06 |                 |                    |                |              | X              | X            |
| RF07 |                 |                    | X              |              | X              |              |
| RF08 | X               |                    |                |              | X              | X            |

## 3. Requisitos x Casos de Teste
| ID   | CT01 - Busca | CT02 - Pagamento | CT03 - Perfil | CT04 - Autenticação | CT05 - Cancelamento |
|------|-------------|------------------|---------------|---------------------|---------------------|
| RF01 | X           |                  |               |                     |                     |
| RF02 |             | X                |               |                     |                     |
| RF03 |             |                  | X             |                     |                     |
| RF04 |             |                  |               | X                   |                     |
| RF05 | X           |                  |               |                     |                     |
| RF06 |             |                  |               |                     | X                   |
| RF07 |             |                  | X             |                     |                     |
| RF08 |             |                  |               |                     | X                   |

## 4. Dependências entre Requisitos
| ID   | RF01 | RF02 | RF03 | RF04 | RF05 | RF06 | RF07 | RF08 |
|------|------|------|------|------|------|------|------|------|
| RF01 | -    |      |      | X    |      |      |      |      |
| RF02 |      | -    | X    | X    |      |      |      |      |
| RF03 |      |      | -    | X    |      |      | X    |      |
| RF04 | X    | X    | X    | -    | X    | X    |      |      |
| RF05 |      |      |      | X    | -    |      |      | X    |
| RF06 |      |      |      | X    |      | -    |      | X    |
| RF07 |      |      | X    |      |      |      | -    |      |
| RF08 |      |      |      |      | X    | X    |      | -    |

## 5. Análise de Impacto - Exemplo Prático
**Cenário:** Adicionar novo método de pagamento (boleto bancário) ao RF02

1. **Componentes Afetados**:
   - Gateway de Pagamento (modificação)
   - Módulo de Notificações (novo template)

2. **Testes Impactados**:
   - CT02 (Pagamento) precisa ser expandido
   - Novo CT06 (Boleto) necessário

3. **Dependências**:
   - RF04 (Autenticação) deve validar novo método
   - RF03 (Perfil) para histórico de pagamentos

4. **Esforço Estimado**:
   - Backend: 3 dias
   - Frontend: 2 dias
   - Testes: 1 dia

> [!NOTE]
> Matriz deve ser atualizada após qualquer mudança nos requisitos!












































































# Matriz de Rastreabilidade de Requisitos

## Histórico de Revisões deste Arquivo

| Data       | Versão | Descrição                | Autor  |
| ---------- | ------ | ------------------------ | ------ |
| DD/MM/AAAA | 1.0    | Versão inicial           | [Nome] |
| DD/MM/AAAA | 1.1    | [Descrição da alteração] | [Nome] |

## 1. Introdução

Este documento apresenta a matriz de rastreabilidade dos requisitos do sistema, permitindo visualizar as relações entre requisitos, casos de uso, componentes do sistema e casos de teste.

## 2. Matriz de Rastreabilidade

### 2.1 Requisitos x Casos de Uso

| Requisito | UC01 | UC02 | UC03 | UC04 | UC05 | ... |
| --------- | ---- | ---- | ---- | ---- | ---- | --- |
| RF01      | X    |      | X    |      |      |     |
| RF02      |      | X    |      |      |      |     |
| RF03      |      |      | X    | X    |      |     |
| ...       |      |      |      |      |      |     |

### 2.2 Requisitos x Componentes do Sistema

| Requisito | Comp01 | Comp02 | Comp03 | Comp04 | ... |
| --------- | ------ | ------ | ------ | ------ | --- |
| RF01      | X      |        | X      |        |     |
| RF02      |        | X      |        |        |     |
| RF03      |        |        | X      | X      |     |
| ...       |        |        |        |        |     |

### 2.3 Requisitos x Casos de Teste

| Requisito | CT01 | CT02 | CT03 | CT04 | CT05 | ... |
| --------- | ---- | ---- | ---- | ---- | ---- | --- |
| RF01      | X    |      | X    |      |      |     |
| RF02      |      | X    |      |      |      |     |
| RF03      |      |      | X    | X    |      |     |
| ...       |      |      |      |      |      |     |

### 2.4 Requisitos x Requisitos (Dependências)

| Requisito | RF01 | RF02 | RF03 | RF04 | RF05 | ... |
| --------- | ---- | ---- | ---- | ---- | ---- | --- |
| RF01      | -    |      | X    |      |      |     |
| RF02      |      | -    |      |      |      |     |
| RF03      | X    |      | -    | X    |      |     |
| ...       |      |      |      |      |      |     |

## 3. Análise de Impacto

Esta seção descreve o processo para análise de impacto de mudanças nos requisitos:

1. Identificar o requisito a ser alterado
2. Consultar a matriz para verificar todos os elementos relacionados
3. Avaliar o impacto da mudança em cada elemento relacionado
4. Documentar a análise de impacto
5. Obter aprovação para a mudança
6. Atualizar todos os artefatos afetados

>[!IMPORTANT]
>A matriz de rastreabilidade deve ser mantida atualizada durante todo o ciclo de desenvolvimento para garantir a integridade do sistema.
