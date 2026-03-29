---
name: MCP Argentina
version: 0.1.0
description: Datos económicos de Argentina en tiempo real - dólar, inflación, riesgo país
author: greydina
homepage: https://github.com/greydina/mcp-argentina
tags: [argentina, dolar, economia, inflacion, mcp]
---

# MCP Argentina

Consulta datos económicos de Argentina en tiempo real: cotizaciones de dólar, inflación, riesgo país, monedas extranjeras.

## Cuándo usar

Usa esta skill cuando el usuario pregunte por:
- Cotización del dólar (blue, oficial, MEP, CCL, cripto, tarjeta, mayorista)
- Inflación (mensual, interanual, acumulada)
- Riesgo país de Argentina
- Cotización de monedas extranjeras (EUR, BRL, UYU, etc.)
- Histórico de cotizaciones
- Conversiones entre ARS y USD
- Comparación de tipos de cambio

## Capacidades

### Dólar
- **7 tipos**: blue, oficial, MEP, CCL, cripto, tarjeta, mayorista
- **Histórico**: 30+ días de evolución
- **Variación**: cálculo porcentual en período

### Indicadores
- **Inflación**: mensual, interanual, acumulada (INDEC)
- **Riesgo país**: índice EMBI en tiempo real

### Monedas
- EUR (Euro), BRL (Real), UYU (Peso Uruguayo), CLP (Peso Chileno), y más

### Conversiones
- ARS → USD y USD → ARS con cualquier tipo de cambio

## Implementación

Para consultar datos, ejecutar Python con el Container:

```python
import asyncio
from mcp_argentina.infrastructure.container import Container

async def consultar():
    c = Container()
    
    # Dólar blue
    blue = await c.repository.obtener_dolar("blue")
    # Acceso: blue.venta.valor, blue.compra.valor
    
    # Todas las cotizaciones
    todas = await c.repository.obtener_todas()
    
    # Inflación
    inf = await c.inflacion.obtener_actual()
    # Acceso: inf.mensual, inf.interanual, inf.acumulada_anio
    
    # Riesgo país
    riesgo = await c.repository.obtener_riesgo_pais()
    
    # Histórico
    hist = await c.historicos.obtener_historico_dolar("blue", dias=30)
    
    # Variación
    var = await c.historicos.obtener_variacion_dolar("blue", dias=7)
    
    # Moneda extranjera
    euro = await c.monedas.obtener_moneda("EUR")
    
    return blue, inf, riesgo

asyncio.run(consultar())
```

## Instalación

### Desde PyPI

```bash
pip install mcp-argentina
```

### Desde source

```bash
git clone https://github.com/greydina/mcp-argentina
cd mcp-argentina
pip install -e .
```

### Configuración MCP Client

Después de instalar, configurar tu cliente MCP:

**Claude Desktop** (`~/Library/Application Support/Claude/claude_desktop_config.json`):
```json
{
  "mcpServers": {
    "mcp-argentina": {
      "command": "python",
      "args": ["-m", "mcp_argentina"]
    }
  }
}
```

**Cursor** (`.cursor/mcp.json`):
```json
{
  "mcpServers": {
    "mcp-argentina": {
      "command": "python",
      "args": ["-m", "mcp_argentina"]
    }
  }
}
```

## Formato de respuesta

### Dólar
```
💵 Dólar Blue
Compra: $1,395
Venta: $1,415
Spread: $20 (1.4%)
```

### Inflación
```
📊 Inflación Argentina
Mensual: 2.9%
Interanual: 33.0%
Acumulada 2026: 5.9%
```

### Riesgo País
```
🌡️ Riesgo País: 615 puntos
```

### Todas las cotizaciones
```
📊 Cotizaciones actuales:
• Oficial: $950 / $1,000
• Blue: $1,395 / $1,415
• MEP: $1,350 / $1,380
• CCL: $1,360 / $1,390
• Cripto: $1,380 / $1,410
• Tarjeta: $1,520 / $1,600
• Mayorista: $980 / $1,005
```

## Fuentes de datos

| Fuente | Datos |
|--------|-------|
| [dolarapi.com](https://dolarapi.com) | Cotizaciones dólar tiempo real |
| [argentinadatos.com](https://argentinadatos.com) | Históricos, inflación, riesgo país |

100% APIs públicas, sin scraping.

## Links

- **MCP Server**: https://github.com/greydina/mcp-argentina
- **PyPI**: https://pypi.org/project/mcp-argentina/
