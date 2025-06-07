# História de Usuário: UC005

## Título
Criação de Ofertas de Carona por Motoristas

## Narrativa
**Como** motorista verificado  
**Eu quero** publicar ofertas de carona com meu trajeto  
**Para que** possa compartilhar meu veículo com outros universitários de forma segura e organizada

## Critérios de Aceitação

### Formulário de Criação
1. [x] Campos obrigatórios:
   - Local de partida (autocomplete com lugares frequentes)
   - Destino (validação de endereço via API Maps)
   - Número de vagas (1-4, com seletor visual)
   - Data/horário (datetime picker com validação futura)

2. [x] Campos opcionais:
   - Valor sugerido (com máscara monetária)
   - Pontos de parada intermediários (max 2)
   - Observações (limite de 200 caracteres)

3. [x] Validações:
   - Somente perfis de motorista verificados
   - Limite de 5 caronas ativas simultâneas
   - Horário mínimo: 1h após publicação

### Pós-Publicação
4. [x] Comportamentos esperados:
   - Aparece nos resultados de busca em até 2 minutos
   - Notificação push para passageiros frequentes
   - Opção de edição até primeira solicitação

## Detalhes Técnicos

### Frontend (React)
```jsx
<RideForm>
  <LocationPicker 
    apiKey={MAPS_API_KEY} 
    types={['address']}
  />
  <SeatSelector 
    min={1} 
    max={4} 
    onChange={updateSeats}
  />
  <DriverVerificationGuard>
    <SubmitButton />
  </DriverVerificationGuard>
</RideForm>
```

### Backend (Node.js)
```javascript
// Middleware de verificação
const driverOnly = (req, res, next) => {
  if (!req.user.isVerifiedDriver) {
    return res.status(403).json({ error: 'Perfil de motorista requerido' });
  }
  next();
};

// Endpoint
router.post('/rides', driverOnly, rideController.create);
```

### Banco de Dados
```sql
CREATE TABLE rides (
  id SERIAL PRIMARY KEY,
  driver_id INT REFERENCES users(id),
  origin JSONB NOT NULL,
  destination JSONB NOT NULL,
  seats INT CHECK (seats BETWEEN 1 AND 4),
  departure TIMESTAMPTZ NOT NULL,
  status VARCHAR(20) DEFAULT 'available'
);
```

## Dependências
1. **RF004**: Verificação de motorista
2. **RF008**: Sistema de geolocalização
3. **RNF005**: Validação em tempo real

## Estimativa
**Story Points:** 5  
**Tempo de Desenvolvimento:** 
- Backend: 3 dias 
- Frontend: 4 dias
- Testes: 2 dias

## Prioridade
**MoSCoW:** Must  
**Justificativa:** Funcionalidade central do produto

## Observações
1. Otimizações necessárias:
   - Cache de lugares frequentes (LRU)
   - Pré-cálculo de rotas alternativas
2. Segurança:
   - Validação de coordenadas geográficas
   - Sanitização de inputs
3. Acessibilidade:
   - Suporte a leitores de tela
   - Contrastes WCAG AA
[Observações adicionais, se houver]
