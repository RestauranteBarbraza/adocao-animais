Amanda Cristina Rodrigues da Silva
RA:72300810

Angelica Cristina de Carvalho
RA:72250275

Beatriz Spíndola da Silva
RA:72300023

Gustavo de Araújo Gomes de Souza
RA:72200361

Saulo de Tarso Lima
RA:72250593

Thaís de Miranda Grochocki
RA:72251162

Introdução
A aplicação foi desenvolvida em Java utilizando o framework Spring Boot para o backend e o Thymeleaf para o frontend. O banco de dados H2 é usado para armazenar informações sobre os animais disponíveis para adoção, permitindo ao usuário consultar, adicionar e remover animais do sistema.

Etapas de Criação
1. Configuração do Projeto Spring Boot
   Inicie um novo projeto Spring Boot e inclua as dependências necessárias: Spring Web, Spring Data JPA, Thymeleaf, e H2 Database.
   Configure as propriedades do projeto no arquivo application.properties para conectar ao banco de dados H2 e personalizar a porta e o contexto da aplicação.
2. Definição do Modelo e Estrutura do Banco de Dados
   Crie a classe Animal como uma entidade JPA para representar os animais no banco de dados. Inclua atributos como id, nome, tipo e descricao.
   Configure o repositório AnimalRepository estendendo JpaRepository para facilitar o acesso ao banco de dados.
3. Desenvolvimento da Camada de Serviço
   Implemente a camada de serviço (AnimalService) para centralizar a lógica de negócios. Esta camada fornece métodos como listarAnimais, encontrarAnimalPorId, salvarAnimal e deletarAnimal.
4. Criação da Camada de Controle
   Crie o controlador AnimalController para gerenciar as requisições HTTP. Defina endpoints para listar, adicionar e remover animais, e redirecione o usuário às páginas apropriadas.
5. Desenvolvimento do Frontend com Thymeleaf
   Use Thymeleaf para construir as páginas HTML. Crie um layout padrão para a aplicação e páginas específicas para listar e adicionar animais, com formulários e tabelas estilizados.
6. Configuração e Teste do Banco de Dados H2
   Configure o banco de dados H2 no arquivo application.properties e acesse a console do H2 para criar e visualizar os dados em tempo real.
   Realize testes para garantir que o banco de dados funciona corretamente e que os dados estão sendo armazenados e exibidos conforme esperado.
   Funcionalidades
   A aplicação oferece as seguintes funcionalidades:

Listar Animais: Exibe todos os animais disponíveis para adoção em uma tabela.
Adicionar Animal: Permite ao usuário adicionar um novo animal ao sistema, especificando o nome, tipo e uma breve descrição.
Remover Animal: Dá a opção de remover um animal do sistema.
Visualizar Animal: Exibe detalhes específicos de cada animal.
Cada funcionalidade é acessível através de uma interface web simples e intuitiva.

Banco de Dados H2
O projeto utiliza o banco de dados H2, que é embutido e fácil de configurar para testes. O banco é configurado para reiniciar a cada execução, eliminando dados antigos e criando novos registros apenas para a sessão ativa.

Acesso ao Console do H2
Para acessar a console do H2:

No navegador, acesse http://localhost:8080/h2-console.
Use as seguintes configurações:
JDBC URL: jdbc:h2:mem:testdb
Username: sa
Password: (deixe em branco)
Clique em "Conectar".
Na console do H2, você pode consultar as tabelas, verificar dados e executar comandos SQL.

Para Acessar o H2 Console:
Configuração ativa: Deixe como "Generic H2 (Embedded)".
Classe com o driver: Certifique-se de que está definido como org.h2.Driver.
JDBC URL: Use jdbc:h2:file:./data/testdb, como configurado.
Usuário: O usuário padrão para o H2 é geralmente sa.
Senha: Se você não definiu uma senha específica, deixe o campo de senha em branco. Caso tenha configurado uma senha no application.properties ou application.yml, insira-a aqui.
Testando a Conexão
Clique em "Testar conexão" para verificar se a conexão está funcionando corretamente.
Se o teste for bem-sucedido, você pode clicar em "Conectar" para acessar o banco de dados e visualizar/modificar os dados conforme necessário.
Esse procedimento deve permitir que você acesse seu banco de dados H2 usando o console. Se ocorrerem erros, verifique se o caminho ./data/testdb realmente existe e está acessível pelo projeto.

Perguntas Norteadoras
1. Como a aplicação funciona?
   A aplicação permite que o usuário visualize os animais disponíveis para adoção e adicione novos animais ao sistema. A interação com o banco de dados H2 possibilita armazenar os dados temporariamente e acessá-los durante o tempo em que a aplicação está ativa.
2. Quais são as funcionalidades principais?
   Listar, adicionar e remover animais.
3. Como acessar cada funcionalidade?
   Listagem de Animais: Página inicial /animais.
   Adicionar Animal: Formulário disponível em /animais/adicionar.
   Remover Animal: Disponível na página de listagem (em desenvolvimento).
4. Como acessar o banco de dados?
   Utilize a console do H2 em http://localhost:8080/h2-console, com as configurações descritas na seção Banco de Dados H2.
   Acesso e Testes
   Acessar a Aplicação:

Inicie o projeto pelo comando mvn spring-boot:run.
Acesse http://localhost:8080 no navegador para visualizar a página inicial.
Testar Funcionalidades:

Na página inicial, você pode listar todos os animais disponíveis.
No formulário de adicionar, insira as informações de um novo animal e verifique se ele aparece na listagem.
Para acessar o banco de dados, use o console do H2 e execute consultas para verificar os dados.
Encerrar o Projeto:

Pressione Ctrl+C para interromper a execução do servidor Spring Boot.

Links para Acesso às Abas do Projeto
Página Inicial - Listagem de Animais

Link: http://localhost:8080/animais
Descrição: Exibe a lista de todos os animais disponíveis para adoção.
Adicionar Animal

Link: http://localhost:8080/animais/adicionar
Descrição: Página com formulário para adicionar um novo animal ao sistema.
Visualizar Detalhes de um Animal

Link: http://localhost:8080/animais/{id}
Descrição: Exibe os detalhes específicos de um animal. Substitua {id} pelo ID do animal desejado.
Remover Animal

Descrição: Remove o animal com o ID fornecido do sistema. Este link geralmente é acionado por um botão na lista de animais.
Banco de Dados H2 Console

Link: http://localhost:8080/h2-console
Descrição: Console do banco de dados H2 para visualização e manipulação direta dos dados.
Observação sobre Rotas Personalizadas
Esses links são sugestões padrão. Certifique-se de verificar o código do controlador (ex.: AnimalController) para confirmar as rotas exatas configuradas, pois as rotas podem ser diferentes dependendo da implementação.

Como Acessar Cada Aba
Para listar animais, vá para a página inicial do projeto (/animais).
Para adicionar um animal, navegue para /animais/adicionar.
Para detalhes específicos de um animal, adicione o ID do animal na URL /animais/{id}.
Para remover um animal, o link é geralmente acionado por um botão de exclusão na lista de animais (/animais/deletar/{id}).
Para acessar o banco de dados e verificar os dados, use o console do H2 em /h2-console.