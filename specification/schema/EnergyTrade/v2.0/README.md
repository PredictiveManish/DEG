# EnergyTrade — v2.0

> ⚠️ **Deprecated** — This schema is superseded by [`P2PTrade`](../../P2PTrade/v2.0/). Use `P2PTrade` (a subclass of `EnergyContract`) for all new energy contract implementations.

P2P energy trade contract — a subclass of [`Contract`](https://schema.beckn.io/Contract/v2.0) specialised for energy delivery between prosumers on a DEG network.

Part of the [DEG Schema](../../../README.md) · [EnergyTrade](../README.md)

## Files

| File | Description |
|------|-------------|
| [attributes.yaml](./attributes.yaml) | JSON Schema 2020-12 definition for `EnergyTrade` (subclass of `Contract`) |
| [context.jsonld](./context.jsonld) | JSON-LD context mapping properties to `deg:` and `schema:` IRIs |
| [vocab.jsonld](./vocab.jsonld) | RDF vocabulary for EnergyTrade domain terms |

## Root linked-data files

| File | Description |
|------|-------------|
| [schema/context.jsonld](../../context.jsonld) | Root JSON-LD context (all schemas) |
| [schema/vocab.jsonld](../../vocab.jsonld) | Root RDF vocabulary (all schemas) |

## Design

`EnergyTrade` is a subclass of `Contract` (via `allOf`) and adds domain-specific energy trading properties by referencing individual domain schemas at their canonical URIs:

| Property | References | Description |
|----------|-----------|-------------|
| `energyResource` | [`EnergyResource/v2.0`](https://schema.beckn.io/EnergyResource/v2.0) | Energy source characteristics |
| `delivery` | [`EnergyTradeDelivery/v2.0`](https://schema.beckn.io/EnergyTradeDelivery/v2.0) | Delivery tracking attributes |
| `offer` | [`EnergyTradeOffer/v2.0`](https://schema.beckn.io/EnergyTradeOffer/v2.0) | Offer terms (pricing model, windows) |
| `customer` | [`EnergyCustomer/v2.0`](https://schema.beckn.io/EnergyCustomer/v2.0) | Customer info (meter, utility, load) |

## Properties

| Property | Type | Required | Description |
|----------|------|:--------:|-------------|
| `energyResource` | `EnergyResource` | — | Energy source characteristics for this trade. |
| `delivery` | `EnergyTradeDelivery` | — | Delivery tracking attributes. |
| `offer` | `EnergyTradeOffer` | — | Energy trade offer attributes. |
| `customer` | `EnergyCustomer` | — | Energy customer attributes. |

*Plus all inherited `Contract` properties: `id`, `displayId`, `items`, `status`, `contractValue`, `participants`, `entitlements`, `fulfillments`.*

## Changes from v0.3

- **Format**: Converted from OpenAPI 3.1 combined file to JSON Schema 2020-12 single-schema file
- **Structure**: `EnergyTrade` is now a proper subclass of `Contract` via `allOf`
- **Domain schemas**: Each of the 7 sub-schemas from the v0.3 combined file is now an independent schema folder under `specification/schema/`
- **References**: Internal schemas use canonical `https://schema.beckn.io/<SchemaName>/v2.0` URIs
