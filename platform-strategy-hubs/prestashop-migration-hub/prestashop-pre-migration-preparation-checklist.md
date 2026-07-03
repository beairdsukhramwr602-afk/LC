# PrestaShop Pre-Migration Preparation Checklist

A PrestaShop migration is easier to control when preparation turns inherited storefront assumptions into clear target decisions before execution begins. PrestaShop can support structured product combinations, descriptive product features, customer-entered customization fields, category governance, customer groups, multistore context, friendly URLs, modules, themes, and open-platform customization. Those strengths create planning value only when the merchant knows which parts of the old store should remain, which should be simplified, and which require special review.

Preparation should not become a generic access checklist. The stronger PrestaShop preparation process gathers evidence that explains how the future store should behave: which products need selectable combinations, which values are only descriptive features, which products need personalization inputs, which categories drive discovery, which customer groups still affect commercial rules, which shops or languages matter, and which module or custom fields carry business meaning.

The objective is practical: make Demo Migration review meaningful, reduce Full Migration uncertainty, and prevent the target PrestaShop store from becoming a technically populated but commercially unclear catalog.

### Define the Future PrestaShop Operating Model <a href="#define-the-future-prestashop-operating-model" id="define-the-future-prestashop-operating-model"></a>

PrestaShop preparation should begin with the target operating model. A merchant moving into PrestaShop may want a cleaner open-source storefront, better catalog governance, more control over product data, a structured multistore setup, a more flexible module ecosystem, or a stronger foundation for future customization. Each goal changes what must be prepared before migration.

A merchant with a single storefront and ordinary products may focus on product, category, customer, order, and URL samples. A merchant with many product variations needs deeper combination planning. A merchant with strong technical specifications needs feature governance. A merchant with customer-specific pricing or visibility expectations must review customer groups. A merchant planning more than one shop context should clarify multistore scope before data is moved.

| Preparation area        | Decision to make before migration                                                  | Why it matters in PrestaShop                                                                    |
| ----------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Catalog model           | Which source choices become combinations, features, or customization fields?       | PrestaShop separates selectable variation, descriptive information, and customer-entered input. |
| Categories              | Which category paths should remain, merge, retire, or change?                      | Categories affect navigation, discovery, SEO metadata, visibility, and group access.            |
| Customer groups         | Which groups still affect pricing, access, discounts, tax, or communication?       | Groups can carry commercial meaning beyond simple customer labels.                              |
| Multistore              | Is one shop enough, or are separate shops/domains/languages/pricing scopes needed? | Multistore decisions affect data assignment and validation.                                     |
| URLs and SEO            | Which friendly URLs and legacy paths need continuity planning?                     | PrestaShop URL structure should be reviewed before launch, not only after migration.            |
| Modules and custom data | Which modules, overrides, custom fields, or integrations own important behavior?   | Standard records may not preserve module- or custom-code meaning.                               |

The operating model should be written in plain business terms before technical mapping begins. A migration team should know what the PrestaShop store is supposed to preserve, not only which entities are selected.

### Prepare Product Combination Evidence <a href="#prepare-product-combination-evidence" id="prepare-product-combination-evidence"></a>

Product preparation should begin with the products that carry the highest structure risk. In PrestaShop, attributes are used for product variations, also called combinations. That means size, color, capacity, material, or another selectable choice can change the sellable version of a product when it truly represents a variation. Preparing those products carefully protects pricing, SKU, stock, image, weight, availability, and customer-choice logic.

The merchant should identify representative products where customer selection affects the actual item being purchased. These examples should include simple products, combination-heavy products, products with multiple attribute groups, products where combinations change price or stock, and products where the source platform used workarounds to represent selectable choices.

| Product pattern                           | Preparation task                                                                 | Review outcome                                               |
| ----------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Simple product                            | Confirm name, SKU, price, image, category, tax, and visibility expectations.     | Establishes baseline migration behavior.                     |
| Size or color product                     | Define attributes and values that should create combinations.                    | Prevents selectable choices from becoming flat descriptions. |
| Product with price-changing options       | Identify which choices affect price and whether they should become combinations. | Protects commercial accuracy.                                |
| Product with stock-changing choices       | Confirm SKU and inventory logic for each sellable version.                       | Supports variation-level validation.                         |
| Product with inherited option workarounds | Decide whether to preserve, simplify, or custom-handle the structure.            | Avoids copying source-side disorder into PrestaShop.         |

Good preparation should also flag combinations that are no longer needed. Old sizes, discontinued colors, duplicate attribute values, or abandoned option logic can make a migrated catalog harder to manage. Migration is often the right moment to preserve the products that still sell and remove structures that only exist because of the previous platform.

### Separate Features From Sellable Choices <a href="#separate-features-from-sellable-choices" id="separate-features-from-sellable-choices"></a>

PrestaShop features should be prepared as descriptive product information, not as selectable purchase choices. Features help customers understand and compare products. They may describe material, technical specifications, dimensions, compatibility, ingredients, finish, energy rating, or other stable characteristics. They should not be confused with attributes used to create combinations.

Preparation should identify which source fields are truly useful features. Many older stores contain inherited fields that are duplicated, outdated, inconsistent, or only meaningful to internal teams. Moving every field into PrestaShop can make product pages cluttered and weaken comparison quality.

A useful preparation review should answer:

* Which product specifications help customers compare alternatives?
* Which feature groups should be standardized across product families?
* Which source fields are obsolete, duplicated, or inconsistent?
* Which values are actually variation choices and should not be treated as features?
* Which features should be visible, searchable, or useful for filtering where the store setup supports it?

The goal is not to maximize feature count. The goal is to make product information consistent enough for customers to compare products and for staff to maintain the catalog after launch.

### Prepare Customization Field Requirements <a href="#prepare-customization-field-requirements" id="prepare-customization-field-requirements"></a>

PrestaShop customization fields require early review because they represent customer-entered information, not product variation. Personalization text, file uploads, engraving names, gift messages, print instructions, uploaded images, and special order notes can affect fulfillment and order interpretation. If these values are migrated or configured incorrectly, the storefront may look correct while operations lose the details needed to fulfill personalized orders.

The merchant should list products that require customer input and define whether each input should be required, optional, visible to staff, visible to customers, included in order review, or handled by another process. If the source store uses a module, app, theme, or custom code to manage personalization, that dependency should be identified before service-path choice.

| Personalization example   | Preparation question                                            | Likely implication                                  |
| ------------------------- | --------------------------------------------------------------- | --------------------------------------------------- |
| Engraving text            | Is the text required, optional, length-limited, or formatted?   | Standard setup may be enough if behavior is simple. |
| File upload               | What file type, size, and fulfillment process are expected?     | May need target-side setup or custom review.        |
| Gift message              | Does it belong to product personalization or order-level notes? | Mapping should preserve operational meaning.        |
| Custom design instruction | Does the source behavior depend on a module or custom code?     | Custom Service review may be needed.                |

Personalization should not be buried under product-description cleanup. It affects customer experience and fulfillment confidence, so it belongs in the preparation package before Demo Migration.

### Prepare Categories, Friendly URLs, and Discovery Paths <a href="#prepare-categories-friendly-urls-and-discovery-paths" id="prepare-categories-friendly-urls-and-discovery-paths"></a>

Category preparation should focus on product discovery and SEO continuity, not only category record transfer. PrestaShop categories help group products, support customer navigation, and carry page-level information such as description, images, metadata, friendly URL, visibility, and group access. A source category tree may contain important landing pages, abandoned seasonal categories, duplicate structures, or search-driven paths that should be protected.

Before migration, the merchant should identify the category paths that matter most:

* top navigation categories;
* high-traffic organic search landing pages;
* categories used for paid campaigns or email campaigns;
* categories that carry merchandising or seasonal value;
* categories used for B2B, wholesale, or restricted access;
* categories that should be merged, renamed, hidden, or retired;
* categories that should not be assigned to the same root context in a multistore setup.

Friendly URL planning should happen before validation. If an old category or product URL matters to search traffic, backlinks, ads, or customer bookmarks, the expected handling should be decided before migration results are accepted. Some URLs may need redirect planning. Others may be safely retired. The merchant should rank priority URLs instead of treating every legacy path as equal.

### Prepare Customer Groups and Commercial Segmentation <a href="#prepare-customer-groups-and-commercial-segmentation" id="prepare-customer-groups-and-commercial-segmentation"></a>

Customer groups should be prepared as commercial rules, not only as contact labels. In PrestaShop, groups can be involved in access, pricing, discounts, tax treatment, and other customer-facing behavior depending on store configuration. A source store may have wholesale groups, retail groups, VIP groups, tax-exempt customers, regional segments, customer-type labels, or legacy groups created by old extensions.

Preparation should clarify which groups still matter and why. If a group only existed for an old campaign, it may not need migration. If a group controls price visibility or category access, it requires stronger review. If group logic depends on a module or external system, it should not be assumed to transfer as ordinary customer data.

| Group type             | Preparation decision                                                                           | Risk if ignored                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Wholesale group        | Confirm pricing, catalog access, tax, and account approval expectations.                       | B2B buyers may see the wrong catalog or price treatment.           |
| VIP or loyalty group   | Decide whether the group is historical, marketing-only, or active.                             | Staff may confuse old segmentation with active benefits.           |
| Tax-exempt group       | Confirm whether tax treatment is a target setup task, migrated history, or custom requirement. | Tax expectations may be misinterpreted.                            |
| Legacy extension group | Identify the extension owner and current business value.                                       | Unsupported behavior may be mistaken for standard migration scope. |

Customer group preparation should include sample customers and sample orders so validation can confirm both profile meaning and historical context.

### Prepare Multistore, Language, and Shop Scope <a href="#prepare-multistore-language-and-shop-scope" id="prepare-multistore-language-and-shop-scope"></a>

PrestaShop multistore planning deserves separate preparation when a merchant expects more than one storefront, domain, language, region, brand, B2B/B2C version, or price context. Multistore should not be treated as a late display decision because it affects how records are assigned, reviewed, and validated.

The merchant should decide whether multistore is actually needed. Some stores can use one PrestaShop shop with categories, languages, customer groups, and modules configured appropriately. Others need distinct shop contexts. Preparation should define which source records belong to which shop, which content should be shared, which products should differ, and which pricing or category assignments should be separate.

| Multistore question                             | Preparation evidence needed                                                  |
| ----------------------------------------------- | ---------------------------------------------------------------------------- |
| Are multiple storefronts required?              | Target shop list, domains, languages, business purpose, and launch sequence. |
| Are products shared or shop-specific?           | Product samples showing shared and separate catalog behavior.                |
| Are categories shared or shop-specific?         | Root category expectations and category assignment examples.                 |
| Are customer groups shared or shop-specific?    | Customer examples and commercial rules.                                      |
| Are prices, taxes, or shipping rules different? | Target setup assumptions and validation ownership.                           |

If multistore scope is unclear, Standard Service assumptions become risky. The preparation package should either make the scope explicit or identify the requirement for stronger service-path review.

### Identify Modules, Themes, Overrides, and Custom Data <a href="#identify-modules-themes-overrides-and-custom-data" id="identify-modules-themes-overrides-and-custom-data"></a>

Open-source flexibility is one of PrestaShop’s strengths, but it also means important behavior may live outside ordinary records. Modules, themes, overrides, custom database fields, ERP connectors, CRM records, reviews, loyalty tools, subscription logic, marketplace data, shipping rules, payment logic, analytics fields, or custom exports may carry business meaning.

Preparation should create a dependency inventory. For each dependency, the merchant should explain what it does, which records it affects, whether the data is still needed, whether the behavior must exist in PrestaShop after migration, and whether the requirement belongs to standard migration scope, Add-ons, Custom Service, or target-side setup.

| Dependency                       | What to document                                                             | Likely planning path                                                    |
| -------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Product module                   | Product fields, combinations, pricing, options, or personalization affected. | Add-on or Custom Service depending on support boundary.                 |
| Theme override                   | Display-only behavior versus stored data.                                    | Target-side design/setup or Custom Service if data meaning is affected. |
| Custom database field            | Field purpose, sample records, target expectation.                           | Custom Service review.                                                  |
| ERP/CRM connector                | IDs, sync rules, ownership, reporting dependency.                            | Custom Service or external integration planning.                        |
| Review/loyalty/subscription data | Source owner, customer impact, target availability.                          | Custom Service or separate platform setup.                              |

This inventory prevents unsupported expectations from appearing late in the project. It also protects Add-ons from being misused as a vague solution for custom behavior.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration samples should be chosen deliberately. The goal is to expose PrestaShop-specific decisions before the full dataset is moved. A weak sample set with only simple products and clean orders may pass while combination-heavy products, customer groups, multistore assignments, URLs, or custom data fail later.

A strong PrestaShop sample set should include:

| Sample type                  | What it should prove                                                    |
| ---------------------------- | ----------------------------------------------------------------------- |
| Simple product               | Baseline product, image, category, price, tax, and visibility behavior. |
| Combination-heavy product    | Attribute and combination handling.                                     |
| Feature-heavy product        | Descriptive specification and comparison logic.                         |
| Personalized product         | Customization field and order-detail behavior.                          |
| High-value category          | Category assignment, metadata, friendly URL, and visibility.            |
| Customer group example       | Pricing, access, communication, or segmentation interpretation.         |
| Multistore record            | Shop assignment, root category, domain, language, or pricing context.   |
| Module/custom-field example  | Add-on, Custom Service, target setup, or exclusion decision.            |
| Refunded or discounted order | Historical order readability and commercial context.                    |

Sample selection should be documented before Demo Migration begins. Reviewers should know what each sample is meant to prove and what failure would mean.

### Plan Access, Backups, and Launch Timing <a href="#plan-access-backups-and-launch-timing" id="plan-access-backups-and-launch-timing"></a>

Access preparation should include the Source Platform, target PrestaShop environment, export access, media files, URL lists, module information, custom-field evidence, and stakeholder permissions needed for review. The merchant should keep backups or export copies wherever available so the target result can be compared against the source state.

Launch timing also needs preparation. If the source store remains active after the first migration run, new products, customers, orders, Blog Posts, or content may appear before launch. The merchant should decide whether later migration activity may be needed and what should be revalidated afterward. Continuing the migration with the last used configuration, continuing with a new configuration, or performing a new migration are not the same operational decision. Each affects what should be checked before launch.

Entity Points planning should also be understood at the right level. New eligible records consume Entity Points when migrated for the first time, while already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path. This matters when launch timing includes new records, changed configuration, or a refreshed migration outcome.

### Conclusion <a href="#conclusion" id="conclusion"></a>

PrestaShop preparation is strongest when it turns catalog structure, customer segmentation, shop scope, URLs, modules, custom data, and launch timing into clear evidence before migration begins. The merchant should know which product choices become combinations, which values remain features, which products require customization fields, which categories and URLs matter, which customer groups still carry commercial rules, and which dependencies require Add-ons, Custom Service, target-side setup, or exclusion.

A well-prepared PrestaShop migration does not simply move more records. It makes the future store easier to validate because each important record type has an expected target meaning.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a PrestaShop migration?**

Start with the future catalog model. Identify products that need combinations, products that rely on descriptive features, and products that require customer-entered customization fields. This gives the rest of the preparation process a clearer target.

**Why are PrestaShop product features reviewed separately from combinations?**

Features describe stable product characteristics, while combinations represent selectable variations. Treating one as the other can make the catalog harder to browse, compare, and validate.

**Should every source category be migrated into PrestaShop?**

No. Categories should be reviewed for discovery, SEO, visibility, customer-group access, and business value. Some old categories should be preserved, while others may be merged, hidden, redirected, or retired.

**When does PrestaShop preparation require Custom Service review?**

Custom Service should be considered when the requirement involves unsupported module data, custom fields, overrides, external-system identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

**Why should later migration activity be planned before launch?**

If the source store keeps changing after an initial migration run, new records or changed configuration may need follow-up handling. The team should know which action is expected and what must be revalidated before launch.
