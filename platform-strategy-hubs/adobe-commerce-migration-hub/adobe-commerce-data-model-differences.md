# Adobe Commerce Data Model Differences

A migration into Adobe Commerce can preserve visible storefront records while changing the commercial meaning behind those records.

Adobe Commerce is built for stores that often need more explicit governance around companies, shared catalogs, customer groups, differentiated pricing, staged content, websites, stores, store views, product structure, URL behavior, extensions, integrations, and custom data. That gives the platform strong enterprise capability, but it also means migration success cannot be judged by record presence alone.

A product may exist in Adobe Commerce but fail to appear for the correct company. A customer may exist but not belong to the right buying structure. A catalog may be present but not carry the intended pricing visibility. A page may be migrated but lose campaign timing. A value may be preserved but land at the wrong website, store, or store-view scope.

This article explains the Adobe Commerce data-model differences that usually matter most when evaluating whether migrated data still supports the intended business model.

### How Adobe Commerce Changes Commercial Meaning <a href="#how-adobe-commerce-changes-commercial-meaning" id="how-adobe-commerce-changes-commercial-meaning"></a>

Adobe Commerce often turns loosely managed source behavior into more explicit target structures.

In many Source Platforms, B2B access, private pricing, customer segmentation, campaign timing, storefront variations, and custom workflow rules may be handled through workarounds, extensions, manual team knowledge, or surrounding systems. In Adobe Commerce, many of those ideas may need to become defined structures inside the Target Platform.

That is why Adobe Commerce migration planning should ask a deeper question than whether data moved. The stronger question is whether the Target Platform understands the business rules the migrated data is supposed to support.

### Core Adobe Commerce Data Layers to Review <a href="#core-adobe-commerce-data-layers-to-review" id="core-adobe-commerce-data-layers-to-review"></a>

#### Company structure and buyer context <a href="#company-structure-and-buyer-context" id="company-structure-and-buyer-context"></a>

Adobe Commerce B2B planning often changes the main commercial unit from an individual customer account to a company relationship.

A customer may still have an account, email address, address book, and order history, but the buying meaning can depend on the company structure around that customer. The review should consider whether buyers, company relationships, roles, access expectations, and purchasing context still make sense after migration.

This matters most when the Source Platform used customer groups, wholesale accounts, manual approval processes, sales-team knowledge, custom fields, or external systems to represent account-based selling.

#### Shared catalogs and product visibility <a href="#shared-catalogs-and-product-visibility" id="shared-catalogs-and-product-visibility"></a>

Shared catalogs can make product access and pricing more explicit in Adobe Commerce.

Instead of treating all products as universally visible, the Target Platform may need to control which companies or buyer groups can see which products and which prices apply. A migration can preserve product records while still failing if shared catalog assignment does not reflect the intended commercial rules.

This area deserves early review when the business has:

* private catalogs
* negotiated pricing
* account-specific product visibility
* customer-specific product access
* wholesale or distributor price structures
* company-specific buying rules
* restricted product ranges

The validation question is not only whether products migrated. It is whether the correct buyers can see and purchase the correct products at the correct commercial terms.

#### Customer groups and shared catalog interaction <a href="#customer-groups-and-shared-catalog-interaction" id="customer-groups-and-shared-catalog-interaction"></a>

Customer groups can still matter in Adobe Commerce, but they should be reviewed in relation to shared catalogs, company accounts, pricing rules, tax classes, promotions, and storefront access.

A customer group that made sense in the Source Platform may not carry the same meaning after migration if Adobe Commerce now uses company and shared catalog structures to govern access. The business should decide whether a group should remain a commercial rule, become part of shared catalog planning, or be simplified during the move.

This is a common source of quiet migration risk because customer groups may appear preserved while their role in the future store has changed.

#### Product types, attributes, and attribute sets <a href="#product-types-attributes-and-attribute-sets" id="product-types-attributes-and-attribute-sets"></a>

Adobe Commerce keeps the Magento product foundation, so product structure still matters deeply.

Products may involve simple, configurable, grouped, bundle, virtual, or downloadable behavior. Attributes and attribute sets can affect product-family governance, layered navigation, comparison, merchandising, administration, and storefront behavior. Adobe Commerce enterprise features do not remove the need to review these baseline structures.

This matters because enterprise teams sometimes focus on company accounts, shared catalogs, and pricing rules while underestimating product-model translation. A B2B catalog is still only reliable if the underlying product structure is accurate.

#### Website, store, and store-view scope <a href="#website-store-and-store-view-scope" id="website-store-and-store-view-scope"></a>

Adobe Commerce uses website, store, and store-view scope to organize storefront contexts, localization, configuration, root categories, and content presentation.

That scope hierarchy can carry heavier commercial meaning in Adobe Commerce because it may interact with company relationships, shared catalogs, customer groups, pricing visibility, language, regional storefront behavior, and operational governance.

A migrated value can be technically present but still placed at the wrong scope. For example, product content, category assignment, URL behavior, CMS content, pricing context, or configuration assumptions may need to differ by website, store, or store view.

The strongest review question is whether each important value appears where the business expects it to apply.

#### Content Staging and campaign timing <a href="#content-staging-and-campaign-timing" id="content-staging-and-campaign-timing"></a>

Adobe Commerce can treat scheduled content and merchandising behavior as part of the platform model.

For stores that depend on seasonal launches, campaign windows, promotional updates, future product visibility changes, CMS updates, or scheduled merchandising, migration review should consider timing and sequencing, not only the current visible storefront state.

This changes how content and merchandising data should be understood. A migrated page, product, category, or promotion may look acceptable at one point in time while still failing to support future campaign behavior.

#### Orders, history, and enterprise interpretation <a href="#orders-history-and-enterprise-interpretation" id="orders-history-and-enterprise-interpretation"></a>

Historical orders should usually remain useful for support, reporting, customer service, accounting reference, and operational review.

In Adobe Commerce, order interpretation may be affected by company context, customer groups, product references, price visibility, tax behavior, shipping references, discounts, payment references, and integration history. The goal is not always to make old orders behave like new Adobe Commerce transactions. The goal is to preserve enough meaning for the business to use them after launch.

Order review should focus on whether stakeholders can still understand what was purchased, by whom, under which commercial context, and how that history supports ongoing operations.

#### URL rewrites and route governance <a href="#url-rewrites-and-route-governance" id="url-rewrites-and-route-governance"></a>

Adobe Commerce can manage URL rewrites for products, categories, and content pages, but native route capability does not replace URL planning.

A URL can redirect successfully and still fail commercially if the destination no longer reflects the original customer intent. Product consolidation, category restructuring, CMS changes, campaign pages, and scope changes can all affect whether the destination is still useful.

For SEO-sensitive migrations, Adobe Commerce route review should focus on high-value paths first and validate whether the destination preserves the strongest available product, category, or content meaning.

#### Extensions, integrations, and custom data <a href="#extensions-integrations-and-custom-data" id="extensions-integrations-and-custom-data"></a>

Adobe Commerce projects often include extensions, integrations, custom attributes, custom modules, ERP or CRM dependencies, external pricing systems, fulfillment systems, reporting fields, marketplace workflows, or custom checkout behavior.

Some of this information may not be standard platform data. Some of it may be necessary for storefront behavior, B2B operations, pricing, inventory, order routing, reporting, or customer support.

When that logic affects commercial outcomes, it should be treated as part of data-model review rather than as a minor technical detail. Custom fields, outside-system identifiers, extension-owned records, and bespoke transformation needs are strong signals for Custom Service review.

### What Migrated Data Must Prove in Adobe Commerce <a href="#what-migrated-data-must-prove-in-adobe-commerce" id="what-migrated-data-must-prove-in-adobe-commerce"></a>

#### Companies and buyers must prove relationship accuracy <a href="#companies-and-buyers-must-prove-relationship-accuracy" id="companies-and-buyers-must-prove-relationship-accuracy"></a>

Company records, buyer relationships, account access, and role meaning should be reviewed together.

The Target Platform should show not only that accounts exist, but that the correct people are attached to the correct buying structures with the correct commercial context.

#### Shared catalogs must prove visibility and pricing accuracy <a href="#shared-catalogs-must-prove-visibility-and-pricing-accuracy" id="shared-catalogs-must-prove-visibility-and-pricing-accuracy"></a>

Shared catalog validation should prove that the right company or buyer context receives the right product visibility and pricing behavior.

The business should test real scenarios, not only administrative records. A strong sample includes companies with different catalog access, different price expectations, different product visibility rules, and different buyer roles.

#### Scope must prove placement accuracy <a href="#scope-must-prove-placement-accuracy" id="scope-must-prove-placement-accuracy"></a>

Values should appear at the right website, store, or store-view level.

This is especially important for multi-brand, multilingual, multi-region, B2B, hybrid B2B/B2C, or campaign-sensitive stores where the same underlying record may need different storefront meaning depending on scope.

#### Product structure must prove commercial usability <a href="#product-structure-must-prove-commercial-usability" id="product-structure-must-prove-commercial-usability"></a>

Products should be reviewed for type, variant behavior, options, attributes, attribute sets, inventory assumptions, visibility, category assignment, and shared catalog access.

A product is not successful only because it appears in Adobe Commerce. It must behave as the intended sellable object for the correct buyer context.

#### Content and campaigns must prove timing logic <a href="#content-and-campaigns-must-prove-timing-logic" id="content-and-campaigns-must-prove-timing-logic"></a>

If staged content matters, validation should include representative scheduled updates, campaign-sensitive pages, products, categories, rules, or CMS content.

The target result should prove that important future behavior is either preserved, intentionally rebuilt, or intentionally excluded from migration scope.

#### Routes must prove destination relevance <a href="#routes-must-prove-destination-relevance" id="routes-must-prove-destination-relevance"></a>

Adobe Commerce URL rewrites and redirects should be validated by customer and search intent.

A passing route is not only technically live. It should lead to the closest useful product, category, CMS page, or equivalent target destination.

### Where Adobe Commerce Data-Model Review Should Start <a href="#where-adobe-commerce-data-model-review-should-start" id="where-adobe-commerce-data-model-review-should-start"></a>

#### Company and shared catalog logic <a href="#company-and-shared-catalog-logic" id="company-and-shared-catalog-logic"></a>

Start with the areas that define Adobe Commerce enterprise value: companies, buyers, shared catalogs, pricing visibility, and catalog access.

If these rules are unclear, the migration can look complete while remaining commercially unreliable.

#### Product and attribute structure <a href="#product-and-attribute-structure" id="product-and-attribute-structure"></a>

Review product types, attributes, attribute sets, configurable behavior, category placement, and product visibility early.

This confirms that the catalog foundation can support both normal storefront behavior and any B2B or enterprise rules layered on top of it.

#### Scope hierarchy <a href="#scope-hierarchy" id="scope-hierarchy"></a>

Review whether websites, stores, and store views are intentionally designed.

Scope should reflect real business differences such as brand, language, market, operational ownership, catalog structure, or configuration requirements. It should not simply recreate old complexity without purpose.

#### Campaign-sensitive content and rules <a href="#campaign-sensitive-content-and-rules" id="campaign-sensitive-content-and-rules"></a>

Identify whether products, categories, price rules, cart rules, CMS pages, CMS blocks, or merchandising changes depend on scheduled behavior.

Those examples should be included in migration planning and validation if they matter to launch readiness or near-term campaigns.

#### Extension and integration dependencies <a href="#extension-and-integration-dependencies" id="extension-and-integration-dependencies"></a>

List the custom modules, extensions, integrations, identifiers, custom fields, and external-system references that affect storefront behavior or operations.

If standard migration does not preserve the meaning behind those dependencies, the scenario should be reviewed for Custom Service or relevant Add-on handling.

### How Custom Platform Sources Change Adobe Commerce Data-Model Review <a href="#how-custom-platform-sources-change-adobe-commerce-data-model-review" id="how-custom-platform-sources-change-adobe-commerce-data-model-review"></a>

When the Source Platform is a Custom Platform, Adobe Commerce data-model review usually needs a more bespoke translation lens.

A Custom Platform may store company logic, account access, pricing rules, catalog visibility, staged behavior, scope-like distinctions, custom attributes, URL structures, or integration identifiers in ways that do not align cleanly with Adobe Commerce structures. In those cases, the migration question is not only what data exists. It is how that source meaning should be interpreted so Adobe Commerce remains commercially coherent.

Custom Platform sources often increase review sensitivity around:

* company and buyer interpretation
* shared catalog assignment
* account-specific pricing or visibility rules
* product-type and attribute-set translation
* website, store, and store-view placement
* staged content assumptions
* URL rewrite and redirect planning
* extension replacement or custom migration logic adjustment
* validation samples that prove real buyer behavior

This is where Custom Service is often needed, because the work may require custom interpretation, transformation, bespoke configuration, or source-specific logic handling rather than ordinary migration execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce data-model differences matter because the platform often makes enterprise commerce rules more explicit.

That can be a major advantage for businesses that need company-based buying, shared catalog visibility, differentiated pricing, governed scope, staged content, extension-aware operations, and stronger validation discipline. It becomes risky when those business rules are unclear before migration or when the team judges success only by record presence.

Before treating Adobe Commerce data as ready, review whether companies, buyers, shared catalogs, product structures, scope placement, staged content, routes, extensions, integrations, and custom fields still carry the intended commercial meaning.

Review a Demo Migration with the hardest Adobe Commerce scenarios: company structures, shared catalog visibility, product and pricing rules, scope-specific content, high-value URLs, staged content assumptions, and custom or extension-driven data. If those areas do not translate cleanly, use Live Chat to confirm whether the migration path needs Custom Service, Add-ons, or deeper planning before full execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What is one of the biggest Adobe Commerce data-model differences?**

One of the biggest differences is that customer meaning may shift from individual customer accounts to company-based buying relationships, shared catalog access, buyer roles, and differentiated pricing behavior.

**Are shared catalogs only product lists?**

No. Shared catalogs can affect product visibility and pricing behavior for different company contexts. Migration review should confirm not only that catalog records exist, but that the right buyers see the right products and prices.

**Does Adobe Commerce still use Magento product structures?**

Yes. Adobe Commerce keeps the Magento product foundation, including product types, attributes, attribute sets, categories, scope, and URL rewrites. Enterprise features add additional structure, but they do not remove the need to validate the underlying catalog model.

**Why does scope matter in Adobe Commerce migration?**

Website, store, and store-view scope can affect localization, configuration, category structure, content, URL behavior, and storefront context. A migrated value can be present but still wrong if it is placed at the wrong scope.

**When does Adobe Commerce data-model migration need Custom Service?**

Custom Service should be considered when the Source Platform uses custom company logic, bespoke pricing rules, extension-owned data, custom fields, outside-system identifiers, staged behavior, or custom migration logic adjustment that cannot be represented through ordinary migration handling.
