# J2Store Data Model Differences

J2Store data should not be reviewed as a simple list of products, customers, and orders. Because J2Store operates inside Joomla, commercial meaning can sit across Joomla articles, J2Store product settings, product types, options, modules, menus, templates, payment plugins, shipping plugins, tax configuration, and extension-owned behavior.

The practical data-model question is not only whether a source field has a target field. The stronger question is whether the target store can preserve the way that data works for shoppers, administrators, search engines, and post-launch operations. A product that looks complete in the target administration area can still be incomplete if its Joomla article content, option behavior, shipping profile, tax rules, menu path, or storefront module context has been lost.

### How J2Store Changes Data Meaning <a href="#how-j2store-changes-data-meaning" id="how-j2store-changes-data-meaning"></a>

J2Store changes migration planning because it connects commerce data to Joomla site architecture. Many source platforms treat products as independent commerce records. In J2Store, product meaning may depend on a Joomla article, category structure, menu path, module position, template layout, product type, app behavior, and checkout configuration.

| Data area            | Common source-platform assumption                                    | J2Store interpretation                                                                                                                                |
| -------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product content      | Product title, description, images, and price form the product page. | Product content may also be Joomla article content with category, metadata, menu, and presentation meaning.                                           |
| Product type         | Product type is often a broad catalog label.                         | Product type can determine selling behavior, option logic, file delivery, stock handling, and validation needs.                                       |
| Options and variants | Options are often treated as one variant table.                      | J2Store options may represent shopper choices, variant combinations, file access, personalization, pricing changes, or implementation-specific logic. |
| Categories           | Categories are usually catalog organization only.                    | Categories may affect Joomla content organization, menu paths, product listings, modules, and discovery flow.                                         |
| Checkout rules       | Tax, shipping, payment, and discounts are often store settings.      | Some behavior belongs to J2Store configuration, apps, plugins, or target setup rather than direct record migration.                                   |
| Storefront display   | Layout is often theme-controlled inside the commerce platform.       | Display may involve Joomla templates, modules, menu items, overrides, and content placement.                                                          |

A successful migration plan classifies each source element by business meaning before deciding where it belongs. Some records are standard migration scope. Some target behavior must be recreated through configuration. Some extension-owned or custom fields require deeper review before they can be treated as supported scope.

### Joomla Article and Product Relationship <a href="#joomla-article-and-product-relationship" id="joomla-article-and-product-relationship"></a>

The most distinctive J2Store data-model issue is the relationship between Joomla articles and products. In many implementations, product pages are not just commerce records. They can be Joomla content items with J2Store product settings attached to them. That means product data can inherit meaning from Joomla content structure as well as from the commerce layer.

This matters when the source platform has rich descriptions, buying guides, product-story content, embedded images, tabs, specifications, SEO metadata, and landing-page relationships. A flat product export may not show how much content belongs to the sellable page and how much belongs to surrounding content architecture.

| Source data element      | Migration question for J2Store                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------ |
| Product long description | Should it become article body content, product description content, or a structured content block?     |
| Product metadata         | Should it follow the product record, the Joomla article, the menu item, or a target SEO configuration? |
| Product landing page     | Is it a product page, Joomla article, category listing, menu item, or module-driven page?              |
| Embedded buying guide    | Is it part of the product page or separate Joomla content that supports conversion?                    |
| Existing product URL     | Does continuity depend on aliases, menus, redirects, or article/category structure?                    |

The important point is that a product should remain sellable and explainable, not merely present. If the source product depends on content formatting, reusable modules, SEO aliases, or category landing pages, those relationships should be reviewed before treating the product as a standard record conversion.

### Product Types, Options, and Selling Behavior <a href="#product-types-options-and-selling-behavior" id="product-types-options-and-selling-behavior"></a>

J2Store product type is not just a classification label. It shapes how the product behaves. A simple product, product with options, variable product, configurable product, downloadable product, or subscription-like implementation can carry different commercial assumptions. Source platforms may store similar behavior through variants, attributes, custom options, downloadable file records, app data, or custom fields.

| Product behavior             | Why it matters in J2Store planning                                                                                  |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Simple product               | Usually suitable when the product has one sellable identity and no variant-level stock or pricing.                  |
| Option-based product         | Requires review of whether options are cosmetic, price-changing, stock-changing, or order-line-critical.            |
| Variable product             | Requires combination logic, SKU behavior, stock behavior, and price behavior to be preserved where supported.       |
| Configurable option behavior | Requires dependency review because not every source option relationship translates as a flat option list.           |
| Downloadable product         | Requires file access, order status, customer access, and delivery rules to be reviewed, not only file names.        |
| Custom product logic         | May require Custom Service if source behavior is app-owned, coded, conditional, or unsupported by standard mapping. |

The same visible option label can mean different things. “Size” may be a simple shopper choice, a separate SKU, a stock-bearing variant, a price modifier, a shipping modifier, or part of a custom production workflow. During migration, the label is less important than the operational meaning attached to it.

### Catalog Organization and Discovery Paths <a href="#catalog-organization-and-discovery-paths" id="catalog-organization-and-discovery-paths"></a>

Catalog data in J2Store sits close to Joomla site structure. Categories, manufacturers, filters, product modules, related products, menu items, and landing pages can all influence how shoppers find products. Source category names are not enough to prove that catalog discovery will remain usable.

A migration plan should distinguish between taxonomy and navigation. Taxonomy explains how products are grouped. Navigation explains how shoppers reach those groups. A source platform may use collection pages, tag filters, vendor pages, search facets, or custom landing pages. J2Store may need category assignments, Joomla menu items, modules, template positions, and filter behavior to recreate the intended path.

| Catalog relationship     | Decision value                                                                                        |
| ------------------------ | ----------------------------------------------------------------------------------------------------- |
| Product categories       | Confirm hierarchy, multi-category placement, and landing-page expectations.                           |
| Manufacturers or brands  | Confirm whether they are product attributes, manufacturer records, filters, or content pages.         |
| Tags and filters         | Confirm whether they become product metadata, Joomla tags, module behavior, or custom implementation. |
| Related products         | Confirm whether relationship data should migrate, be regenerated, or be managed manually.             |
| Menu-based catalog paths | Confirm whether URLs, aliases, breadcrumbs, and category pages depend on Joomla menus.                |

This is where Demo Migration sample selection becomes important. Samples should include ordinary products, multi-category products, filtered products, products tied to manufacturer pages, and products with SEO-sensitive routes.

### Customers, Orders, and Commercial History <a href="#customers-orders-and-commercial-history" id="customers-orders-and-commercial-history"></a>

Customer and order data in J2Store must be interpreted as commercial history, not just archived records. Customers may connect to Joomla users. Orders may include customer details, billing and shipping addresses, payment status, shipping method, tax totals, discount totals, coupon usage, purchased product options, downloadable access, and order statuses.

| Historical data        | What should be preserved or reviewed                                                                               |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Customer profiles      | Identity, address details, Joomla user relationship, and repeat-customer context.                                  |
| Orders                 | Line items, options selected, totals, tax, shipping, payment method, order status, and historical reference value. |
| Coupons and discounts  | Whether codes, usage history, discount totals, or future rule behavior need to be preserved.                       |
| Downloadable purchases | Whether customers need continued access to files or only historical order evidence.                                |
| Order statuses         | Whether source statuses map cleanly to target statuses or require interpretation.                                  |

The target store does not need to reproduce every historical behavior as live behavior. For example, an old payment method may be important inside past orders but not active for new checkout. A retired shipping method may need to remain visible for historical reference but not available for future transactions. This distinction prevents historical data review from being confused with live configuration setup.

### Checkout, Tax, Shipping, and Payment Configuration <a href="#checkout-tax-shipping-and-payment-configuration" id="checkout-tax-shipping-and-payment-configuration"></a>

Some source data describes what happened in the past. Other source data describes how the store should behave in the future. Checkout, tax, shipping, and payment data often sits between those two meanings.

A historical order should preserve the payment method used, shipping method selected, tax amount charged, discount applied, and final total. Future checkout behavior, however, depends on target configuration, plugins, region rules, tax zones, shipping rules, payment gateway setup, and testing. Migrating historical evidence does not automatically recreate live checkout behavior.

| Source item                  | Historical meaning                                | Target behavior question                                             |
| ---------------------------- | ------------------------------------------------- | -------------------------------------------------------------------- |
| Payment method on old order  | Shows how the order was paid or recorded.         | Should the same gateway be configured for future checkout?           |
| Shipping method on old order | Shows how fulfillment was calculated or selected. | Does the target store need the same shipping rules, zones, or rates? |
| Tax total                    | Preserves accounting reference.                   | Are target tax classes, zones, and rates configured correctly?       |
| Coupon usage                 | Shows historical discount evidence.               | Should coupon rules be recreated for future use?                     |
| Custom checkout field        | Preserves operational information.                | Is the field supported, configurable, or custom?                     |

This distinction should guide validation. The reviewer should not approve checkout migration because old orders show totals correctly. Live checkout must still be tested separately with representative products, addresses, customer statuses, coupons, payment methods, and shipping scenarios.

### Joomla Storefront and Presentation Data <a href="#joomla-storefront-and-presentation-data" id="joomla-storefront-and-presentation-data"></a>

J2Store storefront output can depend on Joomla templates, modules, menu items, layout overrides, article content, and extension settings. This creates a data-model boundary that is easy to miss. Some information looks like “content,” some looks like “design,” and some affects conversion directly.

A migration should classify storefront dependencies before assuming that commerce records alone can recreate the store. Product lists may rely on modules. Product pages may rely on article content and template overrides. Category pages may rely on menu aliases. Promotional blocks may be Joomla modules rather than product data. SEO continuity may depend on menu structure and redirects.

| Storefront dependency | Why it affects data meaning                                                              |
| --------------------- | ---------------------------------------------------------------------------------------- |
| Joomla menu items     | Can control aliases, routing, breadcrumbs, and page discovery.                           |
| Modules               | Can display product lists, featured products, banners, filters, and promotional content. |
| Template overrides    | Can change how product fields, prices, buttons, and layouts appear.                      |
| Article content       | Can carry product explanation and conversion content.                                    |
| Redirects and aliases | Can preserve or break SEO-sensitive product and category paths.                          |

These dependencies are not all standard migration records. Some may need target configuration, manual content review, Add-ons, or Custom Service depending on the source and target requirements.

### Extension-Owned and Custom Data <a href="#extension-owned-and-custom-data" id="extension-owned-and-custom-data"></a>

J2Store stores often rely on apps, plugins, custom fields, integrations, and custom code. These elements can create data that looks like ordinary store data but is actually owned by a specific implementation. Common examples include custom checkout fields, subscription logic, invoice customizations, third-party shipping rules, payment metadata, accounting identifiers, CRM links, reporting tables, and custom product fields.

The migration plan should separate three categories:

| Data category                    | Planning implication                                                                                                 |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Standard supported data          | Can usually be mapped through the normal migration scope if supported by the selected source and target.             |
| Configuration-dependent behavior | Should be rebuilt or configured in the target store rather than treated as migrated records.                         |
| Custom or extension-owned data   | Requires review before promising support, especially when fields, tables, identifiers, or behavior are non-standard. |

Custom Service should be reviewed when required data cannot be explained by standard J2Store entities or normal configuration. Add-ons may support defined optional behaviors, but they should not be used as a vague answer for unsupported extension logic.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Store data-model planning is about preserving commercial meaning inside a Joomla-connected store. Products may also be Joomla content. Options may represent variant behavior, customization, pricing, files, stock, or order-line meaning. Categories may affect both organization and storefront discovery. Orders preserve historical evidence, while checkout behavior requires target configuration and testing.

A strong migration plan classifies source data by function before mapping it into J2Store. That classification should cover product type, article relationship, options, catalog discovery, customers, orders, tax, shipping, payment, Joomla presentation, extensions, and custom data. The result is not only a target store with records, but a target store that remains understandable, testable, and operational.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why does J2Store data mapping depend on Joomla articles?**

J2Store can connect product meaning to Joomla content, categories, menus, metadata, and presentation. Product records should therefore be reviewed with their Joomla article and storefront context, not only as commerce fields.

**Are product options the same as variants in J2Store?**

Not always. Options may represent simple choices, variant combinations, price modifiers, personalization fields, downloadable access, or custom logic. Their business meaning should be classified before mapping.

**Does migrating old orders recreate checkout behavior?**

No. Historical orders can preserve payment, shipping, tax, discount, and status evidence, but future checkout behavior depends on target configuration, plugins, zones, gateways, and testing.

**When does J2Store data require Custom Service review?**

Custom Service should be reviewed when required data is stored in custom tables, unsupported apps, non-standard fields, integrations, custom checkout behavior, or source logic that cannot be mapped through standard entities.

**What should be tested after Demo Migration?**

Review products with different product types, option behavior, categories, customer and order history, tax/shipping/payment evidence, Joomla routes, modules, template output, and any custom or extension-owned data.
