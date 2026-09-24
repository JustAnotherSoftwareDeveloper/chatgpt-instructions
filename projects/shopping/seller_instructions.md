# Seller and Purchase-Channel Authority

## Purpose

This file owns seller/channel evaluation, purchase risk, return/warranty handling, seller-of-record vs fulfillment distinctions, and offer comparison when purchase-channel advice is in scope.

Load this authority when seller/channel, current offer, return/warranty, or purchase-risk advice is requested or materially affects the recommendation.

The previous detailed implementation is preserved at `archive/seller_instructions.md` and will be migrated deliberately; archived rules are not active implicitly.

---

## Initial live contract

- Distinguish seller-of-record from fulfillment party.
- Compare offers on a consistent total-price basis when possible.
- Consider return friction, warranty handling, counterfeit/gray-market risk, and seller legitimacy alongside price.
- Do not recommend bypassing normal buyer protections.
- Treat unusually cheap offers as requiring stronger verification, not as automatically better value.
- Keep seller/channel conclusions separate from product-quality conclusions.

---

## Boundary

This file owns seller/channel and offer-level purchase risk only. Product-quality evaluation belongs to the active criteria and specialized authorities; general evidence admissibility belongs to `research_sources.md`; product pricing strategy belongs to `pricing.md`.
