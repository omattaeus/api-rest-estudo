## Requisitos para rodar o projeto

### Setup de ambiente:

- [Java 21](https://www.java.com/pt-BR/)
  - Instalar [`Java 21`](https://www.oracle.com/br/java/technologies/downloads/#java21)
- [Spring Boot 3.2.5](https://spring.io/projects/spring-boot)
  - Usando [`JVM`](https://github.com/nvm-sh/nvm)
    - `winget search Oracle.JDK`
   
### Como rodar na minha máquina?

- Clone o projeto `git clone git@github.com:omattaeus/api-animais.git`
  
- Rode `javac Startup.java`
- Pronto 🎉

### Documentação
    
     🕗 EM DESENVOLVIMENTO

- [Documentação](https://github.com/omattaeus/api-animais/tree/master/documenta%C3%A7%C3%A3o)
    
- `./documentação`: É onde você pode encontrar os arquivos de documentação, como planilha de teste, digramas e entre outros.
- `./documentação/planilha-de-teste`: É onde você pode encontrar os arquivos de planilha de teste com cobertura de teste prevista de 90% e também fazendo utilização do Pitest para Teste de Mutação para fazer verificação e análises dos testes implementados.
- `./documentação/diagramas`: É onde você pode encontrar os arquivos de diagramas, entre eles: Diagramas De Classe, Diagramas de Casos de Uso e Diagrama De Implantação.
Com os Diagramas podemos ter uma visão mais ampla e geral do sistema ao todo.

### Estrutura do projeto

- [src](https://github.com/omattaeus/api-animais/tree/master/src)

- `./src`: É onde você pode encontrar todas as pastas e classes do projeto.
- `./configuration`: É onde estará a configuração de segurança, como quais endpoints serão liberado para acesso e quais serão bloqueados para acesso apenas sendo permito atráves de autenticação.
- `./controllers`: É onde está os controladores da aplicação, ou seja, onde está a parte que será feita a requesição pela URL.
- `./exceptions`: É onde está a toda a parte de tratamento de exceção.
- `./models`: É a parte onde estão representados a entidade que sera mapeada para o banco de dados.
- `./repositores`: É a pasta onde estarão a implementação do JPA ou seja, as interfaces, juntamente com métodos declarados mas ainda não implementado.
- `./securityJwt`: É onde está a toda a parte do JWT como geração de token de acesso, fazer o filtro do token e a configuração do Token JWT.
- `./services`: São todas as lógicas da aplicação, aqui estará fazendo todo o processamento de dados.

### Estrutura do projeto

- [Resources](https://github.com/omattaeus/api-animais/tree/master/src/main/resources)
- [Pom.xml](https://github.com/omattaeus/api-animais/blob/master/pom.xml)

- `./resources`: Aqui estará toda a configuração de acesso, como a parte de conexão com o banco de dados e outras configurações.
- `./pom.xml`: Aqui está todas as dependências necessária para que o projeto funcione.

### Estrutura do projeto - Testes

- [src (testes)](https://github.com/omattaeus/api-animais/tree/master/src/test/java/br/com/compilou/api_animals)

- `./src`: É onde você pode encontrar todas as pastas e classes do projeto.
- `./repositories`: Aqui estará toda a parte de teste do repository, ou seja, os teste de Create, Read, Update e Delete.
- `./services`: Aqui está todos testes da classe de service, como o AnimaisServices.

### ENDPOINTS
Todos os Endpoints foi testado pela ferramenda do POSTMAN.

#### GET (por id)


  
    localhost:8080/api/get-animais/{id}

Deve retornar este JSON:

    {
        "id": "b7fb9b04-cb9a-4d85-802e-a9e5ed107da9",
        "name": "Scobby",
        "age": "3",
        "race": "Dogzinho do Norte"
    }

#### GET (todos os animais)


  
    localhost:8080/api/all-animais

Deve retornar todos os animais em formato JSON

#### POST (criar animais)


  
    localhost:8080/api/create-animais

Neste Endpoint deve ser passado um animal, com name, age e race.

    {
        "name": "Biju",
        "age": "8",
        "race": "Dogzinha da Sul"
    }

#### PUT (alterar dados)

    localhost:8080/api/update-animals

Deve ser passado como JSON a alteração que desejar e também o ID no JSON (o id no formato UUID)

    {
        "id": "354467d6-3c32-4bbf-a6f7-50c4644c2975",
        "name": "Biju",
        "age": "8",
        "race": "Caramela da Sul"
    }

#### DELETE (excluir dados)

    localhost:8080/api/delete-animais/{id}

Neste Endpoints passado pelo ID qual animal será deletado do banco de dados.
Deverá retornar 200OK.
