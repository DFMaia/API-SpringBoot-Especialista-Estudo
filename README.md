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
- Não é uma tecnlogia que pode ser baixada e instalada. 
- É uma especificação de modelo estrutural. 
- É uma especificação que define a forma de comunicação de componentes de software na web independente da linguagem de comunicação.
- É escalável.
- Separação entre cliente e servidor.
- A diferença entre **_REST_** e **_RESTful_** é conceitual. **_REST_** é o estilo arquiterural. **_RESTful_** é construídas em conformidades com as constraints (religiosamente).
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
### Protocolo HTTP
- É uma requisição resposta.
- **_Composição da requisição_**: `[MÉTODO] [URI] HTTP/[VERSÃO] [Cabeçalhos] [CORPO/PAYLOAD]`
- `[MÉTODO GET]`: Obtem a representação de um recurso.
- `[MÉTODO POST]`: Cria um novo recurso dentro de uma coleção de recursos.
- `[MÉTODO PUT]`: Atualiza determinado recurso. Envia no corpo da requisição o que deve ser atualizado. Nesse método, todo o recurso deve ser atualizado. Se algum item do recruso não for enviado/preenchido no corpo da requisição ele será alterado como vazio ou nulo. Alguns desenvolvedor usam o `PUT` ao invés do `POST` para criar novos recursos. Isso é má prática.  
- `[MÉTODO PATCH]`: Atualiza somente um elemento do recurso. _**Não é muito usado**_ e sua implementação não é simples. 
- `[MÉTODO DELETE]`: Remoção de um recurso. Não é passado nada no corpo. 
- `[MÉTODO HEAD]`:  Mesmo que o `GET` mas nunca retorna um corpo na resposta. Usado apenas para buscar um cabeçalho. O consumidor quando usa isso, quer saber se uma `URI` é válida, qual `MediaType` é aceito.
- `[MÉTODO OPTIONS]`: Retorna uma lista de métodos suportada pelo recurso. 
- `[MÉTODO UPDATE]`: Atualiza o dado em um banco. 
- `[URI]`: _Uniform Resource Identifier_ Conjunto de caracteres a dar um endereço aos recursos de forma não ambígua. `URL` é um tipo de `URI`.
- **_Composição da resposta_**: `[HTTP]/[Versão] [STATUS] [Cabeçalhos] [CORPO]`
- - -
### Status HTTP
- A lista de status de HHTP pode ser encontrada nesse [link](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status)
- _**Nível 200**_: Indica que a requisição foi bem sucessida.
&nbsp;&nbsp;&nbsp;&nbsp;200: OK.
&nbsp;&nbsp;&nbsp;&nbsp;2001: Criado.
&nbsp;&nbsp;&nbsp;&nbsp;204: Sem conteudo (_Quando por exemplo um conteúdo é excluído com sucesso e então o recurso fica sem conteúdo_)
- _**Nível 300**_: Indica status de redirecionamento. 
&nbsp;&nbsp;&nbsp;&nbsp;301: Movido permanentemente.
&nbsp;&nbsp;&nbsp;&nbsp;302: Encontrado.
- _**Nível 400**_: Indica algum erro por parte do consumidor da API. (Por parte de quem criou)
&nbsp;&nbsp;&nbsp;&nbsp;400: Requisição mal feita.
&nbsp;&nbsp;&nbsp;&nbsp;401: Não autorizado (precisa ser autenticado)
&nbsp;&nbsp;&nbsp;&nbsp;403: Proibido.
&nbsp;&nbsp;&nbsp;&nbsp;404: Não encontrado.
&nbsp;&nbsp;&nbsp;&nbsp;405: Método não permitido.
&nbsp;&nbsp;&nbsp;&nbsp;406: Não aceito.
- _**Nível 500**_: Indica um problema no servidor ou no código.
&nbsp;&nbsp;&nbsp;&nbsp;500: Erro interno no servidor (por exemplo quando não há um nullPointerException)
&nbsp;&nbsp;&nbsp;&nbsp;503: Serviço indisponível,
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
- [Postman](https://www.postman.com/downloads/)
- - - 
### Sobre o POM
- Toda dependência está sendo adicionada pelo Spring Tools e não por código xml coletado no repositório Maven. `Botão direito no projeto -> Spring -> add starters`
- `DevTools`: Realiza o restart automático da aplicação uma vez que há uma alteração dentro de uma classe ou arquivo. Isso evita que a pessoa desenvolvedora precise parar a aplicação e a inicie de novo. 
- `Spring Data JPA`: Para fazer conexão com o banco de dados.
- `MySQL`: Para se conectar especificamente com o MySQL
- `Lombok`: Para evitar de escrever códigos boiler plates (get e set). Mas é preciso instalar o plugin também nesse [link](https://projectlombok.org/).
- `XML`: Permite que a API responda requisições em XML. Por padrão ela responde sempre em json. :point_down:
~~~XML
<dependency>
			<groupId>com.fasterxml.jackson.dataformat</groupId>
			<artifactId>jackson-dataformat-xml</artifactId>
</dependency>
~~~
- ?
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
- `@ResponseBody`: As respostas dos métodos daquela classe devem ir no corpo de resposta da API.
- `@RestController`: É um `Controller` e um `ResponseBody`
- `@GetMapping`: Método a ser mapeado. Por padrão ele é sempre Get. 
- `@GetMapping(produces = "application/json")` OU : `@GetMapping(produces = MediaType.APPLICATION_JSON_VALUE)`: Para poder escolher quais métodos retornam json ou XML ou qualquer outro formato que você escolher. Pode colocar depois do símbolo = um array { } com todas as Media Types. Isso pode ficar dentro de `@RequestMapping`, pois dessa forma toda a classe poderá retornar somente o que for selecionado. Para isso, antes da String de mapping (exemplo: "/cozinhas"), deve-se inserir o value. Ficaria algi assim: `@RequestMapping(value = "/cozinhas", produces = MediaType.APPLICATION_JSON_VALUE)`
- `@PathVariable`: Usado para retorno de um singleton (um único objeto no corpo do json).
~~~Java
@GetMapping("/{cozinhaId}")
	public Cozinha buscar (@PathVariable("cozinhaId") Long id) {
	return cozinhaRepository.buscar(id);
}
~~~
OU
~~~Java
@GetMapping("/{cozinhaId}")
public Cozinha buscar (@PathVariable Long cozinhaId) {
	return cozinhaRepository.buscar(cozinhaId);
}
~~~
- `@JsonProperty("título")`: Essa `annotation` altera a chave que aparece no corpo do json. Na `@Entity` a propriedade **_nome_** aparece como **_nome_** no json. Quando eu coloco essa `annotation` em cima da propriedade **_nome_**, no corpo do json ao invés de retornar como **_nome_** ele retornar como **_título_**. :point_down:
~~~Java
@JsonProperty("título")
@Column(nullable = false)
private String nome;
~~~
- `@JsonIgnore`: Quando você quer que um atributo da `@Entity` não apareça no corpo da requisição.
- `@JsonRootName("gastronomia")`: Quando fazemos uma requisição get em XML ele retornar o objeto Cozinha como uma tag Cozinha. Aqui eu consigo substiruir por `gastronomia.` Essa `annotation` fica na entidade (não fica em método)
- `@ResponseStatus(HttpStatus.CREATED)`: Coloco em cima do método (geralmente na controller) para informar qual é o status que ele deve retornar.
- - - 
### Sobre código:
- `EntityManager`: É uma interface no JPA. É a que gerencia o contexto de persistência. Gerencia o código e a conversa com o banco. Salva no banco, consulta, altera, delete, etc.
:point_down: _**
- `O próximo tópico não vai ficar no projeto. É apenas uma forma de mostrar que é possível controlar as tags XML caso você queira trabalhar com elas. O padrão Json é o mais usado no mercado, é preciso avaliar se o esforço vale a pena.`**_ :point_down:
- `CozinhaXmlWrapper.class`: É possível responder em xml. E é possível alterar os nomes das tags. Se você quiser todo o controle das tags é preciso criar uma classe como essa e ter o seguint código: 
~~~Java
@JacksonXmlRootElement(localName = "cozinhas")
@Data
public class CozinhasXmlWrapper {
	
	@JsonProperty("cozinha")
	@JacksonXmlElementWrapper(useWrapping = false)
	@NonNull
	private List<Cozinha> cozinhas;

}
~~~
A primeira `annotation @JacksonXmlRootElement(localName = "cozinhas")` é para alterar a tag do objeto. A `annotation @JsonProperty("cozinha")`é para substituir a tag _**item**_. A `annotation @NonNull` é para não permitir que o método dessa classe possua construtor com parâmetro.
Já na classe `CozinhaController`
~~~Java
@GetMapping(produces = MediaType.APPLICATION_XML_VALUE)
public CozinhasXmlWrapper listarXml(){
	return new CozinhasXmlWrapper(cozinhaRepository.listar());
}
~~~
a `annotation @GetMapping(produces = MediaType.APPLICATION_XML_VALUE)` vai explicitar na resposta da requisição as alterações feitas acima. 
- `ResponseEntity<Cozinha>`: Permite que eu construa o tipo de retorno. Perceba no código abaixo que esse método retorna um tipo (uma cozinha) no corpo (body).
~~~Java
@GetMapping("/{cozinhaId}")
public ResponseEntity<Cozinha> buscar (@PathVariable Long cozinhaId) {
	Cozinha cozinha = cozinhaRepository.buscar(cozinhaId);
		
	return ResponseEntity.status(HttpStatus.OK).body(cozinha);
}
~~~
O método de cima :point_up: é bom para quando se está usando condicionais. 
O de baixo :point_down: para quando só há aquela possibilidade mesmo e por isso há uma forma mais simplificada de se faze isso. Repare no retorno:
~~~Java
@GetMapping("/{cozinhaId}")
public ResponseEntity<Cozinha> buscar (@PathVariable Long cozinhaId) {
	Cozinha cozinha = cozinhaRepository.buscar(cozinhaId);
		
	return ResponseEntity.ok(cozinha);
}
~~~
E por fim, quando quero personalizar um header, além de personalizar somente o status :point_down:
~~~Java
@GetMapping("/{cozinhaId}")
public ResponseEntity<Cozinha> buscar (@PathVariable Long cozinhaId) {
	Cozinha cozinha = cozinhaRepository.buscar(cozinhaId);
		
	HttpHeaders headers = new HttpHeaders();
	headers.add(HttpHeaders.LOCATION, "http://api.algafood.local:8080/cpzinhas");
		
	return ResponseEntity
			.status(HttpStatus.FOUND)
			.headers(headers)
			.build();
}
~~~
- 