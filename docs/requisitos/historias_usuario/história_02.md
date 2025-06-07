# História de Usuário: UC002

## Título
Sistema de Pagamento Integrado (PIX/Cartão)

## Narrativa
**Como** passageiro  
**Eu quero** realizar pagamentos digitais seguros  
**Para que** eu possa confirmar minha vaga sem usar dinheiro físico

## Critérios de Aceitação
1. [x] Fluxo PIX:
   - Geração dinâmica de QR Code
   - Validação automática via webhook (max 2min)
   - Opção "Copiar Código" alternativa

2. [x] Fluxo Cartão:
   - Integração com gateway de pagamento
   - Tokenização de dados sensíveis (PCI Compliant)
   - 3D Secure para compras > R$100

3. [ ] Notificações:
   - Passageiro: recibo PDF por e-mail (template HTML)
   - Motorista: push notification + e-mail
   - Sistema: registro no banco de dados

4. [ ] Fallback:
   - Retentativa automática em falhas de conexão
   - Status "Pagamento Pendente" visível

## Detalhes Técnicos
**Frontend:**
```vue
<PaymentOptions>
  <PixQr :transaction-id="tx123" />
  <CreditCardForm @submit="processPayment" />
</PaymentOptions>
```

**Backend:**
```python
# Webhook Handler
@app.route('/webhook/pix', methods=['POST'])
def handle_pix():
    verify_signature(request)
    update_payment_status(request.json['tx_id'])
```

**Segurança:**
- Certificado SSL (TLS 1.3)
- Criptografia AES-256 para dados sensíveis
- Auditoria mensal de compliance PCI-DSS

## Dependências
1. RF008 - Perfil de motorista verificado
2. RNF005 - Gateway de pagamento contratado
3. RF011 - Sistema de notificações

## Estimativa
**Story Points:** 8  
**Sprints:** 2 (Cenário complexo)

## Prioridade
**MoSCoW:** Must  
**Business Value:** Alta  
**Riscos:**  
- Taxas de transação  
- Chargebacks  

## Observações
1. Testar com bancos:
   - Santander, Itaú, Nubank
2. Limites:
   - PIX: R$1.000/dia
   - Cartão: R$2.500/mês
3. Backup:
   - SMS quando e-mail falhar
