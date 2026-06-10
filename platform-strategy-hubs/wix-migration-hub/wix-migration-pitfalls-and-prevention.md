# Wix Migration Pitfalls and Prevention

Wix migrations usually run into problems when the project treats Wix as a simple destination for product, customer, order, and page records. Wix is a hosted website and commerce platform where product options, variants, modifiers, collections, storefront pages, checkout settings, payments, shipping, tax, apps, Velo code, APIs, members, contacts, CMS Pages, Blog Posts, URLs, and SEO settings can all affect the final outcome.

Good prevention starts before Full Migration. The project should identify the records and workflows that carry business meaning, test them through Demo Migration, and separate migrated data from target setup, design work, app behavior, and custom integration requirements.

### Pitfall 1: Treating Wix as a Simple Product and Order Target <a href="#pitfall-1-treating-wix-as-a-simple-product-and-order-target" id="pitfall-1-treating-wix-as-a-simple-product-and-order-target"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration is accepted because products, customers, and orders appear in Wix. The review does not confirm whether products are sellable through the intended Wix Stores setup, options and variants work correctly, collections and filters support storefront discovery, customer records connect to the expected account experience, or orders remain useful for business review.

This creates a false sense of readiness. The records may exist, but the store may still need configuration, page setup, checkout testing, app setup, or custom handling before launch.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* Demo Migration review focuses mainly on record totals.
* Product samples include only simple products.
* Collections, filters, product pages, store pages, and mobile storefront behavior are not checked.
* Customer, member, contact, app, and checkout assumptions are not separated.
* Target Wix site setup is still incomplete when migration results are reviewed.

#### Prevention <a href="#prevention" id="prevention"></a>

Judge Wix readiness by store behavior, not record presence. Select samples that prove products, collections, customers, orders, content, and storefront paths work in the target Wix environment.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

A merchant with product options, collections, Blog Posts, and app-supported reviews should review one complete product family, its collection placement, product page behavior, customer record, representative order, SEO fields, and app-dependent data before accepting the Demo Migration result.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

The migration result proves that representative records are usable inside Wix: products are sellable, collections and filters support browsing, customers and orders remain understandable, content appears in the expected target structure, and app or custom behavior is either handled or clearly excluded.

### Pitfall 2: Ignoring Product Options, Choices, Variants, Modifiers, and Inventory Differences <a href="#pitfall-2-ignoring-product-options-choices-variants-modifiers-and-inventory-differences" id="pitfall-2-ignoring-product-options-choices-variants-modifiers-and-inventory-differences"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products are migrated, but the buying choices do not behave correctly. Product options, choices, variant combinations, modifiers, variant prices, SKU values, barcode or GTIN values, shipping weights, preorder settings, stock, or product media may not match the way shoppers buy the product.

This is especially risky when the Source Platform uses configurable products, custom fields, product builders, add-on options, personalized inputs, bundle-like behavior, or inventory logic that does not translate into Wix options and variants directly.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* Product samples do not include options and variants.
* Modifiers are treated as ordinary variants even when separate inventory or pricing is not needed.
* SKU, barcode, GTIN, weight, cost, and inventory values are not checked at the variant level.
* Product media is reviewed only at the parent product level.
* Shoppers cannot select the intended option combination during testing.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Prepare product samples that expose real selling complexity. Include products with multiple options, many choices, variant-level values, modifiers, media differences, stock-sensitive combinations, and any required customer input.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

For a product with size, color, engraving text, and stock-sensitive SKUs, validate the option choices, modifier behavior, variant price, SKU, inventory, image display, shipping weight, and checkout behavior in Wix.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative products show the expected Wix option, choice, variant, modifier, media, SKU, and inventory behavior, and shoppers can select and purchase the intended product configuration.

### Pitfall 3: Assuming Source Design, Theme, or Custom Code Migrates Directly <a href="#pitfall-3-assuming-source-design-theme-or-custom-code-migrates-directly" id="pitfall-3-assuming-source-design-theme-or-custom-code-migrates-directly"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

The migration is expected to recreate the previous storefront design, theme code, custom templates, page-builder layout, or checkout customization exactly. Wix does not operate as a self-hosted theme and database environment, so storefront appearance and custom behavior often need to be rebuilt through Wix templates, editor settings, Wix Studio where used, apps, CMS structures, or Velo development.

This can cause launch delays when design and content work is discovered after the data migration has already been reviewed.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* The project expects source theme files, custom code, or database templates to move into Wix unchanged.
* Product, category, Blog Post, or landing page layout expectations are not documented.
* Mobile storefront behavior is not checked.
* Velo or app requirements are discussed only after Demo Migration.
* Design acceptance is mixed with data acceptance.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Separate data migration from storefront reconstruction. Define which pages, product layouts, collection displays, menus, mobile views, and custom interactions must be recreated in Wix, and determine whether they belong to standard setup, app configuration, Velo work, or Custom Service review.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A merchant with a custom product detail layout should validate migrated product data separately from the Wix product page design. If the layout requires custom interactions, the requirement should be reviewed as design, app, Velo, or Custom Service scope instead of being treated as ordinary migration output.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

The project has a clear distinction between migrated records and Wix storefront setup, and any design, editor, app, or Velo work needed for launch is planned before Full Migration acceptance.

### Pitfall 4: Accepting Products Without Checking Collections, Filters, and Storefront Discovery <a href="#pitfall-4-accepting-products-without-checking-collections-filters-and-storefront-discovery" id="pitfall-4-accepting-products-without-checking-collections-filters-and-storefront-discovery"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Products exist in Wix, but shoppers cannot find them through the intended collections, category pages, filters, menus, product galleries, landing pages, or storefront widgets. A catalog can look complete in the admin area while failing as a shopping experience.

This is common when the Source Platform uses nested categories, layered navigation, product tags, landing pages, merchandising rules, or custom search behavior.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* Product checks happen only from the product list.
* Collections and store pages are not reviewed.
* Filter values do not match shopper expectations.
* Menus, product galleries, landing pages, and product widgets are left until launch.
* Priority categories or high-revenue product paths are not sampled.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Validate discovery paths as part of the migration review. Important products should be checked through the page, collection, filter, menu, and product-gallery paths that shoppers will actually use.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A merchant with seasonal collections should review one product in the product list, collection page, filtered product gallery, menu path, related product area, and search result before accepting catalog migration quality.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Priority products can be discovered through the intended Wix collections, store pages, filters, menus, galleries, widgets, and search paths.

### Pitfall 5: Confusing Historical Orders with Live Checkout, Payment, Shipping, and Tax Readiness <a href="#pitfall-5-confusing-historical-orders-with-live-checkout-payment-shipping-and-tax-readiness" id="pitfall-5-confusing-historical-orders-with-live-checkout-payment-shipping-and-tax-readiness"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Migrated orders show payment labels, shipping labels, tax amounts, discounts, refunds, tracking values, or fulfillment status. These historical values are mistaken for proof that live Wix checkout, payments, shipping, tax, fulfillment, pickup, delivery, and notification behavior are ready for new orders.

Historical order readability and live checkout readiness are separate outcomes.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* Payment and shipping labels in old orders are treated as checkout proof.
* No live checkout test is performed in the configured Wix site.
* Shipping rules, pickup, delivery, tax settings, payment providers, fulfillment apps, or email notifications are still incomplete.
* Refund, cancellation, discount, and tracking cases are not sampled.
* Order review does not include customer-facing account behavior.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Review migrated orders for historical usefulness, then test live order creation through the configured Wix checkout. Payment, shipping, tax, fulfillment, pickup, delivery, and notification behavior should be checked as target setup, not as migrated history.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A merchant should review one migrated paid order for history, then place a new test order that confirms checkout fields, customer account behavior, payment method, shipping or pickup option, tax result, discount behavior, notification flow, and fulfillment status.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Historical orders are readable, and live checkout has been tested through the expected Wix payment, shipping, tax, fulfillment, pickup, delivery, and customer-account behavior.

### Pitfall 6: Overlooking Contacts, Members, Subscribers, Reviews, Loyalty, and App-Owned Customer Meaning <a href="#pitfall-6-overlooking-contacts-members-subscribers-reviews-loyalty-and-app-owned-customer-meaning" id="pitfall-6-overlooking-contacts-members-subscribers-reviews-loyalty-and-app-owned-customer-meaning"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Customers migrate as basic records, but the broader customer meaning is incomplete. Contacts, members, customer accounts, subscriber status, marketing consent, loyalty points, reviews, wishlists, saved payment details, forms, bookings, events, and app-owned customer records may not transfer as ordinary customer data.

This creates gaps for marketing, account access, customer service, membership experiences, and post-launch personalization.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* Customer review checks only name, email, and address.
* Members and contacts are treated as the same data type.
* Newsletter, consent, loyalty, review, wishlist, booking, event, or form records are not inventoried.
* App-owned customer data is expected to migrate without separate review.
* Saved payment details are expected to move into Wix as ordinary customer fields.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Separate customer records from contacts, members, subscribers, account behavior, consent, reviews, loyalty, and app-owned data. Identify which values are supported migration records, which require target setup, and which require Custom Service review or accepted exclusion.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A merchant with member accounts and loyalty data should review one customer with address history, member status, order history, subscriber status, review activity, loyalty context, and any app-owned customer data that affects post-launch operations.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Customer-related samples prove the required Wix meaning, and unsupported account, consent, loyalty, review, membership, saved-payment, or app-owned data is mapped, configured separately, routed to Custom Service, or accepted as excluded.

### Pitfall 7: Ignoring Apps, Velo, APIs, and External-System Identifiers <a href="#pitfall-7-ignoring-apps-velo-apis-and-external-system-identifiers" id="pitfall-7-ignoring-apps-velo-apis-and-external-system-identifiers"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The migration moves core store records but misses the values that connected workflows depend on. Wix apps, Velo code, commerce APIs, Stores APIs, service plugins, custom fees, shipping-rate logic, external payment handling, ERP, PIM, WMS, CRM, accounting systems, fulfillment tools, and marketplace tools can all depend on identifiers or relationships that are not obvious in a basic product and order review.

When these dependencies are missed, the store may launch with broken automations, disconnected reporting, missing fulfillment context, or lost external references.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* Apps are listed only by name, not by the data they control.
* Velo code, API usage, service plugins, custom checkout behavior, or external integrations are not inventoried.
* Product, customer, or order IDs used by outside systems are not sampled.
* The target integration plan is left until after migration acceptance.
* App-owned records are assumed to migrate as normal store data.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Inventory apps, Velo code, APIs, and external systems before Full Migration. Identify which identifiers must remain visible, which relationships need mapping, and which workflows need Custom Service review or post-migration reconfiguration.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A merchant connected to an ERP and fulfillment app should sample one product, one customer, and one order that include external IDs, fulfillment references, custom field values, and any API-dependent values needed for downstream workflows.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Integration-sensitive records are either migrated with usable meaning, rebuilt through target configuration, handled through Custom Service, or clearly excluded before launch planning proceeds.

### Pitfall 8: Leaving SEO, URLs, Canonical Behavior, and Redirects Until Launch <a href="#pitfall-8-leaving-seo-urls-canonical-behavior-and-redirects-until-launch" id="pitfall-8-leaving-seo-urls-canonical-behavior-and-redirects-until-launch"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Product, collection, page, and Blog Post content moves into Wix, but SEO-sensitive details are reviewed too late. URL slugs, title tags, meta descriptions, canonical behavior, structured data, image alt text, social sharing fields, redirects, and domain behavior may not match the previous store’s priority pages.

This can affect search visibility, paid-campaign landing paths, bookmarked URLs, marketplace references, and customer navigation after launch.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* SEO review begins only after Full Migration.
* Priority product, collection, category, page, and Blog Post URLs are not listed before migration.
* Redirect rules are not planned for changed paths.
* Canonical URLs, meta fields, alt text, and structured data are not sampled.
* Domain cutover expectations are not separated from migrated content.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Prepare an SEO and URL continuity set before Demo Migration. Include priority products, collections, CMS Pages, Blog Posts, landing pages, metadata, image alt text, canonical expectations, redirect rules, and domain requirements.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant with high-traffic category pages should prepare old URLs, expected Wix target URLs, title tags, meta descriptions, canonical expectations, redirect rules, and landing page content for the most valuable product and collection paths.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Priority Wix URLs, metadata, canonical behavior, alt text, redirects, and domain expectations are reviewed before launch, and any unavoidable changes are accepted with a redirect or SEO plan.

### Pitfall 9: Using Record Counts Alone to Accept Demo Migration <a href="#pitfall-9-using-record-counts-alone-to-accept-demo-migration" id="pitfall-9-using-record-counts-alone-to-accept-demo-migration"></a>

#### What Goes Wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

Demo Migration is accepted because record totals appear close to expectations. The review does not test the records that carry the most business risk, such as variant-heavy products, modifiers, app-dependent customers, complex orders, content pages, SEO-sensitive URLs, or external-system references.

This weakens the value of Demo Migration as a decision point and can hide problems until Full Migration or launch preparation.

#### Early Warning Signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

* The Demo Migration checklist contains mostly totals.
* Reviewers do not open complex product, customer, order, content, and SEO samples.
* Apps, Velo, APIs, and external systems are not represented in the sample set.
* The project cannot explain why each sample was chosen.
* Acceptance happens before target Wix setup assumptions are confirmed.

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Design Demo Migration samples around risk, not convenience. Include records that represent real catalog, customer, order, content, SEO, app, and integration complexity.

#### Recommendation Example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

A strong Wix Demo Migration sample set should include a simple product, a variant product, a product with modifiers, a priority collection, a customer with order history, a member/contact case, a refunded or fulfilled order, a CMS Page, a Blog Post, a priority URL, and an app or integration-sensitive record.

#### Pass Condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Demo Migration acceptance is supported by sample-level proof. The project can show that high-risk Wix data and workflows are represented, validated, and either accepted, corrected, excluded, or escalated before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix migration issues usually come from assuming that visible records are enough. A reliable migration review should prove that the new Wix store can support the way products are bought, how customers and members are understood, how orders remain useful, how checkout is configured, how content and SEO continue, and how apps or external systems affect daily operations.

Before approving Full Migration, use Demo Migration to test the records that matter most: variant-heavy products, modifiers, collections, customer and member examples, complex orders, CMS Pages, Blog Posts, priority URLs, app-dependent records, Velo/API requirements, and external-system identifiers. If those samples reveal behavior that standard migration handling cannot represent, clarify whether Add-ons, target setup, accepted exclusions, or Custom Service review are needed before launch planning continues.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the most common mistake in a Wix migration?**

The most common mistake is accepting the migration because record counts look correct. Wix validation should also check product options, variants, modifiers, collections, customer and member meaning, order readability, checkout setup, content, SEO, apps, APIs, and external-system dependencies.

**Why do Wix product options and variants need extra review?**

Wix uses product options, choices, variants, and modifiers in specific ways. A source product with custom options, configurable products, personalized inputs, or stock-sensitive combinations may not behave correctly unless those buying choices are sampled and reviewed in the target Wix store.

**Does a migrated order prove that Wix checkout is ready?**

No. Migrated orders can prove historical readability, but they do not configure or verify live checkout. Payment providers, shipping rules, tax settings, fulfillment behavior, pickup, delivery, discounts, and customer account behavior should be tested separately in the configured Wix site.

**Should apps and Velo code be reviewed before migration?**

Yes. Wix apps, Velo code, APIs, and external integrations can control data or workflows that are not part of ordinary product, customer, order, or page records. They should be inventoried before Full Migration so their data, identifiers, exclusions, or Custom Service requirements are clear.

**How should Demo Migration be accepted for Wix?**

Demo Migration should be accepted through sample-level proof, not record counts alone. Review complex products, collections, customers, members, orders, content, URLs, SEO values, app-dependent records, and integration-sensitive data before deciding whether the migration path is ready for Full Migration.
