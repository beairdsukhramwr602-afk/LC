# Shopware Migration Pitfalls and Prevention

Shopware migration pitfalls usually come from treating the target store as a simple record destination instead of a connected commerce environment. Products, variants, properties, categories, sales channels, rules, content, custom fields, extensions, and integrations all shape how the migrated store behaves. When those relationships are not planned and validated, the migration can appear complete while the storefront, checkout, search, reporting, or operations still fail in practical use.

The most effective prevention strategy is to identify where the source store’s assumptions differ from Shopware’s operating model. Some problems require mapping changes. Some require target configuration. Some require extension setup, custom fields, storefront implementation, or Custom Service. The goal is not to eliminate every complexity before migration. The goal is to recognize each complexity early enough to assign the right service path, preparation work, and validation proof.

### Pitfall 1: Treating Sales Channels as a Minor Configuration Detail <a href="#pitfall-1-treating-sales-channels-as-a-minor-configuration-detail" id="pitfall-1-treating-sales-channels-as-a-minor-configuration-detail"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

Migrated products and categories may be present in Shopware, but they do not appear in the correct storefront, language, currency, domain, or customer-facing context. Teams may assume this is a data failure when the real issue is sales-channel alignment.

Shopware’s sales-channel model can affect product visibility, navigation, domains, currencies, languages, and storefront behavior. When migration planning focuses only on the data import, reviewers may miss the target context where customers will actually browse and buy.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Signal                                                         | What it may indicate                                                  |
| -------------------------------------------------------------- | --------------------------------------------------------------------- |
| Products exist in Administration but not on storefront pages.  | Missing or incorrect sales-channel visibility.                        |
| Localized storefronts show default-language content.           | Language or translation context is incomplete.                        |
| Categories appear in one channel but not another.              | Category assignment or navigation scope was not validated by channel. |
| Prices or availability differ unexpectedly across storefronts. | Currency, rule, or channel-specific configuration is not aligned.     |

#### Prevention <a href="#prevention" id="prevention"></a>

Define the target sales-channel model before migration. Identify which products, categories, languages, currencies, domains, and storefronts matter for launch. Prepare representative samples from each important channel, then validate the migrated records from the Administration and from the storefront.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

For a merchant launching Shopware with multiple regional storefronts, the migration scope should not simply say that Products and Categories will migrate. It should identify which products belong to which sales channels, which translated values are expected, which categories drive each storefront, and which URLs or redirects are critical for launch.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

Products, categories, navigation, language, currency, and storefront visibility behave correctly in every launch-relevant sales channel.

### Pitfall 2: Flattening Product Variants and Properties <a href="#pitfall-2-flattening-product-variants-and-properties" id="pitfall-2-flattening-product-variants-and-properties"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Source-store option structures are migrated into Shopware without preserving the commercial meaning of variants, properties, filters, inherited values, media, stock, and selection behavior. Customers may see duplicated products, broken options, incomplete filters, wrong images, or variants that cannot be purchased correctly.

Shopware product structures can rely on parent-child relationships, inherited values, product properties, translated labels, and category assignments. A flat import may preserve product names and SKUs while losing the relationships that make the catalog usable.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Signal                                                      | What it may indicate                                                      |
| ----------------------------------------------------------- | ------------------------------------------------------------------------- |
| Variant options appear as separate products.                | Parent-child relationship mapping is incomplete.                          |
| Filters are missing or inconsistent.                        | Properties or property groups were not mapped correctly.                  |
| Variant images, prices, or stock values are wrong.          | Inheritance or variant-specific values were not reviewed.                 |
| Product listings include duplicates or incomplete families. | Source options did not translate cleanly into Shopware product structure. |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Prepare catalog samples that include simple products, complex variants, property-heavy products, products with category assignments, products with media galleries, and products with custom fields. Validate the migrated catalog from both product detail pages and listing/filter behavior.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A fashion catalog should include sample products with size and color variants, variant-specific SKUs, variant images, category assignments, and filterable attributes. If those samples fail during Demo Migration review, the mapping should be corrected before full migration.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Variant products display as intended, inherit appropriate values, preserve purchasable options, support filtering, and remain understandable to customers and store teams.

### Pitfall 3: Underestimating Rule-Driven Commercial Logic <a href="#pitfall-3-underestimating-rule-driven-commercial-logic" id="pitfall-3-underestimating-rule-driven-commercial-logic"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Discounts, shipping availability, payment conditions, customer-group behavior, tax expectations, or checkout behavior do not match the old store because source-store rules were treated as ordinary data. In Shopware, commercial behavior may depend on rules and configuration, not just migrated records.

This pitfall is especially common when the old platform used apps, scripts, custom code, or external systems to control price adjustments, customer eligibility, shipping methods, or checkout restrictions.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Signal                                               | What it may indicate                                           |
| ---------------------------------------------------- | -------------------------------------------------------------- |
| Discounts apply to the wrong carts or fail to apply. | Promotion conditions were not rebuilt as Shopware logic.       |
| Shipping methods appear for ineligible regions.      | Shipping rules or delivery conditions are incomplete.          |
| Payment methods appear or disappear unexpectedly.    | Payment availability conditions were not mapped or configured. |
| Customer-group pricing behaves inconsistently.       | Customer segmentation or rule context is incomplete.           |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Document source-store commercial logic before migration. Separate what is migrated as data from what must be configured in Shopware. Use Demo Migration to test realistic checkout scenarios, including standard products, variant products, discounts, different customer groups, shipping regions, and payment methods.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

If the source store applies free shipping only for certain countries, customer groups, or cart values, that behavior should be captured as a rule requirement. The migrated store should then be tested with eligible and ineligible carts before launch.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Pricing, promotions, shipping, payment, and customer conditions behave correctly in representative storefront and checkout scenarios.

### Pitfall 4: Treating Shopping Experiences and SEO Content as Secondary <a href="#pitfall-4-treating-shopping-experiences-and-seo-content-as-secondary" id="pitfall-4-treating-shopping-experiences-and-seo-content-as-secondary"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

The migration preserves catalog records but loses the content and URL context that supports discovery, trust, and conversion. Product pages may exist, but landing pages, category content, CMS layouts, metadata, redirects, navigation links, or campaign destinations are missing or inconsistent.

Shopware storefront presentation may depend on Shopping Experiences, CMS content, category descriptions, media, navigation, and URL planning. If content and SEO are reviewed only after data migration, launch teams may discover gaps too late.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Signal                                                        | What it may indicate                                                      |
| ------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Important landing pages are missing or rebuilt late.          | Content migration and storefront implementation were not scoped together. |
| Product/category URLs do not match redirect expectations.     | SEO continuity was not validated before launch.                           |
| Category pages are technically present but commercially weak. | Product data moved, but merchandising context did not.                    |
| Campaign links or internal links break after migration.       | URL inventory and navigation review were incomplete.                      |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Identify high-value product URLs, category URLs, landing pages, campaign pages, CMS content, and navigation paths before migration. Decide which items should migrate, which should be rebuilt in Shopware, and which should redirect. Validate those decisions before final launch review.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

For a merchant with strong organic traffic to category pages, the preparation file should include priority category URLs, target Shopware category mapping, metadata expectations, redirect requirements, and content ownership for any Shopping Experiences that need rebuilding.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

High-value content, URLs, navigation paths, metadata, and redirects are present, rebuilt, or intentionally redirected with clear launch ownership.

### Pitfall 5: Assuming Custom Fields and Extensions Are Included by Default <a href="#pitfall-5-assuming-custom-fields-and-extensions-are-included-by-default" id="pitfall-5-assuming-custom-fields-and-extensions-are-included-by-default"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Important business context stored in custom fields, plugins, apps, external integrations, or custom code is missing after migration because it was assumed to be part of standard platform data. Teams may discover after launch that ERP identifiers, merchandising flags, loyalty fields, B2B attributes, or extension-owned records were not migrated.

Not all custom or extension-managed data belongs to the standard migration scope. Some items may require Add-ons if the requirement is supported mapping or configuration. Others may require Custom Service when unsupported records, bespoke transformation, custom fields, external-system identifiers, or custom migration logic are involved.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Signal                                                       | What it may indicate                                                    |
| ------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Critical operational fields are not visible after migration. | Custom fields were not included in scope or mapping.                    |
| Plugin behavior is expected but not configured.              | Extension setup is being confused with data migration.                  |
| External-system IDs are missing from migrated records.       | Integration identifiers were not included in migration planning.        |
| Staff cannot reproduce old workflows in Shopware.            | Source behavior depended on custom code or apps outside standard scope. |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Create an extension and custom-data inventory before migration. Identify which fields and behaviors are native Shopware targets, which are supported mapping needs, which require Add-ons, and which require Custom Service or separate implementation work. Confirm expectations during Demo Migration rather than after full migration.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

If the source store uses custom product flags to control ERP synchronization or marketplace publishing, those fields should be listed before migration with sample records and target-field expectations. If there is no standard target equivalent, the requirement should be reviewed as Custom Service or integration work.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Custom fields, extension-owned records, external identifiers, and integration-critical data are either migrated within scope, rebuilt/configured in Shopware, assigned to Custom Service, or explicitly excluded from acceptance.

### Pitfall 6: Validating Orders Without Operational Context <a href="#pitfall-6-validating-orders-without-operational-context" id="pitfall-6-validating-orders-without-operational-context"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Historical orders migrate, but support teams cannot use them effectively. Order numbers, customer relationships, line items, status labels, tax values, shipping values, payment context, refunds, discounts, or external references may be incomplete or difficult to interpret.

Order validation is not only about historical storage. It affects customer service, accounting review, operational lookup, reporting continuity, and integration reconciliation.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Signal                                                   | What it may indicate                                              |
| -------------------------------------------------------- | ----------------------------------------------------------------- |
| Orders exist but staff cannot interpret statuses.        | Source order states were not mapped into usable Shopware context. |
| Line items lack product or variant clarity.              | Product/order relationship mapping is incomplete.                 |
| Refunds, discounts, or shipping adjustments are unclear. | Financial context was not validated with edge-case orders.        |
| ERP or accounting references are missing.                | External identifiers were not preserved within scope.             |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Validate representative historical orders, not only recent simple orders. Include orders with discounts, tax differences, shipping adjustments, refunds, guest checkout, variant products, custom statuses, and external references where relevant. Confirm what historical order data is intended for lookup versus active operational processing.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A merchant with frequent customer-service inquiries about older orders should include sample records from different order statuses and financial conditions. The validation plan should confirm that support agents can identify the customer, items, totals, fulfillment context, and any important external references.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Historical orders are understandable and searchable for the business purposes they are expected to support after migration.

### Pitfall 7: Skipping Indexing, Search, and Performance-Aware Review <a href="#pitfall-7-skipping-indexing-search-and-performance-aware-review" id="pitfall-7-skipping-indexing-search-and-performance-aware-review"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The migrated store appears correct in the Administration, but storefront search, filters, product listings, or customer-facing performance do not reflect the imported data correctly. Teams may mistake this for missing data when the issue is indexing, cache, search configuration, or storefront implementation.

Shopware’s architecture uses indexing and asynchronous processing patterns, so validation should include customer-facing discovery behavior, not only backend record review.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Signal                                                 | What it may indicate                                                 |
| ------------------------------------------------------ | -------------------------------------------------------------------- |
| Newly imported products do not appear in search.       | Indexing or search configuration needs review.                       |
| Filters return incomplete results.                     | Properties, category assignments, or indexing are incomplete.        |
| Storefront results differ from Administration records. | Sales-channel, cache, or storefront consumption needs validation.    |
| Large catalog pages feel unstable after import.        | Performance, indexing, or storefront implementation needs attention. |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Include search terms, filters, key categories, and product listing pages in validation. Confirm indexing and cache-related tasks with the implementation team. If the target uses a custom storefront or external search layer, validate the integration path as part of launch readiness.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A large catalog should be tested with priority search terms, category filters, property filters, and high-value products after migration and indexing. If results are incomplete, the issue should be assigned to mapping, indexing, search configuration, or storefront implementation.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Customers can find migrated products through expected search, filtering, category, and storefront discovery paths.

### Pitfall 8: Treating Demo Migration as a Visual Preview Only <a href="#pitfall-8-treating-demo-migration-as-a-visual-preview-only" id="pitfall-8-treating-demo-migration-as-a-visual-preview-only"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Demo Migration is reviewed only for obvious visual defects instead of being used to test the migration assumptions that will control the full dataset. Teams approve the demo too quickly, then encounter structural problems during full migration or launch review.

For Shopware, Demo Migration should test representative complexity: variants, properties, categories, translations, sales channels, customer groups, orders, custom fields, URLs, content, and extension-dependent records where relevant.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Signal                                                       | What it may indicate                                        |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
| Demo review focuses only on homepage or a few products.      | The sample does not test migration risk.                    |
| Edge-case products are excluded from the sample.             | Variant, property, or custom-field issues may appear later. |
| Orders are not reviewed with financial or status complexity. | Historical records may be unusable after full migration.    |
| Issues are noted but not converted into acceptance criteria. | Full migration may repeat unresolved demo findings.         |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Design Demo Migration samples around risk, not convenience. Include records that represent the real complexity of the source store and the intended Shopware operating model. Convert findings into mapping changes, scope decisions, Add-ons, Custom Service review, or validation requirements before full migration.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

If a merchant has multilingual products, complex variants, custom product flags, and high-value SEO pages, the demo sample should include all four patterns. Approving a demo that includes only ordinary products creates a false sense of readiness.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Demo Migration proves the representative Shopware mapping assumptions before full migration proceeds.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopware migration pitfalls are preventable when teams validate relationships, not just records. Sales channels, products, variants, properties, rules, content, custom fields, extensions, search, orders, and integrations must be reviewed as connected parts of the target operating model.

The safest approach is to identify risk patterns before migration, test them during Demo Migration, assign ownership for target configuration or custom requirements, and use full migration review to prove the store is usable. When each pitfall has a warning signal, prevention action, recommendation, and pass condition, the Shopware migration becomes easier to control and safer to launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the most common Shopware migration pitfall?**

One common pitfall is treating the migration as a simple product and order transfer while underestimating sales channels, variants, properties, rules, content, custom fields, and extensions.

**Why do Shopware variants need special attention?**

Variants may depend on parent-child relationships, inherited values, properties, images, prices, and stock behavior. If those relationships are flattened or misread, products can become difficult to browse, filter, or purchase.

**Are custom fields automatically included in a Shopware migration?**

Not always. Custom fields and extension-owned records should be reviewed during scope planning. Some mapping needs may fit Add-ons, while unsupported records or bespoke transformations may require Custom Service.

**How should Demo Migration be used for Shopware?**

Demo Migration should test representative risk patterns, including variants, properties, categories, sales channels, translations, orders, custom fields, URLs, content, and extension-dependent records where relevant.

**How can teams avoid confusing migration issues with configuration issues?**

Each issue should be assigned to the correct owner: migration mapping, Shopware target configuration, extension setup, storefront implementation, external integration, or out-of-scope custom work.
