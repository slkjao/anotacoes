# notes Java

Created: August 11, 2023 8:39 PM
Reviewed: No

## Estrutura Java

### Campos e métodos

Java tem dois campos primários: métodos, também conhecidos como funções, e campos, conhecidos como variáveis.

### Método main()

Um programa Java começa a sua execução pelo método main(). Um método main é o caminho entre o começo de um aplicativo Java, que é controlado pela JVM, e o código escrito pelo programador. A JVM envia um pedido para o sistema operacional alocar memória, CPU, acesso aos arquivos, etc…

Para compilar um código Java, o arquivo deve conter uma extensão .java. O resultado é um arquivo bytecode com o mesmo nome, mas com uma extensão .class. Bytecode consiste em instruções que a JVM sabe executar.

### Tipos Primitivos

Java tem dois tipos de dados: primitivos e referência.

Os tipos primitivos são classificados em 8 subtipos, e eles representam o tipo mais básico em Java, já que todos objetos Java são uma complexa coleção de tipos primitivos. Eles são:

- boolean // true or false;
- byte // valor inteiro de 8 bits;
- short // valor inteiro de 16 bits;
- int // valor inteiro de 32 bits;
- long // valor inteiro de 64 bits;
- float // valor decimal de 32 bits;
- double // valor decimal de 64 bits;
- char // valor unicode de 16 bits;

### Tipo Referência

Um tipo referência diz respeito a um objeto, a instanciação de uma classe. Diferente dos tipos primitivos, que alocam espaço na memória e armazenam seus valores diretamente neles, os tipos referência não guardam o valor do objeto que referenciam.

Um tipo referência aponta para um objeto, guardando o endereço de memória onde aquele objeto está armazenado.

### Diferenças principais

Tipos referência podem receber o valor null. Tipos primitivos irão lancar um erro de compilação, caso recebam um valor null.

Tipos referência podem ser usados para chamar métodos. Tipos primitivos não tem métodos declarados.

### Variáveis Locais

Uma variável local é uma variável definida dentro de um método. Elas devem ser inicializadas antes do uso. Não recebem um valor padrão.

### Variáveis de Classe

Variáveis de classe também são conhecidas como campos. São compartilhadas através de vários objetos. Elas não precisam ser inicializadas. Na hora que são declaradas, recebem um valor padrão.(falso ou O.O, depende do tipo)

### Destruindo Objetos

Java prevê um coletor de lixo que automaticamente procura por objetos que não estão sendo usados.

Todos os objetos são armazenados na memória heap do programa. O heap, também conhecido como armazenamento livre, representa uma larga área de memória disponíovel, que foi alocada para sua aplicação Java.

### Coletor de Lixo

Garbage Collection se refere ao processo de automaticamente liberar memória no heap, deletando objetos que não são mais alcançáveis no programa. Um objeto não é mais alcançável em duas situações:

- Quando não há nenhuma referencia apontando para ele;
- Todas as referências aquele objeto estão fora do escopo;

### Benefícios do Java

           Orientação a objeto: Todo código é definido em classes, e a maioria dessas classes podem ser  instanciadas em objetos.

            Encapsulação: Java prevê modificadores de acesso para proteger os dados de modificações e acessos indesejados.

            Independente de plataforma: Java é uma linguagem interpretada porque é compilada para bytecode, e então executada em qualquer JVM.

            Robusto: Java tem prevenção para vazamentos de memória, além de fazer garbage collection automaticamente.

            Seguro: Java é executado em uma Virtual Machine, o que protege o código e o computador que o executa.

### Operador Java

Java tem três tipos de operadores: unário, binário e ternário.

Promoção numérica de tipos primitivos.

Se dois valores tem tipos diferentes, Java vai transformar o menor valor para o maior valor. Ex: int para long.

Se um valor é int, e o outro é ponto flutuante, Java vai transformar o inteiro em ponto flutuante.

### Core Java API’s

String é um objeto do tipo referência. Regras de concatenação:

Se os dois operadores forem numéricos, ocorre uma operação.

Se qualquer um for uma string, ocorre uma concatenação.

A expressão é avaliada da esquerda para direita.

### Imutabilidade

Quando um objeto string é criado, não é permitido mudar. Não pode ser feito maior nem menor, nem trocar caracteres dentro.

### String Pool

A String Pool, também conhecida como pool interna, é um local na JVM que coleciona todas essas strings.

Principais métodos de strings:

length() = retorna o número de caracteres em uma String;

charAt(1) = permite enviar um parâmetro int, e retorna o char na posição.

indexOf() = retorne o int index do char ou string passados como parâmetro.

substring() = retorna uma substring parametrizada.

equals e equalsIgnoreCase() = os dois retornam um boolean que verifica a ordem de caracteres de duas strings.

contains(), startsWith(), endsWith() = boolean se a string contém um char ou string parametrizados.

replace() = faz a troca de dois char, ou string.

trim() = tira os espacos das string.

### String Builder

a classe stringBuilder cria um string sem imutabilidade. Ao encadear métodos em uma string, o resultado é o surgimento de uma nova string. O encadeamento de uma stringBuilder muda o seu estado interno, e retorna uma referência para ele mesmo.

### Tamanho x Capacidade

Tamanho é o número de caracteres atuais em sequência. Capacidade é o número de caracteres que o objeto pode armazenar. Como string são imutáveis, o tamanho e a capacidade são as mesmas.

Com o stringBuilder, Java sabe que o tamanho é passível de mudança conforme o programa avança. Ao ser construído, o tamanho padrão de um stringBuilder é 16.

Método stringBuilder

- append() = adiciona o parâmetro para a stringBuilder, e retorna uma referência para ele mesmo.
- insert() = adiciona strings em um index passado como parâmetro.
- delete() = remove caracteres de uma sequência e retorna também uma referência própria.
- toString() = retorna uma string do valor armazenado.

### Equalidade

Não use == para comparar objetos string. Por serem objetos do tipo referência, o que é comparado é se as duas referências apontam para o mesmo objeto. Para comparar o conteúdo de duas strings, utilize o método equals().

### Entendendo Arrays Java

Uma array é uma área da memória no heap com espaço para um determinado número de elementos. Uma string é implemmentada como uma array onde o objeto array é trocado por uma outra array maior, quando fica sem espaço.

Para fazer a ordenação de uma arrau, usamos o método sort(), disponível em Arrays.sort(), que retorna a array em ordem alfabética. Java também dispõe de um método otimizado para fazer procura em uma array, mas somente se a array estiver ordenada, que é o método Arrays.binarySearch().

### ArraysList

Uma Array tem uma desvantagem crucial: você precisa saber de antemão quantos elementos haverá na array no momento de sua criação, e depois não há como mudar. Como um String Builder, um ArrayList pode mudar o tamanho em tempo de execução. Como uma Array, um ArrayList é uma sequência ordenada que permite cópias.

Principais métodos

- add() = insere um novo valor na ArrayList.
- remove() = remove o primeiro valor correspondente encontrado, ou remove o elemento no index específico.
- set() = troca um elemento específico da ArrayList, sem mudar o tamanho.
- isEmpty() e size() = vericfica quantos slots estão em uso.
- clear() = provê uma maneira fácil de descartar todos os elementos de uma ArrayList.
- contains() = verifica se a ArrayList contém um valor específico.
- equals() = verifica se duas ArrayList contém os mesmos elementos na mesma sequência.

### Classes Wrapper

Cada tipo primitivo tem uma classe empacotadora, que é um tipo objeto que corresponde a um tipo primitivo. Os métodos parse() retornam um tipo primitivo, e o método valueOf(), retorna um tipo empacotador.

Trabalhando com hora e data

LocalDate = instancia data

LocalTime = instancia hora

LocalDateTime = instancia hora e data

LocalDateTime.now() = instancia hora-data local.

LocalDateTime.plusDays(5) = adicione 5 dias.

LocalDateTime.minusWeeks(2) = remove 14 dias.

### Classe Período

A classe período em Java obtém uma quantidade de tempo em termo de anos, meses ou dias.

Period.ofYears(1).

### Classe Duration

Funciona de maneira similar a classe período, mas para menores unidades de tempo, como horas, minutos, segundos.

### Formatando hora e data

A classe DateTimeFormatter é usada para formatar qualquer objeto do tipo data ou hora.

- DateTimeFormatter shortDateTime = DateTimeFormatter.ofLocalizedDate(FormatStyle.SHORT);

Parseando Data e Hora

Igual o método format(), o método parse() recebe um formato.

- DateTimeFormatter f= DateTimeFormatter.ofPattern(”MM/dd/yyyy”);
- LocalDate.parse(”01/02/2015”, f);

### Métodos e encapsulamento

Modificadores de acesso

público = o método pode ser chamado por qualquer classe.

private = o método só pode ser chamado pela própria classe.

protected = só pode ser chamado por classes no mesmo pacote, ou subclasses em outros pacotes.

default = só pode ser chamado por classes no mesmo pacote.

### Parametro Varargs

Pode ser usado como um parâmetro meio específico de array, Tem que ser o último parâmetro passado. Com varargs, você pode passar uma array ou uma lista de elementos do mesmo tipo.

### Campos e métodos estáticos

Métodos estáticos não necessitam de uma instanciação para serem acessados. São compartilhados para todos os usuários da classe. Estáticos são membros do objeto único existente, independente de outras instanciações.

Cada classe tem a sua própria cópia das variáveis instanciáveis. Há somente uma cópia do código de métodos instanciáveis. Cada instância da classe pode chamá-la quantas vezes quiser.

No entanto, cada chamado de método recebe espaço extra na stack, para receber os parâmetros e variáveis locais.

Somente as variáveis recebem suas próprias cópias.

Métodos estáticos tem dois propósitos:

- Para utilidade ou métodos auxiliares. Como não há necessidade de acessar as variáveis, métodos estáticos eliminam a necessidade de ter um objeto.
- Para um estado que é compartilhado por todas instâncias de uma classe, como um contador. Todas instâncias devem compartilhar o mesmo estado. Métodos que usam esta instância devem ser estáticos.

### Inicialização Estática

São inicializadores que especificam sua inicialização assim que o código é inicializado. Devem ser evitados e realocados para um construtor, para facilitar a leitura do código.

Static Import

Import regulares são para importar toda uma classe. Import estáticos são para importar membros estáticos de uma classe.

Enviando dados entre métodos

Java é uma linguagem “pass-by-value”. Significa que uma cópia da variável é feita, e o método recebe aquela cópia. O outro padrão é “pass-by-reference”, onde uma referência para um membro é enviada. Essa, quandh chamada, afeta o estado de quem o chamou.

### Sobrecarga de Métodos

Ocorre quando há metodos com diferentes assinaturas, mas com o mesmo nome. Não é permitido sobrecarga em métodos com a mesma lista de parâmetros.

Ordem de inicialização

- Se há uma superclasse, ela é iniciada primeiro;
- Variáveis e inicializadores estáticos, na ordem em que aparecem no arquivo;
- Variáveis e inicializadores instanciáveis, na ordem em que aparecem no arquivo;
- O construtor

### Escrevendo Lambda simples

Java 8 introduziu uma nova maneira de escrever códigos. Programação funcional é uma maneira de escrever códigos mais declarativo. Você especifica o que quer fazer, ao invés de lidar com os estados dos objetos e seus loops.

Uma expressão lambda é um bloco de código usado como parâmetro.

Predicados

Lambdas funcionam com interfaces que tem apenas um método. São conhecidas como interfaces funcionais - interfaces que podem ser usadas com programação funcional.

### Herança

Ao criar uma nova classe em Java, você pode definir essa classe como uma classe que herda de outra classe.

Herança é o processo pelo qual a nova classe filho inclui automaticamente qualquer membro, método ou objeto público ou protegido. Java permite herança única, significa que cada classe só pode herdar diretamente outra classe pai. Java não suporta herança múltipla, pois gerariam códigos complexos de manutenção e leitura. Java permite uma exceção: classes podem implementar múltiplas interfaces.

Regras do construtor

- O primeiro statement de todo construtor é uma chamada para outro construtor dentro da classe usando this(), ou uma chamada para um construtor na classe pai, usando super().
- A chamada do super() não pode ocorrer depois do primeiro statement do construtor.
- Se não há nenhuma chamada explícita para o super() no construtor, Java vai automaticamente inserir um método super() como primeiro statement do construtor.
- Se a classe pai não tem um construtor sem argumentos, e a classe filho não define um construtor, o compilador lança um error, e tenta inserir um construtor padrão sem argumentos na classe filho.
- Se a classe pai não tem um construtor vazio, o compilador requer uma chamada explícita para a classe pai, em cada classe filho.

Em Java, o construtor pai sempre é executado antes do construtor filho.

### Sobrescrita de método

Você pode sobrescrever um método através de declarar um novo método com a mesma assinatura e tipo de retorno do método da classe pai.

Sobrescrever um método tem suas restrições. O compilador perfoma as seguintes checagens ao sobrescrever um método não privado:

- O método na classe filho deve ter a mesma assinatura do método na classe pai.
- O método na classe filho deve ser tão acessível ou mais que o método na classe pai.
- O método filho não pode lançar uma excessão que é nova, ou mais abrangente que o método na classe pai.
- O tipo de retorno deve ser o mesmo.

### Sobrecarga x Sobrescrita

A diferença é que um método sobrecarregado vai usar uma assinatura diferente do que um método sobrescrito.

Escondendo métodos estáticos

Um método escondido ocorre quando a classe filha define um método estático com o mesmo nome e assinatura definidos na classe pai. As regras para um método escondido são as quatros regras de um método sobrescrito, mais uma:

- O método definido na classe filho deve ser marcado como static, se também é marcado momo static na classe pai.

### Criando método finais

Métodos finais não podem ser sobrescritos. É útil marcar um método como final quando se está criando uma classe pai, e se quer garantir certo comportamento de um método, independentemente de qual filho está invocando o método.

### Abstrato

Uma classe abstrata, é uma classe marcada com a keyword abstract e que não pode ser instanciada. Um método abstrato é um método com a keyword abstract, definido em uma classe abstrata, que não tem implementação provida na classe em que é declarada.

### Definindo uma classe abstrata

Uma classe abstrata pode incluir métodos e variáveis não abstratos, embora um método abstrato só pode ser definido em uma classe abstrata. Uma classe abstrata não pode fazer muito, além de definir variáveis e métodos estáticos. Uma classe abstrata se torna útil quando é extendida por uma subclasse concreta. A subclasse também deve implementar todos os métodos abstratos herdados.

### Implementando Interfaces

Apesar de Java não permitir herança múltipla, ele permite que classes implementem qualquer número de interfaces. Uma interface é um dado do tipo abstrato que define uma lista de métodos públicos abstratos, que qualquer classe que a implemente deve definir.

### Herdando uma Interface

Uma interface que estende outra interface, assim como uma classe abstrata que implementa uma interface, herdam todos os métodos como seus.

A primeira classe concreta que implementa uma interface, deve prover uma implementação para todos métodos abstratos herdados.

### Variáveis de Interface

Variáveis de interface são consideradas public, static e final.

Como é considerada final, o valor da variável deve ser declarado no momento da definição.

### Métodos Default de Interface

Um método default é um método definido em uma interface com a palavra Default. Define um método abstrato com uma implementação default.

Um método default só pode ser declarado em uma interface.

É considerado public, e pode ser sobrescrito.

Se uma classe implementar duas interfaces que tem métodos default com o mesmo nome e assinatura, o compilador vai lançar um erro.

### Polimorfismo

Java suporta polimorfismo, a propriedade de um objeto ter diferentes formas. Para ser mais preciso, um objeto Java pode ser acessado usando uma referência do mesmo tipo do objeto, ou a referência de uma superclasse do objeto, ou uma referência que define uma interface que o objeto implementa.

### Objeto x Referência

Em Java, todos os objetos são acessados por referência. Conceitualmente, deve-se considerar um objeto como a entidade que existe na memória, alocada pelo Java Runtime Environment.

O tipo do objeto determina quais propriedades existem do objeto na memória

O tipo de referência para o objeto determina quais métodos e variáveis são acessíveis para o programa Java.

### Casting

Casting de um objeto de uma subclasse para uma superclasse não requer um casting explícito.

Casting de um objeto de uma superclasse para uma subclasse requer um casting explícito.

O compilador não permite casting de tipos não relacionados.

Uma excessão em tempo de execução pode ser lançada, caso o objeto não seja uma instância da classe.

Para verificar se uma classe é uma instanciação de outra, é usado o método instanceOf().

### Método Virtual

Um método virtual é um método em que a implementação específica não é determinada até a execução. Se você chamar um método em um objeto que sobrescreve um método, você recebe o método sobrescrito, mesmo se a chamada do método vier de uma referência de classe pai.

### Parâmetro Polimórfico

Uma das aplicações mais úteis do polimorfismo é a habilidade de passar instancias de uma subclasse ou interface para um método. Por exemplo, você pode definir um método que recebe uma instância de uma interface como parâmetro. Nesse sentido, qualquer classe que implementa a interface pode ser passada para o método. Como você está fazendo o casting de uma subclasse para uma superclasse, um casting explícito não é requerido. Caso você esteja definindo um método que vai ser acessível fora da classe atual, tanto por uma subclasse ou por objetos de outras classes, é boa prática usar a superclasse, ou tipo interface como parâmetros de entrada, sempre que possível.

### Exceptions

Quando o código encontra algum problema, que não é capaz de resolver, ele lança uma excessão. Quando se escreve um método, você pode lidar com a exceção, ou lançá-la para quem chamou o método.

Java tem uma superclasse throwable, que tem todos os objetos para representar exceptions.

Uma runtimeException é definida como a classe RuntimeException e suas subclasses. Também são conhecidas como unchecked exceptions.

Uma runtimeException é definida pela classe RuntimeException e suas subclasses. Também são conhecidas como unchecked exceptions.

Uma runtimeException é um tipo específico de excessão. Todas excessões ocorrem no momento que o programa é executado. A alternativa é erro em tempo de compilação. Quando se refere a runtime, significa unchecked.

Uma checked exception inclui a classe Exception e todas as subclasses que não extendem RuntimeException. Checked exceptions tendem a ser antecipadas. Por isso, Java força que o programador faça algo para lidar com a possível exception.

### Try Statement

Java usa um try statement para separar a lógica que pode lançar uma exceção, da lógica que cuida dessa exceção. O bloco catch só é executado caso alguma exceção seja lançada, e o bloco finally é execcutado independentemente de ter sido lançado alguma exceção ou não.

### Catch com várias exceções

Java avalia os múltiplos blocos de catch na ordem em que eles aparecem. Se for impossível que um bloco catch seja executado, um erro de compilação sobre código inacessível ocorre. No máximo, um bloco catch será executado, e será o primeiro bloco catch que puder ser usado.

### Runtime Exception

RuntimeException não precisam ser lançados ou declarados:

- ArithmeticException: Lançada pela JVM quando o código tenta dividir por zero;
- ArrayIndexOutOfBoundException: Lançada pela JVM quando o código usa um index ilegal para acessar a array;
- ClassCastException: Lançada pela JVM quando se tenta fazer o casting de uma subclasse da qual não é uma instância;
- IllegalArgumentException: Lançada pelo programador para indicar que um método recebeu um parâmetro ilegal;
- NullPointerException: Lançada pela JVM quando se há uma referência null;
- NumberFormatException: Lançada pelo programador quando se tenta converter uma string para um tipo numérico, mas a string não tem o formato apropriado;

StackOverflowError: quando Java chama um método, coloca os parâmetros e variáveis locais desse método na stack. Após fazer isso por várias vezes em recurssão, a stack fica sem espaço na memória e transborda.

### Subclasses

Quando uma classe sobrescreve o método de uma superclasse, ou implementa o método de uma interface, não lhe é permitido adicionar excessões para a assinatura do método. Ela é permitida declarar menos exceções do que a superclasse ou interface.

Similarmente, é permitido a uma classe declarar exceções de um subtipo que foi lançado no método pai, já que a superclasse ou interface já tomaram conta do tipo mais genérico.
