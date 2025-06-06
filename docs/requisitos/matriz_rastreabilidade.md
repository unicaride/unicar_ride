# Matriz de Rastreabilidade de Requisitos - App Carona Universitária

## Histórico de Revisões

| Data       | Versão | Descrição                         | Autor         |
|------------|--------|-----------------------------------|---------------|
| 10/06/2025 | 1.0    | Versão inicial                    | Equipe Dev    |
| 11/06/2025 | 1.1    | Adição de requisitos de segurança | Analista QA   |

## 1. Introdução
Matriz que relaciona os requisitos funcionais (RF) e não-funcionais (RNF) com casos de uso, componentes e testes do sistema.

## 2. Matriz de Rastreabilidade

### 2.1 Requisitos x Casos de Uso

| ID   | Descrição                          | UC001 | UC002 | UC003 | UC004 | UC005 |
|------|------------------------------------|-------|-------|-------|-------|-------|
| RF01 | Buscar caronas por trajeto        | X     |       |       |       |       |
| RF02 | Pagamento via PIX/cartão          |       | X     |       |       |       |
| RF03 | Gerenciamento de perfil           |       |       | X     |       |       |
| RF04 | Avaliação pós-carona              |       |       |       | X     |       |
| RF05 | Criação de ofertas de carona      |       |       |       |       | X     |
| RNF01| Autenticação com e-mail institucional | X   | X     | X     | X     | X     |

### 2.2 Requisitos x Componentes

| ID   | Módulo de Busca | Gateway Pagamento | Perfil Usuário | Notificações | Avaliações |
|------|-----------------|--------------------|----------------|--------------|------------|
| RF01 | X               |                    |                |              |            |
| RF02 |                 | X                  |                | X            |            |
| RF03 |                 |                    | X              |              |            |
| RF04 |                 |                    |                | X            | X          |
| RNF02| X               | X                  | X              | X            | X          |

### 2.3 Requisitos x Casos de Teste

| ID   | CT01 - Busca | CT02 - Pagamento | CT03 - Perfil | CT04 - Segurança |
|------|-------------|------------------|---------------|------------------|
| RF01 | X           |                  |               |                  |
| RF02 |             | X                |               | X                |
| RF03 |             |                  | X             | X                |
| RNF02| X           | X                | X             | X                |

### 2.4 Dependências entre Requisitos

| ID   | RF01 | RF02 | RF03 | RF04 | RF05 | RNF01 |
|------|------|------|------|------|------|-------|
| RF01 | -    |      |      |      |      | X     |
| RF02 |      | -    |      |      |      | X     |
| RF03 |      |      | -    | X    |      | X     |
| RNF01| X    | X    | X    | X    | X    | -     |

## 3. Análise de Impacto

Processo para mudanças:

1. **Identificação**: Exemplo: Alterar RF02 (adicionar boleto)
2. **Rastreamento**: 
   - Componentes: Gateway Pagamento (+ novo módulo)
   - Testes: CT02 precisa ser atualizado
   - Dependências: RNF01 (segurança)
3. **Avaliação**:
   - Impacto técnico: Médio (nova integração)
   - Prazo: +2 sprints
4. **Aprovação**: Reunião com PO e arquiteto
5. **Atualização**:
   - Atualizar matriz
   - Modificar documentação de pagamento

> [!WARNING]
> Alterações em RNF01 exigem reteste completo do sistema!












































































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
