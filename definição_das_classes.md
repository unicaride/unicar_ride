@startuml Diagrama de Classes - App Carona Universitária
!theme materia

```` Definição das Classes;


class*Usuario* { -->   - idUsuario: Integer;
  - nome: String
  - email: String
  - senhaCriptografada: String
  - telefone: String
  - instituicaoEnsino: String
  - fotoPerfilURL: String
  - fazerLogin(email, senha): boolean
  - fazerLogout()
  - editarPerfil(novosDados: Map)
  - verificarIdentidade()
}
``` 



##### Note right of*Usuario*

  Classe base para todos os usuários do sistema.
  
  Contém informações comuns e funcionalidades básicas.
  
  ##### Nota final

#### Class Motorista << (M,orchid) >> extends Usuario {
  + cnh: String
  + avaliacaoMediaMotorista: Float
  + gerenciarVeiculos()
  + oferecerNovaCarona(detalhesViagem: Viagem): Viagem
  + verMinhasCaronasOferecidas(): List<Viagem>
  + gerenciarSolicitacoes(idViagem: Integer): List<SolicitacaoCarona>
  + aceitarSolicitacao(idSolicitacao: Integer): boolean
  + recusarSolicitacao(idSolicitacao: Integer): boolean
  + iniciarViagem(idViagem: Integer)
  + finalizarViagem(idViagem: Integer)
  + atualizarLocalizacaoEmTempoReal(idViagem: Integer, local: Localizacao)
  + avaliarCaroneiro(idViagem: Integer, idCaroneiro: Integer, avaliacao: Avaliacao)
}

##### Note right of*Motorista*

+ Representa um usuário que oferece caronas.
  
+ Herda de Usuário e adiciona atributos e comportamentos específicos de motorista.

 ##### Nota final

#### Class Caroneiro << (C,lightblue) >> extends Usuario {
  - avaliacaoMediaCaroneiro: Float
  + buscarCaronas(origem: Localizacao, destino: Localizacao, dataHora: DateTime, filtros: Map): List<Viagem>
  + solicitarCarona(idViagem: Integer, pontoEncontro: Localizacao, numPassageiros: Integer): SolicitacaoCarona
  + verMinhasSolicitacoes(): List<SolicitacaoCarona>
  + cancelarSolicitacao(idSolicitacao: Integer): boolean
  + verMinhasViagensAgendadas(): List<Viagem>
  + avaliarMotorista(idViagem: Integer, avaliacao: Avaliacao)
  + acompanharTrajetoEmTempoReal(idViagem: Integer): Localizacao
}

##### Note right of*Caroneiro*

+ Representa um usuário que busca caronas.
  
+ Herda de Usuário e adiciona atributos e comportamentos específicos de caroneiro.
end note

#### Class Veiculo {
  - idVeiculo: Integer
  - placa: String
  - modelo: String
  - cor: String
  - anoFabricacao: Integer
  - capacidadePassageiros: Integer
  - renavam: String
  - apelido: String (ex: "Meu possante")
  - cadastrarVeiculo()
  - editarDetalhesVeiculo()
  - removerVeiculo()
}

note left of Veiculo
  Informações sobre o veículo
  utilizado nas caronas.
end note

#### class*Viagem*{
  - idViagem: Integer
  - pontoPartida: Localizacao
  - pontoDestino: Localizacao
  - dataHoraPartidaPrevista: DateTime
  - dataHoraChegadaPrevista: DateTime
  - dataHoraPartidaReal: DateTime
  - dataHoraChegadaReal: DateTime
  - vagasOferecidas: Integer
  - vagasDisponiveis: Integer
  - valorPorPassageiro: Float <<Solidário: pode ser 0>>
  - statusViagem: StatusViagemEnum
  - observacoesMotorista: String
  - rotaPlanejada: List<Localizacao>
  - trajetoRealizado: List<Localizacao>
  - calcularRotaEstimada()
  - adicionarParadaIntermediaria(local: Localizacao)
  - removerParadaIntermediaria(local: Localizacao)
  - notificarParticipantes(mensagem: String)
  - atualizarStatus(novoStatus: StatusViagemEnum)
  - adicionarPassageiroConfirmado(caroneiro: Caroneiro)
  - removerPassageiro(caroneiro: Caroneiro)
  - registrarPontoTrajeto(local: Localizacao)
}

note bottom of Viagem

  Entidade central que representa uma carona oferecida.
  
  Conecta motorista, veículo, caroneiros e detalhes do percurso.
  
  O atributo "valorPorPassageiro" pode ser zero,reforçando o caráter "solidário" do app.
  
  "Acompanhamento de trajeto em tempo real" é feito
  através da atualização de `trajetoRealizado`.
  
##### end note

#### class*SolicitacaoCarona* {
  - idSolicitacao: Integer
  - dataHoraSolicitacao: DateTime
  - pontoEncontroSugerido: Localizacao
  - numeroPassageirosSolicitados: Integer
  - statusSolicitacao: StatusSolicitacaoEnum
  - mensagemOpcional: String
  - criarSolicitacao()
  - cancelarSolicitacaoPeloCaroneiro()
}

##### note top of SolicitacaoCarona

  Representa o pedido de um caroneiro para participar de uma viagem específica.
  
##### end note

#### class*Avaliação* {
  - idAvaliacao: Integer
  - nota: Integer {1..5}
  - comentario: String
  - dataHoraAvaliacao: DateTime
  - registrarAvaliacao()
}

##### note bottom of Avaliação
  Permite que motoristas e caroneiros se avaliem mutuamente após uma viagem,
  promovendo confiança na comunidade.
end note

#### class*Localização* {
  - latitude: Double
  - longitude: Double
  - enderecoDescritivo: String (ex: "Bloco C, Cantina")
  - timestamp: DateTime
  - obterCoordenadas(): Pair<Double, Double>
  - formatarEndereco(): String
}

##### note left of Localização
  Representa um ponto geográfico,
  usado para origem, destino, pontos de
  encontro e rastreamento em tempo real.
  Pode ser adaptado para nomes de locais
  dentro da universidade.
end note

##### enum StatusViagemEnum {
  AGENDADA
  EM_ANDAMENTO
  CONCLUIDA
  CANCELADA_PELO_MOTORISTA
  LOTADA
}

##### enum StatusSolicitacaoEnum {
  PENDENTE
  ACEITA
  RECUSADA_PELO_MOTORISTA
  CANCELADA_PELO_CARONEIRO
  EXPIRADA
}

' Relacionamentos entre as Classes

' Herança
Usuario <|-- Motorista
Usuario <|-- Caroneiro

' Associações
Motorista "1" -- "0..*" Veiculo : possui >
' Um motorista pode ter vários veículos cadastrados.

Motorista "1" -- "0..*" Viagem : oferece >
' Um motorista oferece/conduz zero ou mais viagens.
Viagem "1" -- "1" Motorista : conduzida_por <

Viagem "1" -- "1" Veiculo : utiliza >
' Uma viagem utiliza um veículo específico.

Caroneiro "1" -- "0..*" SolicitacaoCarona : faz >
' Um caroneiro faz zero ou mais solicitações.
SolicitacaoCarona "1" -- "1" Caroneiro : feita_por <

SolicitacaoCarona "0..*" -- "1" Viagem : para >
' Várias solicitações podem ser para uma mesma viagem.
Viagem "1" -- "0..*" SolicitacaoCarona : recebe_solicitacoes <

' Relação de passageiros na viagem (derivada de solicitações aceitas)
Viagem "1" -- "0..*" Caroneiro : transporta_passageiros
' Uma viagem transporta de zero a N caroneiros (passageiros confirmados).
' Esta relação é efetivada quando uma SolicitacaoCarona é ACEITA.

' Avaliações
Avaliacao "1" -- "1" Viagem : referente_a_viagem >
Avaliacao "1" -- "1" Usuario : avaliador >
Avaliacao "1" -- "1" Usuario : avaliado >
' Uma avaliação é sobre uma viagem, feita por um usuário (avaliador) para outro usuário (avaliado).

' Uso de Localizacao como tipo de atributo (implícito nas classes Viagem e SolicitacaoCarona)
' Para o trajeto em tempo real e rota:
Viagem "1" o-- "0..*" Localizacao : possui_pontos_de_trajeto
' Uma viagem tem um conjunto de localizações que compõem sua rota e trajeto realizado.
