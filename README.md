# 📄 PDF Report Generator

![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Gemma 4](https://img.shields.io/badge/Gemma_4-LLM-orange?style=flat-square&logo=google&logoColor=white)
![Privacy-First](https://img.shields.io/badge/Privacy-100%25_Local-brightgreen?style=flat-square)
![Ollama](https://img.shields.io/badge/Ollama-Inference-blueviolet?style=flat-square)

> Turn raw CSV data into polished, professional reports — powered entirely by a local LLM. No API keys, no cloud.

## Architecture

```
┌──────────────────────────────────────────────┐
│              Input Layer                      │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│   │ CSV File │  │  Topic   │  │ Template │  │
│   └────┬─────┘  └────┬─────┘  └────┬─────┘  │
│        └──────────────┼─────────────┘        │
│                 ┌─────▼──────┐               │
│                 │  Data      │               │
│                 │  Analyzer  │               │
│                 └─────┬──────┘               │
│                 ┌─────▼──────┐               │
│                 │  Ollama    │               │
│                 │ (Gemma 4)  │               │
│                 └─────┬──────┘               │
│                 ┌─────▽──────┐               │
│                 │  Report    │               │
│                 │  Renderer  │               │
│                 └─────┬──────┘               │
│        ┌──────────────┼──────────────┐       │
│   ┌────▽────┐   ┌─────▽────┐  ┌─────▽───┐  │
│   │Markdown │   │   HTML   │  │  Text   │  │
│   └─────────┘   └──────────┘  └─────────┘  │
└──────────────────────────────────────────────┘
```

## Features

1. **CSV-to-Report Pipeline** — Upload a CSV file and get a structured, narrative report automatically
2. **Multiple Templates** — Choose from executive, technical, or summary report styles
3. **Statistical Analysis** — Automatic computation of means, medians, distributions, and key metrics
4. **Multi-Format Output** — Export reports as Markdown, HTML, or plain text
5. **Rich CLI Interface** — Beautiful terminal output with color-coded sections and progress indicators
6. **Streamlit Web UI** — Browser-based dashboard for uploading data and previewing reports
7. **FastAPI REST Endpoint** — Generate reports programmatically via API for pipeline integration
8. **Configurable Templates** — Customize report sections, lengths, and formatting via YAML config
9. **Docker Ready** — Full Docker and Docker Compose support for containerized deployment
10. **100% Local & Private** — All inference runs through Ollama locally; your business data never leaves your machine

## Quick Start

### Prerequisites

- Python 3.11 or higher
- [Ollama](https://ollama.com/) installed and running
- Gemma 4 model pulled: `ollama pull gemma4`

### Installation

```bash
git clone https://github.com/kennedyraju55/pdf-report-generator.git
cd pdf-report-generator
pip install -r requirements.txt
```

### Running the Application

**CLI:**
```bash
python -m src.report_generator.cli generate --data sales.csv --topic "Q4 Sales Analysis"
```

**Web UI:**
```bash
streamlit run src/report_generator/web_ui.py
```

**Docker:**
```bash
docker-compose up
```

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| Gemma 4 + Ollama | Local LLM inference for report narrative generation |
| Click + Rich | CLI framework with formatted terminal output |
| Streamlit | Interactive web dashboard for data upload and preview |

## Project Structure

- `src/report_generator/` — Core application: data analysis, report generation, CLI, web UI, API
- `common/` — Shared LLM client utilities for Ollama integration
- `tests/` — Unit and integration test suite
- `docs/` — Documentation and architecture diagrams
- `examples/` — Sample CSV datasets and generated reports

## Author

**Nrk Raju Guthikonda** — [GitHub: kennedyraju55](https://github.com/kennedyraju55) · [Dev.to](https://dev.to/kennedyraju55) · [LinkedIn](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8/)
