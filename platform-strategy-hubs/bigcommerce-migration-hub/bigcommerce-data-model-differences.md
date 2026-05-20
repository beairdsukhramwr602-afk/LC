# BigCommerce Data Model Differences

A migration into BigCommerce can preserve familiar storefront content while changing how the store defines product choices, pricing context, catalog structure, storefront scope, and customer segmentation.

BigCommerce is a governed hosted Target Platform, so migrated data often needs to fit clearer target-side structures than the Source Platform used. The issue is not only whether Products, Customers, Orders, categories, or URLs can move. The more important question is whether the moved data still carries the same commercial meaning once BigCommerce represents choices through variants and modifiers, organizes discovery through categories, applies differentiated pricing through customer groups or price lists, and manages route continuity through redirect rules.

That makes a BigCommerce data model review a meaningful exercise, not just a record transfer exercise. A migration can appear complete yet remain commercially weak if the target store uses the wrong product-choice model, applies pricing in the wrong customer context, places products in unclear category structures, or preserves a URL without preserving the destination intent.

### How BigCommerce Changes Commercial Meaning <a href="#how-bigcommerce-changes-commercial-meaning" id="how-bigcommerce-changes-commercial-meaning"></a>

BigCommerce often makes hidden source-store assumptions more explicit. Stores that previously relied on loosely governed option logic, customer-type workarounds, custom pricing rules, extension behavior, or manually managed redirects may need those behaviors translated into clearer target-side structures.

This can be valuable. BigCommerce can support a more governed catalog, customer, pricing, and storefront behavior than many merchants have used before. But it also means the migration must prove that the target model reflects the business reality, not only that data appears in the admin.

### Core BigCommerce Data Layers to Review <a href="#core-bigcommerce-data-layers-to-review" id="core-bigcommerce-data-layers-to-review"></a>

#### Product Options, Variants, and Modifiers <a href="#product-options-variants-and-modifiers" id="product-options-variants-and-modifiers"></a>

One of the most important BigCommerce data-model differences is the separation between true sellable variation and surrounding option behavior.

A product option may lead to a true variant when the choice represents a distinct sellable version of the product. That usually matters for SKU, inventory, image, price, or purchasable product identity. A modifier can support customer-facing choice or customization without necessarily carrying the same inventory or SKU meaning.

This distinction matters during migration because many Source Platforms blur together:

* true purchasable variations
* personalization inputs
* add-on choices
* option-dependent price behavior
* bundled or app-driven buying logic
* display-only selections

If these meanings are translated into the wrong BigCommerce structure, the storefront may still show options, but the buying journey, stock control, pricing result, or order interpretation can change.

#### Inventory and SKU Meaning <a href="#inventory-and-sku-meaning" id="inventory-and-sku-meaning"></a>

BigCommerce product structure affects how inventory and SKU meaning should be interpreted. A size, color, package, material, or configuration choice may need to become a variant if it represents a distinct sellable item. A non-stocked customization choice may belong elsewhere.

This is where a visually similar migrated product can still be operationally wrong. The customer may be able to select an option, but the business may lose the intended relationship between choice, stock, fulfillment, reporting, or product identity.

#### Categories and Catalog Discovery <a href="#categories-and-catalog-discovery" id="categories-and-catalog-discovery"></a>

Categories in BigCommerce are not only filing containers. They can shape browsing, merchandising, navigation, product grouping, and customer discovery.

A Source Platform may have used categories loosely, duplicated product placement, menu-only groupings, or SEO-driven landing pages that did not map cleanly into the product taxonomy. During migration, the question is not only whether categories exist. The stronger question is whether the new BigCommerce structure still helps customers find the right products and still supports the business’s merchandising logic.

#### Customer Groups and Price Lists <a href="#customer-groups-and-price-lists" id="customer-groups-and-price-lists"></a>

BigCommerce can make pricing context more explicit through structures such as customer groups and price lists. That changes what migrated pricing means.

A product price is not always enough. Some stores need different customer types, wholesale buyers, regional conditions, B2B terms, or negotiated pricing behavior to remain meaningful after migration. If the source store carried that logic through custom rules, extensions, discount workarounds, or off-platform processes, the BigCommerce target needs a clear decision about what should become native pricing context, what needs configuration, and what should remain outside the migrated data layer.

#### Multi-Storefront and Storefront Context <a href="#multi-storefront-and-storefront-context" id="multi-storefront-and-storefront-context"></a>

When BigCommerce Multi-Storefront is relevant, data may carry storefront-specific meaning. A product, category, price rule, redirect destination, or customer-facing experience can be correct in one storefront context and wrong in another.

That means migration review must check not only whether the data exists, but also whether it belongs to the right storefront context and supports the intended customer journey there. Storefront scope affects catalog visibility, navigation, pricing interpretation, and route planning.

#### Redirects and Route Continuity <a href="#redirects-and-route-continuity" id="redirects-and-route-continuity"></a>

BigCommerce route continuity should be reviewed as part of the data model because URLs, redirects, and destination relevance help preserve how customers and search engines interpret the store.

A redirect can technically exist while still being weak if it sends visitors to a less relevant product, an overly broad category, a different storefront context, or a page that no longer supports the same purchase intent. For BigCommerce migration planning, route continuity should be tied to product, category, and storefront meaning rather than treated as a disconnected SEO task.

#### Custom Fields, Apps, and Theme-Owned Meaning <a href="#custom-fields-apps-and-theme-owned-meaning" id="custom-fields-apps-and-theme-owned-meaning"></a>

Not every important BigCommerce outcome lives inside a simple core record. Many stores depend on custom fields, apps, theme behavior, external systems, or specialized storefront logic.

Those layers can affect badges, product recommendations, shipping behavior, product-detail presentation, customer-specific messaging, subscription logic, bundled offers, quote workflows, or reporting. A migration can preserve base records while losing the logic that made those records useful.

When custom fields, app-owned data, or source-side modifications affect storefront behavior or operations, the review should determine whether the requirement can be handled through standard target structures, Add-ons, or Custom Service.

### What Migrated Data Must Prove in BigCommerce <a href="#what-migrated-data-must-prove-in-bigcommerce" id="what-migrated-data-must-prove-in-bigcommerce"></a>

#### Products Must Prove Choice Accuracy <a href="#products-must-prove-choice-accuracy" id="products-must-prove-choice-accuracy"></a>

Product validation should confirm that variants, modifiers, product options, SKUs, inventory, images, and price-impacting choices represent the intended customer and operational behavior. The review should include simple products, complex variant products, customizable products, and products that relied on source-side apps or custom logic.

#### Categories Must Prove Discovery Accuracy <a href="#categories-must-prove-discovery-accuracy" id="categories-must-prove-discovery-accuracy"></a>

Category validation should confirm that products appear in the right groups, navigation remains understandable, merchandising intent is preserved, and important landing paths still point customers toward the right destination.

#### Pricing Must Prove Context Accuracy <a href="#pricing-must-prove-context-accuracy" id="pricing-must-prove-context-accuracy"></a>

Pricing review should not stop at visible product price. It should confirm customer-group behavior, price-list behavior, discounts, negotiated pricing assumptions, storefront context, and any source-side pricing logic that needed translation.

#### Customer and Order Data Must Prove Continuity <a href="#customer-and-order-data-must-prove-continuity" id="customer-and-order-data-must-prove-continuity"></a>

Customer and order review should confirm that customer identity, order history, account continuity, addresses, customer-group context, and commercial interpretation remain usable. The goal is not only historical record survival; the goal is for the target store to support customer service, reporting, and future selling decisions.

#### Storefront and Route Data Must Prove Journey Accuracy <a href="#storefront-and-route-data-must-prove-journey-accuracy" id="storefront-and-route-data-must-prove-journey-accuracy"></a>

When storefront scope or route continuity matters, migrated data should prove that customers can still reach the right product, category, content, or storefront destination. A correct record with a weak path can still create business risk.

### Where BigCommerce Data-Model Review Should Start <a href="#where-bigcommerce-data-model-review-should-start" id="where-bigcommerce-data-model-review-should-start"></a>

The earliest review should focus on the parts of the store where the Source Platform’s meaning is least likely to match BigCommerce directly.

#### High-Priority Review Areas <a href="#high-priority-review-areas" id="high-priority-review-areas"></a>

Start with:

* complex products with variants, modifiers, add-ons, bundles, or personalization
* categories that drive navigation, merchandising, or SEO landing pages
* customer groups, wholesale pricing, segmented pricing, or price-list behavior
* multi-storefront assignment and storefront-specific visibility
* high-value product and category URLs
* custom fields, apps, theme behavior, and external-system dependencies
* Custom Platform source logic that did not follow a standard data model

These areas usually reveal whether the BigCommerce target structure is commercially coherent or merely populated.

### How Custom Platform Sources Change BigCommerce Data-Model Review <a href="#how-custom-platform-sources-change-bigcommerce-data-model-review" id="how-custom-platform-sources-change-bigcommerce-data-model-review"></a>

When the Source Platform is a Custom Platform, BigCommerce data-model review usually needs a more bespoke translation lens.

The source may carry product-choice logic, customer segmentation, pricing behavior, route patterns, content relationships, or external-system identifiers in structures that do not map cleanly to BigCommerce. In those cases, the key question is not only what data should move. It is how the source meaning should be rebuilt so the BigCommerce Target Platform remains usable, governable, and commercially accurate.

Custom Platform sources often require earlier review of variant/modifier interpretation, price context, storefront scope, custom fields, redirect planning, and external-system dependencies. When those requirements involve customization, modification, bespoke transformation, or custom migration logic adjustment, they belong under Custom Service rather than being treated as ordinary standard handling.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce data-model differences matter because they can change how the migrated store understands product choice, category discovery, pricing context, storefront scope, customer meaning, and route continuity.

A successful migration into BigCommerce should not be judged only by whether products, customers, orders, and categories appear in the target. It should be judged by whether the target structure supports the same commercial decisions the business needs after launch. The strongest review starts with the areas where meaning is most likely to change: variants and modifiers, categories, customer groups, price lists, storefront context, redirects, custom fields, apps, and Custom Platform source logic.

Use Demo Migration results to test whether the BigCommerce model represents your most important product, pricing, customer, and storefront behaviors correctly before treating the target data model as settled. If the results reveal unclear product-choice logic, customer-specific pricing gaps, storefront-scope issues, or Custom Platform translation risk, Live Chat can help determine whether the migration needs Add-ons, Custom Service, or a different preparation plan before full execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What is one of the biggest BigCommerce data-model differences?**

One of the biggest differences is that BigCommerce often expects clearer separation between true variants and surrounding modifier or customization behavior. This affects SKU meaning, inventory control, pricing behavior, and how customers make product choices.

**Are BigCommerce categories just administrative folders?**

No. Categories can affect browsing, navigation, product grouping, merchandising, and landing-page meaning. Migration review should confirm that categories still support discovery, not only that category records exist.

**Why do customer groups and price lists matter in BigCommerce migration?**

They can make pricing part of a governed customer or storefront context rather than only a product-level field. That matters when the source store used wholesale pricing, customer-specific pricing, negotiated pricing, or segmentation logic.

**Does Multi-Storefront change how BigCommerce data should be reviewed?**

Yes. When Multi-Storefront is relevant, products, categories, prices, redirects, and customer-facing behavior may need to be reviewed by storefront context, not only as general store-wide records.

**When does a BigCommerce data-model migration need Custom Service?**

Custom Service is usually relevant when the Source Platform uses custom product logic, custom pricing behavior, app-owned data, external-system identifiers, bespoke transformations, Custom Platform structures, or custom migration logic adjustment that cannot be treated as standard target mapping.
