# MegaMan Villains API

<table align="center">
    <tr>
        <td align="center" width="25%">
            <img src="./_docs/assets/icon.png" >
        </td>
        <td align="center" width="75%">
            
# Megaman Bosses API

[![Release workflow](https://github.com/Ryubing/Ryujinx/actions/workflows/release.yml/badge.svg)](https://github.com/Ryubing/Ryujinx/actions/workflows/release.yml)
[![Latest release](https://img.shields.io/github/v/release/GreemDev/Ryujinx)](https://github.com/Ryubing/Ryujinx/releases/latest)
  <br>
[![Canary workflow](https://github.com/Ryubing/Ryujinx/actions/workflows/canary.yml/badge.svg)](https://github.com/Ryubing/Ryujinx/actions/workflows/canary.yml)
[![Latest canary release](https://img.shields.io/github/v/release/Ryubing/Canary-Releases?label=canary)](https://github.com/Ryubing/Canary-Releases/releases/latest)
        </td>
    </tr>
</table>

<p align="center">
  Este é um projeto de API desenvolvido em .NET Core 3.1, que fornece informações sobre os chefes do jogo Megaman. O backend retorna os dados no formato JSON, contendo informações como ID, código, nome, vida (HP) e imagem de cada chefe.
  <br />
</p>

## Formato de Resposta JSON
A API retorna os dados dos chefes no seguinte formato:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Técnicas Utilizadas
Este projeto foi desenvolvido utilizando as seguintes técnicas:

- **Arquitetura MVC** (Model-View-Controller) para organização modular e escalável.
- **Entity Framework Core** para facilitar a interação com o banco de dados.
- **Injeção de Dependências** para desacoplar componentes e facilitar a manutenção.
- **Uso de JSON para comunicação** entre backend e frontend.
- **RESTful API** para fornecer endpoints padronizados.

## Tecnologias Utilizadas
- [**.NET Core 3.1**](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [**Entity Framework Core 3.1.8**](https://docs.microsoft.com/pt-br/ef/core/)
- [**Banco de Dados SQL Server**](https://www.microsoft.com/pt-br/sql-server)
- [**Newtonsoft.Json 12.0.2**](https://www.newtonsoft.com/json)

## API Endpoints

| Método | Endpoint | Descrição |
|--------|---------|-----------|
| **GET** | /api/bosses | Retorna a lista de todos os chefes |
| **GET** | /api/bosses/{id} | Retorna um chefe específico pelo ID |
| **POST** | /api/bosses | Adiciona um novo chefe |
| **PUT** | /api/bosses/{id} | Atualiza um chefe existente |
| **DELETE** | /api/bosses/{id} | Remove um chefe pelo ID |

## Estrutura do Projeto
O projeto segue a arquitetura MVC (Model-View-Controller) e utiliza o Entity Framework Core para gerenciar a persistência dos dados.

### Dependências do Projeto
As dependências utilizadas estão definidas no arquivo .csproj:

| Dependência | Versão |
|------------|--------|
| [Microsoft.EntityFrameworkCore](https://docs.microsoft.com/pt-br/ef/core/) | 3.1.8 |
| [Microsoft.EntityFrameworkCore.Design](https://docs.microsoft.com/pt-br/ef/core/) | 3.1.8 |
| [Microsoft.EntityFrameworkCore.SqlServer](https://docs.microsoft.com/pt-br/ef/core/providers/sql-server/) | 3.1.8 |
| [Newtonsoft.Json](https://www.newtonsoft.com/json) | 12.0.2 |

## Estrutura de Diretórios
```
.vs
.vscode
bin
Controllers
Database
middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json  
global.json
MegamanApi.csproj  
MegamanApi.sln
Program.cs
Startup.cs
```

## Configuração do Banco de Dados
O projeto utiliza o Entity Framework Core para interagir com um banco de dados SQL Server. Certifique-se de configurar a string de conexão no arquivo appsettings.json:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=SEU_SERVIDOR;Database=MegamanBossesDB;Trusted_Connection=True;"
}
```

Para aplicar as migrações do banco de dados, utilize os seguintes comandos no terminal:

```sh
dotnet ef migrations add InitialCreate
dotnet ef database update
```

## Executando o Projeto
Para rodar a API localmente, siga os seguintes passos:

1. Clone o repositório
```sh
git clone https://github.com/seu-usuario/megaman-bosses-api.git
```

2. Acesse o diretório do projeto
```sh
cd megaman-bosses-api
```

3. Restaure as dependências
```sh
dotnet restore
```

4. Execute o projeto
```sh
dotnet run
```

A API estará rodando em http://localhost:5000 (ou na porta configurada no seu ambiente).

## Contribuição
Contribuições são bem-vindas! Para contribuir:
1. Fork o repositório
2. Crie uma branch com sua feature (`git checkout -b minha-feature`)
3. Commit suas alterações (`git commit -m 'Adiciona nova feature'`)
4. Envie para o repositório remoto (`git push origin minha-feature`)
5. Abra um Pull Request

## Arquitetura

```🌐
src
├── 📂 Controllers      [Routes for endpoints]
├── 📂 Models           [Database models]
├── 📂 Services         [Business rules]
├── 📂 Middlewares      [Intermediate functions between the HTTP request and the final server response]
├── 📂 Database         [Structures related to the database]
│   ├── 📂 DTOs             [Input Models and View Models (Data Transfer Objects)]
│   ├── 📂 EntityFramework  [Files related to the ORM Entity Framework]
│   │     ├── 📂 Context         [Entity context settings]
│   │     ├── 📂 Migrations      [Migrations for database updates]
│   ├── 📂 Repositories     [Repository pattern]
```

## Licença
Este projeto está licenciado sob a [MIT License](LICENSE).

<p align="center">

</p>

