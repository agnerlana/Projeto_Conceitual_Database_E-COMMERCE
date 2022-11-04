# Projeto_Conceitual_Database_E-COMMERCE
Projeto Bootcamp DIO Unimed-BH: Refinando um Projeto Conceitual de Banco de Dados - E-COMMERCE

### Escopo do Projeto

Este projeto tem por objetivo realizar na prática a construção de um modelo de bases de dados relacionais estendido (EER), considerando para isso o contexto de um e-commerce, no qual estão relacionadas entidades como Clientes, Pedidos, Produtos, Fornecedores, Estoque, entre outros.

**Narrativa - Produto**

- Os produtos são vendidos por uma única plataforma online. Contudo, estes podem ter vendedores distintos (terceiros).
- Cada produto possui um fornecedor
- Um ou mais produtos podem compor um pedido


**Narrativa - Cliente**

- O cliente pode se cadastrar no site com seu CPF ou CNPJ
- O endereco do cliente irá determinar o valor do frete
- Um cliente pode comprar mais de um pedido. Este tem um período de carência para devolução do produto.

**Narrativa - Pedido**

- Os pedidos são criados por clientes e possuem informações de compra, endereço, status da entrega
- Um produto ou mais compoem o pedido e este pode ser cancelado.

**Narrativa - Fornecedor**

- Os produtos ofertados podem ser obtidos por fornecedores, podem estar disponíveis em estoque ou ainda serem vendidos por terceiros.

**Narrativa - Entrega**

- Os produtos obtidos pelos fornecedores ou disponíveis em estoque são entregues pelo e-commerce
- Os produtos vendidos por terceiros são entregues por terceiros.



#### Desafio: Refinamento do Modelo

- Cliente PJ e PF - Uma conta pode ser PJ ou PF, mas não pode ter as duas informações.
*Solução*: Neste caso, o modelo apresentava os clientes como uma única entidade, a qual foi especializada nas entidades PF (pessoa física) e PJ (pessoa jurídica), de modo que o mesmo cliente pode ter ambos os acessos, a partir do qual o pedido passa a ser realizado de acordo com a natureza jurídica escolhida pelo cliente no momento do login.

Pagamento - Pode ter cadastrado mais de uma forma de pagamento.
*Solução*: Para tanto, foi criada uma entidade Pagamentos relacionada ao Cliente, onde passam a ser armazenadas as informações de pagamento do mesmo. Além disso, os Pagamentos também se relacionam à entidade Pedidos.

Entrega - Possui status e código de rastreio
*Solução*: Juntamente à entidade Estoque foi criada a entidade Entrega, sendo relacionadas pela Expedição. Por meio deste relacionamento deve ocorrer a avaliação da disponibilidade dos produtos em Estoque e demais informações referentes ao envio do pedido. P.S: Com exceção dos produtos vendidos por terceiros, cuja responsabilidade
da entrega é dos terceiros.


### Considerações sobre o projeto apresentado
Tratando-se do desafio inicial sobre modelagem de dados, no projeto apresentado não foram inseridos todos os atributos necessários (ou ainda desejados) para cada entidade apresentada. Sobretudo para facilitar a compreensão do modelo **conceitual**, o objetivo foi demonstrar como são estruturadas as entidades e definidos os seus relacionamentos na construção de um modelo de base de dados.
