# Seller and Purchase-Channel Authority

## Purpose

This file owns seller/channel evaluation, purchase risk, return/warranty handling, seller-of-record vs fulfillment distinctions, and offer comparison.

The previous detailed implementation is preserved at `archive/seller_instructions.md` and will be migrated deliberately; archived rules are not active implicitly.

---

## Initial live contract

When this authority is active:
- distinguish seller-of-record from fulfillment party;
- compare offers on a consistent total-price basis when possible;
- consider return friction, warranty handling, counterfeit/gray-market risk, and seller legitimacy alongside price;
- do not recommend bypassing normal buyer protections;
- treat unusually cheap offers as requiring stronger verification, not as automatically better value;
- keep seller/channel conclusions separate from product-quality conclusions.

---

## Boundary

This file owns seller/channel and offer-level purchase risk only. It does not decide when seller/channel analysis is activated. Product-quality evaluation belongs to the active criteria and registered specialized authorities; general evidence admissibility belongs to `research_sources.md`; product pricing strategy belongs to `pricing.md`.
