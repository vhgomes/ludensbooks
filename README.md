
---

# 📚 Book Review App

Este é um projeto desenvolvido em Laravel que permite listar livros, visualizar detalhes e adicionar avaliações (reviews) para cada livro. O sistema também oferece filtros por popularidade e avaliações, além de cache para otimizar as consultas.

---

## 🚀 Funcionalidades

* 📖 Listagem de livros
* 🔍 Filtro de livros por:

  * Título
  * Mais populares no último mês
  * Mais populares nos últimos 6 meses
  * Melhor avaliados no último mês
  * Melhor avaliados nos últimos 6 meses
* ⭐ Visualização detalhada de um livro, com:

  * Avaliação média
  * Contagem de reviews
  * Lista dos reviews mais recentes
* 📝 Adição de reviews para um livro específico
* ⚡ Otimização de consultas com uso de cache

---

## 🗺️ Rotas Principais

### 📚 Livros (`BookController`)

| Método | Rota            | Descrição                   |
| ------ | --------------- | --------------------------- |
| GET    | `/books`        | Lista os livros com filtros |
| GET    | `/books/{book}` | Exibe detalhes do livro     |

### 📝 Reviews (`ReviewController`)

| Método | Rota                           | Descrição                         |
| ------ | ------------------------------ | --------------------------------- |
| GET    | `/books/{book}/reviews/create` | Formulário para criar review      |
| POST   | `/books/{book}/reviews`        | Salva um novo review para o livro |

---

## 🏗️ Estrutura dos Controllers

### BookController

* `index(Request $request)` → Listagem de livros com filtros e cache.
* `show(int $id)` → Detalhes do livro, reviews recentes, média de avaliações e quantidade de reviews, com cache.

### ReviewController

* `create(Book $book)` → Formulário para criar um review de um livro específico.
* `store(Request $request, Book $book)` → Validação e armazenamento de um review relacionado ao livro.

---

## 🗄️ Dependências

* Laravel 10+ (ou versão compatível)
* Cache habilitado (Redis, Memcached ou file)

---

## 🔧 Instalação

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
```

2. Instale as dependências:

```bash
composer install
```

3. Copie o arquivo de ambiente:

```bash
cp .env.example .env
```

4. Gere a chave da aplicação:

```bash
php artisan key:generate
```

5. Configure o banco de dados no `.env`.

6. Rode as migrations:

```bash
php artisan migrate
```

7. Suba o servidor local:

```bash
php artisan serve
```

---

## 🚦 Como usar

* Acesse `/books` para visualizar a lista de livros.
* Clique em um livro para ver detalhes e reviews.
* Acesse `/books/{book}/reviews/create` para adicionar um review.

---

## 💡 Melhorias Futuras

* Editar e remover reviews.
* Sistema de autenticação para gerenciar quem pode avaliar.
* Implementar paginação na listagem de livros e reviews.
* API pública para acesso aos dados dos livros e reviews.

---

## 🤝 Contribuição

Pull requests são bem-vindos! Para mudanças maiores, abra uma issue antes para discutir o que você gostaria de alterar.

---

## 📄 Licença

Este projeto está sob a licença [MIT](LICENSE).

---
