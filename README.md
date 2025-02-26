# Projeto DecolaTech - Primeiros Passos com Spring Boot

Este projeto faz parte do curso de **Primeiros Passos com Spring Boot** da plataforma DIO, oferecido no programa **DecolaTech** da Avanade. 
O objetivo deste projeto foi criar uma aplicação simples utilizando Spring Boot, implementando uma calculadora com o uso de `CommandLineRunner` para executar operações na inicialização do aplicativo.

## Estrutura do Projeto

O projeto é composto por três classes principais:

### 1. PrimeirosPassosApplication
- **Classe principal** que inicializa a aplicação Spring Boot.
- **Anotação `@SpringBootApplication`**: Indica que esta é a classe de configuração principal da aplicação Spring Boot.
- **Método `main`**: O ponto de entrada da aplicação, que inicializa o Spring Boot através do `SpringApplication.run()`.

### 2. Calculadora
- **Componente** que contém o método de operação de soma.
- **Anotação `@Component`**: Marca a classe como um bean gerenciado pelo Spring, permitindo que o Spring faça a injeção de dependência automaticamente.
- **Método `somar`**: Recebe dois números inteiros e retorna a soma dos mesmos.

### 3. MyApp
- **Classe responsável** por executar a lógica de inicialização e interagir com o componente `Calculadora`.
- **Anotação `@Component`**: Marca a classe como um bean do Spring para que possa ser gerenciada pelo contêiner do Spring.
- **Interface `CommandLineRunner`**: Permite executar código ao iniciar a aplicação. O método `run()` é chamado automaticamente pelo Spring Boot quando a aplicação é iniciada.
- **Anotação `@Autowired`**: Realiza a injeção de dependência da classe `Calculadora` na variável `calculadora`, permitindo que o método `somar` seja chamado.

## Fluxo do Aplicativo

1. Quando a aplicação é iniciada, o Spring Boot executa a classe `PrimeirosPassosApplication`, que é a classe principal.
2. O Spring Boot detecta que a classe `MyApp` é um `CommandLineRunner` e executa seu método `run`.
3. No método `run`, a instância da classe `Calculadora` é automaticamente injetada pelo Spring através da anotação `@Autowired`.
4. A operação de soma é realizada chamando o método `somar(2, 7)` da classe `Calculadora`.
5. O resultado da soma (que é 9) é impresso no console: `"O resultado é 9"`.

## Tecnologias Utilizadas

- **Java 23**
- **Spring Boot 2.x**
- **Maven**
