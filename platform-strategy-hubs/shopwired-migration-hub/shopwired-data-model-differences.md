# ShopWired Data Model Differences

Migrating to ShopWired is not only a matter of moving Products, Customers, Orders, Categories, Reviews, Coupons, and CMS records into a new administration area. ShopWired has a specific commerce structure around products, categories, brands, variations, choices, extras, stock, customer identity, trade features, checkout configuration, VAT and sales tax settings, delivery rules, apps, API behavior, and theme-driven storefront presentation. A good migration plan must translate source data into that structure without losing the business meaning behind the records.

The central question is simple: when a source record lands in ShopWired, will the merchant still understand what it means and will the store still use it correctly? A product option that was previously a simple label may need to become a ShopWired variation, choice, extra, bundle, personalization field, or app-supported behavior. A customer segment may become a customer record, newsletter subscriber, trade customer, pricing group, or custom field. A historical order may be readable for service purposes, but it will not automatically configure checkout, delivery, payment, VAT, sales tax, or B2B behavior for future transactions.

ShopWired works best when migration planning separates record transfer from operational reconstruction. Data should be reviewed by what it is expected to do after launch: drive catalog browsing, control purchasable combinations, preserve customer history, support trade accounts, explain historical orders, maintain search visibility, connect external systems, or support ongoing merchandising.

### ShopWired Data Translation Priorities <a href="#shopwired-data-translation-priorities" id="shopwired-data-translation-priorities"></a>

ShopWired data-model planning should begin with the areas that can change business meaning most directly: product configuration, customer identity, B2B behavior, order interpretation, storefront discovery, and external-system dependencies. These areas determine whether the migrated store is merely populated or genuinely usable.

| Source-store area                  | ShopWired interpretation                                                                                                  | Migration planning question                                                            |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Product variants and options       | Variations, choices, extras, bundles, text/file inputs, or app behavior                                                   | Does the source option affect SKU, price, stock, delivery, tax, or only presentation?  |
| Category and brand structure       | Product discovery, navigation, filtering, SEO, and merchandising logic                                                    | Can customers still find priority products through the expected routes?                |
| Customer records                   | Email-based customer identity, account state, order history, notes, custom fields, and trade separation                   | Do duplicate, guest, B2B, and registered customer records retain the right meaning?    |
| Customer groups and trade accounts | B2B visibility, pricing, account behavior, and operational rules                                                          | Which rules are data, which are ShopWired configuration, and which need custom review? |
| Historical orders                  | Customer history, payment and delivery labels, tax values, order notes, fulfillment context, and external references      | Are historical orders useful for service and reporting after migration?                |
| Content and SEO assets             | Pages, landing pages, blog posts, menus, redirects, metadata, and theme-controlled display                                | Which content affects search, trust, conversion, or B2B onboarding?                    |
| Apps and integrations              | External data ownership, API/webhook behavior, stock feeds, accounting, fulfillment, email, marketplace, or CRM workflows | Which connected systems must be reconfigured, mapped, rebuilt, or excluded?            |

This translation view prevents a common migration mistake: assuming that matching field names are enough. Field similarity does not guarantee operational similarity. For ShopWired, meaning depends on how the record participates in product selection, customer recognition, B2B selling, checkout, fulfillment, tax calculation, and storefront presentation.

### Products, Categories, Brands, and Discovery Data <a href="#products-categories-brands-and-discovery-data" id="products-categories-brands-and-discovery-data"></a>

Products in ShopWired should be planned as merchandising records, not isolated database rows. A migrated product needs a name, description, images, pricing, SKU-related information, stock handling, category placement, brand relationship, visibility, product search relevance, SEO treatment, and customer-facing presentation. When the source store contains a flat catalog, the mapping may be straightforward. When the source store contains complex options, configurators, customer-specific visibility, or app-controlled merchandising, the product model needs closer review.

Categories and brands also carry more than administrative classification. They can define navigation, landing-page value, filter behavior, product grouping, and customer expectations. A source store may use categories as SEO landing pages, brand pages as trust signals, product tags as filters, or manually curated collections as merchandising zones. These structures should not be treated as interchangeable without checking how they will appear and behave in ShopWired.

| Data area                  | What may change in ShopWired                                                                                                      | Quality check                                                                        |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Product identity           | A product may keep its commercial identity while changing option structure, URL behavior, category placement, or display template | Confirm that priority products are recognizable in admin and storefront views        |
| Categories                 | Deep source trees may need simpler navigation, revised parent-child relationships, or selective landing-page treatment            | Test high-traffic category journeys and important product discovery paths            |
| Brands                     | Brand data may become a discovery, SEO, or trust element rather than a simple product attribute                                   | Confirm that brand-led browsing still works for priority manufacturers or labels     |
| Filters and specifications | Source attributes may need to become filters, product fields, custom fields, descriptions, or app behavior                        | Validate products that customers compare by technical specification or compatibility |
| Images and media           | Source image roles may not map cleanly to product, variation, theme, or page presentation                                         | Check main image, gallery order, alt context, and variant-image expectations         |

The most important question is not whether products migrated, but whether product data remains commercially intelligible. Merchants should be able to answer: what is being sold, how customers choose it, how stock and price are controlled, where the product appears, and whether search or navigation still leads to the right buying path.

### Variations, Choices, Extras, and Product Configuration Meaning <a href="#variations-choices-extras-and-product-configuration-meaning" id="variations-choices-extras-and-product-configuration-meaning"></a>

Product configuration is one of the most important ShopWired data-model differences. Many source platforms use a single concept such as variant, option, modifier, add-on, attribute, personalization field, or bundle to cover several different behaviors. ShopWired distinguishes these behaviors more deliberately. A source selection may need to become a variation when it creates a required product combination with attributes such as SKU, price, stock, weight, image, GTIN, MPN, or VAT treatment. A different source selection may work better as a choice, extra, custom text field, customer-submitted file, bundle relationship, or app-supported behavior.

That distinction matters because option behavior affects migration scope. A color selection that changes the SKU and stock quantity is not the same as a gift-wrap checkbox. A custom engraving field is not the same as a size variation. A bundle that reduces inventory across multiple items is not the same as a single product with a descriptive option. If these meanings are flattened, the store may look populated but behave incorrectly.

| Source behavior                                                                     | Likely ShopWired planning route                                          | Why it matters                                                                             |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| Required selection that changes SKU, price, image, stock, weight, GTIN, MPN, or VAT | Variation review                                                         | These fields can affect fulfillment, reporting, tax, and customer choice accuracy          |
| Optional paid add-on or upgrade                                                     | Choice, extra, app feature, or configured behavior review                | The add-on must appear correctly in basket, order history, and operational handling        |
| Personalization text or customer-submitted file                                     | Text/file input or app-supported handling                                | Customer-provided information must remain visible where teams process orders               |
| Product bundle or kit                                                               | Bundle feature, app behavior, or Custom Service review                   | Inventory and fulfillment may depend on relationships between products                     |
| Subscription, pre-order, or quote-related product                                   | App/configuration and migration scope review                             | Purchase timing, account view, and order interpretation may involve more than catalog data |
| Source configurator with conditional logic                                          | Custom Service review where standard structures cannot express the logic | The source behavior may be application logic, not ordinary product data                    |

Demo Migration samples should include the most complex product types, not only the cleanest products. The best sample set includes products with multiple variations, optional extras, custom fields, bundles, B2B pricing relevance, special VAT treatment, stock differences, and important images. That sample set reveals whether product meaning survives the translation into ShopWired.

### Customer, Account, and Marketing Data <a href="#customer-account-and-marketing-data" id="customer-account-and-marketing-data"></a>

Customer data in ShopWired is strongly tied to email identity, account state, order history, and customer-facing account pages. This changes how duplicate customers, guest orders, registered accounts, newsletter subscribers, trade customers, and custom customer fields should be reviewed. If two source customer records share operational identity but use different emails, they may not behave as one customer after migration. If a guest checkout record later becomes an account, order visibility depends on how that history is assigned.

A customer record should be assessed by what the business needs it to support: service lookup, login, order history access, trade pricing, marketing consent, internal notes, custom-field visibility, or segmentation. Some of these needs can be migrated as data. Others require target configuration, app setup, customer communication, or Custom Service review.

| Customer-data question                                       | Why it matters in ShopWired                                                     | Review action                                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Are duplicate customers separated by email address?          | Email identity can split order history and account recognition                  | Identify duplicate patterns before migration and decide whether cleanup is needed      |
| Are guest and registered accounts mixed in the source store? | Customer type can affect account expectations and order visibility              | Sample registered, guest, and post-order account scenarios                             |
| Are newsletter preferences important?                        | Marketing consent and subscriber handling can affect post-launch communications | Separate customer records from newsletter or marketing status where needed             |
| Are trade customers managed separately?                      | B2B account behavior may not be ordinary customer segmentation                  | Map trade records, pricing implications, approval status, and account rules separately |
| Are customer custom fields used operationally?               | Custom values may support service, trade review, compliance, or segmentation    | Decide whether fields are standard data, Add-on scope, or Custom Service scope         |

Customer migration quality is not proven by customer counts alone. It is proven when real customer examples can be found, identified, associated with the correct order history, and interpreted by the teams that will use them after launch.

### B2B, Trade, Quote, and Pricing Data <a href="#b2b-trade-quote-and-pricing-data" id="b2b-trade-quote-and-pricing-data"></a>

ShopWired can support trade and B2B selling, but B2B migration should not be treated as ordinary customer migration. Trade accounts, trade-only products or categories, pricing bands, individual trade pricing, global discounts, quotes, account terms, purchase-order expectations, VAT treatment, delivery rules, and customer-specific visibility may all carry commercial logic.

The key data-model difference is that B2B meaning often sits between data and configuration. A source platform may store a customer group as a label, but the business may use that label to control price, access, payment method, delivery rule, tax treatment, or quoting workflow. In ShopWired, those outcomes may require trade settings, app setup, theme behavior, product visibility decisions, or Custom Service review.

| B2B source element                      | Migration meaning                                                             | Scope implication                                                    |
| --------------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Trade customer account                  | Customer identity plus account-specific commercial treatment                  | Review separately from ordinary customers                            |
| Customer group or pricing tier          | May affect product price, visibility, discount, payment, or delivery behavior | Determine whether it is data, configuration, or custom logic         |
| Quote history                           | Commercial negotiation record, not just an order-like record                  | Validate fields, statuses, notes, and follow-up process expectations |
| Trade-only category or product          | Access-control and merchandising rule                                         | Confirm visibility behavior and storefront testing route             |
| Customer-specific price                 | Pricing exception with operational impact                                     | Escalate if standard structures cannot represent the rule safely     |
| Purchase-order or account-term behavior | Checkout/payment workflow, not just historical label                          | Separate past-order context from live checkout setup                 |

A retail-only migration sample is not enough for a trade seller. B2B samples should include ordinary retail customers, approved trade customers, customers with special pricing, quote-related records, trade-only products, and historical orders that show how the account relationship actually worked.

### Orders, Order Statuses, Quotes, and Transaction Context <a href="#orders-order-statuses-quotes-and-transaction-context" id="orders-order-statuses-quotes-and-transaction-context"></a>

Historical orders must remain understandable after migration. In ShopWired, order meaning may involve customer assignment, product lines, option selections, discounts, vouchers, delivery labels, payment labels, tax values, VAT status, refunds, returns, notes, fulfillment state, quote history, subscription context, and external-system references.

A migrated order does not automatically reproduce live checkout behavior. It preserves past commercial context where supported. New orders depend on ShopWired configuration for checkout, payment gateways, delivery zones and rates, VAT or sales tax, customer account behavior, trade settings, and apps. This distinction should be clear in planning, because merchants often judge migration success by whether old orders are useful for customer service, reporting, reconciliation, and compliance.

| Order-related data           | What to preserve                                                          | What not to assume                                                            |
| ---------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Customer assignment          | Billing email, customer record link, order history visibility             | That all duplicate customer histories will merge automatically                |
| Product lines and options    | Purchased item names, SKUs, selected options, quantities, prices          | That source configurator logic will remain active for future purchases        |
| Payment and delivery labels  | Historical context for service and reconciliation                         | That payment gateways or delivery rates are configured for launch             |
| Discounts, vouchers, credits | Commercial explanation of order totals                                    | That promotional logic will recreate itself in ShopWired                      |
| Tax/VAT values               | Historical compliance and invoice context                                 | That future tax settings match source behavior without setup                  |
| Notes and custom fields      | Operational instructions, B2B notes, fulfillment details                  | That every custom field is standard migration scope                           |
| External IDs                 | Traceability to ERP, accounting, fulfillment, marketplace, or CRM systems | That connected systems will resume using the same identifiers without mapping |

Order validation should include varied examples: retail orders, trade orders, discounted orders, refunded orders, orders with special delivery, orders with custom fields, quote-related orders, and orders with external references. The output should be judged by operational users, not just by a record-count report.

### Checkout, Delivery, Payment, VAT, and Sales Tax Data <a href="#checkout-delivery-payment-vat-and-sales-tax-data" id="checkout-delivery-payment-vat-and-sales-tax-data"></a>

Checkout-related source data has to be separated into history, configuration, and custom behavior. Historical orders may contain payment method names, delivery method names, tax values, customer notes, and selected checkout options. Those values help explain past transactions, but they do not configure the ShopWired checkout for new transactions.

ShopWired setup may involve platform checkout behavior, delivery zones, delivery rates, delivery restrictions, collection options, payment gateway configuration, offline payment, VAT features, VAT zones, custom VAT rates, disability VAT relief, EU business VAT treatment, VAT on delivery costs, US sales tax configuration, checkout apps, and customer-group or trade rules. Migration planning should identify which parts are migrated for history and which parts must be rebuilt as target configuration.

| Source checkout element           | Migration treatment                                              | Launch-readiness dependency                                                          |
| --------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Historical payment method names   | Preserve as order context where supported                        | Configure and test live payment gateways separately                                  |
| Delivery method names and charges | Preserve order history and reporting context                     | Configure delivery zones, rates, restrictions, collection, and fulfillment workflows |
| Tax or VAT values on old orders   | Preserve historical totals and invoice meaning                   | Configure VAT/sales tax settings for future orders                                   |
| Custom checkout fields            | Review as order custom fields, app data, or Custom Service scope | Confirm where the information appears in admin, email, and fulfillment workflows     |
| B2B payment terms                 | Historical label plus live trade-account behavior                | Review trade settings, offline payment, approval, and account-term expectations      |
| Checkout apps                     | App-owned or configured behavior                                 | Reconfigure, map, rebuild, exclude, or escalate depending on business role           |

A good ShopWired migration plan therefore has two different pass criteria: historical checkout context remains readable, and future checkout behavior is configured and tested separately. Treating those as the same task creates avoidable launch risk.

### Content, SEO, Menus, and Theme-Dependent Data <a href="#content-seo-menus-and-theme-dependent-data" id="content-seo-menus-and-theme-dependent-data"></a>

ShopWired storefront presentation depends on more than imported product records. Website pages, landing pages, blog content, product and category metadata, 301 redirects, canonical behavior, breadcrumbs, menus, images, theme settings, customer account pages, and homepage or featured-product areas all influence how migrated data appears.

Content data should be classified by business value. Some pages are informational and can be rebuilt or retired. Others support SEO, B2B onboarding, policy compliance, conversion, product education, or paid traffic landing pages. High-value content deserves sample validation because a missing page, changed URL, broken redirect, weak metadata mapping, or incorrect menu placement can create real post-launch loss even when product data is technically present.

| Content or SEO asset            | Migration meaning                                         | Validation focus                                                                                         |
| ------------------------------- | --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Product and category URLs       | Search continuity and customer bookmarks                  | Priority URL mapping, redirects, canonical signals, and landing-page behavior                            |
| Website pages and landing pages | Trust, policy, B2B onboarding, SEO, or campaign relevance | Content completeness, links, images, forms, and calls to action                                          |
| Blog posts                      | Organic traffic, product education, or brand content      | URLs, metadata, images, author/date relevance, and internal links                                        |
| Menus and link lists            | Customer discovery and storefront wayfinding              | Main navigation, footer navigation, category access, and priority pages                                  |
| Theme-controlled sections       | Visual merchandising and conversion support               | Confirm whether data migration, theme setup, or manual rebuild is required                               |
| Customer account pages          | Account experience after login                            | Theme behavior, order visibility, address pages, subscriptions, favourites, and reward points where used |

The migration plan should not promise visual parity as a data outcome. It should preserve and verify content assets that have measurable business value, while separating theme design, layout reconstruction, and storefront setup from data migration scope.

### Apps, API, Webhooks, and External-System Data <a href="#apps-api-webhooks-and-external-system-data" id="apps-api-webhooks-and-external-system-data"></a>

ShopWired provides app, API, and webhook capabilities, but that does not mean source app data or external workflows automatically transfer. Source stores often depend on accounting tools, fulfillment platforms, stock systems, customer communication tools, marketplace connectors, postcode shipping, tax services, search tools, B2B apps, reward systems, subscription tools, product feeds, or custom integrations. Some records are inside the store database; others live in the app or external system.

The ShopWired data model should be planned around data ownership. If a field is visible in the old storefront but owned by an app, it may not be part of standard product, customer, or order records. If an ERP uses old product IDs, those identifiers may need to be preserved as custom fields or mapping records. If a webhook triggers fulfillment, the target process must be recreated and tested rather than assumed.

| Dependency type               | Typical migration question                                                                                             | Possible handling path                                                              |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| App-owned product data        | Does the app store options, bundles, feeds, reviews, subscriptions, or custom fields outside ordinary product records? | Add-on review, app setup, external export, manual rebuild, or Custom Service review |
| Accounting or ERP references  | Do old product, customer, or order IDs need to remain traceable?                                                       | Mapping file, custom field, Custom Service, or integration rebuild                  |
| Stock and fulfillment systems | Which system is the stock authority after launch?                                                                      | Reconfigure feed, API mapping, webhook setup, or phased validation                  |
| Customer marketing systems    | Are subscribers, consent, tags, or customer groups stored inside or outside the source store?                          | Separate marketing export, API sync, app setup, or accepted exclusion               |
| Marketplace and feed data     | Are listings richer than store product records?                                                                        | Channel-specific mapping, app configuration, or external-system review              |
| Custom fields                 | Are fields operational, reporting-only, or obsolete?                                                                   | Standard mapping where supported, Add-on, Custom Service, or exclusion              |

API planning also affects migration execution. Large data sets may need pagination-aware handling, and connected systems must respect authentication, HTTPS, JSON behavior, rate limits, and error handling. These are not copywriting details; they affect timing, testing, and integration readiness.

### Where Add-ons and Custom Service May Apply <a href="#where-add-ons-and-custom-service-may-apply" id="where-add-ons-and-custom-service-may-apply"></a>

Add-ons and Custom Service should not be merged into one generic “extra work” category. Add-ons are best understood as bounded migration enhancements when the required output fits a supported pattern. Custom Service applies when the required result depends on unsupported data sources, app-owned structures, external identifiers, bespoke transformation, custom migration logic, or custom platform behavior.

| Need                                                     | Typical handling                                                | Why the distinction matters                                                |
| -------------------------------------------------------- | --------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Filter or field mapping within supported structures      | Add-on review                                                   | The desired output fits a bounded migration enhancement                    |
| Product attributes that need structured treatment        | Add-on or Custom Service depending on source and target support | The same visible field may be simple mapping or custom transformation      |
| App-owned product, customer, or order records            | Custom Service review                                           | The data may not exist in ordinary exportable store records                |
| External IDs that must remain traceable                  | Custom Service review or mapping deliverable                    | Operational continuity may depend on preserving reference relationships    |
| B2B, quote, or pricing logic beyond supported structures | Custom Service review                                           | The requirement is business logic, not just record transfer                |
| Unsupported custom fields from a Custom Platform         | Custom Service review                                           | The source structure itself may need tailored extraction or transformation |

This distinction protects the migration plan from two opposite mistakes: treating everything as standard data, or escalating every non-basic request into custom work. The right decision depends on whether the requirement fits a supported transformation pattern.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired data-model planning should focus on meaning, not field matching. The most important differences usually appear around product configuration, B2B and trade behavior, customer identity, order history, checkout context, content and SEO assets, apps, API workflows, external IDs, and custom fields. Each area should be reviewed by how it will be used after launch, not only by whether a record can be imported.

A strong ShopWired migration plan classifies each source behavior as standard data, target configuration, storefront setup, Add-on scope, Custom Service review, external-system work, or accepted exclusion. That classification gives the merchant a more accurate view of what migration can preserve, what ShopWired must be configured to handle, and what must be rebuilt or reviewed separately before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do ShopWired product options need special review during migration?**

Because source product options may represent different behaviors in ShopWired. Some become variations with SKU, price, stock, image, weight, or VAT meaning. Others are better handled as choices, extras, personalization fields, bundles, app features, or Custom Service review.

**Are customer records matched only by name in ShopWired?**

No. Customer identity is strongly tied to email address. Duplicate emails, guest orders, registered accounts, trade accounts, and customer custom fields should be reviewed carefully so order history and account meaning remain usable.

**Do migrated orders configure checkout in ShopWired?**

No. Migrated orders can preserve historical payment, delivery, discount, tax, and fulfillment context where supported. Live checkout still depends on ShopWired payment, delivery, VAT or sales tax, customer-group, trade, and app configuration.

**Can B2B pricing and trade rules be migrated as normal customer data?**

Not always. Trade accounts, pricing bands, customer-specific pricing, quote workflows, product visibility, account terms, and tax treatment may involve configuration or Custom Service review, not only customer-record transfer.

**When should ShopWired data be reviewed for Custom Service?**

Custom Service review is appropriate when source behavior depends on unsupported custom fields, app-owned records, custom platform data, external identifiers, complex product transformation, B2B logic, or integration behavior that standard migration scope cannot safely preserve.
