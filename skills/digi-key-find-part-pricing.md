---
name: digi-key-find-part-pricing
description: Find an electronic component on DigiKey by keyword or part number and read its stock and pricing.
api: DigiKey ProductSearch API
operations: [KeywordSearch, ProductDetails, ProductPricing, PricingOptionsByQuantity]
generated: 2026-10-19
method: generated
source: openapi/digi-key-productsearch-api-products-v4-openapi.yml
---
1. Obtain an OAuth 2.0 bearer token (2-legged client credentials is enough for search); send `X-DIGIKEY-Client-Id` on every call.
2. `KeywordSearch` (POST /search/keyword) with keywords or a manufacturer part number. MyPricing is not returned here.
3. `ProductDetails` or `ProductPricing` for the chosen DigiKey/manufacturer part number to get full detail and MyPricing.
4. `PricingOptionsByQuantity` for the quantity you intend to buy.
Rules: URL-encode special characters in part numbers; on 429 wait the `Retry-After` seconds (Product Information: 120 per minute, 1000 per day). Sandbox (sandbox-api.digikey.com) always returns the example product.
