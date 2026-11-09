# esgotamento_sanitario

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Licença do código](https://img.shields.io/badge/c%C3%B3digo-MIT-green)
![Licença dos dados e texto](https://img.shields.io/badge/dados%20e%20texto-CC--BY%204.0-lightgrey)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-orange)

**Instituição:** Unilasalle, Rio de Janeiro
**Curso:** Bacharelado em Sistemas de Informação, 6º período
**Disciplina:** Linguagem de Programação (Análise e Visualização de Dados com Python)
**Semestre:** [confirmar]
**Docente:** [preencher]
**Autores:** Pedro Henrique dos Santos Gonçalves, [demais integrantes, se houver]

**Artigo (GitHub Pages):** [inserir link após o deploy]

---

## Resumo executivo

Este projeto analisa dados abertos de esgotamento sanitário do Brasil, referentes a 2024, publicados pelo SINISA (Sistema Nacional de Informações em Saneamento Básico). O trabalho constrói um pipeline determinístico em Python (aquisição, limpeza, normalização e persistência) e uma análise exploratória com visualizações estáticas e interativas, comunicadas em um artigo acadêmico em HTML.

> [Complementar com método, achados centrais e implicações quando a análise estiver concluída.]

**Palavras-chave:** saneamento básico; esgotamento sanitário; SINISA; análise exploratória de dados; visualização de dados; ciência aberta.

## Perguntas de pesquisa

> Pendentes de aprovação do docente.

- **RQ1:** [definir]
- **RQ2:** [definir]
- **RQ3:** [definir, opcional]

## Fonte dos dados

- **Fonte primária:** SINISA, módulo Esgoto, ano de referência 2024.
- **Link perene:** [inserir o endereço oficial da página de download dos dados]
- **Bases utilizadas:** [indicar quais após a Fase 0. Disponíveis: municipal, UF/Macrorregião/Brasil, locais e regionais, estações de tratamento e balanço; cada uma com indicadores, gestão técnica e gestão administrativa e financeira.]
- **Granularidade:** [definir conforme a base escolhida]
- **Data de acesso:** [preencher]

Os arquivos originais ficam em `data/raw/` e não são alterados. Se o tamanho passar de 50 MB, o repositório traz um script de download no lugar dos arquivos.

## Estrutura do repositório

```text
nome-do-projeto/
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/                  # dados brutos originais (ou script de download)
│   ├── processed/            # dados tratados (Parquet ou CSV comprimido)
│   └── data_dictionary.md    # dicionário de variáveis
├── notebooks/
│   └── analise_exploratoria.ipynb
├── src/
│   ├── __init__.py
│   └── etl.py                # limpeza, agregações e métricas
└── docs/
    ├── index.html            # artigo publicado no GitHub Pages
    └── assets/               # figuras e visualizações exportadas
```

## Pipeline de dados

1. **Ingestão:** leitura dos arquivos `.xlsx` de `data/raw/`.
2. **Limpeza:** padronização de nomes de colunas, conversão de tipos, tratamento de valores ausentes e de códigos de município.
3. **Métricas derivadas:** indicadores calculados a partir das variáveis originais, documentados no dicionário de dados.
4. **Persistência:** dados tratados gravados em `data/processed/`, sem sobrescrever os brutos.
5. **Rastreabilidade:** o que foi descartado, imputado ou convertido é registrado em log.

## Como reproduzir

```bash
git clone [URL do repositório]
cd nome-do-projeto

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

python src/etl.py                # gera os dados em data/processed/
jupyter notebook notebooks/analise_exploratoria.ipynb
```

O artigo está em `docs/index.html` e pode ser aberto direto no navegador.

## Princípios FAIR

| Princípio | Como é atendido |
|---|---|
| Findable | README com resumo, palavras-chave e link da fonte; autoria, disciplina e instituição identificadas |
| Accessible | Repositório público, sem credenciais pagas; artigo no GitHub Pages, responsivo |
| Interoperable | Dicionário em `data/data_dictionary.md`; dados em formato aberto (Parquet ou CSV comprimido) |
| Reusable | Licenças abertas; `requirements.txt` com versões fixas (`pip freeze`) |

## Licenças

- **Código:** [MIT](LICENSE)
- **Dados processados e texto do artigo:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

Os dados brutos pertencem à fonte original (SINISA) e seguem os termos de uso dela.

## Andamento

- [ ] Fase 0: exploração das bases e definição das perguntas de pesquisa
- [ ] Fase 1: estrutura do repositório
- [ ] Fase 2: ETL e dicionário de dados
- [ ] Fase 3: análise exploratória e gráficos
- [ ] Fase 4: artigo em HTML
- [ ] Fase 5: deploy no GitHub Pages e revisão final

## Como citar

> GONÇALVES, Pedro Henrique dos Santos; [demais autores]. **[Título do projeto]**. [Ano]. Projeto final da disciplina Linguagem de Programação, Unilasalle. Disponível em: [link do repositório].
