# MCP Argentina Skill

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

## Uso

### Consulta simple
```
¿Cuánto está el dólar blue?
```

### Todas las cotizaciones
```
Dame todas las cotizaciones del dólar
```

### Histórico
```
¿Cómo evolucionó el blue en los últimos 30 días?
```

### Inflación
```
¿Cuál es la inflación actual?
```

### Conversión
```
Convertí 100 USD a pesos al blue
```

## Instalación

### Requisitos
- Python 3.10+
- OpenClaw configurado

### Desde PyPI (próximamente)
```bash
pip install mcp-argentina
```

### Desde source
```bash
git clone https://github.com/greydina/mcp-argentina
cd mcp-argentina
pip install -e .
```

## Fuentes de datos

| Fuente | Datos |
|--------|-------|
| [dolarapi.com](https://dolarapi.com) | Cotizaciones dólar tiempo real |
| [argentinadatos.com](https://argentinadatos.com) | Históricos, inflación, riesgo país |

100% APIs públicas, sin scraping.

## Ejemplos de respuesta

### Dólar Blue
```
💵 Dólar Blue
Compra: $1,395
Venta: $1,415
Spread: $20 (1.4%)
Actualizado: 2026-03-29 12:00
```

### Inflación
```
📊 Inflación Argentina
Mensual: 2.9%
Interanual: 33.0%
Acumulada 2026: 5.9%
```

## Links

- **MCP Server**: https://github.com/greydina/mcp-argentina
- **Skill**: https://github.com/greydina/skill-mcp-argentina
