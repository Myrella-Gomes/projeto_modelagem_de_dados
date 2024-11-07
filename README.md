# Projeto_modelagem_de_dados
O processo de modelagem conceitual do projeto levou em consideração o cenário de ordens de serviço de uma oficina. Foram criadas entidades desenvolvido o relacionamento entre cada entidade durante o projeto conceitual, até a execução do projeto lógico no MySQL Workbench. 

# Objetivo:
Criar um esquema conceitual para o contexto de oficina com base na narrativa fornecida pelo BootCamp da DIO.

# Narrativa:
1. Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
2. Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas
3. Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
4. A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
5. O valor de cada peça também irá compor a OSO cliente autoriza a execução dos serviços
6. A mesma equipe avalia e executa os serviços
7. Os mecânicos possuem código, nome, endereço e especialidade
8. Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

# Entidades e Relacionamentos:
- Cliente: um cliente leva um ou mais veículos à oficina e pode solicitar um ou mais serviços. O cliente autoriza a ordem de serviço gerada pelo funcionário e paga pelos serviços contidos na mesma. 
- Veículos: a entidade veículo contém a FK idcliente para identificar o cliente caso mais de um veículo seja levado para oficina.
- Funcionários: a entidade funcionário conta com os mecânicos que irão avaliar o carro e gerar a ordem de serviço com as informações descritas anteriormente. Um funcionário pode gerair mais de uma ordens de serviço, mas uma ordem de serviço é gerada apenas por um funcionário. 
- Ordem de serviço: a entidade fará consultas dos preços na entidade Serviço. Mais de um serviço pode compor uma ordem de serviço.
- Serviço: a entidade se relaciona com as consultas feitas pela entidade Ordens de serviço.
- Pagamento: o cliente pode ter mais de uma forma de pagamento.
