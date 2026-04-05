<div align="center">
<img src="https://img.shields.io/badge/📊_PDF_Report_Generator-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# 📊 PDF Report Generator

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![LLM](https://img.shields.io/badge/LLM-Ollama%2FGemma4-green)
![CLI](https://img.shields.io/badge/CLI-Click-orange)
![Web](https://img.shields.io/badge/Web-Streamlit-red)
![Tests](https://img.shields.io/badge/tests-pytest-yellow)

Generate professional, structured reports from CSV data using a local LLM. Supports multiple templates (executive, technical, summary), multi-format output (Markdown, HTML, text), and both CLI and web interfaces.

## Features

- **Template System** — Executive, technical, and summary report templates
- **Multi-Format Output** — Markdown, HTML, and plain text export
- **Chart Descriptions** — AI-generated visualization recommendations
- **Executive Summary** — Auto-generated executive overview section
- **Automatic Data Analysis** — Statistical profiling for numeric and categorical columns
- **Streamlit Web UI** — Upload data, select templates, preview and download reports
- **Rich CLI** — Beautiful terminal output with tables, spinners, and previews
- **YAML Configuration** — Customizable settings via `config.yaml`
- **Environment Overrides** — Configure via `.env` or environment variables

## Installation

```bash
cd 16-pdf-report-generator
pip install -r requirements.txt
```

Ensure [Ollama](https://ollama.com/) is installed and running:

```bash
ollama serve
ollama pull gemma4
```

## Usage

### CLI

```bash
# Executive report (default)
python -m src.report_generator.cli --topic "Q4 Sales" --data data.csv

# Technical analysis report
python -m src.report_generator.cli --topic "Q4 Sales" --data data.csv --template technical

# HTML output
python -m src.report_generator.cli --topic "Q4 Sales" --data data.csv --format html

# With custom config
python -m src.report_generator.cli --topic "Sales" --data data.csv --config config.yaml --verbose
```

### Web UI

```bash
streamlit run src/report_generator/web_ui.py
```

### CLI Options

| Option       | Required | Default      | Description                         |
|--------------|----------|--------------|-------------------------------------|
| `--topic`    | Yes      | —            | Report topic or title               |
| `--data`     | Yes      | —            | Path to input CSV file              |
| `--output`   | No       | `report.md`  | Output file path                    |
| `--template` | No       | `executive`  | Template: executive/technical/summary |
| `--format`   | No       | `markdown`   | Output format: markdown/html/text   |
| `--config`   | No       | —            | Path to config.yaml                 |
| `--verbose`  | No       | —            | Enable debug logging                |

## Testing

```bash
python -m pytest tests/ -v
```

## Project Structure

```
16-pdf-report-generator/
├── src/report_generator/
│   ├── __init__.py          # Package init
│   ├── core.py              # Core business logic
│   ├── cli.py               # Click CLI interface
│   ├── web_ui.py            # Streamlit web interface
│   ├── config.py            # Configuration management
│   └── utils.py             # Helper utilities
├── tests/
│   ├── __init__.py
│   ├── test_core.py         # Core logic tests
│   └── test_cli.py          # CLI integration tests
├── config.yaml              # Default configuration
├── setup.py                 # Package setup
├── requirements.txt         # Dependencies
├── Makefile                 # Dev commands
├── .env.example             # Environment template
└── README.md
```

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>
