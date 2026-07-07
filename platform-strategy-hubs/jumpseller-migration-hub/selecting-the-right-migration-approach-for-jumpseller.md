# Selecting the Right Migration Approach for Jumpseller

Choosing the right migration approach for Jumpseller depends on how clearly the source store can be translated into Jumpseller’s hosted commerce structure. A small store can still require careful handling if product options drive inventory or pricing. A larger store can still be straightforward if products, categories, customers, orders, pages, and redirects follow predictable structures. The right approach is determined by evidence, not by platform name or data volume alone.

Jumpseller migration planning should separate supported data movement from operational interpretation. Products, categories, customers, orders, CMS Pages, Blog Posts, and other supported data may move through a standard path when the source data is clean and target-side expectations are clear. Add-ons can help when the requirement is filtering, mapping, or supported configuration. Custom Service becomes relevant when the project involves unsupported app data, custom fields with business logic, external identifiers, Custom Platform behavior, or custom migration logic adjustment.

The safest approach is selected after preparation and Demo Migration reveal how the source store actually works. The goal is not to choose the heaviest service path. It is to avoid choosing a light path for requirements that need interpretation, configuration, or custom handling.

### Start With the Migration Responsibility Model <a href="#start-with-the-migration-responsibility-model" id="start-with-the-migration-responsibility-model"></a>

The first decision is who should manage execution and how much operational involvement is needed. A customer-led migration can work when the source data is predictable, the team understands the migration steps, and the target store setup is already prepared. A Next-Cart-led migration can be safer when the team wants execution support, review discipline, or a managed process even if the data itself remains standard.

| Approach         | Best fit                                                                                                                                                        | Caution                                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Standard Service | Supported source data, prepared Jumpseller setup, clean product/category/customer/order structure, and a team ready to self-perform the migration process       | Not ideal if the team expects Next-Cart to interpret complex business logic or manage all execution decisions |
| Managed Service  | Standard migration capability, but the customer wants Next-Cart-led execution and less hands-on migration operation                                             | Still depends on standard migration capability unless additional custom work is agreed                        |
| Add-ons          | Filtering, mapping, or configuration requirements that fit supported Add-on behavior                                                                            | Add-ons do not replace Custom Service for unsupported app data or bespoke transformation                      |
| Custom Service   | Custom Platform handling, unsupported data, app-owned records, custom fields with business behavior, external identifiers, or custom migration logic adjustment | Scope should be defined from evidence, not assumed from a vague request for customization                     |

A Jumpseller migration can also combine approaches. A project may use Managed Service for execution, Add-ons for selective mapping, and Custom Service for a specific unsupported data area. The key is to name the reason for each component instead of treating the migration as one undifferentiated service choice.

### Match the Approach to Product and Catalog Complexity <a href="#match-the-approach-to-product-and-catalog-complexity" id="match-the-approach-to-product-and-catalog-complexity"></a>

Product structure is often the strongest signal for the right Jumpseller migration approach. A clean product catalog with ordinary SKUs, categories, images, prices, stock, and SEO fields can often fit a standard path. A catalog with dense variants, custom fields, app-based product builders, bundles, digital fulfillment, or source-specific option behavior needs closer review.

Jumpseller product options and variants should be tested with representative samples. If the source uses options only as display attributes, the handling may be simpler. If options create sellable combinations with separate SKU, price, stock, image, or weight behavior, the migration approach should prove that those meanings remain usable.

| Product profile                                                                             | Likely service path                                            | Why                                                                                                            |
| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Simple products with ordinary categories, images, prices, stock, and SEO fields             | Standard Service or Managed Service                            | The data meaning is likely predictable if the source platform is supported and the target store is prepared    |
| Products with sellable variants that affect SKU, price, image, or stock                     | Standard Service or Managed Service after Demo Migration proof | The approach is suitable only if variant behavior remains operational in sample results                        |
| Products with large or unusual option matrices                                              | Add-on or Custom Service review depending on source behavior   | Dense structures can expose mapping, limit, or transformation needs                                            |
| Products with custom fields used as specifications                                          | Add-ons may help if the requirement is supported mapping       | Custom Service may be needed if those fields drive purchase behavior or external workflows                     |
| Bundles, kits, subscriptions, product builders, personalization, or app-owned product logic | Custom Service review                                          | These behaviors often depend on app data, custom logic, or external rules rather than standard product records |

The approach should be adjusted when Demo Migration shows that product behavior was underestimated. A clean-looking catalog can become a Custom Service case when the critical product meaning lives outside ordinary product and variant fields.

### Match the Approach to Customers, Orders, and Historical Meaning <a href="#match-the-approach-to-customers-orders-and-historical-meaning" id="match-the-approach-to-customers-orders-and-historical-meaning"></a>

Customer and order data should be assessed for meaning, not only volume. A standard migration may be enough when customer records contain ordinary profile and address information and orders contain understandable line items, totals, payment status, fulfillment status, taxes, discounts, and shipping data. More careful handling is needed when the source store uses custom statuses, group-based logic, payment references, tax identifiers, subscriptions, customer segmentation, staff notes, or external order IDs.

Historical order migration is different from future checkout configuration. A migrated order can preserve the history of what happened, but future payments, shipping, taxes, and checkout behavior must be configured inside Jumpseller. The service path should not assume that order history and operating checkout are the same problem.

| Data area           | Standard-path signal                                                                                         | Upgrade signal                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Customer records    | Name, email, phone, address, account status, and ordinary profile fields                                     | Customer groups control pricing, access, tax, payment, shipping, or external CRM behavior                           |
| Customer accounts   | Customer identity can remain readable and customer communication is planned                                  | Password expectations, account activation, or customer access rules are unclear                                     |
| Orders              | Order history contains ordinary line items, totals, payment status, fulfillment status, discounts, and taxes | Custom statuses, app-owned data, external IDs, partial fulfillment rules, or complex refunds require interpretation |
| Historical payments | Payment method and status need to remain readable                                                            | Transaction references must feed accounting, ERP, or external reconciliation workflows                              |
| Fulfillment         | Shipping method and fulfillment status are enough for history                                                | Warehouse, supplier, marketplace, dropshipping, pickup, or multi-location behavior affects operations               |

A service path that works for catalog data may not be enough for customer and order continuity. If staff need historical order data for service, tax, warranty, returns, or reconciliation, order samples should be reviewed before the approach is confirmed.

### Match the Approach to Content, SEO, Languages, and Redirects <a href="#match-the-approach-to-content-seo-languages-and-redirects" id="match-the-approach-to-content-seo-languages-and-redirects"></a>

Jumpseller migration can involve CMS Pages, Blog Posts, product pages, category pages, metadata, image content, internal links, language versions, and URL redirects. The right approach depends on whether the content can be represented cleanly in Jumpseller or whether the source store uses custom page builders, embedded app content, unusual URL patterns, or multilingual structures that need interpretation.

Do not treat content as secondary if the old store relies on content for search visibility, product education, buying guides, policy trust, or campaign landing pages. A migration that preserves products but breaks key content pathways can create customer friction and SEO loss.

| Content profile                                                         | Likely approach                                                                     | Review focus                                                                        |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Ordinary pages, posts, metadata, and image content                      | Standard Service or Managed Service                                                 | Confirm readability, formatting, internal links, and destination quality            |
| High-value product/category URLs                                        | Standard path with redirect planning, or Add-ons if supported URL mapping is needed | Confirm source URL inventory and target destination quality                         |
| Multilingual content across products, categories, pages, and SEO fields | Demo Migration proof before full execution                                          | Confirm language setup and translation placement before launch                      |
| Page-builder or app-owned content                                       | Custom Service review may be needed                                                 | Determine whether content can move as usable content or requires rebuilding         |
| Complex internal linking or campaign landing pages                      | Add-on or Custom Service review depending on mapping needs                          | Broken internal links and weak redirects can damage usability and search continuity |

The service path should preserve valuable content where it matters and avoid migrating obsolete content only because it exists. Content scope should be an editorial and operational decision, not only a database decision.

### Use Add-ons for Supported Configuration Needs <a href="#use-add-ons-for-supported-configuration-needs" id="use-add-ons-for-supported-configuration-needs"></a>

Add-ons should be used when the migration requirement fits a supported, bounded need such as filtering, mapping, or configuration. They are useful when the project needs selective data movement, value adjustments, field mapping, or scope control that remains within supported migration capability.

Add-ons should not be used as a vague solution for every difficult requirement. If the source requirement depends on unsupported app data, custom fields with business behavior, external identifiers, or custom migration logic adjustment, Custom Service is the correct review path.

| Add-on use case              | Appropriate when                                                                              | Not appropriate when                                                                              |
| ---------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Data filtering               | The project needs to migrate only selected products, customers, orders, pages, or date ranges | The filter depends on unsupported app logic or unclear source meaning                             |
| Field mapping                | Source values need to map into supported target fields or supported custom handling           | Values must drive new business rules or bespoke storefront behavior                               |
| Category or value adjustment | The project needs controlled remapping or cleanup within supported behavior                   | The category structure is tied to custom navigation logic, marketplace rules, or external systems |
| Additional Migration Options | The project needs bounded options relevant to scope, timing, or data handling                 | The request implies unsupported transformation or app-owned data extraction                       |

A useful test is whether the requirement can be described as a supported migration setting or whether it requires custom interpretation. Supported settings belong in Add-ons. Custom interpretation belongs in Custom Service review.

### Use Custom Service for Unsupported or Bespoke Requirements <a href="#use-custom-service-for-unsupported-or-bespoke-requirements" id="use-custom-service-for-unsupported-or-bespoke-requirements"></a>

Custom Service is appropriate when the migration requires customization, modification, Custom Platform handling, unsupported app data, Tailored Add-ons, Custom Add-ons, external identifiers, custom fields with operational meaning, or custom migration logic adjustment. It is not a premium label for ordinary complexity; it is the correct path when standard migration capability is not enough.

For Jumpseller, Custom Service should be reviewed when product behavior, customer behavior, order meaning, stock workflows, content structures, or integration requirements cannot be represented through standard migration behavior or supported Add-ons.

| Custom Service trigger            | Example                                                                                             | Why it matters                                                                |
| --------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Custom Platform source            | The source store uses a custom-built catalog or checkout structure                                  | Data needs interpretation before it can become usable Jumpseller records      |
| Unsupported app data              | Reviews, subscriptions, bundles, loyalty, product feeds, or custom checkout data live in app tables | App-owned data may not be available through standard migration paths          |
| External identifiers              | ERP, warehouse, accounting, marketplace, or fulfillment IDs must remain usable                      | IDs may require specific preservation, transformation, or mapping             |
| Custom fields with behavior       | A field controls pricing, eligibility, stock, product display, or fulfillment                       | The field is business logic, not only informational content                   |
| Custom migration logic adjustment | The project needs bespoke transformation rules                                                      | Standard settings and Add-ons are not enough to express the required handling |

Custom Service should be scoped with examples. The strongest request is not “customize the migration.” It is a clear statement such as: preserve ERP product IDs as usable references, transform source product builder options into Jumpseller-readable product fields, or retain custom order metadata for staff review.

### Use Demo Migration as the Decision Gate <a href="#use-demo-migration-as-the-decision-gate" id="use-demo-migration-as-the-decision-gate"></a>

Demo Migration should decide whether the selected approach matches the real store. It should not be treated as a small preview of easy records. The sample set should include records that prove ordinary behavior and records that expose difficult behavior.

| Demo Migration sample  | What it should test                                                                              | Decision outcome                                                            |
| ---------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------- |
| Simple product         | Product identity, price, image, stock, category, and SEO fields                                  | Confirms baseline catalog handling                                          |
| Variant product        | Option names, option values, SKU, price, image, weight, stock, and availability                  | Confirms sellable choices remain operational                                |
| Complex product        | Custom fields, digital behavior, made-to-order data, bundles, or app-owned logic                 | Reveals Add-on or Custom Service needs                                      |
| Customer sample        | Addresses, language, marketing consent, group labels, and account expectations                   | Confirms customer records are usable without overstating account continuity |
| Order sample           | Payment status, fulfillment status, refunds, taxes, discounts, custom statuses, and external IDs | Confirms historical order meaning remains readable                          |
| Content and URL sample | CMS Pages, Blog Posts, metadata, internal links, and redirects                                   | Confirms content and SEO continuity are realistic                           |
| Integration sample     | Records connected to ERP, fulfillment, warehouse, marketplace, or reporting workflows            | Identifies external-system dependency before full migration                 |

A strong Demo Migration result should lead to one of three decisions: proceed with the selected approach, add supported Add-ons or configuration changes, or move specific requirements into Custom Service review.

### Decide the Safest Jumpseller Migration Approach <a href="#decide-the-safest-jumpseller-migration-approach" id="decide-the-safest-jumpseller-migration-approach"></a>

After preparation and Demo Migration, choose the lightest approach that can reliably preserve business meaning. Do not choose a heavier path just because the source store is large. Do not choose a lighter path just because the store looks simple on the surface.

| Project evidence                                                                                                                     | Recommended direction                                                                     | Reason                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Supported source data, clean catalog, ordinary customers and orders, prepared Jumpseller setup, and customer-led execution readiness | Standard Service                                                                          | The project fits a predictable supported migration path                                   |
| Supported source data, standard complexity, but customer prefers Next-Cart-led execution                                             | Managed Service                                                                           | Execution support is needed even if custom migration logic is not                         |
| Supported data with bounded filtering, mapping, or configuration needs                                                               | Standard Service or Managed Service with Add-ons                                          | Add-ons can handle supported scope or mapping adjustments                                 |
| Supported data plus specific unsupported app records, external IDs, or custom field behavior                                         | Custom Service for those requirements, with the broader execution path defined separately | The custom requirement should be scoped instead of buried inside a general service choice |
| Custom Platform source or bespoke transformation requirement                                                                         | Custom Service                                                                            | The source structure requires custom interpretation or custom migration logic adjustment  |
| Standard start, but Demo Migration exposes difficult product, customer, order, content, or integration behavior                      | Adjust the service path before full migration                                             | Evidence should change the plan before execution creates rework                           |

The safest approach is evidence-led. A migration can start with a standard assumption, but that assumption should remain provisional until the difficult samples are reviewed.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right migration approach for Jumpseller means matching the service path to the source store’s real structure and the target store’s operating requirements. Standard Service can fit clean, supported migrations where the customer is ready to self-perform the migration process. Managed Service can fit standard migrations where Next-Cart-led execution is preferred. Add-ons can support filtering, mapping, and configuration needs when the requirement remains within supported behavior. Custom Service is the right path for unsupported data, Custom Platform handling, external identifiers, custom fields with business meaning, tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

The decision should be made from preparation evidence and Demo Migration results. If the difficult samples preserve product, customer, order, content, SEO, and integration meaning, the selected approach can proceed. If those samples expose unsupported behavior, the service path should be adjusted before full migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a Jumpseller migration?**

Standard Service can be enough when the source path is supported, the data is clean, Jumpseller can represent the required product, customer, order, content, and SEO structure, and the customer is ready to self-perform the migration process. Demo Migration should confirm the assumption before full migration.

**When should Managed Service be selected?**

Managed Service is useful when the migration remains within standard capability but the customer wants Next-Cart-led execution. It is often suitable when the data is not custom, but the team prefers a managed process and support during execution and review.

**When are Add-ons relevant for Jumpseller?**

Add-ons are relevant when the requirement is bounded filtering, mapping, or configuration within supported migration behavior. Examples include selective data movement, value mapping, or supported options that help the migrated data fit the target store more cleanly.

**When does a Jumpseller migration require Custom Service?**

Custom Service is appropriate when the project includes Custom Platform handling, unsupported app data, external identifiers, custom fields with operational meaning, Tailored Add-ons, Custom Add-ons, bespoke transformation, or custom migration logic adjustment.

**Can a project combine Managed Service, Add-ons, and Custom Service?**

Yes. A project may use Managed Service for execution, Add-ons for supported mapping or filtering, and Custom Service for specific unsupported requirements. Each component should have a clear reason and scope.

**What should Demo Migration prove before the final approach is confirmed?**

Demo Migration should prove that ordinary and difficult samples remain usable in Jumpseller. It should test products, variants, categories, customers, orders, content, URLs, and dependency-linked records so the chosen service path is based on evidence rather than assumptions.
