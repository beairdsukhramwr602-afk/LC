# Selecting the Right Migration Approach for Shopify Plus

Selecting the right Shopify Plus migration approach means matching service responsibility to enterprise operating complexity. Shopify Plus belongs to the Shopify family, but the migration decision changes when the target environment includes organization-level management, expansion stores, B2B companies, Markets, localized content, custom apps, automation, and integrations with systems such as ERP, PIM, OMS, WMS, CRM, tax, shipping, loyalty, or subscription platforms.

The best approach is not automatically the most complex service path. It is the lightest path that can still protect the intended Shopify Plus outcome. Some Plus migrations can use Standard Service when data is supported and the customer can review results confidently. Others need Managed Service because execution, sequencing, or team coordination is risky. Add-ons can handle bounded supported adjustments. Custom Service is required when unsupported data, custom logic, external-system identifiers, or bespoke transformation affects the outcome.

### Start With Enterprise Scope, Not Record Count <a href="#start-with-enterprise-scope-not-record-count" id="start-with-enterprise-scope-not-record-count"></a>

Record count is only one planning signal. A Shopify Plus migration with fewer records can still be complex if those records represent B2B companies, regional catalogs, product restrictions, multi-store content, ERP-controlled pricing, localized URLs, or custom data. A larger migration can remain straightforward when the source data fits supported Shopify structures and review ownership is clear.

Begin by classifying the enterprise scope:

| Scope area                    | Approach question                                                                                             | Service-path implication                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Organization and stores       | Is the migration going into one store, multiple expansion stores, or separate B2B/D2C stores?                 | Multi-store scope often increases sequencing and validation needs even when records are supported. |
| B2B                           | Do companies, buyers, catalogs, price lists, payment terms, or restricted products need to be represented?    | B2B structures can require careful mapping, Shopify setup, integrations, or Custom Service review. |
| Markets and localization      | Are countries, currencies, domains, languages, and localized content part of launch?                          | International scope increases URL, content, pricing, and validation complexity.                    |
| Product governance            | Are products controlled by PIM, ERP, merchandising rules, bundles, subscriptions, or custom fields?           | Supported data may fit Add-ons; app-owned or bespoke logic may require Custom Service.             |
| Order and fulfillment context | Are historical orders needed for finance, support, B2B account management, or external-system reconciliation? | Readability and external references may affect scope.                                              |
| Apps and integrations         | Which systems own business-critical data or workflows?                                                        | External-system ownership often determines whether standard migration is enough.                   |

The migration approach should follow the hardest business-critical scope area. Shopify Plus planning fails when the easiest entity type controls the service decision while B2B, localization, or integration complexity is left for later.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be suitable when the selected entities are supported, the target Shopify Plus structure is already clear, and the customer can perform available migration actions and review results without intensive coordination.

Standard Service is usually realistic when:

* the migration is focused on supported products, variants, collections, customers, orders, CMS Pages, Blog Posts, images, reviews, coupons, or other supported entities;
* the target uses one store or a clearly scoped set of stores;
* B2B structures are not central to the migration result or are being configured separately in Shopify Plus;
* Markets, domains, localized content, and redirects are straightforward or handled outside migration scope;
* app-owned data and custom fields are not business-critical migration requirements;
* customer and order history is mainly needed for reference;
* the customer can review Demo Migration and Full Migration results confidently;
* no unsupported source structures or bespoke transformations control the launch outcome.

Standard Service can still be used in a Shopify Plus environment. The Plus plan alone does not require a custom approach. The deciding factor is whether the required result stays within supported behavior and whether the customer can own execution and validation responsibility.

### When Managed Service Is Safer <a href="#when-managed-service-is-safer" id="when-managed-service-is-safer"></a>

Managed Service may be safer when the migration remains within supported capability but the execution environment is too coordination-heavy for a customer-led path. Shopify Plus projects often involve multiple stakeholders: merchandising, localization, wholesale, operations, customer support, finance, SEO, IT, integration partners, and leadership. Even when data structures are supported, sequencing and approval can become the main risk.

Managed Service is especially useful when:

| Managed Service signal     | Shopify Plus context                                                                                  |
| -------------------------- | ----------------------------------------------------------------------------------------------------- |
| Multi-store launch         | Data must be assigned, reviewed, or sequenced across several stores.                                  |
| Complex catalog review     | Product, variant, collection, image, metafield, and status behavior needs structured sample approval. |
| B2B/D2C mix                | Customer, company, catalog, pricing, and account context needs coordinated review.                    |
| International rollout      | Markets, domains, redirects, languages, and localized content must be checked carefully.              |
| Limited internal bandwidth | The customer needs Next-Cart-led execution support while internal teams validate results.             |
| High launch sensitivity    | The business cannot afford unclear responsibility during Demo Migration and Full Migration.           |

Managed Service does not convert unsupported data into supported data. If the need involves app-owned records, custom fields, external identifiers, bespoke transformation, or unsupported source structures, Custom Service should be reviewed even when Managed Service is also useful for execution support.

### Where Add-ons Fit in Shopify Plus Migration <a href="#where-add-ons-fit-in-shopify-plus-migration" id="where-add-ons-fit-in-shopify-plus-migration"></a>

Add-ons fit when the requirement is supported, specific, and bounded. They should not be used as a general label for enterprise customization. For Shopify Plus, Add-ons are often useful when the team needs better control over which records migrate, where supported values go, or how supported output should be configured.

| Add-on type             | Shopify Plus example                                                                                             | Boundary check                                                                                     |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Exclude inactive products, outdated CMS Pages, old orders, or irrelevant Blog Posts from a specific store scope. | Filtering should not remove records needed for B2B support, SEO, finance, or compliance review.    |
| Advanced Data Mapping   | Map supported source fields into appropriate Shopify destinations or custom-data structures where feasible.      | Mapping cannot recreate unsupported app behavior or external-system logic.                         |
| Advanced Data Configure | Adjust supported migration output so Shopify Plus data is easier to review or use.                               | Configuration must remain inside supported behavior.                                               |
| Custom Add-ons          | Handle a bounded special need that has a defined source, target, and acceptance rule.                            | Unsupported records, bespoke transformation, or custom logic should move to Custom Service review. |

The clearest test is whether the requirement can be described as a supported adjustment. If yes, an Add-on may fit. If the requirement depends on unsupported data, custom application behavior, external-system identity, or a unique transformation rule, Custom Service is the safer framing.

### When Custom Service Becomes Necessary <a href="#when-custom-service-becomes-necessary" id="when-custom-service-becomes-necessary"></a>

Custom Service should be considered when the Shopify Plus migration depends on requirements outside supported standard behavior. The trigger is not simply enterprise size. The trigger is a business-critical expectation that needs custom evaluation, bespoke handling, unsupported data interpretation, custom migration logic adjustment, Custom Platform handling, or external-system alignment.

Common Shopify Plus Custom Service triggers include:

* B2B companies, locations, catalogs, pricing, or payment terms that come from custom source structures;
* ERP, PIM, OMS, WMS, CRM, loyalty, subscription, or marketplace identifiers that must remain usable after migration;
* app-owned records that are not part of ordinary source exports;
* custom fields that need transformation into metafields, metaobjects, app structures, or external systems;
* multi-store source data that must be split, merged, or reorganized in a non-standard way;
* localized content, URL structures, or regional catalogs that require bespoke interpretation;
* custom product logic such as bundles, kits, subscriptions, personalization, build-your-own products, or quoting workflows;
* Custom Platform source data with no supported structure;
* migration output that must align with external integration rules.

Custom Service should be scoped through examples, not vague enterprise labels. The customer should provide representative products, companies, customers, orders, URLs, custom fields, integration identifiers, and target expectations. Without examples, Custom Service discussions can sound precise while the real requirement remains undefined.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should decide whether the selected approach is strong enough before Full Migration. For Shopify Plus, the sample set should test the highest-risk target structures, not only ordinary products and orders.

| Demo Migration sample              | Decision it should support                                                                                                              |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Variant-heavy product              | Whether product options, variants, SKUs, images, and inventory remain usable.                                                           |
| B2B company or customer sample     | Whether company, buyer, catalog, pricing, and account context need standard setup, Add-ons, Custom Service, or separate implementation. |
| Market-specific product or content | Whether localization, URL, visibility, and pricing assumptions are understood.                                                          |
| High-value redirect                | Whether old URLs have accepted Shopify Plus destinations.                                                                               |
| Custom-data sample                 | Whether metafields, metaobjects, app data, or custom identifiers are handled correctly.                                                 |
| Integration-owned record           | Whether external-system ownership has been preserved or intentionally excluded.                                                         |
| Exception order                    | Whether refunds, discounts, fulfillment, payment context, tax, and external references remain readable.                                 |
| Expansion-store sample             | Whether store-specific assignment and review responsibility are clear.                                                                  |

If Demo Migration fails because the selected approach cannot preserve business-critical meaning, the response should be scope correction. The team should not approve Full Migration while hoping enterprise issues will become clearer later.

### Entity Points and Shopify Plus Planning <a href="#entity-points-and-shopify-plus-planning" id="entity-points-and-shopify-plus-planning"></a>

Entity Points help estimate eligible migration volume. They do not measure enterprise complexity by themselves. Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path. Newly migrated eligible entities may consume Entity Points when first migrated.

For Shopify Plus, this means Entity Points should be interpreted alongside the operating model. A modest number of B2B companies or custom product records can require more planning than a large set of simple products. A large order history may be manageable when it is needed only for reference, but more complex when finance, support, ERP identifiers, and B2B account context rely on historical records.

| Planning signal  | What it helps estimate                             | What it does not decide                                             |
| ---------------- | -------------------------------------------------- | ------------------------------------------------------------------- |
| Product count    | Migration volume and possible Entity Points usage. | Variant meaning, B2B visibility, market availability, or app logic. |
| Customer count   | Buyer-record volume.                               | Company structure, buyer roles, permissions, or external IDs.       |
| Order count      | Historical volume.                                 | Payment, fulfillment, finance, and integration usefulness.          |
| Blog Posts count | Content volume.                                    | Localization, URL strategy, internal links, or SEO value.           |

Entity Points should support planning, not replace service-path evaluation.

### Additional Migration Options and Launch Timing <a href="#additional-migration-options-and-launch-timing" id="additional-migration-options-and-launch-timing"></a>

Shopify Plus launch windows often require later migration activity because source stores continue operating while the target environment is reviewed. The team may need to continue the migration with the last used configuration, continue with a new configuration, or perform a new migration if the target result should be refreshed.

The approach should define:

* which records may change before launch;
* whether the configuration remains the same;
* whether earlier migrated target data should remain or be replaced;
* who performs the migration action;
* which stores, markets, B2B records, URLs, and integrations must be revalidated;
* whether new eligible entities may consume Entity Points.

This is especially important when several teams validate different areas. A later migration action can affect products, customers, companies, orders, Blog Posts, redirects, localized content, and integration references. The chosen approach should include a revalidation plan, not only a launch date.

### Signals That the Approach Is Too Light <a href="#signals-that-the-approach-is-too-light" id="signals-that-the-approach-is-too-light"></a>

A Shopify Plus approach is too light when it treats enterprise governance as ordinary Shopify record transfer. The warning signs usually appear in review responsibility, target structure, and unsupported expectations.

| Warning signal                                                                        | Likely response                                                                                   |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Multi-store data ownership is unclear.                                                | Clarify store-level scope or consider Managed Service.                                            |
| B2B companies, buyers, catalogs, or pricing cannot be explained through examples.     | Prepare B2B evidence and review Custom Service if needed.                                         |
| Markets, localized URLs, currencies, or languages are treated as post-launch details. | Add market planning and validation before Full Migration.                                         |
| App-owned or external-system fields are business-critical.                            | Review Custom Service rather than relying on ordinary mapping.                                    |
| Demo Migration samples are approved by only one team.                                 | Assign review owners for merchandising, B2B, localization, operations, finance, and integrations. |
| Entity Points are used as the main complexity measure.                                | Reframe scope around operating meaning and validation burden.                                     |
| Later migration activity has no revalidation plan.                                    | Define action type, affected records, and post-action review.                                     |

These signals should be resolved before Full Migration. Waiting until launch makes it harder to separate migration issues, Shopify Plus setup gaps, integration timing, and unsupported expectations.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Shopify Plus migration approach is the lightest service path that can still protect the enterprise operating outcome. Standard Service can be appropriate when supported data and customer-led validation are realistic. Managed Service is safer when execution and stakeholder coordination create risk. Add-ons fit bounded supported adjustments. Custom Service is needed for unsupported data, custom fields, external-system identifiers, bespoke transformations, Custom Platform handling, or custom migration logic adjustment.

A strong approach is evidence-based. It defines the target organization structure, store scope, B2B requirements, Markets and localization, catalog governance, integrations, Entity Points planning, Demo Migration samples, and later migration activity before Full Migration begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Shopify Plus always a Custom Service migration?**

No. Shopify Plus does not automatically require Custom Service. Standard Service or Managed Service can be appropriate when the data is supported, the target structure is clear, and validation responsibility is realistic.

**When is Managed Service safer for Shopify Plus?**

Managed Service is safer when the migration remains within supported behavior but execution requires stronger coordination across stores, B2B, Markets, products, content, URLs, orders, and multiple review teams.

**How are Add-ons different from Custom Service for Shopify Plus?**

Add-ons support bounded filtering, mapping, or configuration within supported behavior. Custom Service handles unsupported data, app-owned records, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

**Do Entity Points measure Shopify Plus complexity?**

No. Entity Points help estimate eligible migration volume, but Shopify Plus complexity also depends on B2B, Markets, integrations, store structure, custom data, and validation responsibility.

**Why should Additional Migration Options be planned before launch?**

Source stores often keep changing while Shopify Plus is reviewed. Planning later migration activity helps the team decide which records should be updated, whether configuration changed, who performs the action, and what must be revalidated.
