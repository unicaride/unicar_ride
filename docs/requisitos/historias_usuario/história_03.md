# História de Usuário: UC003

## Título
Perfil Público de Usuário

## Narrativa
**Como** usuário do sistema  
**Eu quero** ter um perfil público completo  
**Para que** outros participantes possam avaliar minha confiabilidade

## Critérios de Aceitação
1. [x] Seção de informações básicas:
   - Nome completo (obrigatório)
   - Foto (opcional, padrão: avatar inicial)
   - Curso/Faculdade (se estudante)
   - Média de avaliações (★ 1-5)

2. [x] Histórico visível:
   - Últimas 10 caronas (como motorista/passageiro)
   - Estatísticas: "50 viagens | 92% de aprovação"

3. [x] Controles de privacidade:
   - Edição de dados pessoais (exceto avaliações)
   - Toggle "Mostrar perfil completo" (default: ON)

4. [x] Acesso contextual:
   - Visualização ao clicar em nome em:
     - Lista de caronas
     - Chat
     - Solicitações

## Detalhes Técnicos
**Frontend (React):**
```jsx
<UserProfile>
  <AvatarUpload maxSize={2MB} />
  <RatingDisplay value={4.5} />
  <RideHistory limit={10} />
</UserProfile>
```

**Backend (Node.js):**
```javascript
// API Endpoint
router.get('/profile/:userId', 
  authMiddleware,
  rateLimiter(100/req),
  getProfileData
);
```

**Banco de Dados:**
```sql
CREATE TABLE user_profiles (
  user_id UUID PRIMARY KEY,
  bio TEXT,
  course VARCHAR(100),
  rating DECIMAL(2,1),
  is_public BOOLEAN DEFAULT TRUE
);
```

## Dependências
1. RF004 - Sistema de avaliações
2. RF007 - Autenticação de usuário
3. RNF003 - Armazenamento de imagens (S3)

## Estimativa
**Story Points:** 3  
**Tempo de Desenvolvimento:** 5 dias

## Prioridade
**MoSCoW:** Should  
**Justificativa:** Essencial para construção de confiança, mas não bloqueante

## Observações
1. GDPR Compliance:
   - Direito ao esquecimento
   - Exportação de dados
2. Otimizações:
   - Cache de perfil (15min)
   - Lazy loading de imagens
3. Acessibilidade:
   - Alt text para fotos
   - Leitores de tela
