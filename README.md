# 💹 AI Equity Analyst — Quant Research Terminal

**Projeto Final FGV** | IA Aplicada ao Mercado Financeiro | Linha 3.5

Terminal estilo Bloomberg/Wall Street para análise quantitativa de ações brasileiras,
desenvolvido para asset managers e analistas institucionais.

---

## 🚀 Quick Deploy (5 minutos)

### Passo 1 — Substituir arquivos no GitHub

No seu repositório `github.com/sabinagoldstein1-prog/AI-Equity-Analyst`:

**Para CADA arquivo abaixo:**
1. Clique no arquivo na lista
2. Clique no ícone de **lápis (Edit)** no canto superior direito
3. **Ctrl+A** (selecionar tudo) → **Delete** (apagar)
4. **Ctrl+V** (colar o novo conteúdo)
5. Role até o final → **Commit changes**

**Arquivos para substituir:**
- `app.py` — interface Streamlit (terminal Bloomberg)
- `engine.py` — motor com 7 tools quantitativas
- `requirements.txt` — dependências
- `.streamlit/config.toml` — tema dark profissional

**⚠️ DELETAR este arquivo (não usado mais):**
- `ai_analyst.py` — clique nele → ícone lixeira → confirmar

### Passo 2 — Aguardar redeploy

Streamlit Cloud detecta o commit e redeploya automaticamente em ~2 minutos.
Acesse: https://ai-equity-analyst-mx5wpw65fakbqmywsznq8y.streamlit.app/

---

## 🏗️ Arquitetura

```
INPUT (sidebar): tickers + profile + lookback
   │
   ├─ TOOL 1: fetch_prices         → Preços + vol, momentum, drawdown
   ├─ TOOL 2: fetch_fundamentals   → P/E, P/B, EV/EBITDA + ROE, Margins
   ├─ TOOL 3: run_ml               → Random Forest walk-forward + clusters
   ├─ TOOL 4: run_predictive_model → RF Classifier direção diária
   ├─ TOOL 5: run_trading_system   → MA Crossover 20/60 + backtest
   ├─ TOOL 6: run_monte_carlo      → 10K simulações Markowitz
   └─ TOOL 7: run_scoring          → Score composto + Buy/Hold/Sell
   │
OUTPUT: 5 abas (Ranking · Market · ML · Signals · Portfolio)
```

## 📊 5 Abas do Terminal

| Aba | Conteúdo | Técnicas |
|-----|----------|----------|
| **RANKING** | Score composto + tabela de recomendações | Multi-factor scoring |
| **MARKET** | Risk×Return + evolução + fundamentos | Cross-sectional metrics |
| **ML ENGINE** | Walk-forward + feature importance + previsão | Random Forest, KMeans |
| **SIGNALS** | AUC preditivo + trading system backtest | RF Classifier, MA Crossover |
| **PORTFOLIO** | Fronteira eficiente + alocação ótima | Monte Carlo Markowitz |

## ✅ Bug Fixes (v5)

| Bug Anterior | Fix v5 |
|--------------|--------|
| `?` em nome/setor | Hardcoded `SECTOR_MAP` e `NAME_MAP` como fallback |
| `None`/`-` em P_L, P_VP | 3-layer fetch: `.info` → `.fast_info` → `history()` |
| Yahoo Finance retornando vazio | Rate limiting + retry logic |
| Quota Gemini 429 | Chatbot removido completamente |
| Tabela com NaN crus | Formatação pré-display (`fmt_brl`, `fmt_x`, `fmt_pct`) |

## 🎓 Conteúdo Didático

Cada aba contém uma **caixa amarela explicativa** (📚) que ensina o conceito quant
por trás da análise. Exemplos:
- Walk-forward validation
- Sharpe Ratio e fronteira eficiente
- Spearman IC e significância estatística
- Markowitz Modern Portfolio Theory

## 📁 Estrutura Final

```
AI-Equity-Analyst/
├── app.py                    ← Bloomberg terminal Streamlit
├── engine.py                 ← 7 quant tools
├── requirements.txt          ← Dependências Python
├── .streamlit/
│   └── config.toml           ← Dark theme
└── README.md                 ← Este arquivo
```

---

*FGV 2026 | IA Aplicada ao Mercado Financeiro | Prof. João Luiz Chela*
