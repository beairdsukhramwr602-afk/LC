# WooCommerce Validation Priorities

WooCommerce validation must prove more than record transfer. Because WooCommerce commerce data operates inside WordPress, a migration is successful only when products remain purchasable, variations behave correctly, customer and order history remain readable, checkout-related context is preserved where applicable, plugin-owned fields are classified correctly, and store URLs, media, SEO, and content-commerce paths still support the customer journey.

Validation should therefore combine record checks with behavior checks. A WooCommerce Demo Migration or Full Migration should be reviewed through representative samples that expose the real store structure: simple products, variable products, product add-ons, subscriptions, bookings, memberships, coupons, orders, guest customers, registered users, CMS Pages, Blog Posts, redirects, SEO metadata, custom fields, and integration references.

### What WooCommerce Validation Should Prove <a href="#what-woocommerce-validation-should-prove" id="what-woocommerce-validation-should-prove"></a>

WooCommerce validation should confirm that migrated records still support the store operations they represented in the Source Platform. A product that exists but has broken variation choices is not validated. An order that exists but no longer shows tax, shipping, payment, coupon, refund, or metadata context clearly is not validated. A customer account that exists but loses membership, wholesale, or subscription meaning may require deeper review.

| Validation layer       | What should be proven                                                                                              | Why it matters                                                         |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Product structure      | Products, variations, attributes, categories, tags, brands, images, stock, and visibility remain usable            | Customers must still find and buy the intended items                   |
| Order history          | Statuses, totals, line items, tax, shipping, payment labels, notes, refunds, coupons, and metadata remain readable | Staff need usable history for service, reporting, and reconciliation   |
| Customer/account data  | Registered users, guest customers, billing/shipping details, roles, and account-related fields retain meaning      | Customer continuity depends on more than email addresses               |
| Checkout context       | Checkout fields, payment labels, shipping labels, tax values, and order metadata are interpreted correctly         | Historical data should not be mistaken for live checkout configuration |
| WordPress site data    | CMS Pages, Blog Posts, media, menus, URLs, redirects, SEO, and builder content remain connected to commerce        | Store discovery and trust often depend on content-commerce continuity  |
| Plugin and custom data | Extension-owned records, custom fields, custom tables, and external IDs are classified and checked                 | WooCommerce behavior often depends on plugin-specific storage          |
| Service-scope outputs  | Add-ons and Custom Service deliverables are validated against agreed expectations                                  | Non-standard scope needs explicit acceptance criteria                  |

### Validate Product and Variation Behavior <a href="#validate-product-and-variation-behavior" id="validate-product-and-variation-behavior"></a>

WooCommerce product validation should start with customer-facing purchasability, not only product counts. Variable products require especially careful review because parent product records, attributes, and child variations must work together.

| Product sample                                               | Validation priority                                                                                             | Pass condition                                                                                             |
| ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Simple product                                               | Title, SKU, price, stock, images, category, visibility, product URL, and add-to-cart behavior                   | Product is visible where expected and can be purchased or hidden according to business rules               |
| Variable product                                             | Parent product, variation attributes, child SKUs, prices, stock, images, default selections, and purchasability | Customers can select valid combinations and each variation reflects the correct commercial meaning         |
| Product with add-ons or personalization                      | Add-on fields, option labels, price impact, order-line display, and fulfillment notes                           | Add-on information is either migrated, rebuilt, excluded, or routed to Custom Service review intentionally |
| Subscription, booking, membership, bundle, or composite item | Extension ownership, product display, historical order meaning, and post-migration configuration needs          | Store team understands which data is migrated and which behavior depends on target extension setup         |
| Product with brand or custom taxonomy                        | Brand, taxonomy placement, filter use, archive pages, and SEO-sensitive paths                                   | Product discovery remains consistent with the target catalog plan                                          |

A useful validation sample should include the most complex items, not just the most common ones. Stores should include products with variation-level stock, sale pricing, gallery images, special tax or shipping behavior, category overlap, custom attributes, and extension-controlled purchase logic.

### Validate Attributes, Categories, Tags, and Catalog Discovery <a href="#validate-attributes-categories-tags-and-catalog-discovery" id="validate-attributes-categories-tags-and-catalog-discovery"></a>

WooCommerce catalog discovery depends on the relationship between product taxonomies, attributes, URLs, themes, search, filters, and SEO. Validation should confirm that the catalog remains navigable and commercially understandable.

| Discovery element  | What to validate                                                                                                  | Common failure signal                                                        |
| ------------------ | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Product categories | Hierarchy, parent-child relationships, category names, slugs, product assignments, menu usage, and SEO pages      | Products exist but customers cannot browse the catalog naturally             |
| Tags               | Tag cleanup, campaign tags, duplicate terms, and customer-facing usefulness                                       | Source tags clutter the target store or duplicate category meaning           |
| Brands             | Brand taxonomy, brand attribute, brand plugin behavior, archive pages, and filters                                | Brand data appears as plain text but no longer supports discovery            |
| Attributes         | Global attributes, local attributes, variation-enabled attributes, filterable attributes, and display-only values | Product options work, but filters or specification display are wrong         |
| Search and filters | Theme, block, plugin, or search-extension behavior                                                                | Migrated values exist but storefront filtering does not expose them properly |

Validation should distinguish between data transfer and storefront behavior. A taxonomy term can exist in WordPress while still failing to appear in navigation, filters, breadcrumbs, or search results because the target theme, block layout, or extension has not been configured.

### Validate Customers, Accounts, and User Meaning <a href="#validate-customers-accounts-and-user-meaning" id="validate-customers-accounts-and-user-meaning"></a>

WooCommerce customer data can involve WordPress users, guest customers, billing and shipping details, account history, roles, memberships, wholesale groups, subscriptions, loyalty context, and external identifiers. Validation should clarify what each customer record is expected to do after migration.

| Customer/account pattern            | What to validate                                                                                     | Pass condition                                                                     |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Registered customer                 | User account, email, username, display name, billing/shipping addresses, order association, and role | Customer can be identified and tied to historical order context                    |
| Guest customer                      | Order-level billing/shipping details and email continuity                                            | Guest history remains readable even without a registered account                   |
| Wholesale or B2B customer           | Role, group, pricing context, tax status, approval status, and plugin ownership                      | Business-customer meaning is preserved, rebuilt, or intentionally excluded         |
| Subscription or membership customer | Plugin records, access state, renewal context, and historical order links                            | Active business logic is not assumed to migrate as ordinary customer data          |
| External-system customer            | CRM, ERP, loyalty, marketplace, or support-system identifiers                                        | External references remain usable or are flagged for post-migration reconciliation |

Customer validation should not treat email count as sufficient. Account meaning is often stored in roles, metadata, plugin tables, memberships, subscriptions, or external systems that need separate handling.

### Validate Orders, HPOS Context, and Historical Commerce Records <a href="#validate-orders-hpos-context-and-historical-commerce-records" id="validate-orders-hpos-context-and-historical-commerce-records"></a>

WooCommerce order validation must separate historical record readability from live checkout behavior. Migrated orders should preserve enough detail for staff to understand what happened, but payment gateways, shipping calculators, tax engines, fraud tools, and fulfillment workflows usually depend on target configuration or connected systems.

| Order element               | What to validate                                                                           | Why it matters                                                                                           |
| --------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Order status                | Status mapping and operational meaning                                                     | Staff need to distinguish completed, pending, refunded, failed, cancelled, and custom statuses correctly |
| Line items                  | Product names, SKUs, variation details, quantities, prices, discounts, and product links   | Order history should show what was actually purchased                                                    |
| Totals                      | Subtotal, discount, tax, shipping, fees, refunds, and grand total                          | Financial history needs readable context even when reporting is handled elsewhere                        |
| Shipping and payment labels | Method names, transaction references, and gateway labels where migrated                    | Staff need historical context without assuming live gateway continuity                                   |
| Coupons and discounts       | Code, amount, discount type, and order-level application                                   | Promotions should remain understandable in past orders                                                   |
| Notes and metadata          | Customer notes, admin notes, fulfillment details, custom checkout fields, and external IDs | Operational context often sits outside standard order columns                                            |
| HPOS/order storage          | Order visibility and compatibility in the target WooCommerce setup                         | Extension compatibility and order access should be checked before acceptance                             |

Validation should include orders with refunds, coupons, guest checkout, registered customers, custom statuses, variation line items, shipping/tax differences, and extension-owned metadata.

### Validate Checkout Fields, Payments, Shipping, Taxes, and Coupons <a href="#validate-checkout-fields-payments-shipping-taxes-and-coupons" id="validate-checkout-fields-payments-shipping-taxes-and-coupons"></a>

WooCommerce migration should not imply that live checkout rules are automatically recreated. Validation should confirm which elements are historical data, which are target configuration, and which are plugin or Custom Service scope.

| Commerce function | Validation focus                                                                   | Acceptance question                                                                 |
| ----------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Checkout fields   | Historical field values, field labels, required fields, and plugin ownership       | Are migrated field values readable where orders need them?                          |
| Payment data      | Gateway labels, transaction references, paid status, and refund context            | Is historical payment context understandable without assuming gateway recreation?   |
| Shipping data     | Shipping method labels, zones, rates, tracking fields, and fulfillment metadata    | Are historical shipping records readable, and are live rates configured separately? |
| Tax data          | Tax amounts, labels, rates, exemptions, and tax-inclusive or tax-exclusive meaning | Do migrated orders retain tax context for service and review?                       |
| Coupons           | Coupon code, usage, discount amount, validity, and historical application          | Can staff understand prior discounts and test target coupon behavior separately?    |

Live checkout validation should be handled on the configured Target Platform after migration setup. Historical checkout data and live checkout configuration are related, but they are not the same validation task.

### Validate WordPress Content, Media, URLs, and SEO Continuity <a href="#validate-wordpress-content-media-urls-and-seo-continuity" id="validate-wordpress-content-media-urls-and-seo-continuity"></a>

WooCommerce storefront quality often depends on WordPress content and presentation. Product pages may link to CMS Pages, Blog Posts may support buying decisions, media may be reused across products and pages, and SEO paths may depend on permalinks, redirects, canonical values, and plugin metadata.

| WordPress-connected layer | What to validate                                                                  | Pass condition                                                                |
| ------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| CMS Pages                 | Store policy pages, landing pages, buying guides, and product-linked content      | Important content remains accessible and linked to commerce journeys          |
| Blog Posts                | Buying education, SEO articles, internal links, images, and categories            | Blog content remains readable and does not break product discovery paths      |
| Media                     | Product images, galleries, featured images, alt text, file references, and embeds | Images appear correctly and are not disconnected from products or content     |
| Permalinks and slugs      | Product URLs, category URLs, page URLs, redirects, and canonical paths            | Important customer and search paths resolve intentionally                     |
| SEO metadata              | Titles, descriptions, canonical values, schema-related plugin data, and redirects | SEO-sensitive values are preserved, rebuilt, or flagged for target-side setup |
| Themes and builders       | Product templates, blocks, shortcodes, menus, widgets, and layout dependencies    | Migrated content is not accepted until visible presentation is checked        |

A WooCommerce validation pass should include both back-office data checks and customer-facing walkthroughs of product pages, category pages, cart paths, checkout paths, policy pages, and high-value landing pages.

### Validate Plugins, Custom Fields, Custom Tables, and Integrations <a href="#validate-plugins-custom-fields-custom-tables-and-integrations" id="validate-plugins-custom-fields-custom-tables-and-integrations"></a>

WooCommerce stores often depend on extensions and custom code. Some plugin data is ordinary metadata, some sits in custom tables, and some belongs to external systems. Validation must classify these records before deciding whether they are standard scope, Add-ons scope, Custom Service scope, or post-migration configuration.

| Dependency type                  | Validation priority                                                                     | Handling signal                                                               |
| -------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product add-ons                  | Field labels, prices, input values, order-line display, and fulfillment notes           | Often needs extension-aware review or Custom Service discussion               |
| Subscriptions                    | Subscription records, renewal logic, payment-token dependency, and customer association | Active subscription behavior usually needs target plugin and gateway planning |
| Bookings and appointments        | Booking date, availability, resource, staff, and calendar logic                         | Historical booking data and live booking rules should be separated            |
| Memberships or wholesale pricing | Roles, groups, access rules, pricing levels, tax treatment, and approval states         | Group/account meaning may require plugin-aware mapping                        |
| Custom fields                    | Product/order/customer field names, values, display locations, and business purpose     | Decide whether field data is standard, Add-ons, Custom Service, or excluded   |
| Custom tables                    | Table ownership, relationships, keys, and target plugin compatibility                   | Usually requires Custom Service review before acceptance                      |
| External systems                 | ERP, PIM, CRM, WMS, marketplace, payment, tax, shipping, or automation references       | Validate IDs and context, not only visible storefront data                    |

If a field or table affects purchasing, fulfillment, reporting, access, pricing, subscriptions, bookings, or integration reconciliation, it should not be accepted as a low-priority cosmetic detail.

### Validate Add-ons and Custom Service Outputs <a href="#validate-add-ons-and-custom-service-outputs" id="validate-add-ons-and-custom-service-outputs"></a>

Add-ons and Custom Service outputs should be validated against the exact agreed scope. Add-ons can extend migration handling for defined cases, but they do not replace Custom Service when the store depends on custom logic, unsupported extension structures, bespoke tables, external workflows, or target-side development.

| Scope type          | Validation focus                                                                            | Acceptance standard                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Standard Add-ons    | Defined additional fields, filters, mapping, or configuration support                       | Output matches the purchased Add-on scope and is visible in the agreed location               |
| Tailored Add-ons    | Store-specific handling agreed before migration                                             | Edge cases are checked against the documented expectation, not assumed broadly                |
| Custom Add-ons      | Non-standard but bounded extension of migration handling                                    | Validation confirms the custom Add-on output without expanding it into general Custom Service |
| Custom Service      | Bespoke data handling, custom tables, extension-owned structures, or special workflow logic | Output is validated against agreed rules, sample records, and acceptance criteria             |
| Accepted exclusions | Data or behavior intentionally not migrated                                                 | Exclusions remain documented so missing behavior is not treated as a migration defect         |

Validation should also confirm that Add-ons and Custom Service are not mixed together in review language. A migrated custom field does not mean all plugin behavior was recreated.

### Demo Migration and Full Migration Validation Priorities <a href="#demo-migration-and-full-migration-validation-priorities" id="demo-migration-and-full-migration-validation-priorities"></a>

A Demo Migration should prove whether the WooCommerce migration approach can preserve representative store behavior. A Full Migration should confirm complete scope, remaining exceptions, and customer-facing readiness.

| Migration stage           | Validation priority                                                                        | Sample requirement                                                                                                                   |
| ------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| Demo Migration            | Test the hardest representative cases before committing to scale                           | Include variable products, plugin-driven products, guest and registered orders, refunds, coupons, media, URLs, and custom fields     |
| Pre-Full Migration review | Confirm unresolved questions, service scope, Add-ons, Custom Service needs, and exclusions | Do not proceed with unknown product/checkout/order/plugin behavior unresolved                                                        |
| Full Migration            | Confirm full record scope and customer-facing continuity                                   | Review counts, samples, storefront paths, admin visibility, and operational reports                                                  |
| Go-live acceptance        | Confirm target configuration and live business readiness                                   | Payment, shipping, tax, stock, extensions, email, analytics, and external systems should be checked separately from migrated history |

The right validation sample should intentionally include difficult records. If a Demo Migration only includes straightforward simple products and ordinary orders, it does not prove much about WooCommerce migration readiness.

### Additional Migration Options and WooCommerce Revalidation <a href="#additional-migration-options-and-woocommerce-revalidation" id="additional-migration-options-and-woocommerce-revalidation"></a>

Additional Migration Options should trigger renewed validation for changed WooCommerce records. Follow-up migration activity can add new products, customers, orders, CMS Pages, Blog Posts, or other eligible records, and those new records may consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action for the same migration path.

| Follow-up activity          | Revalidation priority                                                                              | Why it matters                                                                            |
| --------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| New products or variations  | Product type, attributes, stock, images, category, URL, and purchasability                         | New catalog data may introduce structures not present in the first validation sample      |
| New customers or orders     | Account links, order status, checkout fields, coupons, tax, shipping, payment labels, and metadata | New live activity may carry different operational context                                 |
| New CMS Pages or Blog Posts | Content formatting, media, internal links, redirects, and SEO metadata                             | Commerce-related content may affect launch quality                                        |
| New plugin or custom data   | Field ownership, custom tables, extension dependencies, and external IDs                           | Follow-up data can expose previously unseen plugin behavior                               |
| Repeated migration action   | Duplicate handling, changed records, and scope boundaries                                          | Revalidation should confirm what changed without double-counting already licensed records |

Follow-up validation should focus on the delta: what changed, what is newly migrated, what was updated, and which previously accepted assumptions no longer hold.

### WooCommerce Validation Priority Matrix <a href="#woocommerce-validation-priority-matrix" id="woocommerce-validation-priority-matrix"></a>

| Priority area           | Low-risk signal                                         | Higher-risk signal                                                                                    | Validation action                                                               |
| ----------------------- | ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Products                | Mostly simple products with basic categories and images | Variable, bundled, composite, subscription, booking, or add-on products                               | Validate purchasability, product type, variation logic, and extension ownership |
| Orders                  | Ordinary statuses and limited metadata                  | Refunds, coupons, custom statuses, checkout fields, HPOS, external IDs, or plugin data                | Validate historical readability and storage compatibility                       |
| Customers               | Basic registered and guest customers                    | Memberships, wholesale groups, subscriptions, loyalty, or external account IDs                        | Validate account meaning and plugin-owned records                               |
| Checkout                | Standard historical labels                              | Custom fields, payment tokens, tax engines, shipping integrations, or fulfillment automation          | Separate migrated history from live target configuration                        |
| Content and URLs        | Simple product/page paths                               | SEO-critical redirects, builder content, internal links, product-linked content, or custom permalinks | Validate customer-facing paths and search visibility                            |
| Plugins and custom data | Limited display-only metadata                           | Custom tables, custom workflows, subscription/booking/membership logic, or external systems           | Confirm Add-ons, Custom Service, or exclusion handling                          |
| Follow-up migration     | Small amount of simple new data                         | New complex products, orders, or plugin fields after initial validation                               | Revalidate changed records and Entity Points impact                             |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WooCommerce validation should prove that migrated data still works as commerce data inside WordPress. The strongest validation process checks record presence, storefront behavior, admin readability, extension ownership, URL continuity, order history, customer meaning, and service-scope expectations together.

A WooCommerce migration should be accepted only after representative samples confirm products remain purchasable, orders remain understandable, customers remain identifiable, content-commerce paths remain usable, and plugin or custom data is either migrated, rebuilt, excluded, or escalated through the appropriate service path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after a WooCommerce Demo Migration?**

Start with the records most likely to expose structural problems: variable products, plugin-driven products, orders with refunds or custom fields, guest and registered customers, coupons, media, category paths, redirects, and SEO-sensitive URLs.

**Is product count enough to validate WooCommerce migration quality?**

No. Product count only confirms volume. WooCommerce validation must also confirm variation behavior, attributes, images, categories, stock, visibility, product URLs, purchasability, and extension-owned product data.

**Should WooCommerce orders be validated against live checkout behavior?**

Historical orders and live checkout configuration should be reviewed separately. Migrated orders should preserve readable historical context, while live payment, shipping, tax, and checkout rules depend on target configuration and extensions.

**Why do plugins matter during WooCommerce validation?**

Plugins can control product add-ons, subscriptions, bookings, memberships, wholesale pricing, checkout fields, custom tables, and external integrations. If plugin-owned data is not classified, validation may miss business-critical behavior.

**Do Additional Migration Options require another validation pass?**

Yes. Follow-up migration activity should be revalidated for changed products, customers, orders, CMS Pages, Blog Posts, custom fields, plugin data, URLs, and Entity Points impact.
