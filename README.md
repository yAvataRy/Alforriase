# Alforriase Landing Page - Guia de Setup

## 📋 Sobre o Projeto

Landing page profissional para **Alforriase**, um serviço de astrologia aplicada e acompanhamento estratégico para mulheres. O projeto foi desenvolvido com **Vue 3**, **TypeScript**, **Tailwind CSS** e **shadcn/vue**.

## 🚀 Stack Tecnológico

- **Vue 3** - Framework JavaScript reativo
- **TypeScript** - Tipagem estática
- **Tailwind CSS 4** - Utilitários CSS
- **shadcn/vue** - Componentes UI reutilizáveis
- **Vite** - Build tool moderno
- **Radix Vue** - Componentes acessíveis

## 📦 Instalação

### 1. Descompactar o arquivo

```bash
# Se usando .tar.gz
tar -xzf alforriase-landing-page.tar.gz
cd alforriase-landing-page

# Se usando .zip
unzip alforriase-landing-page.zip
cd alforriase-landing-page
```

### 2. Instalar dependências

```bash
npm install
```

### 3. Iniciar o servidor de desenvolvimento

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:5173`

## 🏗️ Estrutura do Projeto

```
alforriase-landing-page/
├── src/
│   ├── components/
│   │   ├── Navbar.vue           # Navegação principal
│   │   ├── Hero.vue             # Seção inicial
│   │   ├── Benefits.vue         # Sobre Alforriase
│   │   ├── Services.vue         # Experiências/Serviços
│   │   ├── Testimonials.vue     # Depoimentos
│   │   ├── Team.vue             # Sobre Camila
│   │   ├── Contact.vue          # Formulário de contato
│   │   ├── Footer.vue           # Rodapé
│   │   └── ui/                  # Componentes shadcn/ui
│   ├── assets/
│   │   └── index.css            # Estilos globais e tema
│   ├── icons/                   # Ícones customizados
│   ├── App.vue                  # Componente raiz
│   └── main.ts                  # Entrada da aplicação
├── public/                      # Arquivos estáticos
├── index.html                   # HTML principal
├── package.json                 # Dependências
├── tailwind.config.js           # Configuração Tailwind
├── tsconfig.json                # Configuração TypeScript
└── vite.config.ts               # Configuração Vite
```

## 🎨 Paleta de Cores

- **Bordô (Principal)**: `#6B2026` - Cor primária
- **Verde Musgo (Ação)**: `#50644A` - Cor secundária
- **Bege (Background)**: `#F3EDE6` - Fundo suave
- **Azul Escuro (Textos)**: `#22304B` - Textos secundários

## 📝 Seções da Landing Page

1. **Header/Navbar** - Navegação sticky com links para todas as seções
2. **Hero** - Apresentação principal com CTA
3. **Sobre Alforriase** - História e missão do projeto
4. **Sobre Camila** - Apresentação da fundadora
5. **Experiências** - 4 serviços principais (Jornada Solar, Mapa Astral, Astro Express, Jornada Solar Pocket)
6. **Depoimentos** - Carrossel com 5 depoimentos de clientes
7. **Contato** - Formulário de contato com validação
8. **Footer** - Links e informações adicionais

## 🔧 Personalizações Necessárias

### 1. Email do Formulário

No arquivo `src/components/Contact.vue`, substitua o email:

```typescript
const response = await fetch("https://formsubmit.co/ajax/seu_email@alforriase.com", {
```

Por seu email real.

### 2. WhatsApp

Substitua o número de WhatsApp em:

- `src/components/Hero.vue`
- `src/components/Contact.vue`
- `src/components/Footer.vue`

De: `https://wa.me/5511999999999`
Para: `https://wa.me/seu_numero_aqui`

### 3. Instagram

Substitua o link do Instagram em:

- `src/components/Footer.vue`
- `src/components/Contact.vue`

De: `https://instagram.com/camisdaalforriase`
Para: `https://instagram.com/seu_usuario`

### 4. Imagens

As imagens estão usando URLs do Unsplash. Para usar imagens locais:

1. Adicione as imagens em `public/images/`
2. Atualize os `src` das imagens nos componentes

## 🏗️ Build para Produção

```bash
npm run build
```

Os arquivos compilados estarão em `dist/`

## 📱 Responsividade

O projeto é totalmente responsivo e testado para:

- Mobile: 320px, 375px, 412px
- Tablet: 768px
- Desktop: 1024px, 1440px

## ♿ Acessibilidade

- ✅ Contraste de texto adequado (4.5:1 mínimo)
- ✅ Alt text em todas as imagens
- ✅ Aria-labels em formulários
- ✅ Ordem de headings correta (h1 → h2 → h3)
- ✅ Touch targets ≥ 44px

## 🔍 SEO

Meta tags configuradas para:

- Título: "Alforriase — Clareza que liberta"
- Descrição otimizada
- Open Graph tags
- Twitter Card

## 📚 Dependências Principais

- `vue@^3.5.12` - Framework Vue
- `tailwindcss@^3.4.4` - Utilitários CSS
- `radix-vue@^1.9.7` - Componentes acessíveis
- `vee-validate@^4.13.2` - Validação de formulários
- `lucide-vue-next@^0.452.0` - Ícones
- `embla-carousel-vue@^8.3.0` - Carrossel

## 🚀 Deploy

O projeto pode ser deployado em qualquer plataforma que suporte aplicações Vue estáticas:

- **Vercel**: `vercel deploy`
- **Netlify**: Conecte o repositório Git
- **GitHub Pages**: Configure o build para `dist/`
- **Seu próprio servidor**: Copie os arquivos de `dist/` para o servidor web

## 📞 Suporte

Para dúvidas ou problemas:

1. Verifique se todas as dependências foram instaladas: `npm install`
2. Limpe o cache: `rm -rf node_modules && npm install`
3. Reinicie o servidor de desenvolvimento: `npm run dev`

## 📄 Licença

Este projeto foi desenvolvido para Alforriase.

---

**Desenvolvido com ❤️ para mulheres que buscam clareza e liberdade.**
