# Storeden Validation Priorities

A Storeden migration should be validated by checking whether the migrated result works as a Storeden store, not only whether records appear in the new account. Products, customers, orders, content, marketplace context, apps, and integration references must remain understandable inside a hosted cloud commerce environment.

Validation should focus on the records and workflows that carry the most business meaning. A product with variants, attributes, stock, marketplace relevance, images, and SEO values is more useful than a simple product when judging migration quality. An order with payment, shipping, tracking, tax, customer, channel, and external-system context is more useful than an order that only proves a record count.

### What Validation Should Prove in Storeden <a href="#what-validation-should-prove-in-storeden" id="what-validation-should-prove-in-storeden"></a>

Storeden validation should prove that migrated data can support daily store management, customer service, product discovery, sales-channel coordination, and launch decisions. It should also identify what belongs to target configuration rather than migration output.

| Validation area                          | What should be checked                                                                                                          | Why it matters                                                                                                  |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Product records                          | Names, descriptions, prices, images, categories, SKUs, visibility, and selling status.                                          | Products must be usable for merchandising, management, and storefront review.                                   |
| Variants and attributes                  | Option names, attribute values, SKU relationships, price differences, images, and stock behavior.                               | Product choices must remain clear to shoppers and manageable for the store team.                                |
| Inventory                                | Stock quantities, inventory status, product availability, and external stock references where relevant.                         | Inventory mistakes can affect selling, marketplace synchronization, and fulfillment planning.                   |
| Categories, filters, and discovery       | Category placement, subcategories, filters, tags, navigation, search behavior, and marketplace-facing organization.             | A product can exist in Storeden but still be hard to find or incorrectly grouped.                               |
| Customer and account data                | Customer identity, contact details, account context, B2B indicators, and external references where applicable.                  | Customer-service teams need readable customer records and meaningful account history.                           |
| Order history                            | Products, customer links, totals, discounts, taxes, payment labels, shipping methods, tracking, statuses, and channel origin.   | Order history should remain useful for support, finance, fulfillment, and management.                           |
| Payment, shipping, and logistics context | Historical payment and shipping labels, tracking values, logistics references, and fulfillment context.                         | Historical values must be readable, while live checkout and logistics setup must be tested separately.          |
| Marketplace data                         | Amazon, eBay, Facebook, AliExpress, or other channel-related identifiers, publication context, and order/channel references.    | Multichannel stores need to know what remains connected, what is reference-only, and what must be reconfigured. |
| Apps, APIs, and TeamSystem integrations  | App-owned fields, ERP or accounting identifiers, inventory-system references, API-dependent records, and workflow expectations. | Connected workflows often carry meaning outside standard product, customer, or order fields.                    |
| Storefront, content, URLs, and SEO       | Themes, menus, CMS Pages, landing content, product/category URLs, redirects, metadata, and domain expectations.                 | A technically successful data migration may still need storefront and search-continuity review.                 |

### Validate Products Beyond Record Counts <a href="#validate-products-beyond-record-counts" id="validate-products-beyond-record-counts"></a>

Product validation should begin with a focused group of records that represents the store’s real catalog. Simple products are useful, but they rarely expose the areas where Storeden migration quality can fail.

#### Product details and merchandising values <a href="#product-details-and-merchandising-values" id="product-details-and-merchandising-values"></a>

Check product names, descriptions, pricing, images, categories, visibility, and SEO fields. Product pages should make sense to shoppers and store managers, not only exist in the back office.

For high-value products, compare how the product is presented, how it is grouped, and how it can be found. Storeden validation should confirm that the migrated product supports selling and management in the target environment.

#### Variants, attributes, SKUs, and options <a href="#variants-attributes-skus-and-options" id="variants-attributes-skus-and-options"></a>

Products with variants and attributes should be reviewed carefully. Variant names, option combinations, SKU relationships, price differences, image behavior, stock values, and attribute meaning should remain clear.

If the source store used custom options, configurable products, unusual modifiers, bundles, or marketplace-specific product fields, validation should confirm whether the result is acceptable inside Storeden or whether mapping, configuration, or Custom Service review is needed.

#### Inventory and availability <a href="#inventory-and-availability" id="inventory-and-availability"></a>

Inventory validation should check stock values, availability status, product visibility, and any external inventory references that matter to the business. This is especially important when Storeden is expected to support marketplace selling or TeamSystem ecosystem workflows after launch.

A product should not be accepted simply because it migrated. It should be checked for whether it can be managed, sold, hidden, restocked, synchronized, or excluded correctly in the new environment.

### Validate Storefront Discovery <a href="#validate-storefront-discovery" id="validate-storefront-discovery"></a>

Storefront discovery is where catalog structure becomes visible to shoppers. Categories, subcategories, filters, tags, navigation, search behavior, and marketplace organization should be tested with realistic browsing paths.

A strong validation sample should include products that belong to multiple categories, products that depend on filters, products with variant choices, and products that are important for marketplace or campaign traffic.

| Discovery item               | Validation question                                                                             |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| Categories and subcategories | Are products placed in the right browsing structure?                                            |
| Filters and tags             | Can shoppers narrow products in a way that matches the intended catalog logic?                  |
| Navigation and menus         | Can priority categories and products be reached from expected paths?                            |
| Search behavior              | Are important product names, SKUs, attributes, or descriptors discoverable?                     |
| Marketplace visibility       | Are channel-relevant products ready for review before marketplace synchronization is accepted?  |
| SEO-sensitive paths          | Do priority product and category URLs support the intended redirect and search-continuity plan? |

### Validate Customers, Accounts, and B2B Context <a href="#validate-customers-accounts-and-b2b-context" id="validate-customers-accounts-and-b2b-context"></a>

Customer validation should confirm more than names and email addresses. Check contact details, account identity, customer-to-order relationships, billing or shipping information, and any external references that the business uses for service, accounting, marketing, or integrations.

If the source store used customer groups, B2B pricing, wholesale logic, approval workflows, account-specific terms, or app-managed customer behavior, those areas should be treated as meaning-sensitive. They may not behave like ordinary customer records in Storeden.

B2B-related validation should focus on what the merchant needs after launch: whether the data is readable, whether the target account or app configuration supports the expected behavior, and whether any unsupported source logic needs Custom Service review.

### Validate Orders as Business Records <a href="#validate-orders-as-business-records" id="validate-orders-as-business-records"></a>

Historical order validation should check whether old orders remain useful for customer service, fulfillment review, accounting reference, and management reporting. An order should be evaluated as a business record, not only as a migrated item.

#### Strong order samples <a href="#strong-order-samples" id="strong-order-samples"></a>

Use varied order examples, including paid, unpaid, fulfilled, unfulfilled, canceled, refunded, partially fulfilled, discounted, taxed, marketplace-originated, and tracked orders where available. Orders with multiple products, variant products, different shipping methods, and customer-account relationships are especially useful.

#### Payment, shipping, tax, and logistics context <a href="#payment-shipping-tax-and-logistics-context" id="payment-shipping-tax-and-logistics-context"></a>

Review historical payment labels, shipping methods, tracking numbers, logistics references, tax lines, discount values, order statuses, and fulfillment context. These values help teams understand past transactions after migration.

Live payment, TS Pay, shipping, logistics, tax, and checkout behavior should be validated as target setup. Historical order labels do not prove that new checkout, payment, shipping, or logistics workflows are ready for launch.

### Validate Marketplace and Channel Context <a href="#validate-marketplace-and-channel-context" id="validate-marketplace-and-channel-context"></a>

Storeden’s multichannel model makes marketplace validation important when the source store used Amazon, eBay, Facebook, AliExpress, or other sales channels. Marketplace-related data may include product identifiers, channel availability, feed-related values, publication state, order origin, inventory expectations, or external references.

Validation should identify which values migrated as Storeden data, which remain reference-only, and which must be reconnected or reconfigured after migration. This prevents a false pass where products and orders are present but marketplace workflows are not ready.

For marketplace-sensitive stores, validation should include at least one product or order from each important channel, plus products where marketplace rules affect price, availability, description, title, inventory, or images.

### Validate Apps, APIs, and TeamSystem Integration References <a href="#validate-apps-apis-and-teamsystem-integration-references" id="validate-apps-apis-and-teamsystem-integration-references"></a>

Apps, plugins, API workflows, ERP connections, accounting tools, inventory systems, POS systems, fulfillment tools, and TeamSystem ecosystem integrations can carry meaning outside standard Storeden fields. Validation should check whether those references remain usable, need remapping, or should be excluded from standard acceptance.

| Integration-sensitive area        | What to validate                                                                               | Possible result                                                                            |
| --------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| App-owned product data            | Custom product values, app-specific flags, additional catalog logic, or marketing fields.      | Accepted as migrated data, reconfigured through app setup, or reviewed for Custom Service. |
| ERP or accounting references      | External product IDs, customer IDs, order IDs, invoice references, or management-system codes. | Preserved, remapped, or documented as outside standard migration scope.                    |
| Inventory or warehouse references | External stock IDs, warehouse indicators, synchronization expectations, or availability rules. | Confirmed usable, reconfigured after migration, or escalated for review.                   |
| Marketplace identifiers           | Channel product IDs, listing references, feed values, and channel-order context.               | Preserved where supported, reconnected through channel setup, or handled separately.       |
| API or webhook logic              | External workflows that depend on stable identifiers or custom data structures.                | Rebuilt, remapped, or reviewed under Custom Service.                                       |

### Validate Storefront Presentation, Content, URLs, and SEO <a href="#validate-storefront-presentation-content-urls-and-seo" id="validate-storefront-presentation-content-urls-and-seo"></a>

Storeden validation should include storefront review because migration quality is not limited to back-office records. Themes, menus, static content, CMS Pages, landing pages, policy pages, product pages, category pages, metadata, URLs, redirects, and domain expectations can all affect launch quality.

Theme and content validation should focus on whether the new store communicates the right information and supports the intended customer journey. Source themes or custom frontend behavior should not be assumed to transfer as-is.

SEO validation should prioritize the pages that already carry search, paid campaign, marketplace, or customer-service value. Check product URLs, category URLs, metadata, image text where relevant, redirects, canonical expectations, and domain behavior before launch readiness is approved.

### Separate Migration Validation from Target Setup Testing <a href="#separate-migration-validation-from-target-setup-testing" id="separate-migration-validation-from-target-setup-testing"></a>

Storeden validation should separate migrated-data acceptance from target-configuration readiness. Both matter, but they prove different things.

| Review area            | Migration validation proves                                  | Target setup testing proves                                                            |
| ---------------------- | ------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| Products               | Product data is present, structured, and meaningful.         | Products can be sold, displayed, managed, and synchronized as intended.                |
| Orders                 | Historical order context remains readable and useful.        | New orders can be placed, paid, fulfilled, and tracked.                                |
| Payments               | Historical payment labels and references are understandable. | TS Pay, gateways, wallets, or other payment methods are configured correctly.          |
| Shipping and logistics | Historical shipping and tracking values are readable.        | Live shipping, logistics, tracking, and fulfillment workflows operate correctly.       |
| Tax                    | Historical tax values remain understandable where migrated.  | New tax behavior is configured for the target selling model.                           |
| Marketplaces           | Channel references are present where supported.              | Marketplace synchronization, publication, and channel rules are configured correctly.  |
| Apps and integrations  | App or external references are preserved where included.     | Apps, APIs, ERP, accounting, or TeamSystem workflows operate in the target account.    |
| Storefront and SEO     | Migrated content and metadata can be reviewed.               | Theme, navigation, redirects, domain, and search-continuity behavior are launch-ready. |

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation results should be classified by decision impact. Not every issue means the migration failed, but every issue should be assigned to the right next action.

| Validation result            | Meaning                                                                                                                          | Recommended action                                                                              |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Expected and acceptable      | Data appears correctly and supports Storeden operation.                                                                          | Mark the area as accepted.                                                                      |
| Minor correction needed      | Data is mostly usable, but a small wording, display, or mapping issue remains.                                                   | Correct through supported settings, mapping, or a targeted adjustment where available.          |
| Target configuration needed  | Migrated data is acceptable, but live behavior depends on Storeden setup.                                                        | Complete and test target configuration before launch.                                           |
| Add-on review needed         | Filtering, supported mapping, or supported data configuration would improve the outcome.                                         | Review Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure where appropriate. |
| Custom Service review needed | Custom Platform source behavior, app data, external identifiers, custom logic, or unsupported transformation affects acceptance. | Move the requirement into Custom Service review.                                                |
| Accepted exclusion           | The data or behavior is outside the agreed migration scope.                                                                      | Document the exclusion and confirm the business can proceed without it.                         |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden validation should prove that the migrated store can operate meaningfully inside a hosted multichannel commerce environment. Strong validation checks products, variants, inventory, discovery, customers, orders, payments, shipping, logistics, marketplaces, apps, APIs, TeamSystem references, storefront content, URLs, and SEO continuity.

Before approving Full Migration results, compare the Demo Migration or final output against the records that matter most to the business. Use Live Chat when validation shows unclear mapping, missing business meaning, integration-sensitive data, or a difference between migrated history and live Storeden setup.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after migrating to Storeden?**

Start with products, variants, inventory, categories, customers, and orders that represent real business complexity. Then review marketplace data, apps, integrations, storefront content, URLs, and SEO values that affect launch quality.

**Is record count enough to approve a Storeden migration?**

No. Record count only confirms that records exist. Storeden validation should also check whether those records remain meaningful for selling, order review, customer service, inventory management, marketplace activity, storefront discovery, and connected workflows.

**Should payment and shipping setup be validated as part of migration?**

Historical payment and shipping values should be reviewed as migrated order context. Live payment, TS Pay, shipping, logistics, tracking, tax, and checkout behavior should be tested separately as Storeden target setup.

**How should marketplace data be validated in Storeden?**

Use products and orders that represent each important channel. Check whether channel identifiers, availability, order origin, inventory expectations, and marketplace-facing values are preserved, reconfigured, or outside the agreed scope.

**When does Storeden validation point to Custom Service?**

Custom Service review is appropriate when validation depends on Custom Platform source logic, app-owned records, TeamSystem or ERP identifiers, marketplace-specific data, API or webhook workflows, custom product transformations, or custom migration logic adjustment.
