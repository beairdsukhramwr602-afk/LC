# Cafe24 Data Model Differences

Cafe24 migration changes more than where records are stored. It changes how product structure, storefront design, customer accounts, order history, payment context, shipping operations, redirects, apps, and API-connected workflows need to work together after launch.

A source store may organize commerce data around a simple catalog, a marketplace extension, a custom database, a regional storefront, an ERP-led inventory process, or a heavily customized checkout workflow. Cafe24 can support a structured operating model with product resources, options, variants, inventories, categories, customer tiers, orders, payments, shipments, refunds, returns, redirects, webhooks, storefront design resources, and app connections. The migration question is not whether every source field can be copied somewhere. The question is what each record must still mean when Cafe24 becomes the operating storefront.

For Cafe24, data-model planning should separate record migration from business translation. Product data must still support buying decisions. Customer data must still support account recognition, segmentation, and service review. Order data must still support post-launch support, payment review, shipping review, refunds, returns, and reporting. Storefront and SEO data must still preserve discovery where it matters. App and API data must be assigned to the right future system instead of being treated as ordinary record fields.

### Cafe24 Data Model Translation at a Glance <a href="#cafe24-data-model-translation-at-a-glance" id="cafe24-data-model-translation-at-a-glance"></a>

Cafe24 has a broad data surface. Products, categories, customers, orders, payments, shipments, refunds, returns, redirects, and webhooks can all matter during migration planning. That does not mean every source record belongs in one flat migration scope. Each layer should be interpreted according to its future role in Cafe24.

| Data layer                   | What may exist in the source store                                                   | Cafe24 interpretation question                                                                            |
| ---------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Product identity             | Product name, SKU, brand, model, vendor, supplier code, internal ID                  | Which identifier should remain buyer-facing, admin-facing, or integration-facing?                         |
| Product structure            | Options, variants, bundles, custom attributes, product groups                        | Which elements become product options, variants, product properties, or app/custom logic?                 |
| Inventory                    | Stock quantity, warehouse stock, safety stock, reserved stock, availability rules    | Which stock values should be migrated, configured, synchronized, or excluded from historical context?     |
| Categories and merchandising | Category tree, menu placement, collection rules, campaign groups, featured sections  | Which groupings are true catalog structure and which are storefront presentation or promotion logic?      |
| Customer data                | Accounts, customer tiers, addresses, memos, social login references, consent context | Which customer fields are needed for account continuity, segmentation, service, and marketing use?        |
| Order history                | Orders, items, options, payments, shipments, refunds, returns, coupons, memos        | Which order details must remain usable for support and reporting rather than live fulfillment recreation? |
| Storefront and content       | Menus, boards, pages, product detail fields, SEO settings, redirects, theme logic    | Which elements are data, which are storefront setup, and which require design or development handling?    |
| Apps and integrations        | App-owned data, webhooks, analytics, payment providers, ERP/CRM/WMS identifiers      | Which future system owns the workflow after migration?                                                    |

This translation layer is where Cafe24 migrations can succeed or fail. A migrated record can look present but still be operationally weak if the surrounding meaning is wrong.

### Product Data Is More Than a Product List <a href="#product-data-is-more-than-a-product-list" id="product-data-is-more-than-a-product-list"></a>

Cafe24 product planning should begin with the product’s commercial role: what the buyer sees, what the admin team manages, and what connected systems rely on. A source store may store product attributes as variants, custom fields, metafields, specification tables, category labels, app data, or text blocks. Cafe24 may require a cleaner separation between product resources, product options, variants, product images, SEO fields, tags, categories, custom properties, and inventory records.

The most important distinction is between **choice**, **description**, and **operation**. A color, size, package quantity, or configuration may be a sellable choice. A material, compatibility note, product dimension, or certification may be descriptive content. A supplier code, warehouse bin, customs value, or ERP key may be operational data. Treating all three as the same kind of product field usually creates a weaker Cafe24 catalog.

| Source product element | Usually means                      | Cafe24 planning concern                                                                      |
| ---------------------- | ---------------------------------- | -------------------------------------------------------------------------------------------- |
| SKU                    | Sellable or operational identifier | Confirm whether SKU belongs to the parent product, variant, or external system.              |
| Option name and value  | Buyer selection logic              | Confirm whether each option should create variant behavior or remain informational.          |
| Product image set      | Buyer confidence and merchandising | Confirm whether images attach to parent products, variants, or landing-page presentation.    |
| Specification table    | Product comparison context         | Decide whether to preserve as structured product detail, custom property, or content block.  |
| Promotional label      | Campaign or merchandising logic    | Decide whether it belongs in tags, display settings, app behavior, or launch campaign setup. |
| SEO fields             | Search continuity                  | Preserve high-value metadata and routes where they support discovery.                        |
| Custom field           | Unknown until interpreted          | Define the business meaning before mapping.                                                  |

A high-quality Cafe24 migration does not force every source product detail into the nearest available field. It identifies which details need to remain structured, which can become product content, which require app or design handling, and which should stay outside Cafe24 in a connected system.

### Options, Variants, and Inventory Need Explicit Meaning <a href="#options-variants-and-inventory-need-explicit-meaning" id="options-variants-and-inventory-need-explicit-meaning"></a>

Cafe24 supports product options, variants, and variant inventory resources. That makes it important to decide how source option logic should be represented before the migration runs. Many source stores use different terminology for options, variants, child products, configurable products, product combinations, attributes, bundled items, and modifiers.

A migration plan should avoid two opposite mistakes. The first is flattening source variants into generic product descriptions. The second is trying to preserve every source configuration exactly even when Cafe24 should represent it differently. The right approach is to identify what the buyer must choose, what the merchant must manage, and what inventory or fulfillment systems must recognize.

| Pattern to inspect                  | Why it matters                                            | Recommended interpretation step                                                                   |
| ----------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Options affect price                | Buyer choice changes commercial value                     | Confirm whether Cafe24 variant pricing or another configuration path is needed.                   |
| Options affect stock                | Buyer choice changes availability                         | Confirm inventory ownership at the variant level.                                                 |
| Options affect image                | Buyer choice changes presentation                         | Confirm whether image association should follow variant logic or product-gallery logic.           |
| Options are descriptive only        | Buyer choice does not affect fulfillment                  | Consider product content, specification fields, or filtering context instead of variant creation. |
| Source uses bundled or kit products | One storefront item represents multiple operational items | Determine whether Cafe24, an app, or Custom Service must handle the relationship.                 |

Inventory deserves the same discipline. A stock value can represent available quantity, warehouse quantity, sellable quantity, reserved stock, backorder logic, or a value synchronized from an outside system. If the source store’s inventory is controlled by ERP, POS, marketplace, or warehouse software, Cafe24 should not be treated as the only source of truth without confirming the future operating model.

### Category, Menu, and Discovery Data Are Not the Same Thing <a href="#category-menu-and-discovery-data-are-not-the-same-thing" id="category-menu-and-discovery-data-are-not-the-same-thing"></a>

Source stores often combine categories, menus, collections, landing pages, and campaign groupings. Cafe24 planning should separate those meanings. A category may define product organization. A menu may define navigation. A landing page may define merchandising. A redirect may protect search traffic. A filter may support buyer discovery. Those meanings overlap, but they are not identical.

When category data is migrated without this distinction, the target catalog may contain products but feel disorganized to buyers. Products may exist, but customers may not find them. SEO routes may exist, but internal linking may be weak. Campaign pages may be rebuilt visually but lose their product relationship.

| Source structure      | Possible Cafe24 meaning | Migration concern                                                                 |
| --------------------- | ----------------------- | --------------------------------------------------------------------------------- |
| Main category tree    | Catalog organization    | Preserve only if it supports future buyer navigation.                             |
| Menu labels           | Storefront path         | Rebuild intentionally if menus differ from category structure.                    |
| Featured collection   | Merchandising rule      | Decide whether to use category placement, content, app logic, or manual curation. |
| Campaign landing page | Conversion route        | Preserve content and product context where it supports paid traffic or SEO.       |
| Old URL               | Traffic asset           | Redirect or retire intentionally based on value.                                  |
| Product filter        | Discovery support       | Confirm whether filtering depends on structured fields or theme/app behavior.     |

This is why Cafe24 data-model planning should include discovery, not only database fields. Category and route decisions affect conversion after migration because they determine how quickly buyers can move from intent to product selection.

### Customer Records Need Account and Segmentation Context <a href="#customer-records-need-account-and-segmentation-context" id="customer-records-need-account-and-segmentation-context"></a>

Customer data in Cafe24 may involve accounts, customer tiers, customer properties, customer memos, social account context, payment information resources, signup fields, and marketing or service-related details. A source store may not separate these cleanly. Some customer attributes may be standard fields. Others may come from loyalty apps, B2B apps, CRM systems, marketing platforms, or custom registration forms.

The key question is what customer data must do after migration. A customer record may need to support login continuity, order-history recognition, customer tier assignment, B2B pricing, support review, marketing segmentation, address reuse, or fraud review. Those outcomes require more than a name and email address.

| Customer layer            | Migration meaning                                             | Common risk                                                          |
| ------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------- |
| Account identity          | Recognizes the buyer in Cafe24                                | Duplicate accounts or broken order association.                      |
| Customer tier/group       | Supports pricing, benefits, segmentation, or service handling | Tier meaning is copied without corresponding rules.                  |
| Addresses                 | Supports checkout and service review                          | Address formatting does not match market or shipping requirements.   |
| Signup properties         | Captures business-specific registration fields                | Important fields are ignored because they were custom in the source. |
| Customer memos            | Supports service and internal handling                        | Operational notes migrate without meaning or are lost entirely.      |
| Social/payment references | Connects to outside identity or payment behavior              | Sensitive or provider-owned data is assumed to be migratable.        |

Customer migration should also distinguish between historical usefulness and live account behavior. Historical customer data can support service review, but live login, passwords, payment methods, and customer benefits may require separate platform-specific setup or customer communication.

### Order History Carries Operational Evidence <a href="#order-history-carries-operational-evidence" id="order-history-carries-operational-evidence"></a>

Cafe24 has order resources and related order areas covering items, buyer information, payment timelines, recipients, shipping, refunds, returns, coupons, memos, cancellations, exchanges, sales channels, and migrated order resources. That breadth is useful, but it also raises the standard for interpreting order history correctly.

Historical orders should not be judged only by whether an order number appears. They should be judged by whether the migrated history helps the merchant answer practical questions: what was bought, who bought it, how it was paid, how it was shipped, what discount applied, whether a refund or return occurred, and what customer-service context remains visible.

| Order detail                   | Why it matters after migration            | Planning note                                               |
| ------------------------------ | ----------------------------------------- | ----------------------------------------------------------- |
| Order number and date          | Identifies the historical transaction     | Preserve consistency for support and reporting.             |
| Purchased items and options    | Explains exactly what the customer bought | Keep variant or option meaning readable.                    |
| Payment status and timeline    | Supports payment review                   | Do not assume old provider behavior is recreated.           |
| Shipment and recipient details | Supports fulfillment history              | Confirm address and shipment context remain useful.         |
| Coupons and benefits           | Explains discount outcome                 | Separate historical evidence from live promotion setup.     |
| Refunds, returns, exchanges    | Supports service and accounting review    | Preserve enough context for post-launch support.            |
| Order memos or labels          | Supports internal operations              | Determine whether notes are useful, sensitive, or obsolete. |
| Sales channel                  | Shows where the order originated          | Keep when it affects reporting or service handling.         |

The migration objective is not to turn historical orders into active operational workflows. It is to preserve the evidence needed for customer service, business continuity, and reporting after Cafe24 becomes the main commerce environment.

### Storefront, Design, and Content Data Need Boundary Control <a href="#storefront-design-and-content-data-need-boundary-control" id="storefront-design-and-content-data-need-boundary-control"></a>

Cafe24 includes storefront design concepts such as Smart Design, Smart Themes, modules, components, Web Components, and app-connected features. Source stores may contain CMS pages, blog-like content, banners, menus, scripts, product detail layouts, and promotional pages that do not transfer as ordinary product or order records.

For migration planning, content needs classification. Some content can move as CMS Pages. Some content should be rebuilt in Cafe24’s storefront design system. Some source layout behavior should be retired because it reflects old platform limitations. Some scripts and embedded code should be reviewed before being reintroduced.

| Content or design element                   | Migration interpretation                       | Preferred handling                                             |
| ------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------- |
| Trang Hệ thống quản lý nội dung (CMS pages) | Informational pages with business or SEO value | Preserve or rebuild based on current content strategy.         |
| Product detail layout                       | Presentation logic for buying confidence       | Rebuild intentionally if tied to theme or module behavior.     |
| Banners and landing pages                   | Campaign and merchandising context             | Preserve high-value content; avoid copying obsolete campaigns. |
| Menus and navigation                        | Buyer path                                     | Recreate based on future Cafe24 navigation plan.               |
| Scripts or embeds                           | Custom behavior or tracking                    | Review for compatibility, privacy, and operational need.       |
| Redirects                                   | Search and campaign continuity                 | Map high-value routes before launch.                           |

The data model therefore includes presentation boundaries. A file, page, or script may be valuable, but it may not belong inside the migration scope in the same way as products or customers.

### Apps, APIs, Webhooks, and External Systems Define Ownership <a href="#apps-apis-webhooks-and-external-systems-define-ownership" id="apps-apis-webhooks-and-external-systems-define-ownership"></a>

Cafe24 can operate with apps, APIs, webhooks, analytics, Data Bridge, payment providers, shipping services, marketplace workflows, and outside business systems. In migration planning, these connections define ownership. A record may appear in Cafe24, but another system may control how it is updated, priced, fulfilled, reported, or displayed.

| Connected area               | What to identify                                        | Why it changes data meaning                                            |
| ---------------------------- | ------------------------------------------------------- | ---------------------------------------------------------------------- |
| ERP or inventory system      | Product IDs, stock ownership, warehouse rules           | Cafe24 may display stock while another system owns updates.            |
| CRM or marketing system      | Customer IDs, consent, segments, lifecycle data         | Customer fields may need synchronization rather than static migration. |
| Payment provider             | Transaction references, payment status, refunds         | Historical payment evidence differs from live payment configuration.   |
| Shipping provider            | Rates, tracking, recipient handling, fulfillment status | Shipment records may not recreate provider workflows.                  |
| Marketplace or sales channel | Channel identifiers, stock rules, order source          | Sales-channel meaning affects reporting and operations.                |
| Custom app or webhook        | Trigger logic, event payloads, external IDs             | Custom Service may be needed when behavior must be transformed.        |

This ownership map helps prevent a common mistake: migrating values while ignoring the system that makes those values trustworthy. A stable Cafe24 migration defines which system owns each important data outcome after launch.

### Data Model Decisions That Should Be Made Before Execution <a href="#data-model-decisions-that-should-be-made-before-execution" id="data-model-decisions-that-should-be-made-before-execution"></a>

Cafe24 projects are easier to scope when the merchant decides how each meaningful source layer should behave before migration begins.

| Decision area         | Question to resolve                                                                   | Outcome of a clear decision                                        |
| --------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Catalog structure     | Which products, options, variants, categories, and custom fields matter after launch? | Product data can be mapped by function, not just by field name.    |
| Inventory ownership   | Will Cafe24, ERP, warehouse, marketplace, or another system own stock updates?        | Inventory migration avoids false operational promises.             |
| Customer meaning      | Which customer tiers, account fields, memos, and segmentation details are necessary?  | Customer data supports service and retention after migration.      |
| Order evidence        | Which historical details must remain readable for support and reporting?              | Order history is usable even when old workflows are not recreated. |
| Content boundaries    | Which pages, menus, routes, scripts, and design elements need migration or rebuild?   | Storefront work is separated from record movement.                 |
| Integration ownership | Which apps, APIs, webhooks, and external systems control business outcomes?           | Custom Service needs are visible before execution.                 |

### Market, Language, and Storefront Context Can Change Data Meaning <a href="#market-language-and-storefront-context-can-change-data-meaning" id="market-language-and-storefront-context-can-change-data-meaning"></a>

Cafe24 is often considered by merchants with regional commerce needs, cross-border ambitions, Korean commerce requirements, or a storefront model that must coordinate products, content, payment, shipping, and marketplace operations. That makes market context part of the data model. A product title, category label, customer field, or order status may carry different meaning depending on whether it is used for domestic selling, international selling, wholesale handling, marketplace sync, or customer-service reporting.

When a source store has multiple languages, multiple markets, or country-specific presentation, migration planning should avoid merging all meaning into one generic product description. Some content needs to remain buyer-facing. Some content needs to remain operational. Some content may need to be recreated through Cafe24 storefront setup, apps, external localization processes, or separate market configuration.

| Market-sensitive data        | Why it needs careful handling                                 | Cafe24 planning signal                                                                                           |
| ---------------------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Localized product names      | They affect search, buyer recognition, and product comparison | Confirm whether localized text belongs in Cafe24 content, storefront setup, or a separate localization workflow. |
| Market-specific descriptions | They may include legal, shipping, or buyer-confidence details | Separate content that must remain visible from old text that should be retired.                                  |
| Currency or price context    | Price may depend on market, promotion, or payment channel     | Confirm the future pricing owner before migrating price-related fields.                                          |
| Regional shipping notes      | Delivery availability may not be ordinary product content     | Decide whether the note belongs in product detail, shipping configuration, or service-policy content.            |
| Marketplace identifiers      | Channel-specific IDs can be operationally important           | Preserve only where they support future reporting, sync, or service workflows.                                   |

A Cafe24 data model should therefore be reviewed through future operating context. The same field can have different value depending on whether it supports buyers, admins, integrations, marketplace sync, or post-launch reporting.

### Custom Properties and Admin Notes Require Interpretation <a href="#custom-properties-and-admin-notes-require-interpretation" id="custom-properties-and-admin-notes-require-interpretation"></a>

Cafe24 includes resources around product custom properties, customer properties, memos, labels, board content, and administrative settings. These areas are useful when the migrated store needs richer operational context, but they can also become a dumping ground if the source data is not interpreted.

Custom information should be classified before it is moved. A technical specification may improve product comparison. A customer registration field may support B2B qualification. A product memo may help internal staff but should not appear to buyers. A source database ID may matter only if an ERP or CRM still depends on it. An obsolete app field may no longer deserve migration at all.

| Custom-data type            | Better classification question                      | Possible handling direction                                          |
| --------------------------- | --------------------------------------------------- | -------------------------------------------------------------------- |
| Buyer-facing product detail | Does it help the customer choose?                   | Preserve as structured product information or page content.          |
| Admin-only operational note | Does it help staff support, fulfill, or report?     | Preserve only where it remains useful and safe.                      |
| Integration identifier      | Will another system still reference it?             | Preserve in a controlled field or Custom Service mapping.            |
| Old app flag                | Does the app behavior still exist after migration?  | Rebuild, replace, or retire rather than blindly copy.                |
| Custom signup field         | Does it affect customer tier, approval, or service? | Map to customer/account properties or review through Custom Service. |

The goal is not to maximize the number of migrated fields. The goal is to preserve the fields that still create business value inside Cafe24.

### Cafe24 Data Should Be Validated by Use Case, Not Only by Count <a href="#cafe24-data-should-be-validated-by-use-case-not-only-by-count" id="cafe24-data-should-be-validated-by-use-case-not-only-by-count"></a>

The data model is ready when each major record type can still perform its intended job. A product should help the buyer choose and help operations identify what is sold. A category should guide discovery. A customer record should remain useful for account and service workflows. An order should explain the historical transaction. A redirect should protect meaningful traffic. An integration identifier should still connect the right systems.

| Validation lens  | What to test                                                                | What a good result looks like                                                |
| ---------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Buyer lens       | Can customers understand products, choices, images, categories, and routes? | Product and discovery data supports purchase decisions.                      |
| Admin lens       | Can staff manage products, stock, customers, and historical orders?         | Operational records are readable and correctly associated.                   |
| Service lens     | Can support answer customer questions from migrated data?                   | Orders, customers, refunds, returns, and notes provide enough evidence.      |
| SEO lens         | Do high-value routes and metadata remain intentional?                       | Important product, category, and content routes are preserved or redirected. |
| Integration lens | Do external systems still recognize key records?                            | Required IDs and ownership rules remain clear after migration.               |

This use-case validation keeps Cafe24 migration grounded in operational readiness. It also prevents the project from passing because records exist while the store still lacks usable business meaning.

### What Should Not Be Flattened Into Ordinary Data <a href="#what-should-not-be-flattened-into-ordinary-data" id="what-should-not-be-flattened-into-ordinary-data"></a>

One of the most important Cafe24 data-model decisions is knowing when not to treat a source item as ordinary migration data. Some information is valuable but does not belong in a simple field-to-field movement. If a source value controls business behavior, display logic, external synchronization, or compliance-sensitive handling, it should be reviewed before it is moved.

This is especially relevant for stores coming from custom platforms, agency-built stores, heavily modified open-source platforms, or app-heavy hosted platforms. The export may show a value, but the export may not explain why that value exists or what business rule depends on it. Moving the value without the rule can create a misleading result.

| Source item                             | Why it should not be flattened                              | Better migration treatment                                                          |
| --------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Pricing rule stored in a custom table   | The number may not explain the conditions behind the price  | Review whether the rule belongs to Cafe24 configuration, an app, or Custom Service. |
| Fulfillment flag from an outside system | The flag may only make sense to a warehouse or ERP workflow | Preserve only if the future system still uses it.                                   |
| Theme-controlled product badge          | The badge is presentation behavior, not only product data   | Rebuild through storefront design or display configuration.                         |
| Marketplace-only identifier             | The value may matter only for channel sync                  | Preserve where reporting or future integration requires it.                         |
| Legacy workaround field                 | The old platform needed it, but Cafe24 may not              | Retire or transform instead of migrating blindly.                                   |
| App-generated customer field            | The app may not exist after migration                       | Decide whether the business meaning survives without the app.                       |

This discipline keeps Cafe24 cleaner after migration. A target store should not inherit every workaround that accumulated in the source store. It should inherit the information needed to operate correctly.

### Data Model Quality Signals <a href="#data-model-quality-signals" id="data-model-quality-signals"></a>

A Cafe24 data model is strong when the merchant can explain how each migrated layer will be used after launch. It is weak when the project relies only on source exports, record counts, or broad assumptions about platform compatibility.

| Quality signal             | Strong Cafe24 planning                                                                            | Weak Cafe24 planning                                                         |
| -------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Product interpretation     | Products are reviewed by choice logic, content value, inventory meaning, and operational IDs.     | Products are reviewed only by title, image, price, and description.          |
| Category interpretation    | Categories, menus, filters, landing pages, and redirects are separated.                           | Old categories are copied as if they automatically define future navigation. |
| Customer interpretation    | Tiers, properties, memos, account use, and segmentation are classified.                           | Customer migration is reduced to name, email, and address.                   |
| Order interpretation       | Historical evidence is preserved for support, payment, shipping, refunds, returns, and reporting. | Orders are treated as flat historical rows.                                  |
| Integration interpretation | Future ownership is assigned to Cafe24, ERP, CRM, WMS, marketplace, or another system.            | External IDs and app fields are copied without ownership decisions.          |
| Content interpretation     | CMS, design, route, and script boundaries are defined.                                            | Storefront content is assumed to migrate like catalog data.                  |

These signals are useful because they separate a technically complete transfer from a commercially ready Cafe24 store.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Cafe24 data-model differences are most important where business meaning depends on product options, variants, inventory ownership, customer tiers, order evidence, storefront structure, redirects, apps, APIs, webhooks, and external systems. A good migration plan does not only ask whether source data can be moved. It asks what each record must still prove, display, trigger, or support inside Cafe24.

When the source store contains complex catalog logic, custom fields, app-owned data, multi-system inventory, historical service requirements, or storefront-specific content, prepare representative examples before migration. The stronger the data interpretation is before execution, the easier it becomes to validate Cafe24 by operational readiness rather than by record count alone.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Do Cafe24 product options and variants always match the source store exactly?**

No. Source stores can model options, variants, attributes, bundled products, and modifiers differently. Cafe24 planning should decide which source elements become sellable choices, structured product information, inventory-bearing variants, app behavior, or Custom Service requirements.

**Should all source custom fields be migrated into Cafe24?**

Not automatically. Custom fields should be interpreted before mapping. Some are buyer-facing product information, some are admin-only notes, some are integration identifiers, and some are obsolete source workarounds.

**What order data matters most in a Cafe24 migration?**

The most important order data is the information needed for service and reporting: purchased items, option meaning, customer association, payment status, shipping context, discounts, refunds, returns, exchanges, and useful internal notes.

**Can storefront design data be treated as ordinary migration data?**

No. Storefront content, design modules, scripts, menus, landing pages, and theme behavior should be separated from ordinary product, customer, and order records. Some elements can be migrated; others need redesign, reconfiguration, or development work.

**When does Cafe24 data require Custom Service review?**

Custom Service review is needed when the source data includes custom fields, app-owned data, outside-system identifiers, unsupported structures, custom migration logic adjustment, Custom Platform behavior, or transformation requirements that standard service capability cannot safely interpret.
