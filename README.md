# 📦 API de Cadastro de Produtos

Uma API REST completa para gerenciamento de produtos com integração a serviços externos, desenvolvida em .NET 8.

## 🚀 Sobre o Projeto

Esta API foi desenvolvida como projeto de portfólio, demonstrando conhecimentos em:
- **Clean Architecture** com separação de responsabilidades
- **Entity Framework Core** para persistência de dados
- **Integração com APIs externas** (IBGE, NCM)
- **Documentação com Swagger**
- **Padrões de design** (Repository, Dependency Injection)
- **Validações e tratamento de erros**

## 🛠️ Tecnologias Utilizadas

- **.NET 8** - Framework principal
- **ASP.NET Core Web API** - Para criação da API REST
- **Entity Framework Core** - ORM para acesso a dados
- **SQL Server** - Banco de dados principal
- **Swagger/OpenAPI** - Documentação da API
- **AutoMapper** - Mapeamento entre objetos
- **FluentValidation** - Validação de dados

## 📋 Funcionalidades

### ✅ Implementadas
- [ ] CRUD completo de produtos
- [ ] CRUD de categorias
- [ ] Validação de dados
- [ ] Documentação Swagger
- [ ] Tratamento de erros
- [ ] Logs estruturados

### 🔄 Integrações Externas
- [ ] **API IBGE** - Consulta de municípios e estados
- [ ] **Dados NCM** - Nomenclatura Comum do Mercosul
- [ ] **CEP** - Validação de endereços (opcional)

### 🚧 Próximas Implementações
- [ ] Autenticação JWT
- [ ] Cache Redis
- [ ] Testes unitários e de integração
- [ ] Docker containerization
- [ ] Pipeline CI/CD

## 🏗️ Arquitetura

```
ProductCatalogAPI/
├── src/
│   ├── ProductCatalog.API/          # Controllers, Middlewares, Program.cs
│   ├── ProductCatalog.Application/  # Services, DTOs, Interfaces
│   ├── ProductCatalog.Domain/       # Entidades, Value Objects
│   └── ProductCatalog.Infrastructure/ # Repositories, DbContext, External APIs
├── tests/
│   ├── ProductCatalog.Tests.Unit/
│   └── ProductCatalog.Tests.Integration/
└── docs/
    └── api-documentation.md
```

## 🚀 Como Executar

### Pré-requisitos
- .NET 8 SDK
- SQL Server (ou SQL Server Express)
- Visual Studio 2022 ou VS Code

### Passos para execução

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/ProductCatalogAPI.git
cd ProductCatalogAPI
```

2. **Restaure as dependências**
```bash
dotnet restore
```

3. **Configure a string de conexão**
```bash
# Edite o arquivo appsettings.json na pasta ProductCatalog.API
```

4. **Execute as migrations**
```bash
dotnet ef database update --project ProductCatalog.Infrastructure --startup-project ProductCatalog.API
```

5. **Execute a aplicação**
```bash
dotnet run --project ProductCatalog.API
```

6. **Acesse a documentação**
```
https://localhost:7001/swagger
```

## 📊 Endpoints Principais

### Produtos
- `GET /api/products` - Lista todos os produtos
- `GET /api/products/{id}` - Busca produto por ID
- `POST /api/products` - Cria novo produto
- `PUT /api/products/{id}` - Atualiza produto
- `DELETE /api/products/{id}` - Remove produto

### Categorias
- `GET /api/categories` - Lista todas as categorias
- `POST /api/categories` - Cria nova categoria

### Integrações
- `GET /api/ibge/states` - Lista estados do Brasil
- `GET /api/ibge/cities/{stateCode}` - Lista cidades por estado
- `GET /api/ncm/{code}` - Consulta NCM por código

## 🔧 Configuração

### Variáveis de Ambiente
```bash
ConnectionStrings__DefaultConnection=Server=localhost;Database=ProductCatalogDB;Trusted_Connection=true;
ExternalAPIs__IBGEBaseUrl=https://servicodados.ibge.gov.br/api/v1/
ExternalAPIs__NCMBaseUrl=https://portalunico.siscomex.gov.br/
```

## 📝 Estrutura do Banco de Dados

### Produtos
- Id, Nome, Descrição, Preço, Categoria, NCM, DataCriação, DataAtualizacao

### Categorias  
- Id, Nome, Descrição, Ativa

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

**Seu Nome**
- GitHub: [@dangelofoliveira](https://github.com/dangelofoliveira)
- LinkedIn: [dangelofoliveira](https://linkedin.com/in/dangelofoliveira)
- Email: dangelofoliveira@gmail.com

---

⭐ Se este projeto te ajudou, deixe uma estrela!
