# História de Usuário: UC008

## Título
Cancelamento de Carona por Motorista

## Narrativa
**Como** motorista  
**Eu quero** cancelar uma carona agendada  
**Para que** eu possa evitar situações onde não poderei cumprir com o combinado

## Critérios de Aceitação

### Fluxo Principal
1. [x] Visibilidade do botão:
   - Disponível até 2h antes do horário
   - Exige confirmação em 2 etapas
   - Mostra contador regressivo

2. [x] Processo de cancelamento:
   - Status muda para "cancelado"
   - Remove do feed em até 1 minuto
   - Gera registro de auditoria

3. [x] Notificações:
   - Push notification para passageiros
   - E-mail com motivo padrão
   - Atualização em tempo real no chat da carona

### Regras Especiais
4. [x] Restrições:
   - Limite de 3 cancelamentos/mês
   - Penalidade após limite (resfriamento de 7 dias)
   - Proibido após início da viagem

## Detalhes Técnicos

### Arquitetura
```mermaid
flowchart TD
    A[Frontend] -->|PATCH /rides/{id}/cancel| B[API]
    B --> C[Valida Horário]
    C --> D{2h Antecedência?}
    D -->|Sim| E[Atualiza Status]
    E --> F[Dispara Notificações]
    F --> G[Limpa Cache]
    D -->|Não| H[Erro 403]
```

### Componente React
```jsx
<CancelRideButton 
  ride={selectedRide}
  onConfirm={(reason) => cancelRide(selectedRide.id, reason)}
  countdown={timeLeft}
/>
```

### Endpoints
| Método | Endpoint | Body | Respostas |
|--------|----------|------|-----------|
| PATCH | `/rides/{id}/cancel` | `{reason?: string}` | 200, 403, 404 |

## Dependências
1. **RF005**: Sistema de notificações
2. **RF009**: Chat de carona
3. **RNF003**: Banco de dados em tempo real

## Estimativa
**Story Points:** 4  
**Tempo de Desenvolvimento:**
- Backend: 2 dias
- Frontend: 2 dias
- Testes: 1 dia

## Prioridade
**MoSCoW:** Must  
**Impacto:** Alta (experiência do usuário)

## Observações
1. Políticas:
   - Histórico de cancelamentos visível no perfil
   - Isenção para emergências (via suporte)
2. Otimizações:
   - Cache invalidation
   - Bulk notifications
3. Segurança:
   - Verificação de ownership
   - Rate limiting
