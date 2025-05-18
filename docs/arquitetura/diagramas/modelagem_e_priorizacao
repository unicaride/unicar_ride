# Técnicas de Modelagem Escolhidas

> ## Técnica	Aplicação no App de Carona Universitária
>
+ ### Diagrama de Caso de Uso	Interações entre motoristas, passageiros e sistema.
+ ### Modelo de Domínio	Entidades como "Usuário", "Carona", "Universidade".
+ ### Diagrama de Estados	Estados de uma carona (ex: "Disponível", "Confirmada", "Concluída").
+ ### Requisitos Não-Funcionais	Segurança, tempo de resposta, escalabilidade.

> ## Modelagem de Requisitos
> 
### IMG_1-Modelos Iniciais
![image](https://github.com/user-attachments/assets/038bddba-e4f7-48fd-97d5-bece75596672)
>
### IMG_2-Modelo de Domínio
![deepseek_mermaid_20250510_31f73d ](https://github.com/user-attachments/assets/465a9eee-07c4-477b-9dbb-0b3010f0195f)
>
### Requisitos Não-Funcionais
![image](https://github.com/user-attachments/assets/86cfc8e1-1da7-4f2b-a61b-c672c907f750)

### Diagrama de Estados (Carona)
[Disponível] → [Reservada] → [Em Andamento] → [Concluída]  
[Disponível] → [Cancelada] (por motorista ou passageiro)

> ## Priorização com MoSCoW
> 
+ Prioridade	Requisito	Justificativa
+ Must	Verificação de e-mail institucional	Evitar usuários não universitários.
+ Should	Integração com calendário acadêmico	Sugerir caronas baseadas em horários de aula.
+ Could	Chat entre motorista e passageiro	Melhorar comunicação, mas não essencial.

### Matriz de Rastreabilidade Leve 
![Imagem do WhatsApp de 2025-05-11 à(s) 00 46 01_02939f94](https://github.com/user-attachments/assets/ff0c2424-6f6a-43fa-b234-4cdf3f779c4a)


> ## Estabeleça sua Definition of Ready: 
>
> + ### Avaliação das Histórias:

#### 1. Buscar Caronas Disponíveis ✅ (Pronta)
Critérios claros: Local de partida, destino, informações exibidas (motorista, horário, vagas).

Testável: Pode-se verificar se a busca retorna os dados corretos.

Dependências: Requer integração com listagem de caronas, mas não há impedimentos explícitos.

#### 2. Pagamento Integrado (PIX/Cartão) ✅ (Pronta, mas pode precisar de refinamento técnico)
Critérios claros: QR Code PIX, confirmação pós-pagamento, recibo por e-mail.

Dependências: Necessário integração com gateway de pagamento (ex.: Mercado Pago, PagBank).

Ponto de atenção: Regras de estorno? Tempo de confirmação do PIX?

#### 3. Perfil do Passageiro ✅ (Pronta)
Critérios completos: Exibição de dados, edição limitada, visibilidade para outros usuários.

Testável: Pode-se verificar se as informações são salvas e exibidas corretamente.

#### 4. Cadastro com Verificação de E-mail ✅ (Pronta, mas depende de RNF002)
Critérios claros: Autenticação com e-mail verificado.

Dependência: Necessário serviço de e-mail (ex.: SendGrid) ou provedor de autenticação (Firebase Auth).

#### 5. Aceitar/Recusar Solicitações de Vaga ✅ (Pronta)
Critérios testáveis: Lista de pendentes, confirmação ao aceitar.

Fluxo claro: Pode ser implementado com notificações em tempo real.

#### 6. Avaliação Pós-Carona ✅ (Pronta)
Regras definidas: Só após conclusão, nota 1-5, comentário opcional, média no perfil.

Testável: Pode-se simular uma carona concluída e verificar a avaliação.

#### 7. Cancelamento de Carona (Motorista) ✅ (Pronta)
Critérios específicos: Botão disponível até 2h antes, notificação automática.

Ponto de atenção: E se o motorista cancelar repetidamente? (Pode ser outra história).

#### 8. Criar Oferta de Carona ✅ (Pronta)
Critérios claros: Formulário com partida, destino, vagas.

Restrição definida: Apenas motoristas podem criar.
