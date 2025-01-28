## *SOBRE O PROJETO*

### OBJETIVO
Este projeto tem como objetivo criar o backend de um sistema de coleções de jogos,  
que os organiza em listas de acordo com a categoria, exibe as características dos jogos  
de forma resumida na representação em formato de lista, e disponibiliza informaçoes completas  
ao clicar em um deles.  

### ARQUITETURA
O backend disponibiliza uma API REST para a comunicação com o frontend (este não é desenvolvido  
nesse projeto) e acessa os recursos armazenados em um banco de dados utilizando consultas SQL (nativeQuery = true).

#### Arquitetura Backend (3 camadas) e frontend
<img src="https://private-user-images.githubusercontent.com/113950175/407025513-38f2dc13-1780-4437-8ef5-4be8eb522703.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzgwMzE4MDQsIm5iZiI6MTczODAzMTUwNCwicGF0aCI6Ii8xMTM5NTAxNzUvNDA3MDI1NTEzLTM4ZjJkYzEzLTE3ODAtNDQzNy04ZWY1LTRiZThlYjUyMjcwMy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDEyOFQwMjMxNDRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1lMmY2ZjY2YmIzNmZkNmM1MDA1YWM1MjNkOWUwYzY4MThjMDkzMzdlOWEwOTRjYWNlYmE5NmMzZDBiZTFlYmU3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.TYcp-OzdLiZdDo93FbGEXNXTVbVq38bgG_1MqYpjXT8" width="800" height="500" />

O backend foi desenvolvido em um arquitetura de três camadas, em que "Controladores REST" realizam  
a comunicação entre frontend e backend, atendendo às requisições HTTP e retornando  
objetos DTO (Data Transfer Objects). Esses objetos DTO são criados com intuito de enviar apenas os  
dados necessários para o frontend. Inclusive, eles são elaborados pela "Camada de serviço", que determina  
as ações a serem realizadas para obter os dados desejados, e solicita as informações a  
"Camada de acesso a dados". Esta, por sua vez, realizará consultas SQL para acessar o banco de dados e retornará  
os dados no formato de projeções, utilizando o framework Spring Data JPA (Java Persistance API) para  
criação de repositórios com dados permanentes e o Hibernate para interação com o banco de dados.  

### Verificação das requisições HTTP (Postman)
#### As respostas estão no formato JSON

#### Jogos
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407162965-3304fa81-b4ee-4ae8-9712-c8ad3ff0d70c.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T024736Z&X-Amz-Expires=300&X-Amz-Signature=baaf30a0cf8e8ba427f968821642b77659464eee69c6ad9640a634ee1a90f875&X-Amz-SignedHeaders=host" width="600" height="650" />

#### Listas Disponíveis
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407042419-9e1ce8a6-d3d2-4f1e-89d1-fc15737b3fb4.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T023835Z&X-Amz-Expires=300&X-Amz-Signature=9608de92c6cc28bb3846287a84aa2dcbc9328121fd5f0fd8b2592ad97c60c244&X-Amz-SignedHeaders=host" width="500" height="350" />

#### Jogos Organizados em Listas (exemplo: idLista = 2)
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407042858-fc7b6e68-7441-4eea-9869-39ae9f367c5a.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T024051Z&X-Amz-Expires=300&X-Amz-Signature=95be1073ad7fd48e12c59e517c0da6c11243be4204f80c0b3fac830fd4369d99&X-Amz-SignedHeaders=host" width="500" height="600" />

#### Informações do Jogo ao Clicar (exemplo: idJogo = 1)
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407163416-d5c0bd9d-0108-4122-b499-eccdb9e90ebf.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T025049Z&X-Amz-Expires=300&X-Amz-Signature=78ac5f253cd17848c2a338ad041cf4e8accca61aced4f675fadcfa9c8616bf06&X-Amz-SignedHeaders=host" width="600" height="625" />

#### Realocação do jogo na lista
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407164090-3f8923d5-c3bc-4cac-b628-a578287f8b84.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T025330Z&X-Amz-Expires=300&X-Amz-Signature=1daa040670d06311a6be2cfc646baf6f3e6df0cbb96d9c71566b77fd246ff747&X-Amz-SignedHeaders=host" width="600" height="250" />

Neste caso, foi utilizado o método POST, pois não é uma consulta, e sim uma modificação (não idempotente) no banco de dados.  

#### Banco de Dados H2
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407168626-259cb887-ba1e-4a0a-af38-833b57a24414.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T031921Z&X-Amz-Expires=300&X-Amz-Signature=cf799a23f040399a22d2be1e2c990960175253b8295b18197b5677199b22929a&X-Amz-SignedHeaders=host" width="600" height="300" />

#### Banco de Dados Postgresql (plataforma pgAdmin)

<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/113950175/407170970-e94a6dcb-8b9a-44da-89fe-13c2b3e94dc0.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250128T033329Z&X-Amz-Expires=300&X-Amz-Signature=dfd1ee113bb541a02b616d3d5886a47e78ea32e496ead0bc4192d6eb6ff47e0e&X-Amz-SignedHeaders=host" width="500" height="400" />

### TECNOLOGIAS

#### Linguagens
- Java
- SQL

#### Framework
- Spring Boot

#### Banco de dados
- H2 (testes)
- Postgresql (implantação usando Docker)

