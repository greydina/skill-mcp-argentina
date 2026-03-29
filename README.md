# skill-mcp-argentina

OpenClaw skill for querying Argentine economic data in real-time.

## Features

- 💵 **Dólar**: 7 types (blue, oficial, MEP, CCL, cripto, tarjeta, mayorista)
- 📈 **Históricos**: 30+ days of exchange rate history
- 📊 **Inflación**: Monthly, annual, and accumulated (INDEC)
- 🌡️ **Riesgo país**: Real-time EMBI index
- 💱 **Monedas**: EUR, BRL, UYU, CLP, and more
- 🔄 **Conversiones**: ARS ↔ USD with any exchange rate

## Installation

1. Add this skill to your OpenClaw workspace:

```bash
cd ~/.openclaw/workspace/skills
git clone https://github.com/greydina/skill-mcp-argentina mcp-argentina
```

2. Install the MCP server:

```bash
pip install mcp-argentina  # Coming soon to PyPI
# Or from source:
pip install git+https://github.com/greydina/mcp-argentina
```

3. The skill will be automatically detected by OpenClaw.

## Usage

Just ask naturally:

```
¿Cuánto está el dólar blue?
Dame todas las cotizaciones
¿Cómo evolucionó el MEP en los últimos 7 días?
Convertí 1000 USD a pesos al CCL
¿Cuál es la inflación interanual?
```

## Data Sources

- [dolarapi.com](https://dolarapi.com) - Real-time exchange rates
- [argentinadatos.com](https://argentinadatos.com) - Historical data, inflation, country risk

## Related

- [mcp-argentina](https://github.com/greydina/mcp-argentina) - The MCP server this skill uses

## License

MIT
