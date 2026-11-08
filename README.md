# 🏎️ Porsche Sales Intelligence Dashboard

Uma dashboard interativa, responsiva e de alta performance, desenvolvida em arquivo único para análise das vendas da Porsche. Este projeto substitui relatórios estáticos em Excel por uma visualização web dinâmica, permitindo segmentações em tempo real e análises orientadas a perguntas de negócio.

## 📌 Sobre o Desafio

O desafio consiste em transformar uma base de vendas de veículos (contendo dados crus e sanitizados) em uma dashboard interativa, com visual profissional e publicada na web via **GitHub Pages**.

### 💡 Evoluções Implementadas no Projeto

Além dos requisitos básicos, esta versão inclui melhorias avançadas de engenharia e design:

1. **Regionalização (Filtro por UF):** Mapeamento das cidades da base original em Estados (SP, RJ, MG, PR, RS, SC, DF), permitindo a análise de desempenho por região.
2. **Arquitetura Assíncrona (Fetch Data):** Carregamento dinâmico via `vendas.json`, com mecanismo de *fallback* automático para a base embutida.
3. **Seletor de Temas Visuais (Benchmarking):** Alternância em tempo real entre diferentes identidades visuais:
   - **Porsche:** Estilo dark esportivo com destaques em vermelho e dourado.
   - **Ferrari:** Fundo escuro com acentos em vermelho Corsa.
   - **Tesla:** Visual futurista minimalista em azul elétrico e ciano.
   - **Power BI:** Layout corporativo modular inspirado no Microsoft Power BI Service.
4. **Tratamento de Dados Crus (`INVALID`):** Aplicação de regra de imputação por mediana para registros com valores ausentes ou inválidos, acompanhada por um indicador visual de **Data Quality**.
5. **Arquitetura de Agentes Duplos:** Separação da lógica de construção em duas etapas (*Skill 1: Data Cleaner & Imputer* + *Skill 2: UI Engineer*).

## 📊 Perguntas de Negócio Respondidas

| # | Pergunta de Negócio | Componente Visual | Objetivo Analítico |
|---|---|---|---|
| 1 | Qual o faturamento acumulado por Estado (UF)? | Gráfico de Barras | Mapear as regiões geográficas de maior impacto financeiro. |
| 2 | Como a receita se distribui entre os modelos? | Gráfico Donut | Identificar os modelos líderes de receita na categoria. |
| 3 | Qual a preferência de método de pagamento? | Gráfico de Pizza | Analisar a proporção entre pagamento à vista, financiamento e consórcio. |

## 🛠️ Tecnologias Utilizadas

- **HTML5 e JavaScript (ES6+):** Estrutura da aplicação e lógica dos filtros reativos.
- **Tailwind CSS:** Renderização de estilos responsivos e temas dinâmicos via variáveis CSS.
- **Chart.js:** Renderização dos gráficos interativos.
- **Lucide Icons:** Biblioteca de ícones SVG.

## 📂 Estrutura do Repositório

```bash
├── index.html          # Aplicação principal (UI + Filtros + Gráficos + Temas)
├── vendas.json         # (Opcional) Base de dados externa em formato JSON
└── README.md           # Documentação técnica do projeto
```

## 🚀 Como Executar e Publicar

### Execução Local

Não é necessário instalar dependências ou configurar um servidor local. Basta abrir o arquivo `index.html` diretamente no navegador.

### Publicação no GitHub Pages

1. Crie um repositório no GitHub.
2. Adicione os arquivos `index.html` e `README.md` ao repositório.
3. Envie os arquivos via terminal ou pela interface do GitHub:

   ```bash
   git add .
   git commit -m "feat: dashboard interativa porsche"
   git push origin main
   ```

4. No repositório do GitHub, acesse **Settings** > **Pages**.
5. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
6. Clique em **Save**.

O link da sua dashboard estará disponível em poucos minutos.

## 🤖 Pipeline da Arquitetura de Agentes

```yaml
[ Planilha Crua / Excel ]
          │
          ▼
 ┌──────────────────────────────┐
 │   Skill 1: Data Cleaner      │ ──> Imputação por Mediana & Mapeamento UF
 └──────────────────────────────┘
          │
          ▼ (vendas.json)
 ┌──────────────────────────────┐
 │   Skill 2: UI Engineer       │ ──> Renderização do Dashboard & Temas
 └──────────────────────────────┘
```

## 📄 Licença

Este projeto é de uso livre para fins educacionais e de demonstração sob a licença [MIT](https://choosealicense.com/licenses/mit/).

