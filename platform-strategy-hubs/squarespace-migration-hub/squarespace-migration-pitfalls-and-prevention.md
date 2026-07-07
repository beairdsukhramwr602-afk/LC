# Squarespace Migration Pitfalls and Prevention

Squarespace migration pitfalls usually appear when a migrated store is approved by record presence rather than by storefront behavior. Products may exist, but the selling context may not work. Pages may open, but important discovery paths may be weak. Historical orders may be visible, but live checkout setup may still be untested. Customer records may migrate, while contact, subscriber, donor, member, or marketing meaning remains incomplete.

The safest review pattern is to test each pitfall through evidence: what goes wrong, early warning signs, prevention, a recommendation example, and a pass condition. Tables are used where they clarify decisions or make validation easier to apply, but each pitfall still needs enough explanation to preserve migration judgment.

### Squarespace Pitfall Prevention Overview <a href="#squarespace-pitfall-prevention-overview" id="squarespace-pitfall-prevention-overview"></a>

| Pitfall area                  | Main mistake                                                                                  | Stronger approval evidence                                                                                           |
| ----------------------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Record counts                 | Totals are treated as proof of success.                                                       | Representative products, contacts, orders, pages, redirects, and custom data are validated by business behavior.     |
| Products and variants         | Source product structures are assumed to behave the same in Squarespace.                      | Product type, variant SKU, inventory, images, visibility, Store Page placement, and buying flow are tested.          |
| Store Pages and content       | Site structure is treated as cosmetic work.                                                   | Store Pages, CMS Pages, Blog Posts, navigation, internal links, and priority URLs support customer discovery.        |
| Orders and checkout           | Historical order migration is mistaken for live checkout readiness.                           | Past orders remain readable, and new Squarespace checkout tests prove payment, shipping, tax, and fulfillment setup. |
| Contacts and customer context | Customers, subscribers, donors, members, and guest buyers are flattened into one record type. | People records are validated by support, marketing, account, donation, membership, and order-history use cases.      |
| External systems              | Integrations and custom data are reviewed late.                                               | Each dependency has an owner, handling path, sample record, and validation rule.                                     |

### Pitfall 1: Validating Only Record Counts <a href="#pitfall-1-validating-only-record-counts" id="pitfall-1-validating-only-record-counts"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration appears successful because product, customer, order, or content totals look close to the source store. Counts can confirm that records moved, but they do not prove that Squarespace can use those records correctly. A product count does not confirm Store Page placement. A customer count does not confirm marketing preference, address, subscriber, donor, member, or order-history context. An order count does not confirm refund, fulfillment, payment, transaction, discount, or support readability.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Signal                                                                        | Why it matters                                                                                              |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Approval notes focus on product, customer, order, or page totals.             | Count accuracy can hide broken relationships or weak customer-facing behavior.                              |
| Demo Migration samples contain only clean products and simple orders.         | Edge cases such as variants, refunds, guest buyers, digital products, or custom fields may remain untested. |
| Content review checks whether pages open, not whether they support discovery. | Store Pages, CMS Pages, Blog Posts, navigation, internal links, and redirects may still need work.          |
| Staff cannot explain what changed after a follow-up migration action.         | Validation may be based on an outdated result rather than the latest expected target data.                  |

#### Prevention <a href="#prevention" id="prevention"></a>

Move from count-based approval to sample-based approval. Build a sample set that represents the store’s actual business patterns: simple and variant-heavy products, Store Page examples, content pages, Blog Posts, returning customers, subscribers, donors, members, guest buyers, ordinary orders, exception orders, redirects, and custom-data records.

| Sample type      | Include at minimum                                                                                           | Approval question                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| Product          | Simple product, variant-heavy product, service or digital product, product with custom notes or external ID. | Can buyers understand and purchase it, and can staff manage it after launch?           |
| Content          | Store Page, CMS Page, Blog Post, image-heavy page, high-value landing URL.                                   | Does the page support discovery, trust, and relevant customer action?                  |
| Customer/contact | Returning customer, subscriber, donor, member-like user, guest buyer.                                        | Does the record remain useful for support, marketing, account review, or order lookup? |
| Order            | Completed order, refunded or cancelled order, discounted order, fulfillment-linked order.                    | Can staff understand what happened commercially?                                       |
| Custom data      | Product field, customer note, order reference, external-system ID.                                           | Is the field still usable, searchable, visible, or intentionally excluded?             |

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

If the store has 4,000 products, do not approve migration because 4,000 product records appear in Squarespace. Approve it only after testing products that reflect actual selling behavior: a standard physical item, a variant-heavy item, a service product, a digital product, a product assigned to a specific Store Page, and a product that depends on an external ID or custom field.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The migration passes when representative samples prove business meaning, not just record movement. Each sample should have an expected outcome, visible result, staff-facing validation point, and documented handling path for exceptions.

### Pitfall 2: Assuming Product Structures Behave the Same as the Source Store <a href="#pitfall-2-assuming-product-structures-behave-the-same-as-the-source-store" id="pitfall-2-assuming-product-structures-behave-the-same-as-the-source-store"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Source product structures are moved into Squarespace as if product type, option logic, variant behavior, SKU assignment, image handling, visibility, and inventory ownership will retain the same meaning automatically. The catalog may look complete in the admin area, while customers still face missing selections, unclear product pages, unavailable variants, weak images, or products placed in the wrong selling context.

Squarespace product planning must separate what can migrate as product data from what must be configured, rebuilt, validated, or accepted as a limitation. Physical, service, gift card, and digital products may require different handling, and app-created bundles or configurators should not be treated as ordinary variants without review.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Signal                                                              | Possible impact                                                                                |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Product samples are selected only by category or revenue rank.      | Product behavior differences may remain invisible.                                             |
| Variant SKUs, images, and inventory are reviewed separately.        | Buyers may see the right product but select or purchase the wrong variant.                     |
| Service, digital, gift card, or custom product behavior is assumed. | Fulfillment, access, delivery, or setup expectations may be outside standard migration output. |
| Product visibility and Store Page placement are checked late.       | Products can exist in Squarespace without appearing in the expected selling context.           |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Group product validation by behavior. A Squarespace catalog should be reviewed through the way products are sold, not only through the way the source platform stores them.

| Product pattern                              | What to validate                                                                         | Handling path if it fails                                                          |
| -------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Physical product with variants               | Variant options, SKU, price, image, inventory, and selection flow.                       | Correct mapping, adjust configuration, or document limitation.                     |
| Service product                              | Description, purchase expectation, fulfillment expectation, and customer-facing clarity. | Configure Squarespace-side workflow or define manual handling.                     |
| Digital product                              | Delivery expectation, file/access handling, and post-purchase support.                   | Rebuild delivery setup or separate from migration scope.                           |
| Gift card or special product                 | Supported behavior and customer-facing purchasing logic.                                 | Recreate, exclude, manually configure, or review through custom handling.          |
| Bundle, configurator, or app-created product | Component logic, pricing behavior, and source ownership.                                 | Assign to Custom Service review, app setup, manual rebuild, or accepted exclusion. |

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A product with three color choices and four size choices should not be approved only because its title, description, and images migrated. Validate a full purchase path: the buyer selects the intended option combination, the correct SKU appears, inventory reflects the selected variant, the right image supports the choice, and the order record remains understandable to staff.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

The catalog passes when selected products prove that Squarespace can represent the store’s real selling patterns. Product presence, variant behavior, Store Page placement, visibility, inventory, image order, and staff-facing order detail must align with the expected customer experience.

### Pitfall 3: Treating Store Pages and Site Content as Secondary <a href="#pitfall-3-treating-store-pages-and-site-content-as-secondary" id="pitfall-3-treating-store-pages-and-site-content-as-secondary"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Squarespace is not only a commerce database; it is also the storefront and content environment customers use to discover, trust, and buy from the business. Products can migrate while Store Pages, CMS Pages, Blog Posts, image context, internal links, and navigation still fail to support the buying journey.

When site content is treated as post-migration cleanup, the project may pass data checks but feel incomplete at launch. Customers may land on thin pages, broken links, weak navigation, missing policy pages, incomplete brand content, or Store Pages that do not reflect how the catalog should be browsed.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Signal                                                            | Why it weakens the migration                                                         |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Content scope is reviewed after product and order validation.     | Pages that influence SEO, trust, and conversion may be discovered too late.          |
| Store Pages are treated only as product containers.               | Product discovery, category-like browsing, and customer context may be underplanned. |
| Blog Posts and CMS Pages are grouped as optional content.         | Non-product traffic and educational content may lose continuity.                     |
| Image and internal-link checks are postponed until design review. | Migrated pages may exist but feel broken or incomplete.                              |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Use a content decision map before launch. Each commercially meaningful page needs a handling decision, not just a migration attempt.

| Content type           | Decision options                                       | Validation focus                                                                          |
| ---------------------- | ------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Store Page             | Preserve, split, merge, rebuild, or retire.            | Product placement, listing quality, visibility, navigation path, and customer usefulness. |
| CMS Page               | Migrate, rebuild, merge, redirect, retire, or exclude. | Content completeness, links, images, trust value, and SEO relevance.                      |
| Blog Post              | Migrate, redirect, archive, or rebuild.                | Slug, internal links, images, traffic value, and topical relevance.                       |
| Policy or service page | Rebuild, update, or preserve.                          | Accuracy after platform change and visibility from menus or checkout-related paths.       |
| Landing page           | Rebuild, redirect, merge, or retire.                   | Conversion purpose, campaign relevance, and destination quality.                          |

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

If the source store has high-traffic category pages and long-form buying advice, do not limit validation to product detail pages. Select a Store Page, a CMS Page, a Blog Post, and a landing page. Confirm that each one has useful content, working images, correct internal links, appropriate redirects, and a clear place in the Squarespace navigation structure.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Content passes when important customer paths remain usable. Products, Store Pages, CMS Pages, Blog Posts, navigation, images, links, and redirects should support discovery and trust, even when some source layouts must be rebuilt manually in Squarespace.

### Pitfall 4: Confusing Historical Orders With Live Checkout Readiness <a href="#pitfall-4-confusing-historical-orders-with-live-checkout-readiness" id="pitfall-4-confusing-historical-orders-with-live-checkout-readiness"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Historical order migration is sometimes treated as proof that Squarespace checkout is ready. These are different outcomes. Migrated order history supports lookup, support, reporting context, and customer-service continuity. It does not configure live payment processing, shipping rates, tax settings, checkout fields, notifications, fulfillment workflows, discount rules, or refund handling for new Squarespace orders.

If this distinction is missed, a store can have readable historical orders while still failing a new checkout test.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Signal                                                                        | Risk                                                                                                        |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Historical orders are validated by count, date, and total only.               | Staff may not be able to interpret discounts, refunds, payment labels, fulfillment, or transaction context. |
| Payment labels from migrated orders are treated as live gateway setup.        | New transactions may fail or behave differently from historical records.                                    |
| Shipping, tax, and notification tests are scheduled after migration approval. | Launch readiness may depend on settings that were never validated.                                          |
| Refund and cancelled-order samples are missing.                               | Exception handling may be unreadable to support staff.                                                      |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Separate order-history validation from live checkout validation. The first proves that past records remain useful. The second proves that the new Squarespace store can accept and process future orders.

| Validation stream                 | What to test                                                                                                 | Approval evidence                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Historical order readability      | Customer, items, totals, discounts, taxes, shipping, payment label, fulfillment, refunds, status, and notes. | Staff can explain the order without checking the old store.        |
| Transaction and financial context | Payment references, refunds, donations, and reconciliation-relevant fields where available.                  | Finance or support can interpret the record at the expected level. |
| Live checkout setup               | Payment gateway, shipping, tax, notifications, discounts, and fulfillment flow.                              | A new test order completes with expected operational behavior.     |
| Exception handling                | Cancelled, refunded, partially fulfilled, or manually adjusted orders.                                       | Non-standard history remains understandable.                       |

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Use two different samples: one migrated historical order and one new Squarespace test order. The historical sample should prove support readability. The new order should prove checkout setup. A migrated order with the right total does not prove that a future customer can pay, receive the correct shipping option, or trigger the expected notification.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

The order area passes when historical records remain useful and live checkout is proven separately. Staff should understand past orders, while the target store should complete new orders through configured payment, shipping, tax, fulfillment, and notification paths.

### Pitfall 5: Flattening Customers, Contacts, Subscribers, Donors, and Members <a href="#pitfall-5-flattening-customers-contacts-subscribers-donors-and-members" id="pitfall-5-flattening-customers-contacts-subscribers-donors-and-members"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

People data in Squarespace can include customers, contacts, subscribers, donors, address books, marketing preferences, and member-related expectations. Treating all of these as one generic customer list can flatten important business meaning. A profile may exist, but support, marketing, donor review, membership access, account lookup, or order-history relationships may not behave as expected.

This pitfall is especially common when the source platform uses customer groups, account notes, newsletter flags, membership apps, subscription tools, donation records, or external CRM identifiers.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Signal                                                           | Possible consequence                                                               |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Customer validation uses only repeat retail buyers.              | Subscribers, donors, guest buyers, or member-like records may be missed.           |
| Marketing preferences are not part of sample review.             | Segmentation or consent context may become unclear.                                |
| Member or access expectations are described as customer data.    | Gated content, subscriptions, or access logic may require setup outside migration. |
| Address books and order relationships are not reviewed together. | Support staff may see a person record without enough transaction context.          |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate people data by use case. Each record type should be assessed according to what the business needs to do with it after launch.

| People-data context             | What to check                                                                         | Likely handling path                                                        |
| ------------------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Returning customer              | Addresses, order relationships, support usefulness, and account context.              | Standard validation plus correction if relationships are incomplete.        |
| Subscriber or marketing contact | Subscription status, marketing preference, and segmentation input.                    | Confirm supported migration, manual cleanup, or marketing-platform setup.   |
| Donor                           | Donation history, contact context, and reporting need.                                | Validate readable history or define external handling.                      |
| Member-like user                | Access expectation, content restriction, subscription relationship, or app ownership. | Review as setup, app configuration, Custom Service, or accepted limitation. |
| Guest buyer                     | Order lookup and support context without a reusable account.                          | Validate order-to-person readability.                                       |

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

If the source store has customers who bought products, newsletter-only subscribers, donors, and members, do not validate one repeat customer and assume the people data is complete. Select one sample for each use case. Decide whether the expected result is a Squarespace contact, a customer record, a marketing contact, a manually rebuilt access relationship, or a Custom Service review item.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

People data passes when each meaningful audience type remains useful for its intended business purpose. Support, marketing, donation review, membership/access expectations, and order lookup should be validated with separate samples rather than a single generic customer check.

### Pitfall 6: Expecting Design, Templates, and Layouts to Transfer as Data <a href="#pitfall-6-expecting-design-templates-and-layouts-to-transfer-as-data" id="pitfall-6-expecting-design-templates-and-layouts-to-transfer-as-data"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

The source storefront’s design is expected to appear in Squarespace after migration. Data migration can preserve supported records, but source templates, page-builder sections, theme styling, layout blocks, checkout presentation, menu behavior, and custom front-end logic are not ordinary data records.

When design expectations are not separated from migration scope, teams may reject a technically valid migration because the Squarespace store does not visually match the source site. The real issue is not necessarily data quality; it may be design implementation, page rebuild work, template selection, or Squarespace-side configuration.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Signal                                                                             | Risk                                                                             |
| ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Stakeholders describe success as “the new site should look the same.”              | Visual parity may be confused with data migration quality.                       |
| Page-builder layouts are included in the migration scope without rebuild planning. | Content may move, but layout structure may not.                                  |
| Navigation and product-page display are reviewed only after data approval.         | Customer experience issues may appear late.                                      |
| Checkout design expectations are copied from the source platform.                  | Squarespace checkout behavior may require separate configuration and acceptance. |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Define design continuity as a separate workstream from supported data migration. Migration should be approved against data meaning and usable customer paths; design should be approved against Squarespace implementation requirements.

| Expectation                    | Better planning question                                            | Recommended decision                                |
| ------------------------------ | ------------------------------------------------------------------- | --------------------------------------------------- |
| Same homepage layout           | Which content blocks need to be rebuilt in Squarespace?             | Rebuild, redesign, simplify, or exclude.            |
| Same product-page presentation | Which product fields, images, variants, and content need to appear? | Validate data and configure display separately.     |
| Same navigation                | Which paths matter for discovery and conversion?                    | Rebuild menus and test customer journeys.           |
| Same checkout presentation     | Which checkout behaviors are required after launch?                 | Configure and test Squarespace checkout separately. |

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A source product page may contain tabs, badges, review widgets, custom layout blocks, and cross-sell sections. The migrated product data may include the name, description, images, pricing, SKU, and variants, while the visual arrangement must be rebuilt through Squarespace design and supported features. Approve the data only after confirming what migrated, what requires setup, and what is intentionally redesigned.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Design-related expectations pass when stakeholders understand the boundary between migrated data and Squarespace implementation. The target store does not need to duplicate every source layout, but it must provide a credible, usable, launch-ready customer experience with known rebuild tasks controlled.

### Pitfall 7: Treating SEO, URLs, and Redirects as an Afterthought <a href="#pitfall-7-treating-seo-urls-and-redirects-as-an-afterthought" id="pitfall-7-treating-seo-urls-and-redirects-as-an-afterthought"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

SEO continuity is sometimes reduced to a redirect list prepared near the end of the project. In Squarespace, product URL slugs, Store Page context, CMS Pages, Blog Posts, internal links, images, metadata, navigation, and redirect destinations all influence whether customers and search engines can reach meaningful pages after launch.

A redirect can technically work while still sending users to a weak destination. A product URL can exist while the old category or content path has no clear equivalent. A Blog Post can migrate while internal links still point to source-store paths.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Signal                                           | Risk                                                                                      |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Redirect planning starts after product approval. | SEO and migration results become disconnected.                                            |
| Only product URLs are sampled.                   | CMS Pages, Blog Posts, policies, category-like paths, and landing pages may lose traffic. |
| Destination quality is not reviewed.             | Redirects may lead to thin or irrelevant pages.                                           |
| Internal links are not checked inside content.   | Customers may hit broken paths even when redirects exist.                                 |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Create a prioritized URL and content map. Not every old URL deserves preservation, but every commercially meaningful path needs a decision.

| URL or SEO asset                 | Decision options                                                        | Validation focus                                      |
| -------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------- |
| Product URL                      | Preserve slug, redirect, update, or accept changed path.                | Destination relevance and product readiness.          |
| Store Page or category-like path | Map to Store Page, navigation, redirect, landing page, or retired path. | Discovery continuity and customer intent.             |
| CMS Page                         | Migrate, rebuild, merge, redirect, retire, or exclude.                  | Content value, search intent, and business relevance. |
| Blog Post                        | Migrate, redirect, archive, or rebuild.                                 | Slug, internal links, images, and topical continuity. |
| Internal link                    | Update, redirect, remove, or replace.                                   | Customer path quality inside migrated content.        |

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

If an old category URL brings qualified traffic, do not redirect it automatically to the homepage or a generic product list. Decide whether it should point to a Squarespace Store Page, a rebuilt landing page, a relevant product group, or a retired path with an intentional redirect strategy.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

SEO and URL continuity pass when priority paths have meaningful destinations. Products, Store Pages, CMS Pages, Blog Posts, redirects, metadata, images, and internal links should be sampled together rather than approved as separate technical tasks.

### Pitfall 8: Ignoring External Systems and Custom Data Boundaries <a href="#pitfall-8-ignoring-external-systems-and-custom-data-boundaries" id="pitfall-8-ignoring-external-systems-and-custom-data-boundaries"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

A Squarespace store may depend on external systems for inventory, fulfillment, accounting, shipping, tax, email, analytics, donations, memberships, reviews, subscriptions, or custom reporting. Standard migration can move supported records, but external workflows and unsupported app-owned data may not reconnect or appear automatically.

The pitfall is not that every dependency must be migrated. The pitfall is failing to decide what each dependency means, who owns it, and how it should be handled after migration.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Signal                                                              | Why it matters                                                                                 |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Custom fields are described only as “extra data.”                   | Some fields may be operational identifiers rather than descriptive content.                    |
| External IDs are not included in validation samples.                | ERP, CRM, fulfillment, or accounting workflows may not recognize migrated records.             |
| App-created records are expected to migrate through standard scope. | Reviews, memberships, subscriptions, donations, or custom logic may require separate handling. |
| Integration owners review results only after launch preparation.    | Problems may surface when there is little time for correction.                                 |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Build a dependency inventory that separates supported records from external-system behavior and unsupported data.

| Dependency                                                  | Boundary question                                                            | Handling path                                                                                  |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| ERP, accounting, CRM, or fulfillment ID                     | Does the value need to remain visible, searchable, synced, or only archived? | Preserve where supported, map through Add-ons if applicable, or review through Custom Service. |
| Inventory feed                                              | Which system owns stock after launch?                                        | Separate migrated inventory from future synchronization ownership.                             |
| Review, loyalty, subscription, donation, or membership data | Is the data native, app-owned, external, or custom?                          | Use supported migration, app setup, Custom Service review, manual rebuild, or exclusion.       |
| Analytics and tracking                                      | Is the requirement migrated data or site-side setup?                         | Rebuild tracking in Squarespace-side setup and validate after launch.                          |
| Custom field                                                | Is it descriptive, operational, integration-owned, or obsolete?              | Define target destination, validation sample, and owner.                                       |

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

If a product has an ERP item ID that fulfillment uses, do not treat the ID as a note that can be dropped if the product title and SKU migrate. Decide whether the ID must remain visible, searchable, exported, or connected to another system. If it cannot be handled by supported configuration, assign it to Custom Service review or external-system setup.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

External dependencies pass when each required system, custom field, app-owned record, and operational identifier has a defined owner, handling path, validation sample, and acceptance rule.

### Pitfall 9: Using Add-ons Where Custom Service Review Is Needed <a href="#pitfall-9-using-add-ons-where-custom-service-review-is-needed" id="pitfall-9-using-add-ons-where-custom-service-review-is-needed"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

A non-standard requirement is treated as a normal Add-on even though it involves unsupported app data, external identifiers, custom fields, bespoke transformation, Custom Platform behavior, or custom migration logic adjustment. This creates scope confusion: the team expects a configured migration output, while the requirement actually needs custom analysis, custom handling, manual setup, app-side work, or exclusion.

Add-ons and Custom Service both have value, but they solve different problems. Mixing them weakens planning and makes validation unclear.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Signal                                                                       | Likely issue                                                            |
| ---------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| A request says “just include this extra data” without naming the data owner. | The field may be app-owned, custom, external, obsolete, or unsupported. |
| Filtering and custom transformation are discussed as the same type of work.  | Supported configuration and bespoke logic may be confused.              |
| External IDs are treated as optional labels.                                 | Downstream operational continuity may break.                            |
| The team expects unsupported module data to appear after migration.          | Custom Service review or separate setup may be required.                |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Classify non-standard requirements before execution. Use Add-ons for bounded configuration within supported migration behavior. Use Custom Service review when the requirement depends on unsupported data, external identifiers, custom logic, bespoke transformations, Custom Platform behavior, or custom migration logic adjustment.

| Requirement                                                            | Better fit            | Reason                                                                               |
| ---------------------------------------------------------------------- | --------------------- | ------------------------------------------------------------------------------------ |
| Filter products, customers, orders, or content within supported scope. | Add-on                | The migration output can be controlled through supported selection or configuration. |
| Map supported fields or preserve supported relationships.              | Add-on                | The requirement remains inside known migration behavior.                             |
| Move unsupported app, plugin, module, or extension data.               | Custom Service review | The data may not exist as standard platform records.                                 |
| Preserve external IDs or custom operational fields.                    | Custom Service review | The requirement may affect downstream systems or bespoke logic.                      |
| Apply bespoke transformation or custom migration logic adjustment.     | Custom Service review | The result depends on custom handling, not standard configuration.                   |

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

If the source store has product badges created by an app, customer notes used by a CRM, and a request to migrate only active products, these should not be grouped together. Filtering active products may fit an Add-on. Product badge data and CRM-dependent customer notes may need Custom Service review or manual reconstruction depending on source ownership and target use.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Add-ons and Custom Service handling pass when every non-standard requirement has the right category, business owner, expected output, sample record, and validation rule. No unsupported requirement should be approved under an Add-on label simply because it sounds like extra data.

### Pitfall 10: Skipping Revalidation After Follow-Up Migration Activity <a href="#pitfall-10-skipping-revalidation-after-follow-up-migration-activity" id="pitfall-10-skipping-revalidation-after-follow-up-migration-activity"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

The source store keeps changing after Demo Migration or an earlier run, but another migration action is requested without defining what should change in the target store. New products, customers, orders, pages, Blog Posts, images, redirects, filters, mappings, Add-ons, or Additional Migration Options may alter the expected output.

The result is a launch review based on an earlier migration state. The team may approve records that were correct before the latest change but no longer represent the final target result.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Signal                                                                     | Risk                                                                             |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Another migration run is requested without a written expected outcome.     | The team may not know what should change or remain untouched.                    |
| Mapping, filtering, or option changes are made after validation.           | Previously approved samples may become invalid.                                  |
| Additional Migration Options are selected without follow-up sample review. | The option may affect only part of the result while other areas still need work. |
| Entity Points impact is not discussed before repeated migration activity.  | Cost, scope, and duplicate-consumption expectations may be misunderstood.        |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Define the migration action before requesting it, then revalidate affected samples after the action completes.

| Follow-up situation                                     | What can change                                  | Revalidation focus                                                           |
| ------------------------------------------------------- | ------------------------------------------------ | ---------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | Newly added or changed source records.           | New products, customers, contacts, orders, pages, images, and relationships. |
| Continue the Migration with a new configuration         | Mapping, filtering, or option-controlled output. | Changed samples and any dependent relationships.                             |
| Perform a new migration                                 | The whole expected result.                       | Representative validation across all major data and content areas.           |
| Additional Migration Options are selected               | A specific part of the migration result.         | The option’s actual effect and remaining manual/custom work.                 |
| Entity Points are consumed again                        | Scope and cost expectations.                     | Duplicate-consumption impact and acceptance before execution.                |

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

If a new configuration changes product filtering before launch, do not recheck only the newly migrated products. Revalidate affected Store Pages, product visibility, redirects, order samples, and any custom fields or external IDs tied to those products. A configuration change can affect more than the record that triggered it.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Follow-up migration activity passes when the team validates the latest expected result, not an earlier approved state. The selected migration action, affected data areas, Entity Points expectations, Additional Migration Options, and acceptance samples should all be documented before launch approval.

### Squarespace Pitfall Prevention Checklist <a href="#squarespace-pitfall-prevention-checklist" id="squarespace-pitfall-prevention-checklist"></a>

| Question                                                           | Strong ready signal                                                                                                    |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Are samples selected by business behavior instead of record count? | Products, contacts, orders, content, redirects, and custom data represent real operating patterns.                     |
| Are product structures tested in Squarespace context?              | Product type, variants, SKU, inventory, visibility, Store Page placement, and buying flow are proven.                  |
| Are Store Pages and content treated as migration-critical?         | Products, pages, posts, navigation, images, internal links, and priority URLs support discovery.                       |
| Are historical orders and live checkout reviewed separately?       | Past orders remain readable, and new Squarespace orders prove payment, shipping, tax, and fulfillment setup.           |
| Are people records validated by use case?                          | Customer, subscriber, donor, member-like, guest buyer, and marketing contexts are understood.                          |
| Are design expectations separated from migrated data?              | Layout, template, menu, and checkout presentation tasks have clear Squarespace-side owners.                            |
| Are SEO paths prioritized?                                         | High-value URLs, Store Pages, CMS Pages, Blog Posts, metadata, redirects, and internal links have useful destinations. |
| Are integrations and custom data classified?                       | External IDs, app-owned data, custom fields, and operational dependencies have handling paths.                         |
| Are Add-ons and Custom Service separated?                          | Supported configuration needs and unsupported custom needs are not mixed.                                              |
| Is follow-up migration activity revalidated?                       | The latest migration action and affected samples are checked before launch approval.                                   |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace migration pitfalls are best prevented by approving meaning instead of movement. Products must support buying behavior, Store Pages and content must support discovery, people records must remain useful, historical orders must stay readable, and live checkout must be tested as a separate Squarespace setup outcome.

A strong Squarespace migration review also keeps boundaries clear. Supported data migration, Squarespace-side setup, Add-ons, Custom Service, manual rebuild work, and accepted limitations should each have a defined role. When every pitfall has warning signs, prevention steps, a practical recommendation example, and a pass condition, the launch review becomes easier to trust.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can a Squarespace migration look complete but still have problems?**

Because records can be present without preserving customer-facing behavior. Products, pages, customers, and orders may exist, while Store Page placement, checkout setup, SEO paths, design expectations, contact context, or external-system dependencies still need work.

**What is the most important Squarespace migration pitfall to avoid?**

The most important pitfall is approving record movement without validating business meaning. A strong review checks how products sell, how pages support discovery, how customers and contacts remain useful, how orders can be read, and how live checkout is configured.

**Should every Squarespace pitfall be handled with a table-based checklist?**

No. Tables are useful when they clarify signals, decisions, samples, or pass conditions. They should support the analysis, not replace it. Complex issues still need enough explanation for teams to understand why the problem matters and how to prevent it.

**Why are Store Pages and content important in Squarespace migration?**

Squarespace combines site content and commerce. A migration can move product data while still leaving weak Store Page placement, broken internal links, missing CMS Pages, incomplete Blog Posts, or poor navigation. Content and commerce need to be validated together.

**When should a Squarespace requirement move from Add-ons to Custom Service review?**

A requirement should move to Custom Service review when it involves unsupported app data, external identifiers, custom fields, bespoke transformation, Custom Platform behavior, or custom migration logic adjustment. Add-ons are better suited to supported filtering, mapping, or configuration needs.
