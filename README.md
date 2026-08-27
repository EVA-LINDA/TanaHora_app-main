# Tá na Hora

Aplicativo de apoio a idosos no cuidado com a saúde: lembretes de remédios, receitas médicas, atividades físicas, meta de hidratação e botão de SOS.

🏆 **Projeto criado em uma hackathon e vencedor do 1º lugar no IFTO.** Desde então, venho evoluindo o projeto aos poucos, colocando a ideia em prática e aprimorando funcionalidades.

Este repositório reúne as duas versões do projeto:

- 📱 **App mobile (original)** — feito em React Native com Expo, a versão que nasceu na hackathon.
- 🖥️ **Site (web)** — protótipo em HTML, CSS e JavaScript puro, reproduzindo o design do app para visualização e apresentação rápida direto no navegador, sem precisar instalar nada.

> ⚠️ A versão web é um protótipo **somente visual**. Os dados exibidos são fictícios (mock) e nada é salvo entre sessões — não há conexão com banco de dados ou backend.

## 📱 App mobile (original)

Versão original do projeto, desenvolvida em **React Native + Expo**, com **Firebase Firestore** como backend para persistência dos dados em tempo real.

### Tecnologias

- [Expo](https://expo.dev) (SDK 54) + [Expo Router](https://docs.expo.dev/router/introduction/) (navegação por arquivos)
- React Native 0.81
- Firebase (Firestore)
- TypeScript
- `@expo/vector-icons`

### Telas

| Arquivo | Descrição |
|---|---|
| `index.tsx` | Tela inicial — saudação, botão de SOS e menu principal |
| `lista-remedios.tsx` | Lista de medicamentos, em tempo real via Firestore |
| `cadastro-remedio.tsx` | Cadastro de novo remédio, salvo no Firestore |
| `lista-receitas.tsx` | Lista de receitas médicas |
| `lista-atividades.tsx` | Checklist de exercícios do dia, com atualização em tempo real |
| `alarme-remedio.tsx` | Tela de alarme na hora do remédio, com "deslize para confirmar" |
| `tela-sos.tsx` | Tela de emergência (em desenvolvimento) |
| `tela-meta-agua.tsx` | Acompanhamento da meta diária de água (em desenvolvimento) |

### Como rodar

```bash
npm install
npx expo start
```

No terminal, escolha abrir em emulador Android/iOS, no [Expo Go](https://expo.dev/go) ou na versão web (`npx expo start --web`).

É necessário criar um arquivo `config/firebaseConfig.js` (veja `firebaseConfig.example copy.js`) com as credenciais do seu próprio projeto Firebase.

---

## 🖥️ Versão web — Páginas

| Arquivo | Descrição |
|---|---|
| `index.html` | Tela inicial — saudação, botão de SOS e menu principal |
| `lista-remedios.html` | Lista de medicamentos cadastrados |
| `cadastro-remedio.html` | Formulário de cadastro de um novo remédio |
| `lista-receitas.html` | Lista de receitas médicas |
| `lista-atividades.html` | Lista de exercícios do dia, com marcação de concluído |
| `alarme-remedio.html` | Tela de alarme na hora do remédio, com "deslize para confirmar" |
| `tela-sos.html` | Tela de emergência com contatos e ligação para o SAMU |
| `tela-meta-agua.html` | Acompanhamento da meta diária de copos de água |

## 🎨 Tecnologias e decisões de design

- **HTML5, CSS3 e JavaScript** puros, sem frameworks ou build step.
- Paleta de cores e tipografia herdadas do app original (Expo/React Native) para manter consistência visual entre as duas versões.
- Fontes: [Baloo 2](https://fonts.google.com/specimen/Baloo+2) (títulos) e [Inter](https://fonts.google.com/specimen/Inter) (texto), via Google Fonts.
- Ícones em **SVG embutido** (`js/icons.js`), sem dependência de nenhum CDN externo — o site funciona 100% offline.
- Interações implementadas em `js/main.js`: relógio ao vivo, confirmação por arraste no alarme, contador de copos de água e checklist de exercícios.

## 📁 Estrutura de pastas

```
tanahora-site/
├── index.html
├── lista-remedios.html
├── cadastro-remedio.html
├── lista-receitas.html
├── lista-atividades.html
├── alarme-remedio.html
├── tela-sos.html
├── tela-meta-agua.html
├── css/
│   └── style.css        # tokens de cor, tipografia e todos os componentes
├── js/
│   ├── main.js           # interações das páginas
│   └── icons.js           # biblioteca de ícones SVG inline
└── assets/
    ├── favicon.png
    ├── logo_app.png
    └── logo_site.svg
```

## ▶️ Como rodar localmente

Não é necessário instalar dependências. Basta abrir o `index.html` diretamente no navegador **ou** rodar um servidor local simples:

```bash
# Python 3
python3 -m http.server 8080

# Node (com o pacote serve)
npx serve .
```

Depois acesse `http://localhost:8080` no navegador.

## 🚧 Próximos passos

O projeto nasceu na hackathon e está sendo evoluído aos poucos, colocando a ideia em prática:

- [ ] Conectar os formulários da versão web ao Firebase (mesmo backend do app mobile) ou a `localStorage` para persistência dos dados.
- [ ] Finalizar as telas de SOS e Meta de Água no app mobile.
- [ ] Implementar as telas de Calendário e Falar com Atendente (hoje desabilitadas no menu).
- [ ] Testes de acessibilidade (leitor de tela, navegação por teclado) com público idoso.
