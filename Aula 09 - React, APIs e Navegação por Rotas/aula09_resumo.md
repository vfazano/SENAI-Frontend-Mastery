# 🎮 Aula 09 — React, APIs e Navegação por Rotas

Landing page e catálogo responsivo de jogos, desenvolvido em **React** com **Vite** para demonstrar na prática os conceitos da Aula 09: estado, formulários controlados, efeitos colaterais, consumo de API externa e navegação por rotas.

---

## 🚀 Tecnologias Utilizadas
- **React 18** (Vite)
- **React Router 6** (`BrowserRouter`, `Routes`, `Route`, `Link`, `NavLink`)
- **Supabase** (BaaS, PostgreSQL, Row Level Security - RLS)
- **Wikipedia API** (Consumo REST público)
- **Vercel** (Deploy e variáveis de ambiente em produção)

---

## 💻 Como Executar Localmente

Requer **Node.js LTS** e **npm**.

```bash
# Instalação das dependências
npm install

# Executar em ambiente de desenvolvimento
npm run dev
```

### ⚙️ Configuração do Supabase
Para habilitar o mural compartilhado:
1. Crie um projeto no [Supabase](https://supabase.com/).
2. Execute o script `supabase/schema.sql` pelo **SQL Editor** do Supabase.
3. Copie `.env.example` para `.env.local`.
4. Preencha `VITE_SUPABASE_URL` e `VITE_SUPABASE_ANON_KEY` com a URL e a chave publicável (`anon`) do projeto.
> ⚠️ **Atenção:** Nunca utilize a chave `service_role` no navegador nem a publique no GitHub.

Para gerar a versão de produção:
```bash
npm run build
npm run preview
```

---

## 🧭 Páginas da Aplicação

- **`/`**: Landing page com destaques da seleção e créditos.
- **`/jogos`**: Catálogo com filtros por gênero, fotos e botões para adicionar/remover jogos da lista da sessão.
- **`/jogos/:id`**: Página individual de cada jogo, com apresentação, lembrança pessoal e galeria de imagens.
- **`/comunidade`**: Mural público e compartilhado de recomendações, persistido no **Supabase**, com formulário controlado e validação.
- **`/api`**: Consulta a API da Wikipedia em português para exibir resumos de jogos com tratamento de loading, erro e lista vazia.

---

## 🧠 Conceitos Abordados na Aula

1. **JSX e Componentes:** Estruturação modular com `Layout`, `GameCard`, `GameGrid` e páginas.
2. **Props e Reutilização:** Fluxo unidirecional de dados e eventos passados por props.
3. **State / useState:** Controle reativo de filtros, lista de jogos salvos, formulários e respostas da API.
4. **Formulário e Validação:** Validação no cliente e no banco antes de publicar no mural compartilhado.
5. **useEffect:** Busca assíncrona na Wikipedia ao abrir `/api` e carregamento das recomendações do Supabase em `/comunidade`.
6. **Consumo de API:** Requisições `GET` à API pública da Wikipedia (`https://pt.wikipedia.org/w/api.php`) com tratamento completo de ciclo de vida da requisição (carregamento, sucesso, erro e lista vazia).
7. **Supabase (BaaS):** Leitura e gravação de recomendações na tabela `game_suggestions`, com políticas RLS permitindo inserção e leitura anônimas de forma segura.
8. **React Router:** Roteamento declarativo no client-side com `BrowserRouter`, rotas dinâmicas (`:id`) e links de navegação.
9. **Renderização Condicional:** Apresentação dinâmica da interface conforme os estados da aplicação.

---

## 🔗 Links do Projeto

- **Repositório GitHub:** [https://github.com/vfazano/aula09-react-api-router](https://github.com/vfazano/aula09-react-api-router)
- **Aplicação Online (Deploy):** [https://aula09-react-api-router.vercel.app/](https://aula09-react-api-router.vercel.app/)
- **Mural da Comunidade (Supabase):** [https://aula09-react-api-router.vercel.app/comunidade](https://aula09-react-api-router.vercel.app/comunidade)
- **Relatório de Entrega:** [RELATORIO-AULA09.md](https://github.com/vfazano/aula09-react-api-router/blob/main/RELATORIO-AULA09.md)
