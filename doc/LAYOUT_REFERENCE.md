# Layout Reference - TikTok Shop Academy 2025

Documentaçêo do sistema de layout e design utilizado nas páginas de conteúdo do curso.

---

## 1. Estrutura Base HTML

```html
<!DOCTYPE html>
<html lang="pt-BR" class="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Título do Módulo] | TikTok Shop Academy 2025</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            primary: '#CDDC39',
            accent: '#E040FB',
            dark: { 900: '#111827', 800: '#1f2937', 700: '#374151', 600: '#4b5563' }
          }
        }
      }
    }
  </script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Inter', sans-serif; }
    .dark body { background-color: #111827; }
    html:not(.dark) body { background-color: #f8fafc; }
    html:not(.dark) .bg-dark-900 { background-color: #f8fafc !important; }
    html:not(.dark) .bg-dark-800 { background-color: #ffffff !important; }
    html:not(.dark) .bg-dark-700 { background-color: #f1f5f9 !important; }
    html:not(.dark) .border-dark-600 { border-color: #e2e8f0 !important; }
    html:not(.dark) .text-neutral-100 { color: #1e293b !important; }
    html:not(.dark) .text-neutral-200 { color: #334155 !important; }
    html:not(.dark) .text-neutral-300 { color: #475569 !important; }
    html:not(.dark) .text-neutral-400 { color: #64748b !important; }
  </style>
</head>
<body class="bg-dark-900 text-neutral-100 min-h-screen">
  <!-- Conteúdo aqui -->

  <script>
    // Theme initialization
    if (localStorage.getItem('color-theme') === 'light') {
      document.documentElement.classList.remove('dark');
    } else {
      document.documentElement.classList.add('dark');
    }
  </script>
</body>
</html>
```

---

## 2. Paleta de Cores

### Dark Mode (Padrêo)
| Nome | Código | Uso |
|------|--------|-----|
| `dark-900` | `#111827` | Fundo principal da página |
| `dark-800` | `#1f2937` | Cards, containers |
| `dark-700` | `#374151` | Elementos internos, hover states |
| `dark-600` | `#4b5563` | Bordas, divisores |

### Light Mode
| Nome | Código | Uso |
|------|--------|-----|
| Background | `#f8fafc` | Fundo principal |
| Cards | `#ffffff` | Cards, containers |
| Elementos | `#f1f5f9` | Elementos internos |
| Bordas | `#e2e8f0` | Bordas, divisores |

### Cores de Destaque
| Nome | Código | Uso |
|------|--------|-----|
| `primary` | `#CDDC39` | CTAs, destaques principais, botões |
| `accent` | `#E040FB` | Elementos secundários, badges |

### Cores Semânticas (Tailwind)
| Cor | Uso |
|-----|-----|
| `emerald-400/500` | Sucesso, positivo, "fazer" |
| `red-400/500` | Erro, alerta, "nêo fazer" |
| `blue-400/500` | Informaçêo, dados |
| `yellow-400/500` | Aviso, atençêo |
| `purple-400/500` | Especial, premium |
| `cyan-400/500` | Tech, inovaçêo |
| `pink-400/500` | Beleza, feminino |
| `orange-400/500` | Energia, urgência |
| `amber-400/500` | Destaque suave |

---

## 3. Componentes de Layout

### 3.1 Navigation (Sticky Top)
```html
<nav class="sticky top-0 z-50 bg-dark-900/95 backdrop-blur-sm border-b border-dark-600">
  <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-16">
      <a href="../index.html" class="flex items-center space-x-2 text-neutral-400 hover:text-primary transition-colors">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
        </svg>
        <span>Voltar para Trilha</span>
      </a>
      <span class="text-primary font-semibold">Módulo XX</span>
    </div>
  </div>
</nav>
```

### 3.2 Header do Módulo
```html
<div class="text-center mb-12">
  <span class="inline-block px-4 py-2 bg-[COR]-500/20 text-[COR]-400 rounded-full text-sm font-semibold mb-4">
    MÓDULO X - CATEGORIA
  </span>
  <h1 class="text-4xl sm:text-5xl font-bold mb-4">[EMOJI] Título do Módulo</h1>
  <p class="text-xl text-neutral-400 max-w-2xl mx-auto">
    Descriçêo breve do módulo em 1-2 linhas.
  </p>
</div>
```

### 3.3 Stats Banner (Métricas)
```html
<div class="grid grid-cols-3 gap-4 mb-12">
  <div class="bg-dark-800 rounded-xl p-4 text-center border border-dark-600">
    <div class="text-2xl font-bold text-[COR]-400">XX</div>
    <div class="text-xs text-neutral-400">Label</div>
  </div>
  <!-- Repetir para cada métrica -->
</div>
```

### 3.4 Section com Gradiente
```html
<section class="mb-12">
  <div class="bg-gradient-to-br from-[COR]-900/30 to-dark-800 rounded-2xl p-8 border border-[COR]-500/30">
    <div class="flex items-center mb-6">
      <span class="text-4xl mr-4">[EMOJI]</span>
      <div>
        <h2 class="text-2xl font-bold text-[COR]-400">Título da Seçêo</h2>
        <p class="text-neutral-400">Subtítulo explicativo</p>
      </div>
    </div>
    <!-- Conteúdo -->
  </div>
</section>
```

### 3.5 Section Simples (Card)
```html
<section class="mb-12">
  <div class="bg-dark-800 rounded-2xl p-8 border border-dark-600">
    <div class="flex items-center mb-6">
      <span class="text-4xl mr-4">[EMOJI]</span>
      <div>
        <h2 class="text-2xl font-bold text-neutral-100">Título</h2>
        <p class="text-neutral-400">Subtítulo</p>
      </div>
    </div>
    <!-- Conteúdo -->
  </div>
</section>
```

### 3.6 Box de Informaçêo Interna
```html
<div class="bg-dark-700/50 rounded-xl p-6 mb-6">
  <h3 class="text-xl font-bold text-[COR]-400 mb-4">[EMOJI] Título</h3>
  <!-- Conteúdo -->
</div>
```

### 3.7 Alerta/Destaque Colorido
```html
<div class="bg-[COR]-900/20 p-6 rounded-xl border border-[COR]-500/30">
  <h4 class="font-bold text-[COR]-400 mb-3">[EMOJI] Título</h4>
  <p class="text-neutral-300">Conteúdo do alerta...</p>
</div>
```

### 3.8 Grid de Comparaçêo (Fazer/Nêo Fazer)
```html
<div class="grid md:grid-cols-2 gap-6 mb-6">
  <div class="bg-emerald-900/20 p-6 rounded-xl border border-emerald-500/30">
    <h4 class="font-bold text-emerald-400 mb-4">✓ O que FAZER</h4>
    <ul class="space-y-3 text-neutral-300">
      <li class="flex items-start">
        <span class="text-emerald-400 mr-2">✓</span>
        <span>Item positivo</span>
      </li>
    </ul>
  </div>
  <div class="bg-red-900/20 p-6 rounded-xl border border-red-500/30">
    <h4 class="font-bold text-red-400 mb-4">✗ O que NêO fazer</h4>
    <ul class="space-y-3 text-neutral-300">
      <li class="flex items-start">
        <span class="text-red-400 mr-2">✗</span>
        <span>Item negativo</span>
      </li>
    </ul>
  </div>
</div>
```

### 3.9 Timeline/Passos Numerados
```html
<div class="flex items-start mb-8">
  <div class="w-16 h-16 bg-[COR]-500 rounded-full flex items-center justify-center text-white font-bold text-lg mr-4">
    1
  </div>
  <div>
    <h4 class="text-xl font-bold text-[COR]-400">Título do Passo</h4>
    <p class="text-neutral-400">Descriçêo</p>
  </div>
</div>
```

### 3.10 Barra de Progresso
```html
<div>
  <div class="flex justify-between mb-1">
    <span class="text-sm text-neutral-300">Label</span>
    <span class="text-sm text-[COR]-400">XX%</span>
  </div>
  <div class="w-full bg-dark-600 rounded-full h-4">
    <div class="bg-[COR]-500 h-4 rounded-full" style="width: XX%"></div>
  </div>
</div>
```

### 3.11 Checklist Interativo
```html
<div class="flex items-center bg-dark-800/50 p-3 rounded-lg">
  <input type="checkbox" class="mr-3 w-5 h-5 accent-primary">
  <span class="text-neutral-300">Item do checklist</span>
</div>
```

### 3.12 Tabela
```html
<div class="overflow-x-auto">
  <table class="w-full text-sm">
    <thead>
      <tr class="border-b border-dark-600">
        <th class="text-left py-3 px-4 text-neutral-400">Coluna 1</th>
        <th class="text-left py-3 px-4 text-neutral-400">Coluna 2</th>
      </tr>
    </thead>
    <tbody class="text-neutral-300">
      <tr class="border-b border-dark-700">
        <td class="py-3 px-4">Dado 1</td>
        <td class="py-3 px-4">Dado 2</td>
      </tr>
    </tbody>
  </table>
</div>
```

### 3.13 CTA Final / Resumo
```html
<section class="mb-12">
  <div class="bg-primary/10 rounded-2xl p-8 border border-primary/30">
    <h2 class="text-2xl font-bold text-primary mb-6 text-center">[EMOJI] Título do Resumo</h2>
    <!-- Conteúdo -->
    <div class="text-center mt-8">
      <a href="../index.html" class="inline-flex items-center space-x-2 px-6 py-3 bg-primary text-dark-900 rounded-lg font-bold hover:bg-primary/90 transition-colors">
        <span>Voltar para o Curso</span>
        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
        </svg>
      </a>
    </div>
  </div>
</section>
```

### 3.14 Footer
```html
<footer class="bg-dark-900 border-t border-dark-700 py-8">
  <div class="max-w-4xl mx-auto px-4 text-center">
    <p class="text-neutral-500 text-sm">
      TikTok Shop Academy 2025 - [Nome do Módulo]
    </p>
  </div>
</footer>
```

---

## 4. Padrões de Espaçamento

| Classe | Uso |
|--------|-----|
| `mb-12` | Entre seções principais |
| `mb-6` | Entre sub-seções |
| `mb-4` | Entre elementos dentro de uma seçêo |
| `mb-2` | Entre linhas de texto |
| `p-8` | Padding de cards principais |
| `p-6` | Padding de boxes internos |
| `p-4` | Padding de elementos menores |
| `p-3` | Padding de itens de lista |
| `gap-4` | Espaço entre itens de grid |
| `gap-6` | Espaço maior entre itens de grid |
| `space-y-3` | Espaço vertical entre itens de lista |

---

## 5. Tipografia

| Elemento | Classes |
|----------|---------|
| Título da página (h1) | `text-4xl sm:text-5xl font-bold` |
| Título de seçêo (h2) | `text-2xl font-bold` |
| Título de sub-seçêo (h3) | `text-xl font-bold` |
| Título pequeno (h4) | `font-bold` ou `font-semibold` |
| Parágrafo destaque | `text-lg text-neutral-300` |
| Parágrafo normal | `text-neutral-300` |
| Texto secundário | `text-neutral-400` |
| Texto pequeno | `text-sm text-neutral-300` |
| Texto muito pequeno | `text-xs text-neutral-400` |
| Badge/Tag | `text-sm font-semibold` |

---

## 6. Container Principal

Todas as páginas usam `max-w-4xl` para largura máxima do conteúdo:

```html
<main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
  <!-- Conteúdo -->
</main>
```

---

## 7. Responsividade

- Grid de 2 colunas: `grid md:grid-cols-2`
- Grid de 3 colunas: `grid md:grid-cols-3`
- Grid de 4 colunas: `grid grid-cols-2 md:grid-cols-4`
- Texto responsivo: `text-4xl sm:text-5xl`
- Padding responsivo: `px-4 sm:px-6 lg:px-8`

---

## 8. Efeitos Visuais

| Efeito | Classes |
|--------|---------|
| Blur no background | `backdrop-blur-sm` |
| Transparência | `bg-dark-900/95` (95% opacidade) |
| Gradiente | `bg-gradient-to-br from-[cor]-900/30 to-dark-800` |
| Hover em link | `hover:text-primary transition-colors` |
| Hover em botêo | `hover:bg-primary/90 transition-colors` |
| Borda colorida à esquerda | `border-l-4 border-[cor]-500` |

---

## 9. Emojis por Categoria

| Categoria | Emojis Sugeridos |
|-----------|------------------|
| Mentalidade | 🧠 💡 ⏰ ✨ 🎯 |
| Algoritmo | ⚙️ 🤖 📊 🔄 🎯 |
| Tempo | ⏱️ 🏗️ 🔄 ⚡ 📐 |
| Conteúdo | 🎬 📋 🪝 ✓ |
| Gatilhos | 💡 😲 ✓ 🎯 💭 ⭐ |
| Roteiros | 📝 🏠 💄 👗 🎧 🧹 |
| Sucesso | ✅ ✓ 🎉 🚀 |
| Alerta | ⚠️ ❌ ✗ |
| Info | 📊 📈 💡 ℹ️ |

---

## 10. Checklist de Criaçêo de Página

- [ ] Estrutura HTML base com Tailwind config
- [ ] Navigation sticky com link de volta
- [ ] Header com badge, título e descriçêo
- [ ] Stats banner (se aplicável)
- [ ] Seções com gradiente para conceitos principais
- [ ] Boxes de comparaçêo (fazer/nêo fazer)
- [ ] Alertas coloridos para dicas
- [ ] Resumo final com CTA
- [ ] Footer
- [ ] Script de inicializaçêo do tema
- [ ] Verificar responsividade
- [ ] Verificar dark/light mode
