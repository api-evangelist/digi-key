---
name: digi-key-quote-and-order
description: Build a DigiKey quote, place an order and track its status.
api: DigiKey Quote API, Ordering API V3, OrderStatus
operations: [CreateQuote, AddProductsToQuote, GetQuote, Order, SearchOrders, RetrieveSalesOrder]
generated: 2026-10-19
method: generated
source: openapi/
---
1. Three-legged OAuth 2.0 (authorization code) is required for customer-account operations; send `X-DIGIKEY-Account-ID` where the spec asks for it.
2. `CreateQuote`, then `AddProductsToQuote`, then `GetQuote` to review.
3. `Order` (Ordering V3) places the order. No idempotency key is documented and no cancel operation is published: never retry a timed-out `Order` blindly — check `SearchOrders` first.
4. `RetrieveSalesOrder` to follow the sales order.
Rate limits: Ordering and Quoting are 10 per minute.
