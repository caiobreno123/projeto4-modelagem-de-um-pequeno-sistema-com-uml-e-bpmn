# projeto4-modelagem-de-um-pequeno-sistema-com-uml-e-bpmn

# Projeto de matriz UML e PBMN
o modelo criado tem como base um usuario reservando uma ou mais reservas de um restaurante.
## INTEGRANTES DA EQUIPE:
- Gustavo Silva de Souza
- Caio Breno

Modelo UML

    +-------------------+                           +-------------------+                           +-------------------+
       USUÁRIO                                          RESERVA                                         SALA
    +-------------------+                           +-------------------+                           +-------------------+
       - id: int                                       - id: int                                    - id: int
       - nome: String                                  - data: Date                                - nome: String
       - email: String                                 - horaInicio: Time                          - capacidade: int
                                                      - horaFim: Time                            
                                                      - status: String
    +-------------------+                           +-------------------+                           +-------------------+
     + cadastrar()                                    + confirmar()                                 + verificarDisponibilidade()
     + cancelarReserva()                              + cancelar()                                 + listarReservas()
    +-------------------+                           +-------------------+                           +-------------------+
    
              1                                      N                        1                    N
    +-------------------+---------------------------+------------------------+--------------------+
    | Um Usuário pode fazer várias Reservas         | Uma Sala pode ter várias Reservas         |
    +-------------------+---------------------------+------------------------+--------------------+


Modelo BPMN

    graph TD;
    A[Início] --> B[Usuário acessa o sistema]
    B --> C[Seleciona a Sala]
    C --> D[Escolhe data e horário]
    D --> E[Verifica disponibilidade]
    E -- Disponível --> F[Confirma reserva]
    E -- Não disponível --> C
    F --> G[Reserva registrada]
    G --> H[Fim]

