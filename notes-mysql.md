# notes mysql

## Banco de Dados - Modelo Relacional

O modelo ER é conceitual e tem como objetivo representar o mundo real como entidades e seus relacionamentos com outras entidades.

- **Entidades Físicas:** elas existem e são visíveis no mundo real.
- **Entidades Conceituais:** existem devido a interação com outras entidades.

- **Atributos:** propriedades que descrevem as entidades.
- **Atributos chave:** conjunto de um ou mais atributos que tem a finalidade de identificar exclusivamente cada instância de cada entidade.
- **Atributos simples:** atributo que não pode ser dividido, pois já constitui uma unidade atômica.
- **Atributo composto:** atributo que pode ser dividido em vários outros atributos.
- **Atributo monovalorado:** atributos que podem possuir apenas um valor.
- **Atributo multivalorados:** possuem, ou podem possuir muitos valores.
- **Atributos derivados:** pode ter o valor obtido de outro atributo armazenado.

### Relacionamentos

**Relacionamentos** podem ser expressos por uma associação entre entidades. Podemos identificar a quantidade de instâncias de um relacionamento dos quais a entidade pode participar.

- **Relacionamento 1:1:**
  Utilizado quando se permite apenas uma ocorrência de dada entidade.
  Nesse tipo de relacionamento, uma linha em uma tabela está associada a apenas uma linha em outra tabela e vice-versa. Por exemplo, considere um cenário em que você tem uma tabela de "Pessoas" e outra tabela de "Documentos". Cada pessoa pode ter apenas um documento associado (como um passaporte), e cada documento está associado a apenas uma pessoa. Isso é um relacionamento um-para-um.

- **Relacionamento 1:N e N:1:**
  Análogos, visto que eles são diferenciados apenas pela direção em que ocorre a restrição de participação.
  Nesse tipo de relacionamento, uma linha em uma tabela está associada a várias linhas em outra tabela, mas cada linha na segunda tabela está associada a apenas uma linha na primeira tabela. Esse é o tipo de relacionamento mais comum. Por exemplo, você pode ter uma tabela de "Clientes" e outra tabela de "Pedidos". Cada cliente pode fazer vários pedidos, mas cada pedido pertence a um único cliente. Portanto, é um relacionamento um-para-muitos.

- **Relacionamento N:M:**
  Ocorre quando há a possibilidade de ocorrência de diversas instâncias de ambas as entidades.
  Nesse tipo de relacionamento, várias linhas em uma tabela podem estar associadas a várias linhas em outra tabela. No entanto, esse tipo de relacionamento não pode ser diretamente implementado em um banco de dados relacional. É necessário criar uma terceira tabela intermediária, muitas vezes chamada de tabela de junção, que armazena os relacionamentos entre as duas tabelas principais. Por exemplo, considere as tabelas "Alunos" e "Cursos". Um aluno pode se inscrever em vários cursos e um curso pode ter vários alunos matriculados. Para representar esse relacionamento muitos-para-muitos, você precisaria de uma tabela de junção que armazena os pares de aluno e curso.

  **Participação de relacionamento**

- **Participação opcional:** indica que o relacionamento é opcional. Essa cardinalidade mínima é representada pelo número 0.
- **Participação obrigatória:** indica relacionamento obrigatório. Cardinalidade mínima representada pelo número 1.

**Grau de relacionamentos:** O grau dos relacionamentos indica o número de entidades envolvidas em um relacionamento.

- **Relacionamento unário:** quando ocorre a participação de apenas uma entidade em um relacionamento.
- **Relacionamento binário:** ocorre quando há a participação de duas entidades em um relacionamento.
- **Relacionamento ternário (ou de grau maior):** ocorre quando três entidades participam de um relacionamento. Permite ao projetista uma maior liberdade semântica ao modelar um problema.

**Atributos de relacionamento:** Pode se utilizar atributos para aprofundar as informações de um relacionamento entre as entidades.

**Modelo entidade - relacionamento estendido:** Há uma gama de aplicações de banco de dados que demandam por mais exatidão em seus esquemas de dados, em termos de propriedades e restrições. O modelo ER pode ser estendido, de forma a adicionar mais semântica aos esquemas de dados.

**Subclasses, superclasses e herança:** Pode ocorrer de um grupo de entidade se subdividir em vários outros grupos com especificidades diferentes. A entidade pai é chamada de superclasse. As classes subdivididas são chamadas de subclasses.

**Herança:** uma entidade do tipo subclasse representa sua superclasse. Logo, a subclasse deve possuir todos os atributos de sua superclasse, mais os atributos específicos dela mesma.

**Especialização e Generalização:** O processo de definir um conjunto de subclasses de um tipo de entidade superclasse é chamado de especialização. Os objetivos de uma especialização são:

- Definir um conjunto de subclasses.
- Determinar seus atributos específicos.
- Estabelecer seus relacionamentos específicos adicionais.

**Generalização:** Consiste no processo de definir um tipo de entidade genérico a partir de uma série de subclasses. Processo útil para a abstração de características comuns de um conjunto de subclasses.

**Restrições sobre generalização e especialização**

- **Disjunta / total:** Uma instância da superclasse só poderá ser membro de apenas uma subclasse.
- **Disjunta / parcial:** Uma instância de uma superclasse pode ser membro de uma subclasse ou de nenhuma delas. Porém, não pode ser membro de mais de uma subclasse ao mesmo tempo.
- **Sobreposta / total:** Todas as instâncias de uma superclasse devem ser necessariamente membros de alguma subclasse. Porém, podem ocorrer sobreposições.
- **Sobreposta / parcial:** As instâncias de uma superclasse podem ser membros de uma ou mais subclasses ao mesmo tempo.

## Modelo Relacional

O modelo relacional permite aos projetistas focar na representação lógica dos dados e de seus relacionamentos em vez de lidar com detalhes do armazenamento físico.

**Relações e suas características:** Uma tabela pode ser entendida como uma estrutura bidimensional formada por linhas e colunas. As principais características de uma tabela são:

- Estrutura bidimensional composta por linhas e colunas;
- Cada linha representa uma única ocorrência de entidade;
- Cada coluna representa um atributo e possui um nome distinto;
- Cada interseção entre linha e coluna representa um valor único;
- Todos os valores de uma coluna possuem o mesmo formato;
- Cada coluna possui uma faixa de valores;
- A ordem das linhas e colunas é indiferente ao SGBD;
- Cada tabela deve apresentar um atributo ou um conjunto de atributos que identifiquem cada instância;

**Restrições:** Um banco de dados relacional pode conter diversas limitações através das restrições. As características de um modelo de dados, assim como as características do modelo relacional apresentadas, correspondem às restrições inerentes ao modelo de dados.
