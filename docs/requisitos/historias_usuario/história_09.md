# História de Usuário: UC009

## Título
Sistema Unificado de Perfis

## Narrativa
**Como** usuário do sistema  
**Eu quero** visualizar perfis completos de outros participantes  
**Para que** eu possa avaliar a confiabilidade antes de compartilhar caronas

## Critérios de Aceitação

### Visualização de Perfil
1. [x] Informações básicas:
   - Nome e foto (verificados)
   - Avaliação média (★ 1-5)
   - Status de motorista verificado (selo)

2. [x] Dados específicos:
   - **Motoristas**:
     - Modelo do veículo
     - Histórico de viagens (últimas 20)
     - Taxa de cancelamento
   - **Passageiros**:
     - Número de viagens
     - Compatibilidade de horários
     - Avaliações recebidas

3. [x] Controles de privacidade:
   - Toggle "Mostrar perfil completo"
   - Opção de contato via chat interno
   - Bloqueio de usuários

## Detalhes Técnicos

### Componente React
```jsx
<ProfileView>
  <VerificationBadge 
    type={user.role} 
    isVerified={user.isVerified}
  />
  <RatingDisplay 
    value={user.avgRating} 
    count={user.ratingCount}
  />
  <RoleSpecificInfo 
    user={user} 
    showDetails={!isBlocked}
  />
</ProfileView>
```

### Modelo de Dados
```typescript
interface UserProfile {
  id: string;
  name: string;
  avatar: string;
  role: 'driver' | 'passenger';
  stats: {
    totalRides: number;
    avgRating: number;
    cancellationRate?: number;
  };
  preferences: {
    showFullProfile: boolean;
    allowContact: boolean;
  };
}
```

### API Endpoints
| Método | Endpoint | Parâmetros |
|--------|----------|------------|
| GET | `/profiles/{id}` | `?fields=basic,stats` |
| PATCH | `/profiles/privacy` | `{showFullProfile: boolean}` |

## Dependências
1. **RF003**: Sistema de verificação
2. **RF006**: Histórico de caronas
3. **RNF004**: Armazenamento de imagens

## Estimativa
**Story Points:** 3  
**Tempo de Desenvolvimento:**
- Backend: 2 dias
- Frontend: 3 dias
- Testes: 1 dia

## Prioridade
**MoSCoW:** Should  
**Impacto:** Médio (melhoria de experiência)

## Observações
1. Otimizações:
   - Lazy loading de imagens
   - Cache de perfis (TTL 15min)
2. Segurança:
   - Máscara de dados sensíveis
   - Rate limiting (30 reqs/min)
3. Acessibilidade:
   - Contrastes WCAG AA
   - Suporte a leitores de tela

## Observações

![iPhone 13   14 - 2](https://github.com/user-attachments/assets/87e38431-b613-4ccf-a452-a3e8d3af024f)
