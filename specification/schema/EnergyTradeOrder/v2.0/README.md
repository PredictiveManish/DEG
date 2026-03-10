# EnergyTradeOrder — v2.0

Order attributes for P2P energy trading — BAP/BPP participant identification and total contracted energy quantity.

Part of the [DEG Schema](../../../specification/schema/) · [EnergyTradeOrder](../README.md)

## Files

| File | Description |
|------|-------------|
| [attributes.yaml](./attributes.yaml) | JSON Schema 2020-12 definition for `EnergyTradeOrder` |
| [context.jsonld](./context.jsonld) | JSON-LD context (namespace: `https://schema.beckn.io/deg/EnergyTradeOrder/v2.0/`) |
| [vocab.jsonld](./vocab.jsonld) | RDF vocabulary for `EnergyTradeOrder` terms |

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `bap_id` | `string` | ✅ | BAP subscriber ID (buyer platform) |
| `bpp_id` | `string` | ✅ | BPP subscriber ID (seller platform) |
| `total_quantity` | [Quantity](https://schema.beckn.io/Quantity/v2.0) | | Total energy in kWh (`unitText: kWh`, `unitCode: KWH`) |

## Changes from v0.3

- Extracted from combined `EnergyTrade/v0.3/attributes.yaml` into standalone schema
- Published as JSON Schema 2020-12 (was OpenAPI 3.1 component)
- External `Quantity` ref uses canonical `https://schema.beckn.io/Quantity/v2.0` URI
