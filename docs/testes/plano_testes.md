# Plano de Testes

## Histórico de Revisões

| Data       | Versão | Descrição                | Autor  |
| ---------- | ------ | ------------------------ | ------ |
| DD/MM/AAAA | 1.0    | Versão inicial           | [Nome] |
| DD/MM/AAAA | 1.1    | [Descrição da alteração] | [Nome] |

## 1. Introdução

Este documento descreve o plano de testes para o aplicativo Unicaride, cujo objetivo é conectar estudantes do campus universitário interessados em oferecer ou solicitar caronas. O plano visa garantir a qualidade e o funcionamento adequado do sistema antes de sua disponibilização para uso.

### 1.1 Objetivos

Verificar se o sistema reflete corretamente a oferta e solicitação de caronas
Validar a experiência do usuário em dispositivos móveis  
Testar a comunicação entre usuários através do chat interno
Avaliar a segurança básica do sistema

### 1.2 Escopo

O escopo dos testes inclui as funcionalidades principais do aplicativo, cadastro de usuários, criação de ofertas de carona, busca por caronas disponíveis, sistema de mensagens entre usuários.
Funcionalidades como gerenciamento administrativo, métricas de uso e histórico detalhado de caronas não serão abordadas nesta fase de testes.

### 1.3 Definições, Acrônimos e Abreviações

Ux: user experience(experiência do usuário)
Api: application programming interface
MVP: minimum viable product

## 2. Estratégia de Teste

### 2.1 Níveis de Teste

Os testes, vão ser avaliados em três niveis, nivel basico, nivel médio, e nivel avançado

#### 2.1.1 Testes Unitários

Verificação da lógica da função, como cálculos de distancia e filtragem de caronas

#### 2.1.2 Testes de Integração

Validação de comunicação entre front end, back-end e banco de dados.

#### 2.1.3 Testes de Sistema

Teste de funcionamento da aplicação

#### 2.1.4 Testes de Aceitação

Simulação da experiência final do usuário

### 2.2 Tipos de Teste

#### 2.2.1 Testes Funcionais

Objetivo: Verificar se o passageiro consegue encontrar e visualizar caronas.

Pré-condições: Passageiro logado e com caronas disponíveis cadastradas.

Passos Principais:

Inserir Origem e Destino: Digitar e selecionar os endereços de partida e chegada.
Selecionar Data e Hora: Escolher a data e o horário da carona.
Buscar Caronas: Clicar no botão de busca.

Resultado Esperado:

O aplicativo deve exibir corretamente uma lista de caronas compatíveis, mostrando o motorista, veículo, preço e avaliação.
Se não houver caronas, deve mostrar uma mensagem clara como "Nenhuma carona encontrada".

#### 2.2.2 Testes de Performance

Objetivo: Verificar se o aplicativo consegue buscar caronas rapidamente e sem falhas quando muitos usuários o utilizam ao mesmo tempo.

O que faremos: Simular um grande número de passageiros (ex: 200 usuários virtuais) pesquisando caronas ao mesmo tempo, durante um período de tempo definido.

Como medimos:

Tempo de Resposta: Quanto tempo cada busca leva para ser concluída (esperamos que seja menos de 1 segundo para a maioria).
Taxa de Erros: Quantas buscas falham (deve ser quase zero).
Uso de Recursos: Se os servidores estão sobrecarregados (CPU e memória devem ficar abaixo de 80%).
Para que serve: Garante que o aplicativo não "trave" ou fique lento nos horários de pico, oferecendo uma experiência fluida para todos os usuários.

#### 2.2.3 Testes de Segurança

Avaliar a segurança básica do sistema, ver se não há vazamentos de dados, e visando oferecer uma experiencia segura, a todos os usuários do aplicativo

#### 2.2.4 Testes de Usabilidade

Objetivo: Avaliar o quão fácil, eficiente e agradável é usar o aplicativo de caronas para seus usuários (passageiros e motoristas). O foco é entender a experiência real do usuário.

O que faremos: Observar usuários reais (representantes do público-alvo) realizando tarefas típicas no aplicativo, e coletar seus feedbacks.

Cenários/Tarefas Típicas para Teste:

Para Passageiros:

Buscar e Solicitar uma Carona: Observar se o passageiro consegue facilmente encontrar e pedir uma carona, sem confusão.
Realizar um Pagamento: Verificar se o processo de pagamento é claro e seguro.
Avaliar um Motorista: Confirmar se é simples dar uma nota e um feedback após a viagem.

Para Motoristas:

Oferecer uma Carona: Observar se o motorista consegue cadastrar uma nova carona de forma rápida e intuitiva.
Aceitar um Passageiro: Verificar a facilidade em gerenciar as solicitações de carona.
Verificar Ganhos: Confirmar se o extrato de ganhos é claro e fácil de entender.
Processo de Aprovação: Avaliar a clareza e a facilidade do processo de envio de documentos.
Como Medimos (Métricas Comuns):

Taxa de Sucesso da Tarefa: Quantos usuários conseguem completar uma tarefa sem ajuda.
Tempo para Completar a Tarefa: Quanto tempo o usuário leva para realizar uma ação (ex: buscar e solicitar carona).
Número de Erros: Quantos erros o usuário comete ao tentar realizar uma tarefa.
Satisfação do Usuário: Como o usuário se sente em relação à experiência (coletado via questionários ou entrevistas).
Pontos de Frustração: Quais são as dificuldades ou obstáculos que os usuários encontram.
Para que serve: Este teste ajuda a identificar pontos onde o aplicativo pode ser confuso, lento ou difícil de usar. Com base nos resultados, é possível fazer melhorias no design e na interface, tornando o aplicativo mais amigável e eficiente para todos. O objetivo final é criar uma experiência de usuário fluida e positiva.

#### 2.2.5 Testes de Regressão

Objetivo: Garantir que novas mudanças (correções de bugs, novas funcionalidades) no aplicativo de caronas não introduziram novos problemas ou quebraram funcionalidades existentes que antes funcionavam.

O que faremos: Reexecutar um conjunto de testes importantes já existentes para as funcionalidades críticas do aplicativo após cada nova alteração no código.

Quando é feito:

Sempre que uma nova funcionalidade é adicionada.
Sempre que um bug é corrigido.
Após grandes atualizações de sistema ou infraestrutura.
Foco dos testes:

Funcionalidades Essenciais:
Login/Cadastro de Usuário.
Busca e Solicitação de Carona (para passageiro).
Oferta e Gerenciamento de Carona (para motorista).

Integrações Chave:
Mapas (se ainda funcionam corretamente)..
Notificações (se ainda são enviadas).

Como Medimos:

Resultados Consistentes: Os testes devem passar com os mesmos resultados esperados de antes da mudança.
Sem Novos Erros: Não deve haver o aparecimento de novos bugs ou falhas em funcionalidades que antes funcionavam.
Para que serve: É uma "rede de segurança" para o aplicativo. Ele garante que, ao melhorar ou consertar algo, você não esteja estragando outras partes do sistema. Isso mantém a estabilidade e a qualidade do aplicativo a longo prazo, evitando que os usuários encontrem problemas em funções que eles esperam que funcionem perfeitamente.

## 3. Recursos

### 3.1 Ambientes de Teste

Para Todos: Cadastro, login e gerenciamento de perfil.
Para Passageiros: Buscar caronas, enviar solicitações, pagar, conversar com motoristas e avaliar a viagem.
Para Motoristas: Cadastrar veículo, passar por um processo de aprovação de segurança, oferecer caronas, gerenciar pedidos, receber ganhos, conversar com passageiros e avaliá-los.

2. Como o app funcionará (Requisitos Não Funcionais)
Performance: Será rápido e escalável, suportando muitos usuários sem lentidão.
Segurança: Todos os dados serão protegidos e criptografados. O processo de aprovação de motoristas será rigoroso.
Usabilidade: Será fácil de usar e intuitivo, com um design claro.
Confiabilidade: Estará sempre disponível e lidará bem com erros.
Compatibilidade: Funcionará perfeitamente em iOS e Android.

3. Garantindo a Segurança (Aprovação de Motoristas)
Motoristas só poderão oferecer caronas após verificação completa de CNH, e documento do seu veículo

4. Testes Essenciais (Como garantimos a qualidade)
Funcional: Verificamos se cada função (ex: buscar carona) faz o que deveria.
Performance: Testamos a velocidade e estabilidade do app sob alta demanda.
Segurança: Procuramos por falhas para proteger dados e evitar acessos indevidos.
Usabilidade: Observamos usuários para garantir que o app é fácil e agradável de usar.
Regressão: Reaplicamos testes para garantir que novas mudanças não quebrem o que já funciona.
Ambiente de Teste: Tudo isso é feito em um ambiente seguro e separado do aplicativo real, usando dados fictícios.

### 3.2 Ferramentas

Postman
react native
javascript
python

### 3.3 Equipe

[Descrição dos papéis e responsabilidades da equipe de teste]

## 4. Cronograma

[Cronograma de atividades de teste]

## 5. Critérios

### 5.1 Critérios de Entrada

Verificar se a funcionalidade implementada foi integrada ao sistema

### 5.2 Critérios de Saída

Visualizar se os testes foram realizados com sucesso, e se nenhum bug foi relatado no momento, ou se o aplicativo esteve rodando normalmente

### 5.3 Critérios de Suspensão e Retomada

Por que Suspender (Gatilhos):

Denúncias: Outros usuários reportam problemas.
Comportamento Ruim: Avaliações consistentemente baixas ou atividades suspeitas.
Regras Quebradas: Violação dos termos de serviço do aplicativo.

O Processo:

Notificação: O usuário é avisado da suspensão, incluindo o motivo e, se aplicável, como reativar a conta.
Bloqueio: A conta suspensa perde o acesso às funcionalidades do app.
Registro: A suspensão é registrada internamente.

Como Reativar (Retomada - apenas para suspensões temporárias):

Automático: Se a suspensão for por um tempo fixo, a conta reativa sozinha após o período.
Ação do Usuário: O usuário pode precisar fazer algo (ex: entrar em contato com o suporte, passar por um treinamento online) para ter a conta de volta.
Revisão: Em alguns casos, o usuário pode pedir para a equipe revisar a suspensão.

## 6. Matriz de Risco e Contingência

1-) Falhas de Segurança e Vazamento de Dados:

Risco: Informações dos usuários são expostas ou sistemas invadidos.
Plano de Contingência: Comunicar imediatamente os afetados e autoridades, acionar a equipe de segurança para investigar e corrigir, e reforçar a comunicação sobre as medidas tomadas.
Prevenção: Usamos criptografia forte, fazemos testes de segurança constantes e monitoramos atividades suspeitas 24/7.

2-) Aplicativo Fora do Ar (Indisponibilidade):

Risco: Usuários não conseguem usar o app devido a problemas técnicos.
Plano de Contingência: Ativar sistemas de reserva, acionar a equipe de TI para resolver o problema rapidamente e manter os usuários informados sobre o status.
Prevenção: Monitoramos tudo 24/7, temos backups regulares e nossa infraestrutura na nuvem é construída para ser resistente a falhas.

## 7. Casos de Teste

Exemplo de Caso de Teste: Verificação de CNH do Motorista
Este caso de teste visa garantir que o aplicativo processa e verifica corretamente a CNH enviada pelo motorista.

ID do Caso de Teste: CT-APROV-001
Título do Teste: Validar a funcionalidade de envio e verificação da CNH do motorista.
Funcionalidade Testada: Processo de Aprovação de Motorista - Verificação de CNH
Pré-condições:
O motorista deve ter uma conta cadastrada no aplicativo unicaride e estar logado.
O motorista ainda não deve ter sua CNH aprovada.
O dispositivo do motorista deve ter conexão à internet e acesso à câmera (para foto) ou à galeria de fotos.
Ter disponível uma imagem de CNH válida para teste.
Ter disponível uma imagem de CNH inválida (ex: vencida, ilegível, falsa) para teste.

## 8. Métricas

Métricas para avaliar a eficácia dos testes
As métricas que utilizaremos, para avaliar os testes, vão ser, se o aplicativo consegue gerar uma notificação de corrida para o usuário que deseja a carona, e para o motorista se o pop up de corrida chega nele, outra métrica vai ser se o aplicativo está rodando de uma forma ‘’lisa’’, sem bugs.

Critérios de cobertura mínima

100% dos campos de busca (origem, destino, data, hora) devem ser testados com entradas válidas e inválidas.
Pelo menos um cenário de "carona encontrada" e um cenário de "nenhuma carona encontrada" devem ser testados.
A interface da lista de resultados da busca deve ser validada para garantir que todas as informações essenciais da carona (motorista, veículo, preço) são exibidas corretamente.

Nível aceitável de defeitos
O nível mínimo de defeitos que procuramos atingir, é de cerca de 65%, já a máxima que procuramos estar atingindo é de 80% de eficiência sem bugs, para dessa forma o aplicativo seguir seu fluxo normalmente.


## 9. Relatórios

Este relatório apresenta um resumo do Plano de Teste desenvolvido para o aplicativo de caronas unicarride. O objetivo principal foi garantir a qualidade, segurança e usabilidade do aplicativo antes de seu lançamento.

Estratégia de Teste

Realizamos uma série de testes essenciais para cobrir diferentes aspectos do aplicativo:

Testes Funcionais: Verificamos se todas as funcionalidades (busca de caronas, cadastro, pagamento, etc.) operam como esperado.
Testes de Performance: Avaliamos a velocidade e a capacidade do aplicativo sob condições de uso intenso.
Testes de Segurança: Buscamos vulnerabilidades para proteger os dados dos usuários e o sistema.
Testes de Usabilidade: Analisamos a facilidade de uso e a experiência do usuário.
Testes de Regressão: Asseguramos que novas alterações não comprometeram funcionalidades existentes.
Os testes foram executados em um ambiente de teste separado, utilizando dados fictícios, para não impactar a operação real do aplicativo.

## 10. Aprovação

| Nome   | Papel   | Assinatura | Data       |
| ------ | ------- | ---------- | ---------- |
| [Nome] | [Papel] |            | DD/MM/AAAA |
| [Nome] | [Papel] |            | DD/MM/AAAA |

>[!WARNING]
>A execução completa do plano de testes é essencial para garantir a qualidade do software. Qualquer desvio do plano deve ser documentado e justificado.
