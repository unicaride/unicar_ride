
# História de Usuário: UC001

## Título
Buscar Caronas Disponíveis

## Narrativa
**Como** passageiro  
**Eu quero** buscar caronas disponíveis por local de partida e destino  
**Para que** eu possa encontrar uma carona que atenda meu trajeto universitário

## Critérios de Aceitação
1. [x] Campo de busca com autocomplete para:
   - Local de partida (obrigatório)
   - Destino (obrigatório)
2. [x] Resultados devem exibir:
   - Nome e foto do motorista
   - Horário da carona
   - Vagas disponíveis (ex: "2/4 vagas")
   - Distância até o ponto de partida
3. [x] Ordenação padrão por:
   - 1. Proximidade geográfica
   - 2. Horário mais próximo
4. [x] Opção de filtros:
   - Data/horário
   - Valor máximo
   - Somente motoristas verificados

## Detalhes Técnicos
**Frontend:**
- Componente: `RideSearch.vue`
- API Endpoint: `GET /api/rides?from=...&to=...`
- Bibliotecas:
  - `vue-google-autocomplete` para campos de localização
  - `date-fns` para formatação de horários

**Backend:**
- Query: 
```sql
SELECT rides.*, users.name, users.rating 
FROM rides 
JOIN users ON rides.driver_id = users.id
WHERE status = 'available'
AND departure_time > NOW()
AND ST_DWithin(pickup_location, :userLocation, 10)
```
- Cache: Redis (5min TTL)

## Dependências
1. RF001 - Sistema de geolocalização
2. RF003 - Perfil de usuário (motorista)
3. RNF002 - Autenticação segura

## Estimativa
**Story Points:** 5 (Fibonacci)  
**Tempo Dev:** 3 dias

## Prioridade
**MoSCoW:** Must  
**Release:** 1.0

## Notas
- Considerar otimização para 100+ resultados simultâneos
- Adicionar skeleton loading durante busca
- Limitar busca a 20km raio padrão

## Observações

![iPhone 13   14 - 6](https://github.com/user-attachments/assets/c9712a41-053d-40e8-8c72-68135ac8f758)















