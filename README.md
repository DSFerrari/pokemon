# Pokemon Flutter App

**Aplicação tutorial em Flutter para consumo de APIs, operações assíncronas e scroll infinito com busca integrada.**

---

## 🚀 Descrição

Este projeto serve como base para aulas e estudos de Flutter, abordando conceitos fundamentais como consumo de APIs REST/GraphQL, gerenciamento de estados assíncronos (Future, Completer), debounce, scroll infinito e cache de imagens.

---

## 📦 Tecnologias e Pacotes

* **Flutter & Dart**
* `http` – requisições HTTP
* `cached_network_image` – cache de imagens de rede
* `graphql` (via endpoint GraphQL da PokéAPI)
* `AppDebounce` – utilitário para debounce

---

## 🎯 Funcionalidades

### Principais

1. **Scroll "infinito"** na lista de Pokémons usando `ListView.builder` e `ScrollController`.
2. **Busca por nome** de Pokémon via GraphQL (/graphql/v1beta), retornando resultados parciais.

### Secundárias

* Estilização aprimorada (layouts, botões, cards).
* Helper de formatação de texto (capitalização de nomes).
* Página de detalhes do Pokémon com informações enriquecidas.

---

## 🛠️ Instalação e Execução

### Pré-requisitos

* Flutter SDK (>= 3.0)
* Ambiente configurado para desenvolvimento Flutter (Android Studio, VS Code, emulador ou dispositivo físico)

### Passos

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/pokemon-flutter-app.git
cd pokemon-flutter-app

# Instale as dependênciaslutter pub get

# Execute no emulador ou dispositivo conectado
flutter run
```

---

## 📁 Estrutura do Projeto

```
lib/
├── models/
│   ├── navigable_pokemon.dart       # Modelo de listagem
│   └── pokemon_detail_response.dart # Modelo de detalhes
├── services/
│   └── pokemon_api.dart             # Camada de API (REST + GraphQL)
├── utils/
│   └── debounce.dart                # Utilitário de debounce
├── pages/
│   ├── pokemon_list_page.dart       # Tela de listagem com scroll infinito e busca
│   └── pokemon_detail_page.dart     # Tela de detalhes do Pokémon
└── main.dart                        # Entry-point do app
```

---

## 🔗 Endpoints de API

* **Listagem (REST)**

  ```http
  GET https://pokeapi.co/api/v2/pokemon?limit={limit}&offset={offset}
  ```
* **Detalhes (REST)**

  ```http
  GET https://pokeapi.co/api/v2/pokemon/{id-ou-nome}
  ```
* **Busca por nome (GraphQL)**

  ```graphql
  query search($like: String!) {
    pokemon_v2_pokemon(where: { name: { _like: $like } }) {
      id
      name
    }
  }
  ```

---

## 🤝 Contribuições

1. Fork este repositório
2. Crie sua feature branch (`git checkout -b feature/awesome`
3. Commit suas mudanças (`git commit -m 'Add awesome feature'`)
4. Push para a branch (`git push origin feature/awesome`)
5. Abra um Pull Request

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
