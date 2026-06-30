# Shopware Data Model Differences

A Shopware migration should not be evaluated only by whether Products, Customers, Orders, Categories, Coupons, Reviews, CMS content, and related records arrive in the target store. Shopware can preserve familiar commerce records while changing how those records express storefront context, product discoverability, pricing behavior, content meaning, customer interaction, and operational ownership.

That difference matters because Shopware is built around a modular, API-first commerce architecture. Core commerce data, sales channels, storefront presentation, Administration workflows, APIs, extensions, rules, translations, and the Data Abstraction Layer work together to determine how the store behaves. A migrated product can exist in the database and still be incomplete if it is not visible in the right sales channel, connected to the right properties, grouped into the right variant structure, presented through the right content experience, or supported by the right commercial logic.

### Shopware Data Translation Starts With Operating Context <a href="#shopware-data-translation-starts-with-operating-context" id="shopware-data-translation-starts-with-operating-context"></a>

Data translation into Shopware begins by deciding what each source record means in the future operating model. Some values are direct commerce records. Some are sales-channel decisions. Some are storefront or CMS context. Some are configuration. Some are extension-created behavior. Some are external-system references that need to remain usable for staff, integrations, or reporting.

| Source-store pattern                                | Shopware translation question                                                                              | Migration implication                                                                           |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| One storefront with simple catalog records          | Should the target operate as one Shopware sales channel or multiple contexts?                              | Storefront structure should be confirmed before judging imported records.                       |
| Multiple languages, markets, domains, or sub-stores | Which contexts belong to sales channels, languages, currencies, domains, or content structures?            | The same product record may need different visibility, content, or routing behavior by context. |
| Attribute-heavy products                            | Which values should become properties, variant options, custom fields, filters, or informational text?     | Attribute transfer alone may not preserve search, filtering, comparison, or buying logic.       |
| Rule-based pricing, shipping, or promotions         | Which behavior is migrated data and which behavior is Shopware configuration or custom scope?              | Commercial logic may need separate setup or validation beyond record transfer.                  |
| Extension-owned fields or custom workflows          | Which records are supported, which are target-side configuration, and which require Custom Service review? | Unsupported app, plugin, module, or custom behavior should be classified before migration.      |

This translation lens prevents a common failure: treating Shopware as a neutral container for old data. Shopware can become a better-structured target, but only when old source meanings are interpreted into the correct target concepts.

### Sales Channels Change Storefront Meaning <a href="#sales-channels-change-storefront-meaning" id="sales-channels-change-storefront-meaning"></a>

Sales channels are one of the most important Shopware concepts for migration planning. They can define how products, categories, domains, storefronts, languages, currencies, customer-facing content, and routes are organized for different buying contexts. A source platform may have handled these contexts through separate stores, store views, language folders, marketplace feeds, theme logic, or manual configuration. Shopware asks the merchant to clarify the target storefront context more deliberately.

A product that exists in Shopware is not automatically ready for every customer-facing context. The product still needs the right visibility, category placement, route behavior, content relationship, and commercial availability in the relevant sales channel.

| Sales-channel data area                 | What must be translated                                                            | Failure signal                                                                  |
| --------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Product availability                    | Which products should appear in each storefront context.                           | Products exist but are missing from the intended channel.                       |
| Category and navigation context         | Which category paths belong to each customer-facing experience.                    | Category trees import but do not support the intended journey.                  |
| Domains and language context            | Which URL, language, and regional assumptions must continue.                       | Pages resolve but use the wrong market, language, or destination intent.        |
| Pricing, shipping, and payment behavior | Which conditions depend on channel context.                                        | Checkout behavior differs from customer expectations even though records exist. |
| Content and Shopping Experiences        | Which landing pages, content blocks, and merchandising areas support each channel. | Commerce data is present but content-led buying paths are incomplete.           |

The migration question is not only “did the record migrate?” It is “does the record operate correctly inside the right Shopware sales-channel context?”

### Product Meaning Depends on Structure, Not Only Fields <a href="#product-meaning-depends-on-structure-not-only-fields" id="product-meaning-depends-on-structure-not-only-fields"></a>

Shopware product migration should preserve product meaning, not just product names, SKUs, descriptions, prices, and stock. Products can depend on manufacturer data, media, categories, properties, variant relationships, visibility, SEO fields, tax and price behavior, reviews, cross-selling context, custom fields, and integration references.

This creates a stronger data-model review than a basic product import check. A product can look present while still failing customer-facing or operational expectations if the surrounding structure is missing.

| Product area   | Shopware meaning                                                                  | Review focus                                                                                      |
| -------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Product record | Core item identity, descriptions, SKU, media, status, and commercial baseline.    | Confirm that important products are complete, active where expected, and understandable to staff. |
| Variants       | Selectable product differences under a parent/product structure.                  | Confirm that buying choices remain clear and purchasable.                                         |
| Properties     | Descriptive values that can support filtering, comparison, and product discovery. | Confirm that source attributes did not become dead text where filters are needed.                 |
| Categories     | Browsing, merchandising, content, and discovery structure.                        | Confirm category relationships support future navigation, not only old hierarchy.                 |
| Custom fields  | Business-specific values used by staff, integrations, or storefront logic.        | Confirm which values are supported, which need mapping, and which require custom handling.        |

The most important product samples are usually not the simplest products. The best samples are variant-heavy, property-heavy, high-revenue, high-traffic, integration-linked, promotion-sensitive, or operationally important products.

### Properties and Variants Need Deliberate Interpretation <a href="#properties-and-variants-need-deliberate-interpretation" id="properties-and-variants-need-deliberate-interpretation"></a>

Source platforms often use different concepts for product options, attributes, variations, configurable products, grouped products, and product families. Shopware may require those concepts to be separated into product variants, properties, filters, or custom fields depending on how the values are used.

The distinction is important because descriptive data and buying-choice data are not the same thing. A value used only to describe a product may belong in a different place from a value that determines a purchasable variant. A technical specification used for filtering may require different handling from a hidden value used only by an ERP or PIM.

| Source value use                                       | Better Shopware interpretation                                              | Why it matters                                                                       |
| ------------------------------------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Customer selects the value before purchase             | Variant-related structure may be needed.                                    | Buying choices must remain selectable and tied to the correct SKU or stock behavior. |
| Customer filters or compares products by the value     | Property/filter meaning may be needed.                                      | Discovery and category browsing depend on structured values.                         |
| Staff or external systems use the value internally     | Custom field or integration reference may be more appropriate.              | Internal meaning should not be forced into customer-facing filters.                  |
| The value is descriptive copy                          | Product description, specification content, or content block may be enough. | Over-structuring descriptive text can create unnecessary migration complexity.       |
| The value drives pricing, availability, or fulfillment | Rule, configuration, custom field, or integration review may be needed.     | Commercial behavior may not be preserved by field migration alone.                   |

A strong Shopware data migration therefore separates product values by function. The same source “attribute” can become several different target meanings depending on how the merchant uses it.

### Categories, Content, and Shopping Experiences Are Connected <a href="#categories-content-and-shopping-experiences-are-connected" id="categories-content-and-shopping-experiences-are-connected"></a>

Shopware category migration should not be reduced to moving a parent-child hierarchy. Categories can support navigation, product discovery, landing-page meaning, SEO value, storefront content, and merchandising. In Shopware, content and commerce can also interact through Shopping Experiences and other content structures, so category and CMS review should happen together when category pages carry more than a product list.

This is especially important for merchants whose source store used categories as SEO landing pages, campaign pages, buying guides, brand pages, or content-rich shopping paths. The target store may need to preserve both the structural category relationship and the content purpose behind the page.

| Area                               | Data relationship to preserve                                          | Validation question                                                               |
| ---------------------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Category hierarchy                 | Parent-child browsing structure and merchandising logic.               | Do customers still reach the right product groups through expected paths?         |
| Category content                   | Intro text, media, landing-page blocks, and content-led merchandising. | Does the page still explain and sell the category, not just list products?        |
| Shopping Experiences / CMS content | Reusable content areas, landing pages, and presentation context.       | Are content blocks connected to the right storefront purpose?                     |
| SEO routes                         | Product, category, and content destinations with search intent.        | Do priority URLs resolve to pages that still satisfy the original intent?         |
| Sales-channel context              | Channel-specific category or content expectations.                     | Are category and content experiences correct for the relevant storefront context? |

Content migration into Shopware should preserve the customer journey. If content only moves as isolated text or disconnected pages, the target store may lose the relationship between buying intent, discovery, and conversion.

### Pricing, Promotions, and Rules Change Commercial Meaning <a href="#pricing-promotions-and-rules-change-commercial-meaning" id="pricing-promotions-and-rules-change-commercial-meaning"></a>

Shopware can express commercial behavior through structured rules, conditions, pricing, promotions, shipping, payment availability, visibility decisions, flows, and configuration. That means migration planning should distinguish between static values and conditional business logic.

A source store may have stored commercial behavior in discount tables, customer groups, custom code, extensions, app settings, spreadsheets, or ERP rules. Shopware may require those assumptions to be rebuilt, configured, mapped, or reviewed as custom behavior rather than simply imported.

| Commercial area                   | Data-model question                                                           | Migration consequence                                                             |
| --------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Base product prices               | Are prices simple migrated values or part of broader price logic?             | Standard data transfer may be enough only when pricing is straightforward.        |
| Advanced or conditional pricing   | Which customer, quantity, channel, cart, or product conditions matter?        | Rule/configuration planning may be required before launch.                        |
| Promotions and discounts          | Are source promotions transferable records or behavior that must be rebuilt?  | Imported coupon data may not preserve full commercial logic.                      |
| Shipping and payment availability | Which rules control eligibility and customer experience?                      | Checkout readiness requires scenario-based validation.                            |
| Workflow automation               | Which outcomes were created by apps, plugins, custom code, or manual process? | Custom Service or target-side rebuild may be needed when behavior is unsupported. |

Commercial behavior should be tested through representative scenarios. Checking only a product price or coupon record will not prove that Shopware reproduces the intended buying conditions.

### Customers and Orders Need Business Context <a href="#customers-and-orders-need-business-context" id="customers-and-orders-need-business-context"></a>

Customer and order records should remain usable for account review, customer service, reporting, segmentation, support history, and operational continuity. Shopware migration should preserve not only customer and order counts, but also the meaning attached to those records.

Customer context can include account identity, addresses, group-like logic, segmentation assumptions, communication preferences, custom fields, and integration references. Order context can include line items, taxes, shipping, payment method, status, discounts, historical totals, fulfillment references, and customer-service interpretation.

| Record area                 | Meaning to preserve                                             | Review focus                                                          |
| --------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------- |
| Customer identity           | Account and contact details remain recognizable.                | Customer service can identify and support the customer.               |
| Addresses and contact data  | Billing, shipping, and communication context remains usable.    | Address and contact records are complete and associated correctly.    |
| Historical orders           | Past purchases remain understandable.                           | Order lines, totals, taxes, shipping, payment, and status make sense. |
| Segmentation or group logic | Customer-facing or operational classification remains usable.   | Important classifications are mapped, configured, or documented.      |
| Integration identifiers     | ERP, CRM, fulfillment, or external references remain traceable. | Staff can reconcile records with outside systems where required.      |

Historical data does not need to behave exactly like new checkout data, but it must remain interpretable. A migrated order that exists but cannot be understood by support staff is not a successful operational outcome.

### Translations and Localization Affect More Than Text <a href="#translations-and-localization-affect-more-than-text" id="translations-and-localization-affect-more-than-text"></a>

Shopware’s data structure can include language and translation behavior that affects products, categories, properties, content, routes, and storefront presentation. Translation planning is especially important when the source store used store views, language folders, regional domains, multilingual content, or duplicated product records to represent language or market differences.

Localization is not only text replacement. It can affect discovery, SEO continuity, customer trust, pricing perception, shipping/payment expectations, and content relevance. When language and market meaning are unclear, migrated records may appear correct in one context but incomplete or misleading in another.

| Localization area              | Migration question                                           | Risk if ignored                                           |
| ------------------------------ | ------------------------------------------------------------ | --------------------------------------------------------- |
| Product names and descriptions | Which languages need complete product content?               | Storefronts show fallback, missing, or inconsistent copy. |
| Properties and filters         | Are filter labels and values translated appropriately?       | Customers cannot compare or filter products clearly.      |
| Categories and content         | Do localized browsing and content paths remain meaningful?   | Navigation works structurally but fails customer intent.  |
| SEO URLs and metadata          | Which language or market paths matter for search continuity? | Priority organic destinations lose relevance.             |
| Sales channels and domains     | Which storefront context owns each language or market?       | Records appear in the wrong customer-facing context.      |

Multilingual migration samples should include products, categories, filters, content pages, and priority URLs, not only language strings.

### Extensions, Apps, Plugins, and Custom Fields Can Carry Critical Meaning <a href="#extensions-apps-plugins-and-custom-fields-can-carry-critical-meaning" id="extensions-apps-plugins-and-custom-fields-can-carry-critical-meaning"></a>

Shopware’s extensibility is a strength, but migration planning should identify where important business meaning lives outside standard commerce records. Plugins, apps, custom fields, custom entities, storefront themes, API integrations, ERP/PIM/CRM connections, search extensions, checkout customizations, and merchandising logic can all shape how the store works.

Some extension-related requirements may be handled through supported configuration, Add-ons for supported filtering or mapping, or target-side setup. Others require Custom Service because they involve unsupported extension data, custom fields, bespoke transformation, Custom Platform handling, outside-system identifiers, or custom migration logic adjustment.

| Dependency type                                      | Data-model implication                                           | Planning path                                                                        |
| ---------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Custom fields used for display or operations         | Values may need mapping or custom handling.                      | Identify field purpose and target use before migration.                              |
| Extension-owned catalog or checkout behavior         | Standard entities may not contain the full business logic.       | Classify whether behavior is target configuration, Add-ons scope, or Custom Service. |
| ERP, PIM, OMS, CRM, or search integration references | External identifiers may be required for post-launch operations. | Preserve traceability where the outside system remains active.                       |
| Theme or storefront customizations                   | Presentation meaning may not be part of core data.               | Decide what will be rebuilt, migrated, simplified, or replaced.                      |
| Custom source structures                             | Records may require interpretation before they fit Shopware.     | Use Custom Service when source data cannot be mapped through supported behavior.     |

The safest migration scope is the one that separates transferable records from behavior and dependencies that must be rebuilt or specially handled.

### What Shopware Data Must Prove After Migration <a href="#what-shopware-data-must-prove-after-migration" id="what-shopware-data-must-prove-after-migration"></a>

A Shopware data review should prove that the target store can operate with the migrated information. Record counts help confirm presence, but they cannot prove product meaning, storefront context, rule behavior, content continuity, or operational usability.

| Proof area                           | What should be demonstrated                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Catalog usability                    | Products, variants, properties, media, categories, and visibility support the intended buying journey.           |
| Sales-channel readiness              | Products, categories, domains, languages, and storefront content appear in the correct contexts.                 |
| Commercial logic                     | Pricing, promotions, shipping, payment, and rule-dependent behavior are configured or scoped correctly.          |
| Content and SEO continuity           | Priority product, category, CMS, and landing-page destinations preserve intent.                                  |
| Customer and order usability         | Staff can recognize, support, and interpret migrated customer and order records.                                 |
| Extension and integration continuity | Required custom fields, identifiers, or external-system relationships remain usable or are clearly out of scope. |

The strongest Shopware data model review ends with operational proof. The target store should not merely contain old data; it should make that data meaningful in Shopware’s commerce structure.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopware changes migration planning because familiar store records can take on new meaning inside a modular, API-first commerce environment. Sales channels, products, variants, properties, categories, content, translations, rules, custom fields, extensions, and external systems all influence whether migrated data remains usable.

A successful Shopware migration translates source data into target meaning. Products should support discovery and purchase. Categories and content should preserve customer intent. Customer and order records should remain operationally useful. Commercial behavior should be configured, validated, or scoped separately when it is not part of ordinary record transfer. That translation work is what separates a complete import from a store that is actually ready to operate on Shopware.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the biggest Shopware data-model difference to understand?**

The biggest difference is that Shopware data meaning depends strongly on context. Products, categories, content, rules, translations, and visibility may need to be reviewed by sales channel, storefront purpose, and business behavior rather than only by record presence.

**Why are sales channels important in a Shopware migration?**

Sales channels can shape product visibility, domains, languages, currencies, storefront behavior, content context, and customer-facing routes. A product can exist in Shopware but still be wrong if it does not appear or behave correctly in the intended sales channel.

**How should product attributes from another platform be interpreted in Shopware?**

They should be classified by use. Some values may become properties, some may support variants, some may belong in custom fields, some may remain descriptive content, and some may require custom handling because they drive pricing, fulfillment, or integration behavior.

**Does Shopware content migration only involve CMS pages?**

No. Content migration may include Shopping Experiences, category content, landing pages, media, navigation meaning, SEO routes, and content blocks that support the buying journey. Content should be reviewed together with the commerce context it supports.

**Do extensions or custom fields always require Custom Service?**

No. Some supported fields or mapping needs may fit Standard Service, Managed Service, or Add-ons. Custom Service becomes relevant when unsupported extension data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment is required.
