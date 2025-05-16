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

Horário e vagas disponíveis.

Botão "Solicitar Vaga".
