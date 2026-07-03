# Bagisto Validation Priorities

Bagisto validation should prove more than whether records arrived. A Bagisto migration must show that migrated data can operate inside Bagisto’s Laravel-based commerce structure, where product types, attributes, attribute families, categories, channels, inventory sources, customer groups, orders, CMS content, marketing rules, extensions, APIs, themes, and optional marketplace or B2B layers all shape how the store works after launch.

A successful validation pass separates migrated facts from configured behavior. Product names, SKUs, customer records, and order history may be visible in the admin area, but visibility alone does not confirm that products can be maintained, filtered, purchased, priced, assigned to the right channel, connected to inventory sources, found through search, or interpreted correctly in historical orders. Validation has to test operating meaning.

The strongest validation model for Bagisto follows a clear sequence: confirm the target operating model, validate catalog structure, validate customer and order continuity, validate channels and inventory, validate CMS and SEO behavior, validate extensions and custom development boundaries, and use Demo Migration evidence to decide whether Full Migration is ready.

### What Validation Means for Bagisto <a href="#what-validation-means-for-bagisto" id="what-validation-means-for-bagisto"></a>

Validation for Bagisto means checking whether migrated records behave correctly inside Bagisto’s commerce model. It is not a record-count exercise. A count can confirm that many Products, Customers, Orders, CMS Pages, or Blog Posts arrived, but it cannot prove that product types, attributes, attribute families, channel visibility, inventory sources, customer groups, tax behavior, shipping behavior, search behavior, or API usage remain usable.

Bagisto validation should answer three questions:

| Validation question             | What it proves                                                                                        | Why it matters                          |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------- |
| Did the record migrate?         | The expected object exists in Bagisto                                                                 | Confirms baseline transfer completeness |
| Does the record retain meaning? | The object still expresses the right product, customer, order, content, or rule behavior              | Confirms business continuity            |
| Can the merchant operate it?    | The object can be edited, displayed, filtered, purchased, reported, or connected to the right process | Confirms launch readiness               |

The third question is the most important. A product that exists but uses the wrong attribute family is not ready. A customer that exists but has lost group meaning may damage pricing or access assumptions. An order that exists but no longer explains discounts, shipping, taxes, invoices, shipments, refunds, or transaction references may not support support-team work after launch. A CMS Page that migrated but lost URL or layout relevance may still create search or conversion issues.

Bagisto validation should also distinguish supported migration scope from target-side implementation. Some items are migrated data. Others are configuration, development, theme work, extension setup, or integration testing. The validation process should not force every issue into the migration scope. It should assign each issue to the right owner and decide whether the problem requires data correction, mapping adjustment, Add-ons, Custom Service, target configuration, or separate development work.

### Validate the Bagisto Operating Model <a href="#validate-the-bagisto-operating-model" id="validate-the-bagisto-operating-model"></a>

Before reviewing individual records, confirm that the migrated store matches the intended Bagisto operating model. Bagisto can support a straightforward single-channel store, but it can also support multi-channel commerce, multiple inventory sources, custom packages, headless builds, marketplace layers, B2B structures, and API-driven integrations. The validation plan should reflect the actual target operating shape.

Start with a simple operating-model check:

| Operating layer      | Validation focus                                                           | Pass signal                                                                           |
| -------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Selling model        | Single store, multi-channel, marketplace, B2B, or headless use             | Migrated data is organized around the intended selling model                          |
| Product architecture | Product types, attributes, attribute families, and product relationships   | Products can be edited and purchased according to their intended behavior             |
| Channel model        | Locale, currency, theme, catalog visibility, and channel-specific settings | Products and content appear in the right channels with the right assumptions          |
| Inventory model      | Inventory sources, stock status, availability, and source assignment       | Availability is understandable and operationally usable                               |
| Customization model  | Extensions, packages, APIs, themes, or frontend components                 | Custom behavior is assigned to configuration, Add-ons, Custom Service, or development |

This check helps prevent a common validation mistake: reviewing Bagisto as if it were only a data repository. Bagisto’s flexibility creates value only when migrated data is placed into the right operating model. For example, a product may validate in a simple product list but fail when tested by channel, inventory source, attribute family, or custom product type. A CMS Page may appear in the admin area but fail in the storefront or headless frontend if routing, theme placement, or API consumption is incomplete.

Validation should classify findings into three statuses:

| Status | Meaning                                                                                          | Action                                       |
| ------ | ------------------------------------------------------------------------------------------------ | -------------------------------------------- |
| Pass   | Data and behavior are ready for the intended Bagisto use                                         | Continue toward launch readiness             |
| Watch  | Data is mostly correct but needs configuration, mapping adjustment, or owner review              | Resolve before final approval                |
| Block  | Data or behavior would break launch, reporting, checkout, SEO, inventory, or customer continuity | Stop Full Migration approval until corrected |

This status model keeps validation practical. It prevents minor display issues from being treated like structural failures, but it also prevents serious product, order, channel, inventory, or customization problems from being hidden inside a broad “needs review” label.

### Validate Products, Product Types, Attributes, and Attribute Families <a href="#validate-products-product-types-attributes-and-attribute-families" id="validate-products-product-types-attributes-and-attribute-families"></a>

Product validation is the center of most Bagisto migration reviews. Bagisto supports multiple product types and relies heavily on attributes and attribute families. A product should not be approved only because its SKU, name, price, and description are present. It should be approved only when its selling behavior and maintenance structure work correctly.

Begin with product-type validation. Test representative records for simple, configurable, virtual, downloadable, bundle, grouped, booking, and custom product behavior where relevant. The goal is to confirm that each product type expresses the right buying experience. Configurable products should show the right choices. Bundle and grouped products should preserve the right relationships. Downloadable and virtual products should not behave like physical goods. Booking or custom product types should be reviewed with extra care because behavior may depend on target-side configuration or development.

Next validate attributes and attribute families. Attributes should not be treated as loose fields. Check whether each important attribute is required, visible, searchable, filterable, comparable, used for variants, or used only internally. Attribute families should group products in a way that makes admin maintenance realistic. If every product was forced into one broad family, the admin experience may become messy. If the migration created too many narrow families, product maintenance may become unnecessarily complex.

Use this product validation matrix:

| Product area       | What to test                                                                              | Watch signal                                         | Blocking signal                                            |
| ------------------ | ----------------------------------------------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------- |
| Product identity   | SKU, parent-child logic, duplicate handling, product status                               | Minor SKU formatting differences                     | Duplicate or broken product identity                       |
| Product type       | Simple, configurable, bundle, grouped, downloadable, virtual, booking, or custom behavior | Product type is correct but needs display adjustment | Product behaves as the wrong type                          |
| Attributes         | Required, searchable, filterable, comparable, variant-forming, internal                   | Attribute exists but has wrong storefront role       | Product cannot be filtered, edited, or purchased correctly |
| Attribute families | Field grouping by product class                                                           | Family assignments need cleanup                      | Admin maintenance becomes unreliable or misleading         |
| Media              | Image roles, gallery order, missing files, alt text                                       | Low-priority image order issue                       | Key product images missing or assigned incorrectly         |
| Pricing            | Base price, special price, tier or group pricing where relevant                           | Rule needs target configuration                      | Customer sees incorrect purchase price                     |

A useful validation sample should include easy records and difficult records. Easy products confirm baseline transfer quality. Difficult products reveal whether the migration can survive real catalog complexity. Include products with variants, product-specific attributes, multiple categories, special pricing, inventory-source implications, downloadable content, bundled relationships, and extension-created behavior where relevant.

### Validate Categories, Channels, Inventory Sources, and Storefront Discovery <a href="#validate-categories-channels-inventory-sources-and-storefront-discovery" id="validate-categories-channels-inventory-sources-and-storefront-discovery"></a>

Categories in Bagisto should be validated as discovery structures, not just as record containers. A category tree can look complete while still failing customer browsing, product assignment, channel visibility, SEO continuity, or filter behavior. Each important category should be checked against storefront use.

Category validation should confirm hierarchy, product assignment, category status, image or banner use, SEO fields, and channel relevance. If the old store had categories created for admin convenience rather than customer discovery, those categories may not deserve the same role in Bagisto. If categories carry SEO value, URL and metadata behavior need a separate check.

Channel validation is especially important when the Bagisto target will use multiple channels, locales, currencies, themes, or storefronts. A product may be correct in the default channel but missing from another channel. A CMS Page may look correct in one storefront but not another. A category may exist globally but require channel-specific visibility. Validation should test the intended customer-facing channel, not only the default admin view.

Inventory-source validation should confirm whether stock quantities and availability make sense in Bagisto. A legacy store may have used one stock number, manual fulfillment, supplier assumptions, or hidden warehouse logic. Bagisto validation should test how those assumptions are represented through inventory sources, stock status, and availability display.

| Validation layer      | Practical test                                                            | Pass signal                                                       |
| --------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Categories            | Browse top categories, subcategories, product assignments, and SEO fields | Customers can find products through the intended structure        |
| Channels              | Compare product and content visibility across channels                    | Each channel shows the right catalog and content assumptions      |
| Inventory sources     | Review quantity, stock status, and availability behavior                  | Product availability is operationally understandable              |
| Search and filters    | Test keyword search, layered navigation, and attribute filters            | Customers can narrow and find products without misleading results |
| Storefront experience | Review navigation, product cards, product pages, and checkout entry       | Migrated catalog supports a normal buying path                    |

This validation should be done with business context. A product missing from a hidden channel may not matter. A product missing from the primary channel is a launch blocker. A filter issue on an internal attribute may be minor. A filter issue on size, color, brand, compatibility, or product family can damage conversion and support workload.

### Validate Customers, Orders, and Commercial History <a href="#validate-customers-orders-and-commercial-history" id="validate-customers-orders-and-commercial-history"></a>

Customers and Orders must be validated for continuity, not just presence. Bagisto customer records should preserve identity, contact information, address quality, group assignment, newsletter status where relevant, review links, and any commercial meaning tied to customer groups or B2B behavior. Order records should preserve the historical facts needed for support, accounting review, fulfillment follow-up, and customer service.

Customer validation should compare a representative set of customers across normal retail accounts, guest-like histories, customer groups, high-value accounts, inactive accounts, and accounts with address variations. If the target Bagisto build uses customer groups for pricing, permissions, segmentation, or B2B behavior, group validation becomes a launch-readiness issue.

Order validation should include orders with discounts, taxes, shipping charges, payment references, invoices, shipments, refunds, transactions, order comments, and status transitions. Historical order records often contain logic from the old platform. Bagisto does not need to recreate every old configuration as live behavior, but the historical record should still be understandable.

| Record area                 | What to validate                                                 | Watch signal                        | Blocking signal                                   |
| --------------------------- | ---------------------------------------------------------------- | ----------------------------------- | ------------------------------------------------- |
| Customer identity           | Name, email, account status, addresses                           | Minor address cleanup needed        | Duplicate or merged accounts create confusion     |
| Customer groups             | Pricing, segmentation, permission, or B2B meaning                | Group names need normalization      | Group-based commercial logic is lost              |
| Orders                      | Products, totals, discounts, taxes, shipping, payment references | Minor status naming difference      | Historical totals or line items are misleading    |
| Invoices and shipments      | Invoice references, shipment status, refund references           | Some references require explanation | Support team cannot interpret fulfillment history |
| Reviews and account content | Product reviews, account-linked history                          | Minor formatting issue              | Important trust or account records are missing    |

The validation team should also test support scenarios. Can a support agent answer what a customer bought, what discount was applied, what tax was charged, whether a shipment or refund occurred, and what status the order ended with? If not, the order record may be technically migrated but operationally weak.

### Validate CMS, Marketing Rules, SEO, and Content Continuity <a href="#validate-cms-marketing-rules-seo-and-content-continuity" id="validate-cms-marketing-rules-seo-and-content-continuity"></a>

Bagisto validation should include CMS and marketing continuity because these areas affect more than appearance. CMS Pages, content blocks, menus, email templates, URL rewrites, search terms, cart rules, catalog rules, newsletters, and campaign-related content can influence discoverability, conversion, compliance, and customer communication.

CMS validation should test high-value landing pages, policy pages, product-support pages, brand pages, and content blocks that appear in navigation or checkout. A CMS Page that exists but is not linked, styled, routed, or localized correctly may still fail its purpose. Content should be checked in the storefront context where customers will see it.

Marketing-rule validation should distinguish historical meaning from active behavior. A discount visible in an old order may need to remain interpretable as history. An active cart or catalog rule in Bagisto must be rebuilt and tested as live behavior. Do not assume that old promotion logic can be copied directly into Bagisto rules without review.

SEO validation should cover URLs, metadata, canonical assumptions, redirects, category/product page indexing, sitemap behavior, and search continuity. If the migration changes category paths, product URLs, or CMS page slugs, redirect planning becomes part of launch readiness.

| Area                             | Validation question                                          | Pass signal                                                     |
| -------------------------------- | ------------------------------------------------------------ | --------------------------------------------------------------- |
| CMS Pages                        | Are key pages present, linked, styled, and accessible?       | Customers can reach and use important content                   |
| Menus and content blocks         | Do navigation and page elements appear in the right context? | Storefront browsing remains coherent                            |
| Cart and catalog rules           | Are active promotions rebuilt and tested?                    | Discounts apply only when intended                              |
| Email and customer communication | Are templates, messages, or content assumptions ready?       | Customer-facing communication is not broken by launch           |
| URLs and redirects               | Are important product, category, and CMS URLs handled?       | Search and referral traffic have a safe path into the new store |
| Search behavior                  | Do search terms and important queries return useful results? | Customers can find important products after launch              |

CMS and SEO issues are often underestimated because they do not always appear in record-count checks. They can still affect revenue immediately after launch. Validation should therefore treat high-value content and high-value URLs as launch assets.

### Validate Extensions, APIs, Headless Behavior, and Custom Development Boundaries <a href="#validate-extensions-apis-headless-behavior-and-custom-development-boundaries" id="validate-extensions-apis-headless-behavior-and-custom-development-boundaries"></a>

Bagisto projects often include extensions, custom packages, API integrations, custom themes, and headless or hybrid frontend components. These should be validated separately from migrated data because they may depend on code, target configuration, external systems, deployment ownership, or custom development.

Start by identifying which behaviors are native Bagisto configuration, which are supported through migration mapping, which can be handled through Add-ons, and which require Custom Service or separate implementation. Add-ons can support bounded filtering, mapping, or configuration within supported migration behavior. Custom Service is appropriate when unsupported records, custom fields, extension-created tables, custom packages, bespoke transformations, or custom development data must be handled.

Validation should include integration-facing tests. If an external ERP, PIM, shipping system, payment provider, marketplace connector, search tool, analytics layer, or frontend consumes Bagisto data, test the payloads, identifiers, synchronization direction, and failure handling. A record can look correct in Bagisto but fail in the connected system if identifiers or field formats changed.

| Dependency type   | Validation focus                                                         | Decision cue                                                        |
| ----------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| Extensions        | Records, settings, owned fields, and behavior impact                     | Preserve through configuration, Add-ons, Custom Service, or rebuild |
| Custom packages   | Database tables, models, admin screens, and storefront behavior          | Usually needs Custom Service or separate development scope          |
| APIs              | External IDs, payloads, authentication, sync ownership, update direction | Validate with real integration cases                                |
| Headless frontend | Routes, product payloads, CMS consumption, search, cart entry            | Validate customer-facing behavior, not only admin records           |
| Theme work        | Layout, menus, product cards, checkout entry, responsive behavior        | Treat as implementation readiness, not raw migration data           |

This section is where validation protects the project from false confidence. A Demo Migration may succeed for standard records while the launch still fails because the frontend, ERP, search engine, marketplace integration, or custom package cannot interpret the migrated data. Those problems should be visible before Full Migration approval.

### Use Demo Migration Evidence to Decide Launch Readiness <a href="#use-demo-migration-evidence-to-decide-launch-readiness" id="use-demo-migration-evidence-to-decide-launch-readiness"></a>

Demo Migration should be used as proof, not reassurance. The sample must include Bagisto-relevant complexity: product types, attributes, attribute families, categories, channels, inventory sources, customers, orders, CMS content, SEO behavior, marketing rules, extensions, APIs, headless components, marketplace or B2B records where relevant, and custom development data when it affects operation.

A useful Demo Migration review should produce a launch-readiness decision:

| Decision                 | Evidence pattern                                                                                                        | Next action                                            |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Ready to continue        | Representative records pass data, behavior, configuration, and ownership checks                                         | Proceed toward Full Migration planning                 |
| Continue with correction | Core scope is valid but mapping, configuration, filtering, or sample selection needs adjustment                         | Correct issues and rerun affected samples              |
| Escalate scope           | Unsupported records, custom packages, API behavior, marketplace data, B2B logic, or custom product behavior is material | Review Add-ons or Custom Service before Full Migration |
| Stop and re-plan         | Target operating model, channel plan, inventory model, or development ownership is unclear                              | Rebuild the migration scope before proceeding          |

Validation should also define what happens after the first run. If new products, customers, orders, Blog Posts, CMS changes, or configuration changes occur before launch, follow-up migration planning should be handled deliberately. Continue the Migration with the last used configuration when new records need to be added and the mapping remains valid. Continue the Migration with a new configuration when mapping, filtering, or configuration has changed. Perform a new migration when the target store, data scope, or business rules have changed enough that continuing would layer inconsistent assumptions onto Bagisto.

The final launch decision should be specific. Do not approve launch because “the data looks fine.” Approve it because representative records prove that Bagisto can support the intended operating model, customers can buy correctly, administrators can maintain the catalog, historical records remain interpretable, integrations have owners, and unresolved issues have clear handling.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Bagisto validation should prove operating readiness. The most important checks are not only record counts or admin visibility, but whether migrated data works inside Bagisto’s product-type, attribute, channel, inventory, customer, order, CMS, marketing, extension, API, and storefront model.

A strong validation process separates what migrated correctly from what must be configured, rebuilt, mapped, escalated, or owned by implementation work. It uses Demo Migration evidence to test representative complexity before Full Migration. It classifies issues as pass, watch, or block. It also defines follow-up migration handling before launch, so late changes do not create inconsistent target data.

When validation is handled this way, Bagisto migration becomes less risky. Merchants can launch with a clearer understanding of what was transferred, what was configured, what was rebuilt, and what is ready for real customers.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is record count enough to validate a Bagisto migration?**

No. Record count confirms transfer completeness, but Bagisto validation also needs to prove product behavior, attributes, channels, inventory sources, customer groups, orders, CMS content, SEO, extensions, APIs, and storefront usability.

**Which Bagisto records should be included in Demo Migration validation?**

Use representative records: simple and complex products, different product types, attributes, attribute families, category assignments, channel assignments, inventory-source cases, customer groups, orders with discounts and taxes, CMS Pages, marketing rules, and custom or integration-dependent records.

**How should custom packages or extensions be validated?**

Check whether they create records, fields, tables, API behavior, storefront behavior, or checkout behavior. Supported mapping may fit normal migration scope, bounded adjustments may fit Add-ons, and unsupported or custom behavior may require Custom Service or separate development.

**What makes an issue a launch blocker?**

An issue should block launch when it would make products unbuyable, pricing misleading, inventory unreliable, orders hard to interpret, customers incorrectly grouped, SEO continuity unsafe, integrations unusable, or the Bagisto storefront unable to support the intended operating model.

**When should follow-up migration options be planned?**

Plan them before launch. If new records arrive and configuration is unchanged, continue with the last used configuration. If mapping changes, continue with a new configuration. If the target store or business rules changed materially, perform a new migration.
