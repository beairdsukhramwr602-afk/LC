# PrestaShop Data Model Differences

PrestaShop migration should be planned as a structured-commerce translation, not a simple field transfer. The Target Platform can hold familiar commerce records such as Products, Categories, Customers, Orders, Coupons, CMS Pages, images, and SEO fields, but the meaning of those records changes when they enter PrestaShop’s catalog, customer-group, multistore, URL, module, and storefront-governance environment.

The most important data-model difference is that PrestaShop does not treat product meaning as one broad option layer. A source store may use product options, attributes, specifications, app fields, custom checkout notes, or module behavior to represent many different things. In PrestaShop, those meanings may need to become combinations, attributes, features, customization fields, product associations, category assignments, customer group behavior, shop-specific scope, or Custom Service requirements.

That distinction is not cosmetic. If selectable product choices become descriptive features, customers may no longer be able to buy the right version. If descriptive specifications become combinations, the product can become harder to manage and validate. If customer group meaning is treated as a label rather than storefront behavior, pricing, visibility, discounts, tax treatment, or account expectations may become unclear. If multistore context is flattened, shop ownership, URL paths, and product visibility can become difficult to trust.

### PrestaShop Data Meaning Starts With Catalog Structure <a href="#prestashop-data-meaning-starts-with-catalog-structure" id="prestashop-data-meaning-starts-with-catalog-structure"></a>

PrestaShop gives merchants strong control over catalog organization, but that control depends on correctly separating product meaning. The migration plan should identify what each source product field actually does before deciding where it belongs in PrestaShop.

Some source platforms use a single option model for variation, filtering, product specification, personalization, bundle choices, or marketing labels. Other stores rely on modules, templates, custom fields, or scripts to show product choices that are not clearly represented in export data. PrestaShop can support a structured catalog, but the source data must be interpreted through the correct target behavior.

| Source-side meaning              | PrestaShop planning question                                               | Migration implication                                                                              |
| -------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Selectable product version       | Should it become a combination based on attributes?                        | Wrong classification can affect purchasable choices, price, SKU, stock, and product-page behavior. |
| Product specification            | Should it become a feature?                                                | Features support description, comparison, and discovery rather than purchasable variation.         |
| Customer-entered personalization | Should it become a customization field or custom requirement?              | Personalization should not be mistaken for ordinary variation or descriptive content.              |
| Module-managed option            | Is the behavior supported, module-owned, or custom?                        | Module data may need Add-ons, Custom Service review, or target-side rebuilding.                    |
| Product grouping                 | Is it a category, association, pack, accessory, or merchandising decision? | Catalog relationships need target meaning, not just copied labels.                                 |

The safest PrestaShop data model review begins by asking what customers and staff need the product data to do after launch. Only then should the migration team decide whether the source value belongs in core migrated records, target-side configuration, Add-ons, Custom Service, or an excluded expectation.

### Products, Combinations, Attributes, and Features Are Not Interchangeable <a href="#products-combinations-attributes-and-features-are-not-interchangeable" id="products-combinations-attributes-and-features-are-not-interchangeable"></a>

Product migration into PrestaShop requires special attention to combinations, attributes, and features. These terms may sound similar to source-platform options or specifications, but they are not interchangeable. The distinction affects product display, customer choice, filtering, catalog administration, and validation.

Attributes are the basis for PrestaShop product variations, commonly called combinations in the PrestaShop interface. They represent properties that change between purchasable versions of the same product, such as size, color, capacity, material, or another selectable difference. A product can only have combinations if the changing choice is represented by at least one attribute. Features, by contrast, are intrinsic product characteristics that remain the same across combinations and provide descriptive product information.

This creates a clear migration test: if the source value affects which version the customer buys, it probably needs variation-level review. If it explains the product but does not create a different purchasable version, it is more likely to be a feature or descriptive field. If it asks the customer to enter text, upload information, or personalize an item, it may belong to a customization field or custom handling path.

| PrestaShop structure          | What it usually represents                                          | Migration risk if misused                                                                          |
| ----------------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Attribute                     | A changing property used to create combinations.                    | Product choices may fail if attributes are missing, merged, duplicated, or confused with features. |
| Combination                   | A purchasable product variation built from attributes.              | SKU, price, stock, image, or option selection may become unreliable.                               |
| Feature                       | A stable characteristic used for product information or comparison. | Specifications may become harder to browse or may be overbuilt as purchasable choices.             |
| Customization field           | Customer-entered or customer-provided product personalization.      | Personalized buying flows may be lost if treated as simple notes or options.                       |
| Module-owned product behavior | Extended behavior created outside core structures.                  | Standard migration may not preserve the behavior without review.                                   |

A high-quality PrestaShop migration should not try to force every source option into combinations. It should preserve the commercial meaning of each source field. The target catalog should remain understandable for customers, manageable for staff, and realistic for later validation.

### Category Data Carries Discovery, Visibility, and SEO Meaning <a href="#category-data-carries-discovery-visibility-and-seo-meaning" id="category-data-carries-discovery-visibility-and-seo-meaning"></a>

PrestaShop categories should be treated as discovery structures, not only containers. A category tree can affect how customers browse, how products are grouped, how landing pages are understood, and how SEO metadata and friendly URLs are reviewed.

Source platforms often mix several roles into category-like structures. A category might function as an admin folder, customer navigation path, campaign page, brand page, collection, SEO landing page, or product filter shortcut. Migrating every source category directly into PrestaShop may preserve old clutter instead of supporting clean target browsing.

PrestaShop category review should determine which categories still deserve target visibility and which categories should be merged, retired, redirected, or handled as content rather than catalog structure. This is especially important when the source store has deep trees, duplicate categories, seasonal groups, language-specific paths, brand collections, or category pages with meaningful search value.

| Category role in the source store | PrestaShop data-model decision                                                         |
| --------------------------------- | -------------------------------------------------------------------------------------- |
| Permanent product family          | Usually belongs in category migration and validation.                                  |
| Campaign or seasonal grouping     | May need retirement, redirect, or target-side merchandising review.                    |
| SEO landing page                  | Requires URL, metadata, content, and redirect review, not just category-name transfer. |
| Customer-group-specific access    | Must be checked against group and visibility behavior.                                 |
| Multistore-specific catalog area  | Requires shop-scope review before migration acceptance.                                |
| Navigation-only menu item         | May belong to storefront setup instead of migrated catalog records.                    |

A category can be technically present and still fail its migration purpose. The stronger validation question is whether the category still helps customers find products, preserves important landing paths, and supports the target storefront structure.

### Customer Records and Customer Groups Need Separate Interpretation <a href="#customer-records-and-customer-groups-need-separate-interpretation" id="customer-records-and-customer-groups-need-separate-interpretation"></a>

PrestaShop customer migration should separate buyer identity from customer treatment. A Customer record may preserve name, email, address, order relationship, and account context. A customer group may affect how the storefront treats the buyer through pricing, discounts, tax behavior, access, or segmentation, depending on the store configuration.

The risk is treating groups as harmless labels. If groups influenced commercial behavior in the source store, the migration plan should define what that behavior should mean in PrestaShop. Wholesale buyers, retail buyers, loyalty members, trade accounts, tax-exempt customers, regional groups, and special access groups may all need different handling.

| Source customer pattern            | PrestaShop interpretation question                                  | Planning result                                                    |
| ---------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Ordinary retail customer           | Is standard customer migration enough?                              | Usually straightforward when identity and order history are clean. |
| Wholesale or trade customer        | Does the group affect price, discount, tax, or access?              | Group behavior needs preparation and validation.                   |
| Loyalty or membership buyer        | Is the value core data, module data, or external CRM data?          | May require Add-ons, Custom Service, or external-system handling.  |
| Guest buyer                        | Should order history remain readable without full account behavior? | Validate customer-order relationships and support expectations.    |
| Duplicate or inconsistent customer | Which record should staff trust after migration?                    | Cleaning, filtering, or post-migration review may be needed.       |

Customer-group migration should be judged by business meaning. A group that exists but no longer controls the right customer experience can create confusion for staff and buyers, even if the record count looks correct.

### Multistore Changes the Scope of Products, Categories, Customers, and URLs <a href="#multistore-changes-the-scope-of-products-categories-customers-and-urls" id="multistore-changes-the-scope-of-products-categories-customers-and-urls"></a>

PrestaShop multistore can make migration planning more powerful and more fragile. When multiple shops, domains, brands, languages, or B2B/B2C storefronts are managed through one back office, migrated records may need shop-specific interpretation.

A product may exist in one shop but not another. A category may belong to one storefront hierarchy. A customer group may apply differently by shop context. A CMS Page may support one storefront but not all of them. Friendly URLs, domains, and shop URLs may define where customers land after launch.

This means multistore migration is not merely a larger version of a single-store migration. It requires shop-scope governance.

| Multistore data area        | What must be clarified                                                          |
| --------------------------- | ------------------------------------------------------------------------------- |
| Products                    | Which shops should carry each product, price, visibility, or stock expectation? |
| Categories                  | Which catalog tree belongs to which shop or root category?                      |
| Customers and groups        | Whether segmentation applies globally or shop-specifically.                     |
| CMS Pages and Blog Posts    | Which storefront or language context owns the content.                          |
| Friendly URLs and shop URLs | Whether important old paths map cleanly to the correct target storefront.       |
| Modules and themes          | Whether behavior differs across shops, domains, or themes.                      |

If source data does not carry reliable shop context, the migration plan should avoid promising exact multistore preservation. Shop assignment may need source cleanup, supported mapping, Add-ons, Custom Service, or target-side governance.

### Orders Preserve History but Do Not Recreate Storefront Behavior <a href="#orders-preserve-history-but-do-not-recreate-storefront-behavior" id="orders-preserve-history-but-do-not-recreate-storefront-behavior"></a>

Order migration into PrestaShop should preserve useful historical meaning. Orders can help staff answer customer questions, review previous purchases, understand totals, check discounts, and maintain service continuity. But historical order data should not be mistaken for live target behavior.

A source order may contain statuses, payment method labels, shipment data, tax lines, discounts, vouchers, notes, module references, customer group context, and product snapshots. Some of this data may migrate as supported order history. Some may need custom review. Some may only remain as historical reference.

The migration plan should separate past commercial evidence from future PrestaShop setup. Live payment modules, shipping carriers, tax rules, voucher behavior, email templates, checkout flow, and module configuration are target-side operational areas. Their configuration should be prepared and validated separately from order-record migration.

| Order data area      | Migration meaning in PrestaShop                                                     |
| -------------------- | ----------------------------------------------------------------------------------- |
| Order status         | Historical status context may need interpretation, not exact workflow reproduction. |
| Payment method label | Useful for history, but not proof that the live payment module is configured.       |
| Shipping method      | Historical context, not automatic carrier setup.                                    |
| Voucher or discount  | May preserve order history but may not recreate active promotion logic.             |
| Tax lines            | Historical reference that still requires target-side tax configuration.             |
| Module references    | May require Custom Service review if the source behavior is business-critical.      |

Historical order validation should use representative examples: ordinary orders, refunded orders, discounted orders, orders with tax differences, orders tied to customer groups, and orders created through important modules.

### Modules, Themes, Overrides, and Custom Data Can Own Business Meaning <a href="#modules-themes-overrides-and-custom-data-can-own-business-meaning" id="modules-themes-overrides-and-custom-data-can-own-business-meaning"></a>

PrestaShop’s modular ecosystem is one of its strengths, but it also creates migration boundaries. Modules, themes, overrides, and custom fields may shape product pages, checkout behavior, discounts, loyalty, reviews, marketplace feeds, tax rules, shipping logic, payment behavior, SEO, analytics, and admin workflows.

The key migration question is whether the data belongs to supported PrestaShop records or to a custom/module-owned layer outside ordinary migration scope. A source store may show information in a way that appears native, while the actual value comes from a module or custom table. Without source review, that value can be missed, flattened, or migrated into the wrong place.

| Dependency type       | Why it matters for data migration                                                                  |
| --------------------- | -------------------------------------------------------------------------------------------------- |
| Module data           | May hold reviews, loyalty, subscriptions, bundles, advanced filters, or payment/shipping settings. |
| Theme behavior        | May display product or category fields that are not native target records.                         |
| Overrides/custom code | May alter product, customer, order, or checkout behavior beyond standard PrestaShop logic.         |
| External systems      | ERP, CRM, PIM, inventory, or accounting IDs may require custom mapping or integration review.      |
| Custom fields         | May need Add-ons if supported or Custom Service if non-standard handling is required.              |

Add-ons and Custom Service should be separated at this stage. Add-ons can support specific bounded filtering, mapping, or configuration needs within supported behavior. Custom Service should be considered when the requirement involves unsupported module data, bespoke transformation, external identifiers, Custom Platform sources, or custom migration logic adjustment.

### PrestaShop Data Model Review Should End With Acceptance Signals <a href="#prestashop-data-model-review-should-end-with-acceptance-signals" id="prestashop-data-model-review-should-end-with-acceptance-signals"></a>

The final data-model question is not whether PrestaShop has a place for every source value. It is whether the migrated result supports the target selling environment.

A product should be understandable as a PrestaShop product. Combinations should preserve selectable variation. Features should support product understanding and comparison. Customization fields should support customer personalization where relevant. Categories should help discovery. Customer groups should preserve meaningful buyer treatment. Multistore context should be intentional. Orders should remain useful for support. URLs and CMS Pages should support continuity. Module-owned or custom data should be either supported, handled through Add-ons, scoped for Custom Service, rebuilt in the target, or excluded intentionally.

| Data-model area           | Acceptance signal                                                                                                |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Products and combinations | Customers can choose the right purchasable version, and staff can validate SKU, price, stock, and image meaning. |
| Features                  | Product specifications remain useful without being confused with variation.                                      |
| Categories                | Browsing and landing-page structure still support discovery and revenue priorities.                              |
| Customer groups           | Commercial treatment is explainable and validated.                                                               |
| Multistore                | Shop assignment and URL context are intentional.                                                                 |
| Orders                    | Historical records remain readable and useful.                                                                   |
| Modules/custom data       | Handling path is known before launch.                                                                            |

This makes PrestaShop migration more than data preservation. It becomes a controlled translation of catalog, customer, storefront, and operational meaning into the target environment.

### Conclusion <a href="#conclusion" id="conclusion"></a>

PrestaShop data model differences matter because the platform gives structure to product variation, descriptive product information, customer personalization, customer groups, shop scope, category discovery, friendly URLs, modules, and historical order context. A migration can look complete while still weakening the way products are chosen, categories are browsed, customers are treated, orders are interpreted, or shop-specific records are governed.

The strongest PrestaShop data-model plan classifies source meaning before migration. It distinguishes combinations from features, personalization from variation, category structure from navigation clutter, customer records from customer treatment, multistore assignment from simple record volume, and supported data from module-owned or custom requirements.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are PrestaShop combinations so important during migration?**

Combinations represent selectable product variations built from attributes. If source product choices are not interpreted correctly, customers may lose the ability to select the right version, and staff may struggle to validate SKU, price, image, or stock behavior.

**Are PrestaShop features the same as product options?**

No. Features are intrinsic characteristics used to describe or compare products. They do not create product variations. Source values that customers select to buy a different version should be reviewed as variation or combination logic instead.

**Why do customer groups need special review in PrestaShop?**

Customer groups can affect buyer treatment depending on how the target store is configured. If groups influenced pricing, access, tax behavior, discounts, or segmentation in the source store, they should be validated as business logic rather than preserved as simple labels.

**Does multistore change how data should be migrated to PrestaShop?**

Yes. Multistore can change product visibility, category ownership, shop URLs, customer context, CMS Pages, and module behavior. The migration plan should define which records belong to which shop context before accepting the result.

**When does PrestaShop data require Custom Service review?**

Custom Service should be considered when the requirement involves unsupported module data, custom fields, external identifiers, bespoke transformation, Custom Platform sources, or custom migration logic adjustment beyond supported migration behavior.
