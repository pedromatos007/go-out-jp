[README.md](https://github.com/user-attachments/files/26128865/README.md)
# 🗺️ Go Out JP

> **O guia emocional de João Pessoa** — explore a cidade pelo que você quer *sentir*, não pelo que você quer *fazer*.

![Go Out JP](https://img.shields.io/badge/João%20Pessoa-Paraíba%20🇧🇷-blue?style=flat-square)
![HTML](https://img.shields.io/badge/HTML-Single%20File-orange?style=flat-square&logo=html5)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

---

## ✨ O que é

Go Out JP é um Progressive Web App (PWA) de **arquivo único** que transforma a forma de explorar João Pessoa. Em vez de listas genéricas, o app sugere lugares com base no seu **estado emocional do momento** — quer relaxar? socializar? focar? escapar?

Desenvolvido com HTML, CSS e JavaScript puros — sem frameworks, sem build tools, sem instalação. Abre direto no browser.

---

## 🎯 Funcionalidades

### Core
- **9 humores** para filtrar lugares (Relaxar, Socializar, Foco, Introspecção, Energia, Família, Criatividade, Escapar, Explorar)
- **Slider calmo ↔ energético** sincronizado com os humores
- **Busca em linguagem natural** — perguntas abrem o assistente IA automaticamente
- **Filtros inteligentes** — Aberto agora, Gratuito, Manhã, Tarde, Noite, Com chuva
- **Filtro por bairro** — Tambaú, Cabo Branco, Manaíra, Bessa, Varadouro, Oceania, Mangabeira

### Lugares (70+ locais reais)
Restaurantes · Bares · Cafeterias · Shows & Baladas · Cinemas · Teatros · Cultura & Arte · Shoppings · Praias · Parques · Jogos & Kids · Passeios

### Abas
| Aba | Conteúdo |
|-----|----------|
| 🗺️ Explorar | Todos os lugares filtrados por humor |
| 📅 Eventos | Agenda março–abril 2026 |
| 🏨 Hospedagem | Hotéis e pousadas com preços reais |
| 🗺️ Bairros | Personalidade de cada bairro |
| 🌊 Maré | Tábua de marés para Areia Vermelha |
| 🕐 Histórico | Últimos 30 lugares visitados |
| ✦ Rotas | 8 roteiros emocionais prontos |
| 🏝️ Guia JP | Preços, dicas e informações essenciais |
| 💡 Dicas | Com chuva, gratuito, melhores praias... |
| Mapa | Mapa interativo com marcadores por humor |

### Drawer de cada lugar
- 💰 **Widget de preço médio** com indicador visual (💰💰💰💰)
- ♿ **Chips de acessibilidade** — coberto, pets ok, crianças, instagramável
- 📊 **Barras emocionais** — Energia · Social · Tranquilidade · Criatividade
- 📷 **Links para Instagram e site oficial**
- ⭐ **Avaliação pessoal** (1–5 estrelas, salva localmente)
- 🙋 **Feedback de visita** — energia, social, clima
- ⚖️ **Comparar** dois lugares lado a lado
- ↗ **Compartilhar** via Web Share API

### IA Assistente
- Powered by **Claude claude-sonnet-4-20250514** (Anthropic)
- Contexto completo com todos os 70+ lugares, eventos, hotéis e dicas de JP
- 17+ sugestões rápidas pré-definidas
- Responde sobre maré, preços, Ilha de Areia Vermelha, surf, roteiros, acessibilidade...

### UX & Performance
- 🌙 **Tema escuro/claro** — persiste entre sessões
- 📡 **Indicador offline** — avisa quando sem conexão
- 🕐 **Barra de recentes** — últimos 5 lugares acessados
- 🆕 **Badge "Novo"** em lugares recém adicionados
- 🌊 **Alerta automático de maré** nas janelas de baixa-mar
- 📲 **PWA installável** — funciona como app nativo
- ⌨️ **Atalhos de teclado** — `/` para busca, `H` para histórico, `Esc` para fechar
- 👆 **Swipe down** para fechar o drawer no mobile

---

## 🚀 Como usar

### Opção 1 — Abrir direto
Baixe o `index.html` e abra no browser. Funciona 100% offline (exceto IA e clima).

### Opção 2 — GitHub Pages
1. Fork este repositório
2. Vá em **Settings → Pages → Branch: main → Save**
3. Acesse em `seuusuario.github.io/go-out-jp`

---

## 🔑 API Keys (opcionais)

O app funciona sem nenhuma chave. As funcionalidades que dependem de API:

| Feature | API | Onde configurar no código | Sem chave |
|---------|-----|--------------------------|-----------|
| 🤖 Assistente IA | Anthropic | `fetch('https://api.anthropic.com/v1/messages', ...)` | IA desativada |
| 🗺️ Mapa interativo | Google Maps | `src="...?key=SUA_CHAVE"` no `<script>` final | Placeholder exibido |
| 🌡️ Clima em tempo real | OpenWeatherMap | `appid=SUA_CHAVE` no `fetchWeather()` | Mostra "~30°C" |

### Como inserir sua chave da Anthropic

```html
<!-- No fetch do assistente, o header x-api-key é necessário: -->
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'sk-ant-...',
  'anthropic-version': '2023-06-01'
}
```

> ⚠️ **Atenção:** Não exponha chaves de API em repositórios públicos. Para produção, use um backend (Vercel Functions, Cloudflare Workers, etc.) que guarda a chave no servidor.

### Como restringir a chave do Google Maps

No [Google Cloud Console](https://console.cloud.google.com/), restrinja a chave para:
- **HTTP referrers:** `seuusuario.github.io/*`
- **APIs habilitadas:** Maps JavaScript API

---

## 📁 Estrutura

```
go-out-jp/
└── index.html     # App completo — HTML + CSS + JS em arquivo único (~180KB)
```

Tudo em um arquivo. Zero dependências externas além das fontes do Google Fonts.

---

## 🗺️ Dados

Todos os dados são reais e pesquisados para 2026:

- **70+ lugares** com: categoria, tag sensorial, humores compatíveis, horários reais, preço médio, localização, redes sociais
- **10 eventos** da agenda março–abril 2026
- **11 hotéis/pousadas** com preços reais (Booking.com/Kayak 2026)
- **7 bairros** com personalidade e vibe
- **8 rotas emocionais** prontas
- **Tábua de marés** simulada para Cabedelo (semi-diurnal)

---

## 🛠️ Tecnologias

- **HTML5** — estrutura e PWA manifest
- **CSS3** — design system com variáveis CSS, animações, tema claro/escuro
- **JavaScript (ES6+)** — sem frameworks, estado centralizado
- **Google Fonts** — Syne + Lora
- **Claude API** — assistente IA (Anthropic)
- **Google Maps JS API** — mapa interativo
- **OpenWeatherMap API** — clima em tempo real
- **localStorage** — favoritos, histórico, avaliações, feedback

---

## 📸 Preview

```
┌─────────────────────────────────────┐
│ 🌊 go out jp          ⛅ ~30°C 🤖 ♡ │
│─────────────────────────────────────│
│ Humor: [Relaxar] [Socializar] [...]  │
│ Calmo ────────●────────── Energético │
│─────────────────────────────────────│
│ [Explorar] [Eventos] [Restaurantes]  │
│─────────────────────────────────────│
│ ✦ Combinam com seu humor            │
│ ┌──────────┐ ┌──────────┐           │
│ │ 🏖️ Praia  │ │ ☕ Café   │           │
│ │ Tambaú   │ │ Visse    │           │
│ │ Gratuito │ │ R$20–45  │           │
│ └──────────┘ └──────────┘           │
│                                     │
│        🎲 Surpreenda-me             │
└─────────────────────────────────────┘
```

---

## 🙏 Créditos

Feito com ❤️ para João Pessoa — a cidade mais a leste das Américas.

Dados de preços e avaliações: Google Maps, TripAdvisor, Booking.com, Kayak (2026).

---

## 📄 Licença

MIT — use, modifique e distribua livremente.
