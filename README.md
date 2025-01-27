***SOBRE O PROJETO

Esse projeto tem como objetivo criar o backend para um sistema de coleções de jogos,
que os organiza em listas de acordo com a categoria, informa as características dos jogos
de forma resumida na representação no formato de lista e completa ao clicar em um deles.

O backend disponibiliza uma API REST para a comunicação com o frontend, este não é desenvolvido
nesse projeto, e acessa os recursos armazenados em um banco de dados utilizando consultas SQL (nativeQuery = true).

![image](https://github.com/user-attachments/assets/38f2dc13-1780-4437-8ef5-4be8eb522703)

O backend foi desenvolvido em um arquitetura de três camadas, em que "Controladores REST" realizam 
a comunicação entre frontend e backend, atendendo as requisições HTTP e retornando 
objetos DTO (Data Transfer Objects). Estes objetos DTO são criados com intuito de enviar apenas os
dados necessários para o frontend, inclusive, eles são elaborados pela "Camada de serviço", que determina
as ações a serem realizadas para obter os dados desejados, e solicita as informações a 
"Camada de acesso a dados", esta irá realizar consultas SQL para acessar o banco de dados e retorna
os dados no formato de projeções utilizando o framework Spring Data JPA (Java Persistance API) para
criação de repositórios com dados permanentes, e Hibernate, para interação com o banco de dados.



***TECNOLOGIAS

Linguagens
- Java
- SQL

Framework
- Spring Boot

Banco de dados
- H2 (testes)
- Postgresql (implantação)

