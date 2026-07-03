# PrestaShop Constraints and Risks

PrestaShop migration risk usually appears where structured target behavior meets unclear source meaning. The platform can support strong catalog control, customer segmentation, multistore governance, friendly URLs, modules, themes, and custom behavior, but those strengths become risky when migration assumptions are vague.

The main risk is not that data fails to arrive. The main risk is that migrated data arrives without the right PrestaShop meaning. Products may exist, but combinations may not represent the right purchasable choices. Categories may exist, but discovery may still feel disorganized. Customers may migrate, but customer groups may not preserve the right commercial treatment. Orders may be readable, but historical payment or shipping labels may be mistaken for live target setup. Modules may have shaped the old storefront, but their data may not be part of standard migration behavior.

PrestaShop risk review should therefore connect each platform constraint to a business consequence and a mitigation path. The goal is not to make the migration sound difficult. The goal is to identify which assumptions must be checked before Demo Migration, Full Migration, and launch.

### Where PrestaShop Risk Concentrates <a href="#where-prestashop-risk-concentrates" id="where-prestashop-risk-concentrates"></a>

PrestaShop risk concentrates in records that carry more than one meaning. Product options can represent variation, specification, personalization, bundle logic, or module behavior. Categories can act as browse paths, admin folders, SEO landing pages, access-controlled groups, or multistore structures. Customer groups can be labels, price-control structures, tax contexts, discount segments, or access rules. Modules and themes can display storefront behavior that is not visible in a simple export.

A good risk review should identify where the source store hides decisions that PrestaShop expects to be explicit.

| Risk area                        | Why it matters in PrestaShop                                                                                     |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Product structure                | Combinations, attributes, features, and customization fields have different target meanings.                     |
| Category and discovery structure | Categories affect browsing, product grouping, metadata, friendly URLs, and sometimes group access or shop scope. |
| Customer groups                  | Groups may affect commercial treatment, not just segmentation labels.                                            |
| Multistore                       | Products, categories, CMS Pages, URLs, and configuration may need shop-specific governance.                      |
| Friendly URLs and routes         | SEO continuity requires more than record presence.                                                               |
| Modules, themes, and overrides   | Business behavior may live outside standard core records.                                                        |
| Historical orders                | Order records preserve history but do not configure live payment, shipping, tax, or voucher behavior.            |

The following constraints should be reviewed as risk chains: assumption, platform constraint, operational consequence, mitigation, and validation signal.

### Constraint 1: Product Options Can Be Misclassified <a href="#constraint-1-product-options-can-be-misclassified" id="constraint-1-product-options-can-be-misclassified"></a>

A common source-store assumption is that every product option should migrate into one target option structure. PrestaShop makes that assumption unsafe because product meaning can belong to several layers.

Combinations represent purchasable variations based on attributes. Features describe stable product characteristics. Customization fields support customer-entered personalization. Modules may create add-ons, bundles, advanced filters, or product-page behavior that does not belong neatly to any standard field. If these meanings are not classified, the migrated product can look present but behave incorrectly.

| Assumption                                  | PrestaShop constraint                                                 | Business consequence                                                            | Mitigation                                                             | Validation signal                                           |
| ------------------------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ----------------------------------------------------------- |
| All source options are variations.          | Combinations should represent selectable product versions.            | Descriptive data may become unnecessary variations, increasing catalog clutter. | Classify source options by buying function.                            | Representative products show correct purchasable choices.   |
| Specifications can become combinations.     | Features are descriptive and do not create variations.                | Customers may see confusing choices or staff may overmanage product versions.   | Separate specifications from selectable variation.                     | Product pages display features without forcing selection.   |
| Personalization is just an order note.      | Customization fields may be needed for customer-entered product data. | Personalized products may lose required buying inputs.                          | Identify text, upload, engraving, or personalization flows.            | Personalization samples can be reviewed in target behavior. |
| Module-created options are ordinary fields. | Module data may sit outside supported migration behavior.             | Important product behavior may be missing after migration.                      | Inventory modules and custom product extensions before scope approval. | Module-dependent products have a defined handling path.     |

This constraint affects any store with configurable products, personalized products, module-created product options, product comparison needs, or product lines where wrong variation logic changes the buying journey.

### Constraint 2: Category Continuity Can Fail Even When Categories Migrate <a href="#constraint-2-category-continuity-can-fail-even-when-categories-migrate" id="constraint-2-category-continuity-can-fail-even-when-categories-migrate"></a>

Categories in PrestaShop can affect more than catalog organization. They can shape customer browsing, product discovery, visibility, SEO metadata, friendly URLs, and sometimes shop or group context. A category tree that exists in the target is not automatically a successful migration result.

The risk is strongest when the source store has old campaign categories, duplicate product groupings, deep trees, SEO landing pages, brand paths, manually curated navigation, or categories tied to access rules. Copying everything into PrestaShop may preserve disorder instead of supporting the target storefront.

| Risk pattern                                              | Operational impact                                                         | Mitigation approach                                               |
| --------------------------------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Old categories are copied without review.                 | Customers encounter cluttered or outdated navigation.                      | Identify high-value browse paths and retire low-value structures. |
| SEO category pages are treated as ordinary folders.       | Search continuity may weaken if URLs, metadata, and redirects are ignored. | Prioritize important category landing pages and route decisions.  |
| Categories are assigned globally in a multistore context. | Products may appear in the wrong shop or storefront.                       | Define shop-specific category ownership.                          |
| Group-restricted categories are not checked.              | Buyer access or visibility expectations may change.                        | Validate customer-group and category visibility assumptions.      |

The mitigation is not simply to create a cleaner category tree. The merchant must decide which source categories still serve a real target purpose and how PrestaShop should represent that purpose.

### Constraint 3: Customer Groups Can Preserve Labels but Lose Commercial Meaning <a href="#constraint-3-customer-groups-can-preserve-labels-but-lose-commercial-meaning" id="constraint-3-customer-groups-can-preserve-labels-but-lose-commercial-meaning"></a>

Customer groups can be valuable in PrestaShop because they may influence customer treatment. They can support segmentation, access expectations, discounts, pricing assumptions, or tax-related behavior depending on the target configuration. The risk is migrating group names without preserving or revalidating the behavior behind them.

A source store may have used customer groups, roles, tags, wholesale flags, loyalty states, company accounts, or module-owned customer attributes. Some of those meanings may fit PrestaShop customer groups. Others may require module review, target-side setup, Add-ons, Custom Service, or exclusion.

| Customer group risk                         | Why it matters                                                           | Control point                                                      |
| ------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Groups are imported as labels only.         | Pricing, visibility, access, tax, or discount expectations may not hold. | Define what each group should control.                             |
| Wholesale and retail buyers are mixed.      | Staff may not trust customer treatment after launch.                     | Validate high-value customer samples and their group assignments.  |
| Loyalty or membership data is module-owned. | Supported customer migration may not preserve business logic.            | Identify source owner and target handling path.                    |
| Old workaround groups remain active.        | Target store inherits unnecessary complexity.                            | Retire or filter groups that no longer support business operation. |

Customer-group review should occur before service-path approval. If the target behavior is simple and supported, Standard Service or Add-ons may be enough. If behavior depends on custom fields, outside systems, or module data, Custom Service review may be required.

### Constraint 4: Multistore Scope Can Hide Assignment Errors <a href="#constraint-4-multistore-scope-can-hide-assignment-errors" id="constraint-4-multistore-scope-can-hide-assignment-errors"></a>

PrestaShop multistore can allow several front offices to be managed from one back office. That capability becomes risky when the migration plan treats all records as if they belong to one global store.

Products, categories, prices, customers, CMS Pages, URLs, modules, and themes may need shop-specific interpretation. A product that belongs in one shop may not belong in another. A category tree may be correct for one storefront but not another. A URL can be technically valid but point to the wrong shop context. A module may behave differently by shop, domain, language, or theme.

| Multistore assumption                     | Risk                                                                | Mitigation                                                |
| ----------------------------------------- | ------------------------------------------------------------------- | --------------------------------------------------------- |
| All products belong everywhere.           | Products may appear in irrelevant storefronts.                      | Define shop assignment before migration.                  |
| One category tree fits all shops.         | Brand, language, B2B/B2C, or regional storefronts may lose clarity. | Map root categories and shop-specific paths.              |
| Customer groups apply globally.           | Buyer treatment can become inconsistent.                            | Define whether group behavior is global or shop-specific. |
| One URL plan covers all shops.            | Redirects and landing paths may fail by domain or shop.             | Validate shop URLs and priority routes.                   |
| Modules behave consistently across shops. | Storefront behavior may differ after launch.                        | Review module configuration by shop context.              |

Multistore risk should be handled through scope governance, not late cleanup. If the source store cannot provide reliable shop assignment, the merchant should not approve a target result based only on aggregate counts.

### Constraint 5: Friendly URLs and SEO Routes Need More Than Field Transfer <a href="#constraint-5-friendly-urls-and-seo-routes-need-more-than-field-transfer" id="constraint-5-friendly-urls-and-seo-routes-need-more-than-field-transfer"></a>

PrestaShop can support friendly URLs, metadata, category paths, product pages, CMS Pages, and shop URLs, but SEO continuity still requires migration planning. A source URL is not preserved just because the target product or category exists.

The risk is treating URLs as a formatting detail rather than a launch-critical relationship between old customer paths and new PrestaShop destinations. Product routes, category routes, CMS Pages, image paths, language paths, and multistore domains can all affect traffic continuity.

| URL or SEO risk                                       | What can go wrong                                               | Prevention                                                         |
| ----------------------------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------ |
| Product URLs are generated without redirect planning. | Indexed pages and backlinks may lose their destination.         | Map priority product URLs before launch.                           |
| Category URLs are reviewed only by category name.     | High-value landing pages may not be protected.                  | Validate category metadata and redirect paths.                     |
| CMS Pages are ignored.                                | Trust, policy, buying-guide, or campaign content may disappear. | Identify CMS Pages that should migrate, be rebuilt, or redirected. |
| Multistore domains are not checked.                   | Customers may land on the wrong storefront.                     | Validate shop URLs and domains separately.                         |
| Module-created landing pages are assumed native.      | Important pages may be missed.                                  | Identify module or theme ownership before scope approval.          |

The mitigation is to prioritize high-value routes. Not every old URL deserves equal effort, but revenue-driving products, categories, CMS Pages, and search-visible paths should be reviewed before launch.

### Constraint 6: Module, Theme, and Override Dependencies Can Be Invisible in Standard Data <a href="#constraint-6-module-theme-and-override-dependencies-can-be-invisible-in-standard-data" id="constraint-6-module-theme-and-override-dependencies-can-be-invisible-in-standard-data"></a>

PrestaShop stores often depend on modules, themes, overrides, or custom code. These can affect discounts, payment, shipping, reviews, loyalty, product options, checkout behavior, SEO fields, filters, feeds, marketplaces, inventory, or admin workflows. The problem is that this behavior may not appear clearly in ordinary exported records.

A migration can preserve core Products, Customers, Orders, Categories, Coupons, CMS Pages, and Blog Posts while still missing module-owned business meaning. This is especially risky when the merchant expects the target store to behave like the source store without identifying which behavior came from extensions or customization.

| Dependency                    | Risk if ignored                                                     | Likely handling path                               |
| ----------------------------- | ------------------------------------------------------------------- | -------------------------------------------------- |
| Module-owned product data     | Product pages may lose add-ons, bundles, filters, or reviews.       | Custom Service review or target-side module setup. |
| Theme-displayed custom fields | Important visible content may not migrate as standard data.         | Field mapping review, Add-ons, or Custom Service.  |
| Overrides/custom code         | Target behavior may differ even when data is present.               | Custom Service or target-side development review.  |
| External identifiers          | ERP, PIM, CRM, or accounting continuity may break.                  | Custom Service review when IDs must be preserved.  |
| Payment/shipping modules      | Historical records may remain, but live behavior is not configured. | Target-side setup and validation.                  |

The control is to inventory dependencies before Full Migration. If a value affects customer experience, order processing, reporting, or operational continuity, it should have an explicit migration or setup path.

### Constraint 7: Historical Orders Can Be Misread as Live Configuration <a href="#constraint-7-historical-orders-can-be-misread-as-live-configuration" id="constraint-7-historical-orders-can-be-misread-as-live-configuration"></a>

Historical orders are useful, but they do not configure the live PrestaShop store. The migration plan should preserve readable order history where supported while separating that history from active payment, carrier, tax, discount, voucher, email, and workflow setup.

This distinction matters because PrestaShop stores often rely on modules for payment, shipping, tax, or order-management behavior. A migrated order may show a payment method label, shipping method name, voucher, tax line, or order status, but that does not prove the equivalent live behavior is ready.

| Historical order element   | Common mistaken assumption           | Correct risk control                            |
| -------------------------- | ------------------------------------ | ----------------------------------------------- |
| Payment method label       | The payment module is configured.    | Test live payment setup separately.             |
| Shipping method label      | The carrier is ready for launch.     | Configure and validate carriers in PrestaShop.  |
| Voucher or discount record | Active promotion logic is recreated. | Review active rules separately from history.    |
| Tax line                   | Target tax rules are ready.          | Validate tax configuration and sample checkout. |
| Order status               | Workflow behavior is identical.      | Validate target order states and staff process. |

Order validation should include representative history, not just totals. Discounted, refunded, module-created, customer-group-specific, multistore, and high-value orders should be included if those patterns exist in the source store.

### PrestaShop Risk Review Should Produce a Handling Path <a href="#prestashop-risk-review-should-produce-a-handling-path" id="prestashop-risk-review-should-produce-a-handling-path"></a>

A PrestaShop risk review should not end with a list of concerns. Each concern needs an action path. The most useful classification separates supported migration, Add-ons, Custom Service, target-side setup, manual cleanup, and accepted exclusions.

| Finding type                                                            | Handling path                                                                    |
| ----------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Supported product, customer, order, category, CMS Page, or coupon data  | Standard Service or Managed Service depending on execution and validation needs. |
| Supported records need filtering or mapping adjustment                  | Add-ons where the requirement stays within supported behavior.                   |
| Custom fields, module-owned data, external IDs, bespoke transformations | Custom Service review.                                                           |
| Live payment, shipping, tax, theme, module, or checkout configuration   | Target-side setup and validation, not ordinary data migration.                   |
| Old categories, groups, or records no longer needed                     | Filtering, cleanup, exclusion, or manual retirement.                             |
| Unclear source behavior                                                 | Demo Migration sample and scope review before Full Migration.                    |

This classification protects PrestaShop migrations from two opposite mistakes: underestimating custom behavior and over-escalating ordinary supported migration work.

### Conclusion <a href="#conclusion" id="conclusion"></a>

PrestaShop migration risks concentrate where source data needs clearer target meaning. Product options must be classified as combinations, features, customization fields, module-owned behavior, or custom scope. Categories must support discovery and SEO continuity. Customer groups must preserve meaningful buyer treatment. Multistore scope must be governed intentionally. Friendly URLs and CMS Pages require route continuity planning. Modules, themes, overrides, and custom fields must be separated from standard records.

The safest PrestaShop migration plan turns each risk into a handling path before launch. Supported records can follow the appropriate Migration Service path. Supported filtering, mapping, or configuration needs may use Add-ons. Unsupported module data, custom fields, external identifiers, or bespoke transformations should be reviewed for Custom Service. Live target behavior such as payment, shipping, tax, modules, and themes should be configured and validated separately from migrated history.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can PrestaShop products migrate but still behave incorrectly?**

Products can appear in PrestaShop while their meaning is assigned to the wrong structure. Selectable choices, specifications, personalization, module data, and product-page behavior need different handling. If those meanings are mixed, the product can look complete but fail during customer selection or staff validation.

**What is the biggest category risk in a PrestaShop migration?**

The biggest category risk is preserving category records without preserving customer discovery. Categories should be reviewed for browsing logic, product assignments, metadata, friendly URLs, group access, and shop context where relevant.

**When do customer groups create migration risk?**

Customer groups create risk when they affect pricing, discounts, tax treatment, access, visibility, or buyer segmentation. In those cases, groups should be validated as commercial behavior rather than simple labels.

**Does multistore always require Custom Service?**

No. Multistore does not automatically require Custom Service. It requires clear shop-scope planning and validation. Custom Service becomes relevant when shop assignment, custom behavior, unsupported fields, or bespoke transformation falls outside supported migration behavior.

**Why should module dependencies be reviewed before Full Migration?**

Modules can own important product, checkout, payment, shipping, SEO, loyalty, review, or reporting data. If module-owned behavior is assumed to be standard data, the migrated PrestaShop result may miss business-critical functionality or require late Custom Service review.
