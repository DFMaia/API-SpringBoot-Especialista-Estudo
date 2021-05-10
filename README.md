# Sobre esse repositório:
- Esse repositório é um esoforço para aprender sobre REST API
- O objetivo do projeto é se tornar um espcialista SpringRest. 
- O Curso é disponibilizado pela AlgaWorks.
- Esse projeto é um MVP (Produto Mínimo Viável) de uma API de delivery de comidas.
- - -
### O que é uma API?
- :point_right: Application Programming Interface.
- Sistemas operacionais como o Windows, MacOS, iOS, Android, etc, disponibilizam API's para o código do desenvoldor para poder desenvolver funcionalidades e/ou fornecer informações. 
- - -
### O que é REST?
- :point_right: Representation State Transfer
- - -
### O que é Spring?
- :point_right: É uma tecnologia de backend. Não é apenas um framework. Um _**conjunto**_ de projetos que resolvem vários problemas de um programador backend.
- É comum ver o spring ser chamado de um ecossistema. 
- SpringBoot não somente é usado para aplicações web. Poderá ser usando para aplicações não web.
- [Documentação Spring - Oficial](https://spring.io/)
- [Documentação Spring (Não oficial)](https://spring.io/projects/spring-boot).
- [GitHub do Spring](https://github.com/spring-projects/spring-boot).
- [Documentação Spring Properties](https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html).
- - - 
### Porque Usar o Spring?
- Canivete suíço para desenvolvedores Java.
- Simplicidade.
- Maturidade.
- Modularidade.
- Evolução constante.
- Open Source.
- Comunidade grande e forte.
- Popularidade.
- Empregabilidade.
- - - 
### O que é persistência de dados?
- Dados que continuam a existir depois que a aplicação para de ser executada. 
- Um Driver JDBC é o que intermedia o código Java e o Banco de Dados MySQL: `Código Java -> Driver JDBC -> MySQL`.
- ORM (Object Relational Mapping) técina de mapeamento de classes que representam entidades para tabelas de um banco de dados relacional: `Código Java -> ORM -> Driver JDBC -> MySQL`.
- O ORM implicitamente executa códigos MySQL. Consegue fazer isso porque todo o código foi mapeado e atribui aos objetos as tabelas. 
- Redução de código.
- - - 
### O que é JPA?
- É uma especificação Java EE.
- Uma solução ORM.
- - - 
### O que é Hibernate?
- Hibernate é a implementação da especificação JPA.
- - - 
### Ambiente de Desenvolvimento
- JDK 12.
- IDE de uso: [Spring Tools Suite](https://spring.io/tools).
- MySQL Workbench. [Documentação](https://dev.mysql.com/doc/connector-j/8.0/en/)
- - - 
### Sobre o POM
- Toda dependência está sendo adicionada pelo Spring Tools e não por código xml coletado no repositório Maven. `Botão direito no projeto -> Spring -> add starters`
- `DevTools`: Realiza o restart automático da aplicação uma vez que há uma alteração dentro de uma classe ou arquivo. Isso evita que a pessoa desenvolvedora precise parar a aplicação e a inicie de novo. 
- `Spring Data JPA`: Para fazer conexão com o banco de dados.
- `MySQL`: Para se conectar especificamente com o MySQL
- - - 
### applications.porpeties
- Para a conexão com o banco de dados :point_down:
- spring.datasource.url=< aqui a sintaxe do banco >?createDatabaseIfNotExist=true&serverTimezone=UTC
- spring.datasource.username=< insira aqui o usuário do banco >
- spring.datasource.password=< a senha >  
-  - -
- spring.jpa.generate-ddl=true: :point_right: Essa configuração faz com que as tabelas (entidades e afins) que que eu estiver escrevendo no Java, já criem tabelas no MySQL. Ele vai executar comandos MySQL.
- spring.jpa.hibernate.ddl-auto=create: :point_right: Derruba e cria o banco toda vez que a aplicação reinicia. (Somente para ambiente de teste) Facilita para criar e apagar nomes nas tabelas sem ter que ficar alterando no banco. 
- - - 
- import.sql :point_right: Esse arquivo na verdade não fica dentro de porpeties, mas fica dentro da pasta de porpeties. Uma vez criado como file, digite os comandos dos valores que quer inserir no banco e salve. Ele vai inserir esses dados diretamente no banco. 
- - - 
- spring.jpa.show-sql=true :point_right: mostra os comandos sql no terminal gerado quando o código está sendo executado.
- - -
### Sobre as Annotations
- `@Controller`: Responsável por receber requisições web.
- `@GetMapping`: Caminho para se chegar nessa resposta.
- `@ResponseBody`: É a resposta a requisição feita no `Controller`. É o que será respondido pelo método de retornno.
- `@Component`: Permite que o objeto possa ser injetado em outras classes. O `Controller` é um `Component`: e por sua vez o `Component` é um `@Bean`. 
- `@Configuration`: configura outros `@Bean`. Dentro da classe `Configuration` outros métodos de outras classes podem ser configurados e as classes em si desses objetos passam a não precisar de uma `Annotation`.
- `@Autowired`: Injeção de dependência.
- `@Primary`: Caso eu esteja classes que implementam uma interface e o componente não souber qual usar, essa `Annotation` define qual a classe que terá a prioridade de uso. 
- `@Qualifier("string")`: Para ser usado na mesma situação acima. No entanto eu coloco esse `Qualifier` com um argumento no método e nas outas classes que o utilizam.  
- `@Entity`: Classe de cada tabela. 
- `@Table(name="nome_real_na_tabela")`: Quando o nome na tabela tem um nome diferente da classe no java, anotamos isso logo abaixo da `annotation @Entity`
- `@Id`: identificador único.
- `@GeneratedValue(strategy = GenerationType.IDENTITY)`: Faz com que o id seja incrementado de 1 em 1.
- `@Column`: Coluna da tabela que no Java é um atributo. Caso o nome na tabela desta coluna seja outro, coloque entre parênteses logo depois da `annotation`: (name = "nome_cozinha").
- `@PersistenceContext`: É usado para a interface `EntityManager`. Pode ser usado o `@Autowired`, mas como existe uma `annotations` diretamente para o `EntityManager`, então é bom usá-la. 
- - - 
### Sobre código:
- `EntityManager`: É uma interface no JPA. É a que gerencia o contexto de persistência. Gerencia o código e a conversa com o banco. Salva no banco, consulta, altera, delete, etc.