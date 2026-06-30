# Squarespace Migration Pitfalls and Prevention

Squarespace migration problems usually appear when a project treats Squarespace as a simple cart destination instead of a hosted content-first commerce Target Platform. Products, Store Pages, templates, sections, pages, Blog Posts, media, checkout settings, customer/contact records, orders, inventory, subscriptions or payment plans, SEO controls, redirects, domains, apps, APIs, and external integrations can all affect the final result.

The prevention approach is not to overcomplicate every project. It is to identify which parts of the Source Platform can move as records, which parts must be configured inside Squarespace, which parts require Add-ons, and which parts need Custom Service review before launch decisions are made.

### Pitfall 1: Treating Squarespace as a Generic Cart Migration <a href="#pitfall-1-treating-squarespace-as-a-generic-cart-migration" id="pitfall-1-treating-squarespace-as-a-generic-cart-migration"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration is planned around products, customers, and orders only. Store Pages, site pages, Blog Posts, templates, sections, media, navigation, redirects, checkout setup, and domain launch work are treated as secondary details even though they shape how Squarespace operates after migration.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

The scope mentions record counts but not Store Pages, site structure, content, SEO, redirects, design expectations, or launch responsibilities. The merchant expects the old storefront experience to appear automatically after the data transfer.

#### Prevention <a href="#prevention" id="prevention"></a>

Define Squarespace as a hosted content-first commerce Target Platform at the start of the project. Separate migrated records from site setup, design implementation, checkout configuration, integration work, and launch tasks. Confirm which pages, product discovery paths, commerce settings, and content areas must be ready before the target store can be accepted.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

For a content-led brand moving from a plugin-based store, include representative products, Store Pages, landing pages, Blog Posts, media, product URLs, redirects, and checkout configuration in the Demo Migration review instead of checking product records alone.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The migration plan identifies migrated records, Squarespace configuration tasks, site/content rebuild expectations, SEO and redirect responsibilities, Add-ons, Custom Service review points, and accepted exclusions before Full Migration.

### Pitfall 2: Assuming Product Structures Will Behave the Same Way <a href="#pitfall-2-assuming-product-structures-will-behave-the-same-way" id="pitfall-2-assuming-product-structures-will-behave-the-same-way"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products appear in Squarespace, but their selling behavior, product types, variants, options, images, inventory, service-product handling, digital downloads, gift cards, or subscription/payment-plan context no longer match the source experience.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

The source catalog includes complex option logic, product builders, bundled items, custom price rules, downloadable products, service products, gift cards, recurring purchase behavior, or specialized inventory rules, but the migration sample checks only simple products.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Group products by selling model before migration. Test ordinary products, variant-heavy products, media-heavy products, service products, digital or gift-card-style products, low-stock products, hidden products, SEO-sensitive products, and products controlled by apps or external systems. Use Add-ons for supported field or mapping needs, and use Custom Service review when source product logic has no direct Squarespace equivalent.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

If the source store has products with many variants and custom configuration choices, choose a Demo Migration sample that includes the largest variant sets, products with multiple images, products with important SEO fields, and products connected to inventory or fulfillment systems.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Key product types, variants, options, images, inventory values, visibility rules, product SEO values, and unsupported product behaviors have documented outcomes in Squarespace before launch.

### Pitfall 3: Confusing Store Pages and Product Discovery With Categories Alone <a href="#pitfall-3-confusing-store-pages-and-product-discovery-with-categories-alone" id="pitfall-3-confusing-store-pages-and-product-discovery-with-categories-alone"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Categories or collections migrate as expected, but shoppers cannot find products naturally because Store Pages, navigation, filters, product landing pages, summary sections, menus, and content-commerce pathways were not rebuilt for Squarespace.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

The source store depends on nested categories, custom landing pages, faceted filters, brand pages, collection pages, editorial buying guides, or menu-driven product discovery. The project scope treats category mapping as enough.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Audit product discovery as a storefront journey, not only as taxonomy migration. Identify priority Store Pages, category/tag structures, navigation labels, content landing pages, internal links, filters, and homepage or campaign paths that must guide shoppers to products after migration.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

For a store where product discovery starts from editorial pages or seasonal landing pages, validate the migrated products together with Store Pages, internal links, image blocks, page sections, and redirect rules.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Priority products can be found through Squarespace navigation, Store Pages, search/discovery paths, content links, and key landing pages, not only through the admin product list.

### Pitfall 4: Treating Historical Orders as Checkout Configuration <a href="#pitfall-4-treating-historical-orders-as-checkout-configuration" id="pitfall-4-treating-historical-orders-as-checkout-configuration"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Historical orders migrate, but the live Squarespace checkout is not ready. Payment providers, shipping rates, tax settings, discount behavior, fulfillment workflows, notifications, and subscription/payment-plan requirements are not configured or tested before launch.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

The merchant reviews old orders but has not tested a new checkout transaction, shipping rule, tax calculation, discount code, fulfillment update, refund process, or payment-provider path inside Squarespace.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Separate historical order migration from live checkout readiness. Validate order history for readability and customer context, then separately test Squarespace payment, tax, shipping, discount, fulfillment, notification, and subscription or payment-plan workflows with target-store settings enabled.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Before launch, complete at least one test order for each major shipping zone, tax scenario, payment method, discount type, and fulfillment process while separately checking migrated historical orders for totals, items, taxes, discounts, and customer links.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Historical orders are readable and reconciled, and live checkout, payment, shipping, tax, discount, fulfillment, refund, and notification workflows have passed target-store testing.

### Pitfall 5: Misreading Customers, Contacts, Members, and Profiles <a href="#pitfall-5-misreading-customers-contacts-members-and-profiles" id="pitfall-5-misreading-customers-contacts-members-and-profiles"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Customer-related data is moved as a single record type even though the source store used separate meanings for buyers, contacts, members, subscribers, donors, account holders, marketing contacts, loyalty participants, or external CRM identities.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

The source system has multiple customer-like tables or app records. The merchant expects member accounts, newsletter status, customer history, donor context, subscriber records, and CRM segments to behave the same way after migration without defining which meanings Squarespace should preserve.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Map customer-related records by business meaning. Separate commerce buyers, contacts, members, subscribers, donors, profiles, marketing records, account expectations, and external CRM or email-platform identifiers. Confirm what belongs in the Migration Service, what belongs to target configuration, and what requires Custom Service or external-system handling.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

For a membership-driven store, validate buyers with order history separately from site members, newsletter contacts, subscribers, and external CRM records. Do not assume one migrated customer record proves every account-related workflow is preserved.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Customer/contact/member/profile meanings are documented, representative samples validate correctly, and unsupported or external-system-owned records are assigned to Add-ons, Custom Service, external setup, or accepted exclusions.

### Pitfall 6: Underestimating Content, Media, URL, and SEO Work <a href="#pitfall-6-underestimating-content-media-url-and-seo-work" id="pitfall-6-underestimating-content-media-url-and-seo-work"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Products and orders look acceptable, but content continuity suffers. CMS Pages, Blog Posts, media, images, metadata, slugs, redirects, internal links, domain settings, page structure, and search visibility are incomplete or inconsistent after launch.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

The source site has SEO-sensitive product URLs, long-running Blog Posts, important landing pages, image-heavy pages, embedded media, category pages, custom slugs, or ranking pages, but the migration checklist focuses on products and orders.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Prepare a content and SEO inventory before Full Migration. Identify high-value pages, Blog Posts, product URLs, Store Pages, redirects, metadata, images, alt text, internal links, and domain-launch dependencies. Validate content samples alongside commerce samples.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

For a store where organic traffic depends on blog content and product pages, include top traffic URLs, top revenue product URLs, priority Blog Posts, image-heavy pages, and redirects in Demo Migration validation.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Priority CMS Pages, Blog Posts, media, product URLs, redirects, SEO metadata, internal links, and domain-launch steps have been validated or assigned to a clear post-migration action owner.

### Pitfall 7: Expecting Templates and Design to Transfer as Data <a href="#pitfall-7-expecting-templates-and-design-to-transfer-as-data" id="pitfall-7-expecting-templates-and-design-to-transfer-as-data"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The target store has migrated records, but the storefront does not match brand expectations because templates, sections, product page layouts, navigation, mobile presentation, content blocks, and visual styling were assumed to migrate automatically.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

The merchant asks for exact visual parity, old theme behavior, custom page layouts, custom checkout presentation, or special product display behavior, but the migration scope does not include design rebuild or Custom Service review.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Separate data migration from Squarespace site implementation. Decide which design expectations can be handled through Squarespace setup, which require manual rebuild, which require external design work, and which should be excluded from Migration Service scope. Validate the storefront as a shopper experience, not only as a data table.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

For a brand-led store, create a launch-critical design checklist covering homepage sections, product listing pages, product detail layout, navigation, footer links, mobile views, checkout presentation, and priority landing pages.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

The merchant has accepted which design elements are target-site setup, which are manual rebuild work, which require Custom Service review, and which are outside migration scope.

### Pitfall 8: Overlooking API, App, and External-System Boundaries <a href="#pitfall-8-overlooking-api-app-and-external-system-boundaries" id="pitfall-8-overlooking-api-app-and-external-system-boundaries"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Records migrate into Squarespace, but connected operations fail because external systems, apps, inventory feeds, fulfillment platforms, accounting tools, email systems, analytics, payment systems, or CRM identifiers were not considered.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

The source store uses external systems to control inventory, fulfillment, subscriptions, customer segmentation, product feeds, tax logic, shipping, email automations, analytics, or order exports. The migration plan does not list these dependencies.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Inventory every external dependency before launch. Identify which data should migrate, which identifiers must be preserved or cross-referenced, which integrations must be reconnected in Squarespace, and which behaviors require Add-ons or Custom Service review. Treat API availability as a planning boundary, not a guarantee that every source behavior can be recreated.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

For a store connected to fulfillment and accounting systems, validate migrated orders with external references, SKU consistency, fulfillment status, tax and shipping values, customer email identity, and export readiness.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Critical integrations and external identifiers are documented, test records validate correctly, and unsupported workflows have an owner outside standard record migration.

### Pitfall 9: Treating Add-ons as a Substitute for Custom Service <a href="#pitfall-9-treating-add-ons-as-a-substitute-for-custom-service" id="pitfall-9-treating-add-ons-as-a-substitute-for-custom-service"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

The project uses Add-ons to cover extra fields or specific mapping requirements, but the source store actually depends on custom workflows, unsupported structures, integration logic, or target implementation work that requires Custom Service review.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

The source store includes custom product builders, custom checkout rules, unusual subscription behavior, custom databases, complex customer/account workflows, app-owned entities, specialized fulfillment logic, or strict design parity expectations. The proposed handling only lists Add-ons.

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Use Add-ons for defined additional migration needs and use Custom Service for requirements that need assessment beyond standard supported migration behavior. Do not use Add-ons as a substitute for Custom Service, target-store build work, custom development, or third-party integration setup.

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

If a source store has product configurators and custom checkout validation, scope supported product fields separately from the custom workflow. The product records may be migration-ready while the workflow requires Custom Service review or accepted exclusion.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Add-on items are specific and bounded, Custom Service review points are explicit, and unsupported expectations are not hidden inside general migration wording.

### Pitfall 10: Skipping Revalidation After Follow-Up Migration Activity <a href="#pitfall-10-skipping-revalidation-after-follow-up-migration-activity" id="pitfall-10-skipping-revalidation-after-follow-up-migration-activity"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

After the main migration, new products, customers, orders, Blog Posts, content updates, or changed source records are handled through follow-up migration activity, but the target store is not revalidated. New data may affect URLs, inventory, product display, orders, customers, redirects, SEO, integrations, or launch readiness.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

The merchant assumes a later migration activity only adds records and does not require renewed review. New eligible records, changed records, content updates, order activity, or post-Demo changes are present, but validation remains limited to the original sample.

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Treat Additional Migration Options as a reason to recheck affected Squarespace areas. Validate newly migrated products, customers, orders, Blog Posts, content, redirects, inventory, order totals, and integration references when they are relevant. New Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time; records already counted through the service license do not consume Entity Points again simply because another migration action occurs.

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

If new products and Blog Posts are migrated shortly before launch, revalidate product visibility, Store Pages, images, URLs, redirects, metadata, internal links, inventory values, and content formatting before the target store is accepted.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Follow-up migration activity has a defined validation checklist, newly migrated eligible records are scoped correctly for Entity Points, and affected commerce, content, SEO, and integration areas are rechecked before launch.

### Squarespace Pitfall Prevention Checklist <a href="#squarespace-pitfall-prevention-checklist" id="squarespace-pitfall-prevention-checklist"></a>

| Prevention area        | What to confirm before launch                                                             | Why it matters                                  |
| ---------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Target role            | Squarespace is being used as a hosted content-first commerce Target Platform.             | Prevents generic cart assumptions.              |
| Catalog                | Product types, variants, Store Pages, inventory, media, and SEO are sampled.              | Prevents catalog display and selling errors.    |
| Checkout               | Payment, tax, shipping, discounts, fulfillment, refunds, and notifications are tested.    | Prevents operational launch failure.            |
| Customers and contacts | Buyers, contacts, members, subscribers, donors, and profiles are separated by meaning.    | Prevents account and CRM confusion.             |
| Content and SEO        | CMS Pages, Blog Posts, URLs, redirects, media, metadata, and internal links are reviewed. | Protects search and content continuity.         |
| Design                 | Templates, sections, navigation, mobile views, and storefront presentation are assigned.  | Prevents mistaken design-transfer expectations. |
| Integrations           | External systems, identifiers, feeds, exports, apps, and APIs are checked.                | Prevents disconnected operations.               |
| Scope extensions       | Add-ons and Custom Service are separated clearly.                                         | Prevents under-scoping.                         |
| Follow-up handling     | Additional Migration Options trigger targeted revalidation.                               | Prevents late-stage data drift.                 |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace migration pitfalls are usually preventable when merchants plan for Squarespace as both a hosted site environment and a commerce Target Platform. A successful migration does not depend only on whether products, customers, and orders appear in the target admin. It depends on whether Store Pages, content, SEO, checkout, customer/contact meaning, integrations, design expectations, Entity Points, Add-ons, Custom Service, and follow-up migration handling have all been reviewed in the right role.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Squarespace migrations need content and SEO review?**

Squarespace stores often depend on pages, Blog Posts, media, Store Pages, URLs, redirects, templates, and internal links. Product and order migration can be technically successful while content continuity still needs additional review.

**Can migrated order history prove that Squarespace checkout is ready?**

No. Historical orders and live checkout configuration are separate. Payment, shipping, tax, discounts, fulfillment, refunds, and notifications should be tested inside Squarespace before launch.

**When do Squarespace requirements need Custom Service review?**

Custom Service review is appropriate when the source store depends on unsupported product logic, custom checkout behavior, unusual customer/account structures, external-system rules, custom design parity, or records that do not fit standard supported migration behavior.

**Do Add-ons replace Custom Service for Squarespace migration?**

No. Add-ons address defined additional migration needs. They are not a substitute for Custom Service, target-site implementation, custom development, or third-party integration setup.

**What should be checked after Additional Migration Options are used?**

Affected products, customers, orders, Blog Posts, content, URLs, redirects, inventory, SEO values, and integration references should be revalidated according to the data and business areas touched by the follow-up migration activity.
