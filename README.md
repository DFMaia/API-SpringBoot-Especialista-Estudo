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
### Ambiente de Desenvolvimento
- JDK 12.
- IDE de uso: [Spring Tools Suite](https://spring.io/tools).
- ???
- - -
### Sobre o POM
- `DevTools`: Realiza o restart automático da aplicação uma vez que há uma alteração dentro de uma classe ou arquivo. Isso evita que a pessoa desenvolvedora precise parar a aplicação e a inicie de novo. 
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
- - - 