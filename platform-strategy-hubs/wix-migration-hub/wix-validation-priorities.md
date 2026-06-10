# Wix Validation Priorities

Validation for a Wix migration should prove that the migrated result works inside a hosted website and commerce environment, not only that records arrived. Wix often combines store data, website content, design structure, business apps, member areas, forms, bookings, blogs, CMS collections, SEO settings, and optional Velo or API-driven behavior. A strong validation process checks the records that customers see, the information staff use, and the connected workflows that keep the business running.

The most useful validation approach is sample-based and outcome-focused. Instead of checking only totals, review representative products, collections, customers, contacts, members, orders, pages, URLs, apps, and integration-sensitive records. The goal is to confirm whether the migrated Wix store can support real browsing, buying, order review, customer service, content continuity, and launch readiness.

### What Wix Validation Needs to Prove <a href="#what-wix-validation-needs-to-prove" id="what-wix-validation-needs-to-prove"></a>

A Wix migration should be validated across commerce, content, customer, storefront, and integration layers. Each layer answers a different question.

| Validation layer                 | What to prove                                                                                                                                     | Why it matters                                                                                                                   |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Storefront experience            | Shoppers can find products, read details, choose options, view prices, and move toward checkout.                                                  | A product can exist in the dashboard but still fail as a usable storefront item.                                                 |
| Product structure                | Products, options, choices, variants, modifiers, SKUs, images, inventory, and collections appear with the expected meaning.                       | Wix Stores product behavior may differ from the Source Platform’s product model.                                                 |
| Customer and audience records    | Customers, contacts, members, subscriptions, and account-related context remain understandable.                                                   | Wix may separate commerce buyers, contact records, member profiles, and app-specific user behavior.                              |
| Order history                    | Orders remain readable for customer service, finance, and operational review.                                                                     | Historical order value depends on context such as totals, payment labels, shipping labels, discounts, taxes, and customer links. |
| Checkout readiness               | Live checkout, payment, shipping, tax, delivery, pickup, and fulfillment behavior are configured and tested separately.                           | Migrated historical data does not automatically prove new order workflow readiness.                                              |
| Content and SEO                  | CMS Pages, Blog Posts, product pages, collection pages, metadata, redirects, and priority URLs support the intended launch experience.            | Wix is also a website platform, so content and URL continuity can affect perceived migration quality.                            |
| Apps and extensions              | Wix apps and business tools that shape bookings, events, restaurants, forms, memberships, subscriptions, or marketing are identified and checked. | App-owned data and workflows may not behave like standard store records.                                                         |
| Velo, APIs, and external systems | Custom code, API behavior, third-party IDs, and external-system relationships remain accounted for.                                               | Custom workflows often require mapping, configuration, accepted exclusions, or Custom Service review.                            |

### Validate Product and Catalog Meaning <a href="#validate-product-and-catalog-meaning" id="validate-product-and-catalog-meaning"></a>

Product validation should start with items that represent the real complexity of the store. Simple products are useful, but they rarely expose the most important Wix migration risks. A stronger sample includes products with multiple choices, variants, modifiers, images, SKUs, inventory rules, sale pricing, product ribbons or labels, collection placement, and SEO-sensitive product URLs.

#### Product samples to check <a href="#product-samples-to-check" id="product-samples-to-check"></a>

Review product samples that include:

* a simple product with standard price, image, SKU, and inventory;
* a product with several options, choices, or variant combinations;
* a product where choices affect price, SKU, inventory, image, or availability;
* a product with modifiers, personalization, add-ons, or custom option behavior;
* a digital product if the source store sells downloadable goods;
* a subscription, recurring, membership-linked, booking-linked, event-linked, or service-like product if used;
* products assigned to important collections or storefront filters;
* products with SEO-sensitive titles, descriptions, slugs, metadata, or image alt text.

The pass condition is not only that the product appears. The product should be easy to find, easy to understand, and usable in the target storefront. Customers should be able to select expected options, see correct prices, view images, understand availability, and move toward checkout without losing important product meaning.

### Validate Collections, Navigation, Filters, and Storefront Discovery <a href="#validate-collections-navigation-filters-and-storefront-discovery" id="validate-collections-navigation-filters-and-storefront-discovery"></a>

Wix stores can depend on more than product records. Collections, menus, product galleries, filters, search behavior, page layout, and app-driven display choices can determine whether customers can actually find the migrated catalog.

Validation should confirm that priority categories or collections remain meaningful in the new Wix store. If the source store used nested categories, brand pages, filtered product lists, landing pages, or custom merchandising paths, the migrated Wix result should be checked from the storefront, not only from the dashboard.

| Discovery area       | What to check                                                                                      | Pass condition                                                             |
| -------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Collections          | Products appear in the expected collections or equivalent Wix structures.                          | Important product groups are usable for browsing and merchandising.        |
| Menus and navigation | Store pages, product galleries, and collection links appear where customers expect them.           | Priority catalog paths are reachable without manual guesswork.             |
| Filters and sorting  | Relevant product attributes or choices support expected filtering where applicable.                | Customers can narrow the catalog in ways that match business expectations. |
| Product galleries    | Product lists display images, names, prices, ribbons, availability, and calls to action correctly. | Storefront presentation supports buying decisions.                         |
| Search behavior      | Key products can be found through search or planned browsing paths.                                | High-value products are discoverable after migration.                      |

### Validate Customers, Contacts, Members, and Audience Context <a href="#validate-customers-contacts-members-and-audience-context" id="validate-customers-contacts-members-and-audience-context"></a>

Wix can involve several audience-related layers: store customers, contacts, site members, form submissions, subscribers, bookings users, event attendees, restaurant customers, loyalty-related information, and app-specific records. These layers should not be validated as if they were one generic customer table.

A strong review checks whether customer identities, email addresses, phone numbers, addresses, account context, order links, marketing permissions, member status, and app-related relationships remain understandable. If the Source Platform separates wholesale accounts, customer groups, company accounts, memberships, or segmented audiences, the Wix result should be reviewed against the target structures that will actually support those relationships after launch.

Validation should answer practical questions: Can staff identify the customer? Can they see relevant order history? Can customer service understand the relationship between buyer, contact, member, and app activity? Are marketing or consent-sensitive fields handled within the approved scope?

### Validate Orders and Historical Commerce Context <a href="#validate-orders-and-historical-commerce-context" id="validate-orders-and-historical-commerce-context"></a>

Order validation should focus on readability and operational usefulness. Historical orders are often needed for customer service, finance, returns, disputes, fulfillment review, and business reporting. A migrated order record is useful only when its context remains understandable.

Review orders that represent different scenarios:

* paid and unpaid orders;
* fulfilled and unfulfilled orders;
* canceled, refunded, partially refunded, or partially fulfilled orders;
* orders with discounts, coupons, gift cards, tax, shipping, delivery, or pickup context;
* orders linked to customers, members, or contact records;
* orders with product variants, modifiers, or custom option selections;
* orders with app, marketplace, external payment, shipping, or accounting references.

The pass condition is that staff can read the order and understand what happened. The order should show the relevant customer, products, quantities, options, totals, payment labels, shipping labels, status context, and historical notes that matter for daily operations.

### Validate Checkout, Payment, Shipping, and Tax Separately <a href="#validate-checkout-payment-shipping-and-tax-separately" id="validate-checkout-payment-shipping-and-tax-separately"></a>

Historical order validation does not prove live checkout readiness. Wix checkout, payment providers, shipping rules, delivery methods, pickup settings, tax behavior, coupons, gift cards, subscriptions, and fulfillment workflows are target configuration concerns.

These areas should be tested separately from migrated records. A Wix store can have readable migrated orders while still needing additional setup for new transactions. Validation should confirm the target behavior that will be used after launch, especially when the store uses multiple shipping zones, tax rules, local delivery, pickup, third-party fulfillment, external payments, or subscription logic.

| Live setup area                    | What to test                                                                            | Why it is separate from migration acceptance                               |
| ---------------------------------- | --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Payment methods                    | Customers can complete checkout through the intended payment options.                   | Migrated payment labels do not activate payment providers.                 |
| Shipping and delivery              | Rates, zones, delivery, pickup, and fulfillment expectations work for target scenarios. | Historical shipping methods do not configure live delivery behavior.       |
| Tax                                | Tax settings match the launch requirements for relevant locations and products.         | Historical tax amounts do not establish future tax calculation.            |
| Coupons and discounts              | Active promotions behave as intended after setup.                                       | Migrated coupon history does not guarantee active discount rules.          |
| Subscription or recurring behavior | Recurring purchase expectations are confirmed where applicable.                         | Subscription behavior often depends on app, plan, and configuration logic. |

### Validate CMS Pages, Blog Posts, and Content-Led Commerce <a href="#validate-cms-pages-blog-posts-and-content-led-commerce" id="validate-cms-pages-blog-posts-and-content-led-commerce"></a>

Wix migrations often involve website content as much as commerce data. CMS Pages, Blog Posts, landing pages, policies, brand pages, galleries, forms, menus, images, and embedded content can shape the launch result. Content validation should check whether important pages are present, readable, linked correctly, and aligned with the intended Wix site structure.

For content-led stores, review the pages that contribute directly to revenue or trust: home page sections, category landing pages, product education pages, policy pages, shipping and return pages, FAQ pages, blog posts with traffic value, and pages used in ads or email campaigns. The result should not be judged only by product records when customers also rely on content to decide what to buy.

### Validate SEO, URLs, Domains, and Redirect Priorities <a href="#validate-seo-urls-domains-and-redirect-priorities" id="validate-seo-urls-domains-and-redirect-priorities"></a>

SEO validation should focus on priority continuity, not exhaustive perfection. Wix URL structure, page slugs, product URLs, collection paths, blog URLs, metadata, image alt text, canonical expectations, redirects, and domain configuration can affect launch quality.

Validation should include a short priority URL list. This list should cover top product pages, top category or collection pages, high-traffic blog posts, paid landing pages, backlinks, branded pages, and important policy pages. Each should be checked for target availability, redirect planning, metadata, page title, and customer-facing readability.

A strong pass condition is that the highest-value paths have a clear target outcome. Some URLs may be preserved, some may redirect, and some may intentionally change, but the decision should be visible before launch.

### Validate Apps, Velo, APIs, and External-System Dependencies <a href="#validate-apps-velo-apis-and-external-system-dependencies" id="validate-apps-velo-apis-and-external-system-dependencies"></a>

Wix App Market tools, Wix business apps, Velo code, APIs, webhooks, service plugins, third-party systems, CRM records, ERP references, fulfillment tools, analytics, email platforms, and automation logic can all affect migration quality. These dependencies should be validated as business workflows, not just as data fields.

If a source store relies on custom scripts, external IDs, headless behavior, app-owned records, product feeds, subscriptions, bookings, events, restaurants, wholesale workflows, or custom checkout logic, validation should confirm what was migrated, what must be configured separately, what is outside standard service capability, and what belongs in Custom Service review.

| Dependency type                     | Validation question                                                                          | Pass condition                                                                     |
| ----------------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Wix apps                            | Does the app support the expected post-migration workflow?                                   | App-related data and setup expectations are confirmed or excluded deliberately.    |
| Velo code                           | Does custom code depend on migrated identifiers or specific field structures?                | Required custom behavior is accounted for through configuration or Custom Service. |
| APIs and webhooks                   | Do external systems need stable IDs, events, or mapped fields?                               | Integration-sensitive records are sampled and reviewed.                            |
| External systems                    | Do CRM, ERP, fulfillment, accounting, analytics, or marketing tools depend on migrated data? | Required relationships are confirmed, remapped, or assigned to follow-up work.     |
| Custom catalog or checkout behavior | Does the source behavior have a Wix equivalent?                                              | Supported behavior is validated; unsupported behavior is scoped before launch.     |

### Interpret Demo Migration Results Carefully <a href="#interpret-demo-migration-results-carefully" id="interpret-demo-migration-results-carefully"></a>

Demo Migration should be treated as a structured proof sample. It is not a full launch approval by itself. The strongest Demo Migration review checks whether selected samples prove the key areas of the Wix migration: catalog behavior, product choices, variants, modifiers, customers, members, orders, content, SEO, apps, APIs, and integration-sensitive records.

If Demo Migration results show clean standard records but fail to prove complex products, app-owned data, custom checkout behavior, customer-member relationships, or URL continuity, the sample is too light. The next step should be to expand the sample, adjust Add-on use where appropriate, or move the relevant requirement into Custom Service review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix validation should confirm that the migrated store works as a hosted website and commerce environment, not merely that data exists in the target account. The most important proof comes from realistic samples: products with choices and variants, important collections, customer and member records, varied orders, key content pages, priority URLs, app-dependent workflows, and integration-sensitive data.

Use Demo Migration results to decide whether the Wix migration is ready for Full Migration, needs additional filtering or mapping through Add-ons, requires target setup work, or includes customization that should be reviewed through Custom Service before launch planning continues.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be checked first after a Wix Demo Migration?**

Start with the records that prove the store’s real operating model: complex products, variants, options, modifiers, collections, customers, members, varied orders, priority pages, and important URLs. These samples reveal more than simple record totals.

**Does a successful product count mean the Wix migration is valid?**

No. Product count only confirms that records were created. Validation should also check product choices, variants, modifiers, images, SKUs, inventory, collection placement, storefront display, pricing, and checkout usability.

**Should Wix checkout be validated separately from migrated orders?**

Yes. Migrated orders show historical order context. Live checkout, payment providers, shipping, delivery, pickup, tax, discounts, and fulfillment behavior depend on target setup and should be tested separately.

**Why should customers, contacts, and members be reviewed separately?**

Wix may use different structures for commerce customers, contacts, site members, subscribers, and app-related users. These records should be checked against the way the business will use them after launch.

**When do Wix validation results point to Custom Service?**

Custom Service should be reviewed when validation depends on custom product behavior, app-owned records, Velo code, API relationships, external-system identifiers, custom checkout logic, unsupported data structures, or tailored migration behavior beyond standard service capability.
