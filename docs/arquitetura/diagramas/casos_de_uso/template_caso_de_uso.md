# Caso de Uso: [ID]

Caso de Uso: Buscar Caronas Disponíveis
1. Nome do Caso de Uso
UC001 – Buscar Caronas Disponíveis

2. Descrição
Este caso de uso permite que um passageiro busque caronas disponíveis com base em local de partida e destino, visualizando informações como nome do motorista, horário e vagas disponíveis.

3. Atores
Ator Primário: Passageiro

Atores Secundários: Motorista (fornece as caronas disponíveis)

4. Pré-condições
O usuário está autenticado no sistema.

Existem caronas cadastradas no sistema.

5. Fluxo Básico
O passageiro acessa a tela principal e seleciona "Buscar Caronas".

O sistema exibe um formulário com os campos:

Local de Partida (obrigatório)

Destino (obrigatório)

O passageiro preenche os campos e clica em "Buscar".

O sistema retorna uma lista de caronas disponíveis, contendo:

Nome do motorista

Horário da carona

Vagas disponíveis

O passageiro seleciona uma carona e clica em "Solicitar Vaga".

O sistema registra a solicitação e notifica o motorista.

6. Fluxos Alternativos
Alternativa 1: Filtros Adicionais
No passo 2, o passageiro pode aplicar filtros adicionais (ex.: data, horário).

O sistema atualiza a lista de caronas conforme os filtros selecionados.

Alternativa 2: Nenhuma Carona Encontrada
No passo 4, se não houver caronas disponíveis, o sistema exibe:

"Nenhuma carona encontrada para o trajeto selecionado."

O passageiro pode ajustar os critérios de busca e tentar novamente.

7. Fluxos de Exceção
Exceção 1: Campos Obrigatórios Não Preenchidos
No passo 3, se o passageiro não preencher os campos obrigatórios, o sistema exibe:

"Preencha o local de partida e destino para buscar caronas."

O sistema impede a busca até que os campos sejam preenchidos.

Exceção 2: Falha na Conexão
No passo 4, se houver falha na conexão, o sistema exibe:

"Não foi possível buscar caronas. Verifique sua conexão e tente novamente."

8. Pós-condições
O passageiro visualiza a lista de caronas disponíveis.

Se uma solicitação for enviada, o motorista é notificado.

9. Requisitos Relacionados
RF001: Buscar caronas por local de partida e destino.

RF008: Motorista pode criar ofertas de carona.

RNF002: Segurança na autenticação do usuário.

10. Interface de Usuário
Tela de Busca:

Campos de texto para Local de Partida e Destino.

Botão "Buscar".

Lista de resultados com:

Foto e nome do motorista.



>> Caso de Uso: Pagamento Integrado (PIX/Cartão)
>> 
1. Nome do Caso de Uso
UC002 – Realizar Pagamento da Carona

2. Descrição
Permite que o passageiro realize o pagamento de uma carona solicitada e aceita, utilizando PIX ou cartão de crédito/débito, gerando um comprovante digital.

3. Atores
Ator Primário: Passageiro

Atores Secundários:

Motorista (recebe confirmação do pagamento)

Sistema de Pagamento (processa a transação)

4. Pré-condições
O passageiro está autenticado no sistema.

O motorista aceitou a solicitação de carona.

O passageiro ainda não realizou o pagamento.

5. Fluxo Básico
O sistema exibe a opção "Pagar Carona" na tela de caronas confirmadas.

O passageiro seleciona o método de pagamento (PIX ou Cartão).

Para PIX:

O sistema gera um QR Code ou código copia-e-cola.

O passageiro realiza o pagamento via app bancário.

Para Cartão:

O sistema redireciona para tela de inserção de dados do cartão.

O passageiro preenche os dados e confirma o pagamento.

O sistema processa o pagamento e:

Envia confirmação ao motorista.

Gera e envia recibo digital por e-mail ao passageiro.

A vaga na carona é oficialmente reservada.

6. Fluxos Alternativos
Alternativa 1: Pagamento com Cartão Salvo
No passo 2, se o passageiro tiver cartão cadastrado:

O sistema mostra opção "Usar Cartão Salvo".

O pagamento é processado automaticamente após confirmação.

Alternativa 2: Pagamento Pendente (PIX não concluído)
Se o passageiro não finalizar o PIX em 30 minutos:

O sistema cancela a reserva automaticamente.

Notifica o passageiro: "Pagamento não concluído. Tente novamente."

7. Fluxos de Exceção
Exceção 1: Pagamento Recusado
Se o pagamento for recusado (cartão negado/PIX falho):

O sistema exibe: "Pagamento não aprovado. Tente outro método."

Permite nova tentativa ou alteração de método.

Exceção 2: Falha no Processamento
Se houver erro no sistema durante o pagamento:

O sistema registra a falha e exibe: "Erro ao processar. Tente mais tarde."

A carona permanece como "pendente de pagamento".

8. Pós-condições
O motorista recebe confirmação da reserva paga.

O passageiro recebe recibo por e-mail.

A vaga é marcada como ocupada na carona.

9. Requisitos Relacionados
RF002: Pagamento via PIX ou cartão.

RNF002: Segurança nas transações (dados criptografados).

RF005: Motorista só confirma após pagamento.

10. Interface de Usuário
Tela de Pagamento:

Seletor de método (PIX/Cartão).

QR Code ou campo para dados do cartão.

Botão "Confirmar Pagamento".

Mensagem de status (ex.: "Aguardando confirmação PIX").

E-mail de Recibo:

Detalhes da carona (motorista, horário, valor).

Código da transação.

Horário e vagas disponíveis.

Botão "Solicitar Vaga".

>> Caso de Uso: Gerenciar Perfil do Usuário
>> 
1. Nome do Caso de Uso
UC003 – Gerenciar Perfil do Usuário

2. Descrição
Permite que o usuário (passageiro ou motorista) visualize, edite e mantenha seu perfil atualizado com informações pessoais, foto e histórico de caronas, garantindo transparência e confiabilidade no sistema.

3. Atores
Ator Primário: Usuário (Passageiro ou Motorista)

Atores Secundários:

Outros usuários (visualizam o perfil)

Sistema de Avaliações (atualiza as médias)

4. Pré-condições
O usuário está autenticado no sistema.

O perfil do usuário foi criado durante o cadastro.

5. Fluxo Básico
O usuário acessa a seção "Meu Perfil" no menu principal.

O sistema exibe as seguintes informações:

Nome completo

Foto (se cadastrada)

Curso/faculdade (opcional)

Média de avaliações (1-5 estrelas)

Histórico de caronas (como passageiro/motorista)

Para editar:

O usuário clica em "Editar Perfil".

O sistema permite modificar:

Foto (upload ou remoção)

Curso/faculdade

Outras informações pessoais (exceto avaliações)

O usuário confirma as alterações clicando em "Salvar".

O sistema atualiza o perfil e exibe mensagem: "Alterações salvas com sucesso!".

6. Fluxos Alternativos
Alternativa 1: Visualizar Perfil de Outro Usuário
O usuário clica no nome/perfil de outro participante (em uma carona ou chat).

O sistema exibe:

Informações públicas (nome, foto, avaliações médias).

Botão "Enviar Mensagem" (se aplicável).

Não é possível editar o perfil de outros usuários.

Alternativa 2: Usuário Não Possui Foto
Se o usuário não tiver foto cadastrada:

O sistema exibe um ícone padrão (silhueta).

Mostra a opção "Adicionar Foto" destacada.

7. Fluxos de Exceção
Exceção 1: Falha ao Salvar Alterações
Se houver erro de conexão ao salvar:

O sistema exibe: "Não foi possível atualizar. Verifique sua conexão."

Mantém os dados anteriores.

Exceção 2: Tentativa de Editar Avaliações
Se o usuário tentar modificar avaliações recebidas (via inspeção HTML/console):

O sistema bloqueia a ação e exibe: "Avaliações não podem ser alteradas."

8. Pós-condições
As informações editadas são atualizadas no perfil.

Outros usuários visualizam as mudanças em interações futuras.

A média de avaliações permanece imutável pelo usuário.

9. Requisitos Relacionados
RF003: Perfil com nome, foto, curso e avaliações.

RF006: Avaliações após caronas concluídas.

RNF001: Autenticação segura para acesso ao perfil.

10. Interface de Usuário
Tela de Perfil Pessoal:

Foto (ou ícone) + botão "Alterar Foto".

Campos editáveis (nome, curso, etc.).

Seção de avaliações (somente leitura).

Botão "Salvar"/"Cancelar".

Tela de Perfil de Terceiros:

Apenas visualização (sem opções de edição).

Botão "Enviar Mensagem" (se não bloqueado).

>>Caso de Uso: Cadastro e Verificação de Identidade
1. Nome do Caso de Uso
UC004 - Cadastrar Usuário e Verificar Identidade

2. Descrição
Permite que novos usuários (passageiros e motoristas) criem uma conta no sistema através de cadastro com e-mail e complete a verificação de identidade necessária para utilizar a plataforma.

3. Atores
Ator Primário: Novo Usuário

Ator Secundário: Sistema de Autenticação

4. Pré-condições
O usuário não possui conta cadastrada no sistema

O dispositivo possui conexão com internet

5. Fluxo Básico
O usuário acessa a opção "Criar Conta" na tela inicial

O sistema exibe formulário de cadastro solicitando:

Nome completo

E-mail válido

Senha (mínimo 8 caracteres)

Confirmação de senha

O usuário preenche todos os campos obrigatórios

O sistema valida os dados e envia e-mail de verificação

O usuário acessa seu e-mail e clica no link de verificação

O sistema confirma a verificação e redireciona para completar perfil

6. Fluxos Alternativos
Alternativa 1: Cadastro como Motorista
No passo 6, o usuário seleciona "Quero ser Motorista"

O sistema solicita documentos adicionais (CNH e documento com foto)

O usuário faz upload dos documentos

O sistema envia para verificação manual

Após aprovação (em até 48h), perfil de motorista é liberado

7. Fluxos de Exceção
Exceção 1: E-mail já cadastrado
No passo 4, se e-mail já existir no sistema:

Exibe mensagem: "Este e-mail já está em uso. Recuperar senha?"

Oferece opções: "Tentar outro e-mail" ou "Recuperar acesso"

Exceção 2: Link de verificação expirado
Se usuário tentar verificar após 24h:

Sistema exibe: "Link expirado. Reenviar verificação?"

Ao confirmar, enga novo e-mail de verificação

8. Pós-condições
Nova conta é criada no sistema (status "não verificado")

Após verificação, conta muda para status "ativo"

Usuário pode acessar todas funcionalidades básicas

9. Requisitos Relacionados
RF004: Cadastro com e-mail e verificação

RNF002: Segurança na autenticação

RF008: Diferenciação passageiro/motorista

10. Interface de Usuário
Tela de Cadastro:

Campos: Nome, E-mail, Senha (com indicador de força)

Checkbox "Concordo com Termos de Uso"

Botão "Criar Conta"

E-mail de Verificação:

Assunto: "Confirme seu e-mail para [NomeApp]"

Corpo com botão "Verificar Agora" (link válido por 24h)

Tela de Documentos (Motorista):

Área de upload para CNH e RG/CPF

Preview dos documentos enviados

Status "Em Análise" após envio

Regras de Negócio:

Senha deve conter: 8+ caracteres, 1 número e 1 caractere especial

Contas não verificadas em 7 dias são excluídas automaticamente

Motoristas precisam ter CNH válida e documento com foto legível
