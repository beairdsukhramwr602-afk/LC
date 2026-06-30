# Selecting the Right Migration Approach for WooCommerce

WooCommerce approach selection should be based on how much commerce behavior depends on WooCommerce data, WordPress site structure, extensions, custom fields, order storage, checkout logic, and external systems. A store with clear products and ordinary orders may fit a lighter path. A store with subscriptions, bookings, memberships, wholesale rules, custom checkout fields, HPOS-sensitive metadata, plugin-owned records, or custom tables needs more controlled scope review.

The right approach should not be chosen from record counts alone. WooCommerce migrations can look simple because products, posts, pages, users, media, and metadata live inside WordPress. The real decision is whether the store’s buying logic, order meaning, customer account behavior, URLs, and plugin data can be handled through Standard Service, supported through Managed Service, extended through Add-ons, or reviewed as Custom Service scope.

### What WooCommerce Approach Choice Should Decide <a href="#what-woocommerce-approach-choice-should-decide" id="what-woocommerce-approach-choice-should-decide"></a>

A WooCommerce migration approach should decide four things: what data should migrate, how much execution support is needed, which supported adjustments are required, and which custom or extension-owned requirements need individual review. It should also define how Demo Migration will prove that the chosen path is strong enough.

| Decision layer               | What it answers                                                                                       | WooCommerce-specific signal                                                                                                                       |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Standard Service             | Can supported source and target data be migrated with ordinary configuration?                         | Products, customers, orders, coupons, categories, tags, CMS Pages, Blog Posts, media, and URLs have clear standard mapping.                       |
| Managed Service              | Does the merchant need guided execution, setup coordination, sample selection, or validation support? | Store data is mostly supported, but the team needs help interpreting products, orders, content, URLs, or plugins.                                 |
| Add-ons                      | Are there supported extra requirements beyond the basic service license?                              | Filtering, additional mapping, or supported configuration adjustments are needed.                                                                 |
| Custom Service               | Does the store depend on unsupported, extension-owned, custom-table, or workflow-specific behavior?   | Subscriptions, bookings, memberships, wholesale rules, custom checkout fields, external IDs, HPOS metadata, or custom plugin records need review. |
| Additional Migration Options | How should later migration activity be handled?                                                       | New products, customers, orders, Blog Posts, coupons, media, or plugin fields may appear after the first migration run.                           |

This decision should produce a practical working path. It should not become a service glossary. The merchant needs to know which approach protects the WooCommerce outcome and which assumptions still need evidence before Full Migration.

### When Standard Service Can Be Enough <a href="#when-standard-service-can-be-enough" id="when-standard-service-can-be-enough"></a>

Standard Service can be suitable when the WooCommerce scope is supported, structurally clear, and easy for the merchant to validate. The strongest candidates have ordinary products, coherent variation logic, understandable customers and orders, limited plugin-owned data, and clean WordPress content or URL needs.

| Standard Service signal                                                                        | Why it supports a lighter approach                                                             | Demo Migration proof                                                                                           |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Products use ordinary simple, variable, virtual, downloadable, grouped, or external structures | Product meaning can be interpreted through common WooCommerce fields.                          | Product name, SKU, price, images, stock, categories, tags, and attributes appear correctly.                    |
| Variable products have clean attribute logic                                                   | Parent-child product relationships are understandable.                                         | Variations remain purchasable and display correct choices.                                                     |
| Orders use standard WooCommerce fields                                                         | Historical order readability is easier to confirm.                                             | Status, customer, line items, totals, coupons, tax, shipping, payment labels, refunds, and notes are readable. |
| Customer accounts are not controlled by complex membership or wholesale rules                  | Customer migration can focus on identity, addresses, and order history.                        | Customer records connect to account data and order history.                                                    |
| WordPress content scope is limited and clean                                                   | CMS Pages, Blog Posts, media, and URLs can be sampled without extensive custom interpretation. | Key pages, posts, images, internal links, and redirects remain usable.                                         |
| Plugin impact is limited                                                                       | Fewer records depend on custom fields, custom tables, or external workflows.                   | Store admin review does not reveal missing extension-owned meaning.                                            |

Standard Service is not a reason to skip review. Even a standard WooCommerce migration should use Demo Migration to check product purchasability, order readability, customer-account continuity, media display, URL behavior, and important WordPress content paths.

### When Managed Service Is Safer <a href="#when-managed-service-is-safer" id="when-managed-service-is-safer"></a>

Managed Service is appropriate when the migration is mostly within supported scope but the merchant needs guided execution, configuration support, sample selection, issue interpretation, or validation discipline. WooCommerce stores often benefit from this path when the team is not confident separating standard migration data from plugin behavior, target setup, and accepted exclusions.

| Managed Service signal                                                        | Why Managed Service helps                                                    | Typical support need                                             |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Store has many products, variations, categories, images, and reviews          | Data may be supported, but review workload is high.                          | Sample planning and structured validation.                       |
| Orders include refunds, notes, custom checkout fields, or external references | Historical order readability needs careful interpretation.                   | Demo Migration review and issue classification.                  |
| WordPress content affects commerce traffic                                    | Product discovery depends on pages, posts, menus, SEO fields, and redirects. | Content and URL continuity review.                               |
| Plugin list is long but not every plugin requires data migration              | Scope must be separated from configuration, exclusions, and custom work.     | Plugin-scope classification.                                     |
| Team needs launch support around Full Migration and later activity            | New records may appear while the target store is being prepared.             | Additional Migration Options planning and revalidation sequence. |

Managed Service does not turn unsupported plugin behavior into standard migration scope. Its value is coordination: making sure the migration is prepared, executed, reviewed, and corrected through the right handling path.

### Where Add-ons Fit WooCommerce Scope <a href="#where-add-ons-fit-woocommerce-scope" id="where-add-ons-fit-woocommerce-scope"></a>

Add-ons are useful when the WooCommerce migration has supported requirements beyond the basic service license but does not require a fully custom path. They should be chosen for specific, bounded needs. They are not a substitute for Custom Service, plugin setup, custom development, or target-store build work.

| Add-on use case         | WooCommerce example                                                                                                   | Boundary to confirm                                                                    |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Migrate selected orders, customers, products, categories, CMS Pages, or Blog Posts by date, status, or relevance.     | Filtering changes scope but does not rebuild extension workflows.                      |
| Advanced Data Mapping   | Align supported source fields with WooCommerce attributes, metadata, customer fields, order fields, or product facts. | Mapping requires clear source and target meaning.                                      |
| Advanced Data Configure | Apply supported configuration adjustments during migration.                                                           | Configuration support is not the same as live gateway, tax, shipping, or plugin setup. |
| Custom Add-ons          | Address a bounded special requirement that remains feasible within supported behavior.                                | Custom Add-ons should not be treated as full Custom Service by default.                |

Add-ons should be planned before Demo Migration when possible. If Demo Migration reveals fields or records that need additional supported handling, the approach should be updated before Full Migration.

### When Custom Service Should Be Reviewed <a href="#when-custom-service-should-be-reviewed" id="when-custom-service-should-be-reviewed"></a>

Custom Service should be considered when WooCommerce store meaning depends on data or behavior that standard assumptions cannot interpret. The trigger is not simply store size. The trigger is custom, unsupported, extension-owned, externally controlled, or bespoke logic that affects migration output.

| Custom Service trigger                                                                                  | Why it changes the approach                                                             | Review evidence                                                                      |
| ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Subscription, booking, membership, wholesale, bundle, composite, or add-on behavior defines the product | Product meaning is not only name, SKU, price, stock, and image.                         | Product examples, extension ownership, order examples, expected target behavior.     |
| Custom checkout fields affect operations                                                                | Historical orders may depend on field values; live checkout may require separate setup. | Orders with populated fields, field definitions, conditional rules, reporting needs. |
| Order metadata depends on HPOS, extensions, or custom tables                                            | Order readability may differ across admin screens and integrations.                     | Order-storage mode, metadata examples, extension compatibility notes.                |
| Customer account meaning depends on roles, memberships, external IDs, or plugin records                 | Customer migration may require more than email, address, and order history.             | Customer samples, roles, membership data, external references.                       |
| Product pricing or availability depends on code, customer roles, external systems, or plugin rules      | Standard price fields may not represent buying behavior.                                | Price examples, customer-role examples, integration references.                      |
| External systems own fulfillment, accounting, CRM, WMS, marketplace, or ERP references                  | WooCommerce may display values that are operationally controlled elsewhere.             | IDs, reports, sample records, downstream system requirements.                        |

Custom Service does not automatically mean the entire store build, plugin configuration, live integration setup, or custom development work is included. It means the migration requirement needs individual review because standard supported behavior is not enough.

### Entity Points and WooCommerce Volume Planning <a href="#entity-points-and-woocommerce-volume-planning" id="entity-points-and-woocommerce-volume-planning"></a>

Entity Points should be planned according to the records that need to move and the timing of launch. WooCommerce projects often continue receiving new products, customers, orders, Blog Posts, coupons, and media updates while migration work is in progress.

| Scope area                  | Entity Points consideration                                                                          | Planning implication                                                    |
| --------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Products                    | New Product records may consume Entity Points when migrated for the first time.                      | Track new products created after the first migration run.               |
| Customers                   | New Customer records may consume Entity Points when migrated for the first time.                     | Review registered customers, guest-order context, and duplicate emails. |
| Orders                      | New Order records may consume Entity Points when migrated for the first time.                        | Plan around active sales before Full Migration.                         |
| Blog Posts                  | New Blog Posts may consume Entity Points when migrated for the first time.                           | Include commerce-supporting posts in scope review.                      |
| Repeated migration activity | Previously counted records should not be counted again only because another migration action occurs. | Separate already recorded entities from newly eligible records.         |

Records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path. New eligible records may consume Entity Points when migrated for the first time, including when a new migration is performed for the same migration path.

### Demo Migration as the Approach Decision Point <a href="#demo-migration-as-the-approach-decision-point" id="demo-migration-as-the-approach-decision-point"></a>

Demo Migration should confirm whether the chosen WooCommerce approach is sufficient. It should test the records that carry business meaning, not only a few clean products or recent orders.

| Demo Migration sample        | What it should prove                                                                                              | Approach signal                                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Simple product               | Basic WooCommerce product fields migrate cleanly.                                                                 | Supports Standard Service if other areas are clean.               |
| Variable product             | Attributes, variation SKUs, prices, images, stock, and purchasability are preserved.                              | Confirms whether product complexity remains manageable.           |
| Product with extension logic | Add-ons, subscriptions, bundles, bookings, memberships, or wholesale behavior is visible for review.              | May require Add-ons, Custom Service, configuration, or exclusion. |
| Order with custom fields     | Checkout values, metadata, line items, taxes, shipping, payment labels, refunds, and notes are readable.          | Helps decide Managed Service or Custom Service needs.             |
| Customer with history        | Account details, addresses, roles, and order links remain coherent.                                               | Confirms customer-account continuity.                             |
| Content and URL sample       | Product pages, categories, CMS Pages, Blog Posts, media, SEO fields, redirects, and internal links remain usable. | Confirms WordPress-connected commerce continuity.                 |

A successful Demo Migration should produce clear decisions: continue with the chosen approach, add supported Add-ons, move to Managed Service, request Custom Service review, accept exclusions, or adjust samples before Full Migration.

### How Additional Migration Options Affect Approach Planning <a href="#how-additional-migration-options-affect-approach-planning" id="how-additional-migration-options-affect-approach-planning"></a>

Additional Migration Options matter when the WooCommerce store keeps changing after the first migration run. The approach should define which new records and changed values need renewed review before launch.

| Follow-up scenario                               | Approach implication                                    | Revalidation focus                                                                            |
| ------------------------------------------------ | ------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| New products or product updates are added        | May affect Entity Points and product validation.        | New SKUs, variations, images, prices, categories, and stock.                                  |
| New customers and orders are created             | May affect Entity Points and order/customer continuity. | New orders, customer links, taxes, shipping, payment labels, refunds, and notes.              |
| Coupons, checkout fields, or plugin data changes | May require renewed scope classification.               | Determine whether change is standard data, Add-on scope, Custom Service, setup, or exclusion. |
| Blog Posts, CMS Pages, media, or URLs change     | May affect content and SEO continuity.                  | Recheck links, redirects, metadata, and commerce-supporting content.                          |
| Target setup changes after Demo Migration        | May affect interpretation of migrated data.             | Revalidate before Full Migration or launch.                                                   |

Additional Migration Options should be planned as launch control, not as a way to ignore Demo Migration findings. Later migration activity still needs validation when changed records affect product discovery, checkout support, order readability, customer service, or SEO continuity.

### WooCommerce Approach Decision Matrix <a href="#woocommerce-approach-decision-matrix" id="woocommerce-approach-decision-matrix"></a>

| Store condition                                                                                          | Best-fit approach                                   | Why                                                                                         |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Simple catalog, ordinary products, clean customers/orders, limited plugins                               | Standard Service                                    | Data can be interpreted through common WooCommerce and WordPress structures.                |
| Supported scope but large review workload or limited internal migration experience                       | Managed Service                                     | Guidance helps sample selection, configuration, validation, and issue handling.             |
| Supported extra fields, filters, or mapping requirements                                                 | Add-ons with Standard or Managed Service            | Need is bounded and can be handled through supported extended scope.                        |
| Plugin-owned data, custom checkout fields, custom tables, complex order metadata, or extension workflows | Custom Service review                               | Store meaning depends on behavior beyond standard migration assumptions.                    |
| Active store with new products, orders, customers, and content before launch                             | Approach plus Additional Migration Options planning | Later migration activity must be scoped, counted, and revalidated correctly.                |
| Theme, checkout, payment, shipping, tax, or plugin setup is unfinished                                   | Migration approach plus target setup plan           | Migration can move data, but live operation requires configuration outside record transfer. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WooCommerce approach selection should match the store’s actual commerce behavior. Standard Service may be enough for clean product, customer, order, coupon, content, and media migration. Managed Service helps when the project needs guided execution and disciplined review. Add-ons support bounded extended needs. Custom Service should be considered when plugin-owned data, custom fields, custom tables, HPOS-sensitive order metadata, or external-system references define the store’s meaning.

A strong approach uses Demo Migration as evidence, preserves the Add-ons and Custom Service boundary, plans Entity Points correctly, and treats Additional Migration Options as a controlled follow-up path for new or changed records before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for WooCommerce migration?**

Standard Service can be enough when products, variations, customers, orders, coupons, categories, tags, media, CMS Pages, Blog Posts, and URLs are structurally clear and do not depend heavily on extension-owned behavior, custom tables, or external systems.

**When should a WooCommerce migration use Managed Service?**

Managed Service is useful when the migration is mostly within supported scope but the team needs help with configuration, sample selection, Demo Migration review, issue interpretation, launch sequencing, or later migration activity.

**When does WooCommerce require Custom Service review?**

Custom Service review is appropriate when subscriptions, bookings, memberships, wholesale rules, product add-ons, custom checkout fields, custom tables, HPOS-sensitive metadata, or external-system references define important store behavior that standard migration assumptions cannot fully interpret.

**Do Add-ons replace Custom Service for WooCommerce?**

No. Add-ons support bounded extended requirements such as filtering, supported mapping, or supported configuration adjustments. Custom Service is for requirements that need individual review because data meaning depends on extension behavior, custom logic, unsupported structures, or nonstandard workflows.

**How should Additional Migration Options be planned for WooCommerce?**

Additional Migration Options should be planned when the store continues receiving new products, customers, orders, Blog Posts, coupons, or plugin-field updates before launch. Records already counted through the service license should not consume Entity Points again only because another migration action occurs.
