# Adobe Commerce Platform Overview

Adobe Commerce is an enterprise commerce Target Platform for businesses whose migration planning depends on a governed catalog structure, B2B customer relationships, differentiated pricing, campaign-aware merchandising, and operational control across storefront contexts.

It shares a technical foundation with Magento Open Source, but migrating to Adobe Commerce should not be treated as a simple move to “Magento with more features.” The real planning question is whether the future store can preserve the commercial rules that make the business work: company-based access, shared catalog visibility, customer-group behavior, price visibility, staged content, scope-aware storefront structure, URL continuity, and extension or integration logic.

For many enterprise migrations, a record can appear present in the Target Platform while the operating meaning behind that record is incomplete. A product may exist, but the right company may not see it. A customer may exist, but buyer access may not follow the intended company structure. A catalog may exist, but pricing visibility may not reflect the right business relationship. A page may exist, but campaign timing or storefront scope may no longer behave as expected.

This hub helps merchants evaluate Adobe Commerce as a migration target, identify where planning needs to go deeper, and prepare for the validation required to demonstrate that enterprise commerce behavior remains usable after migration.

### What Changes in a Migration to Adobe Commerce <a href="#what-changes-in-a-migration-to-adobe-commerce" id="what-changes-in-a-migration-to-adobe-commerce"></a>

A migration into Adobe Commerce usually changes how the business thinks about customer structure, catalog visibility, pricing, campaign timing, and storefront governance. The migration is not only about moving Products, Customers, Orders, and supporting content. It is about translating existing commerce behavior into an environment where access, scope, and business rules are more explicitly governed.

#### Company structure becomes part of customer meaning <a href="#company-structure-becomes-part-of-customer-meaning" id="company-structure-becomes-part-of-customer-meaning"></a>

In simpler stores, the customer account is often the main buyer unit. In Adobe Commerce projects, the more important unit may be the company, the people attached to it, and the buying rules that follow that relationship.

This matters because B2B migration success is not proven by customer record presence alone. The Target Platform must also support the intended relationship between companies, buyers, access permissions, catalog visibility, and pricing expectations. If company logic is unclear before migration, Adobe Commerce can expose that ambiguity quickly.

#### Shared catalogs can control product access and pricing visibility <a href="#shared-catalogs-can-control-product-access-and-pricing-visibility" id="shared-catalogs-can-control-product-access-and-pricing-visibility"></a>

Adobe Commerce can represent product access and custom pricing through shared catalogs. That makes the platform valuable for B2B or enterprise models where different companies, accounts, or customer groups need different catalog experiences.

Migration planning must therefore define which products should be visible, which pricing rules should apply, which customers or companies should receive each commercial view, and whether those rules can be represented cleanly in the Target Platform. A migration that preserves products but loses shared-catalog logic can undermine sales workflows even when catalog records appear complete.

#### Scope hierarchy becomes a governance layer <a href="#scope-hierarchy-becomes-a-governance-layer" id="scope-hierarchy-becomes-a-governance-layer"></a>

Adobe Commerce uses the website, store, and store view hierarchy inherited from the Magento architecture. This hierarchy affects storefront structure, root categories, localization, configuration, and where certain data or behavior applies.

For enterprise stores, scope is not only a technical setting. It can shape how different markets, languages, brands, customer groups, catalogs, and operational teams are organized. Before migration, the business should decide what belongs at the website level, what belongs at the store level, what belongs at the store view level, and what should not be split at all.

#### Content and merchandising timing can become part of the operating model <a href="#content-and-merchandising-timing-can-become-part-of-the-operating-model" id="content-and-merchandising-timing-can-become-part-of-the-operating-model"></a>

Adobe Commerce includes Content Staging, which can support planned updates for products, categories, catalog price rules, cart price rules, CMS pages, and CMS blocks. This makes campaign timing, scheduled merchandising, and future content changes part of migration planning where those behaviors matter.

A static review of the new storefront is not enough when the business depends on scheduled campaigns or timed merchandising. The migration plan should clarify whether important scheduled behavior needs to be recreated, simplified, rebuilt, or validated separately after launch.

#### Extensions and custom logic carry heavier business meaning <a href="#extensions-and-custom-logic-carry-heavier-business-meaning" id="extensions-and-custom-logic-carry-heavier-business-meaning"></a>

Adobe Commerce projects often involve extensions, custom fields, custom workflows, integrations, and business-specific logic. Some of this information may not be standard platform data. Some may come from the Source Platform, custom modules, ERP or CRM systems, marketplace tools, pricing systems, fulfillment logic, or other external sources.

When that logic affects product availability, pricing, buyer access, catalog rules, merchandising, order processing, or reporting, it should be reviewed as part of Custom Service planning rather than treated as ordinary record movement.

### Where Adobe Commerce Is Often a Strong Target <a href="#where-adobe-commerce-is-often-a-strong-target" id="where-adobe-commerce-is-often-a-strong-target"></a>

Adobe Commerce is often strongest when the business needs enterprise-native control rather than a lighter storefront structure.

#### B2B businesses with company-based buying relationships <a href="#b2b-businesses-with-company-based-buying-relationships" id="b2b-businesses-with-company-based-buying-relationships"></a>

Adobe Commerce is a strong candidate when the future store must support company accounts, buyer roles, account-level purchasing context, and differentiated catalog or pricing behavior. The platform is especially relevant when customer relationships are not adequately represented by simple customer groups or generic tags alone.

#### Catalogs that require controlled visibility or differentiated pricing <a href="#catalogs-that-require-controlled-visibility-or-differentiated-pricing" id="catalogs-that-require-controlled-visibility-or-differentiated-pricing"></a>

Adobe Commerce fits businesses that need more explicit rules for who can see which products, which prices apply, and how catalog access should differ by company, customer group, market, or commercial arrangement.

This is important for wholesale, distributor, manufacturer, enterprise account, or negotiated-pricing models where the storefront experience should change based on buyer identity.

#### Stores with governed merchandising and campaign operations <a href="#stores-with-governed-merchandising-and-campaign-operations" id="stores-with-governed-merchandising-and-campaign-operations"></a>

Adobe Commerce can be a good Target Platform when campaigns, merchandising updates, content changes, and promotion timing need stronger control. If the business depends on seasonal launches, scheduled price changes, planned content changes, or campaign coordination across teams, migration planning should treat those workflows as part of the target model.

#### Multi-context stores that need clearer governance <a href="#multi-context-stores-that-need-clearer-governance" id="multi-context-stores-that-need-clearer-governance"></a>

Adobe Commerce can also fit businesses that need stronger governance across websites, stores, store views, language contexts, brand contexts, or operational teams. This is useful when the future store must support multiple contexts without losing control over catalog structure, configuration, access logic, or validation responsibility.

### Where Deeper Planning Is Usually Needed <a href="#where-deeper-planning-is-usually-needed" id="where-deeper-planning-is-usually-needed"></a>

Adobe Commerce can carry more capability than lighter platforms, but that capability also increases planning responsibility. A business should not choose Adobe Commerce only because the store is large or complex. It should choose Adobe Commerce when the target operating model is clear enough to use that structure effectively.

#### Company and catalog logic is not yet clearly defined <a href="#company-and-catalog-logic-is-not-yet-clearly-defined" id="company-and-catalog-logic-is-not-yet-clearly-defined"></a>

If the business cannot clearly explain which companies exist, which buyers belong to them, which products they should see, and which pricing rules should apply, the migration can produce a technically populated store that remains commercially confusing.

Adobe Commerce rewards clear governance. It does not automatically resolve unclear B2B rules.

#### The old store depends heavily on custom behavior <a href="#the-old-store-depends-heavily-on-custom-behavior" id="the-old-store-depends-heavily-on-custom-behavior"></a>

Custom fields, extensions, app logic, custom modules, external pricing rules, customer-specific workflows, and proprietary order handling can all create migration risk. These details often require Custom Service because the Target Platform must preserve business meaning, not simply move visible records.

#### Storefront scope is being redesigned during migration <a href="#storefront-scope-is-being-redesigned-during-migration" id="storefront-scope-is-being-redesigned-during-migration"></a>

If the business is changing websites, stores, store views, language structures, domains, market segmentation, or root-category logic during migration, the project needs stronger planning. Scope changes can affect product visibility, URL continuity, content assignment, customer access, and validation responsibilities.

#### Campaign timing or scheduled behavior matters commercially <a href="#campaign-timing-or-scheduled-behavior-matters-commercially" id="campaign-timing-or-scheduled-behavior-matters-commercially"></a>

If scheduled content, promotions, catalog updates, or merchandising changes are important, they should be reviewed before migration. The business should decide whether those behaviors need to be recreated in Adobe Commerce, rebuilt manually after migration, simplified, or validated as separate launch-critical scenarios.

### What Should Be Understood Early Before Moving into Adobe Commerce <a href="#what-should-be-understood-early-before-moving-into-adobe-commerce" id="what-should-be-understood-early-before-moving-into-adobe-commerce"></a>

Adobe Commerce migration planning should begin with business-rule clarity. The more the store depends on governed B2B behavior, staged merchandising, scope hierarchy, and custom logic, the more important early planning becomes.

#### Company, buyer, and access structure <a href="#company-buyer-and-access-structure" id="company-buyer-and-access-structure"></a>

The business should define whether company accounts are needed, which customers belong to each company, what buyer relationships matter, and what permissions or purchasing expectations must remain usable after migration.

#### Shared catalog and pricing rules <a href="#shared-catalog-and-pricing-rules" id="shared-catalog-and-pricing-rules"></a>

The business should identify which catalog views, product access rules, and pricing differences must exist after the move. This includes deciding which rules belong in standard Adobe Commerce structures and which require additional configuration, Add-ons, or Custom Service planning.

#### Website, store, and store view scope <a href="#website-store-and-store-view-scope" id="website-store-and-store-view-scope"></a>

The business should decide what the future Adobe Commerce scope hierarchy should look like. This includes brands, regions, languages, storefront contexts, root categories, configuration differences, URL paths, and operational ownership.

#### Content, campaign, and promotion timing <a href="#content-campaign-and-promotion-timing" id="content-campaign-and-promotion-timing"></a>

If staged content or scheduled commercial behavior matters, the business should list the most important campaigns, rules, product changes, category changes, CMS pages, or promotional timing patterns before migration begins.

#### Extension, integration, and custom-data dependencies <a href="#extension-integration-and-custom-data-dependencies" id="extension-integration-and-custom-data-dependencies"></a>

The business should identify which extensions, custom fields, integration records, reporting fields, and external-system identifiers are required for operations. These dependencies should be reviewed before deciding whether Standard Service, Managed Service, Add-ons, or Custom Service is the safest approach.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce is a strong migration target when the future store needs enterprise-grade commercial structure: company-based buying relationships, controlled catalog visibility, differentiated pricing, staged content operations, scope-aware storefront governance, and deeper validation discipline.

Its value is not only that it can support more advanced features. Its value is that it can make complex commercial rules more explicit when the business has planned those rules clearly. Risk increases when merchants treat Adobe Commerce as a generic upgrade path without defining company logic, shared-catalog behavior, scope hierarchy, custom dependencies, and launch-critical validation scenarios.

A practical next step is to run a Demo Migration using samples that reflect the hardest Adobe Commerce questions: company structures, shared catalog rules, customer-group behavior, high-value product types, scope-specific storefront behavior, URL continuity, and custom or extension-driven data. If the result leaves uncertainty about how the Target Platform should represent those rules, Live Chat can help clarify whether the selected migration path, Add-ons, or Custom Service planning should be adjusted before the full migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What makes Adobe Commerce different from Magento in migration planning?**

Adobe Commerce shares the Magento foundation, but it usually adds heavier planning around B2B company structure, shared catalogs, differentiated pricing, staged content operations, and enterprise governance. Migration planning should focus on whether those commercial rules can be represented and validated correctly.

**Is Adobe Commerce only useful for B2B migration projects?**

No. Adobe Commerce can also support complex B2C, multi-brand, multi-market, or promotion-heavy businesses. However, it is especially useful when company accounts, shared catalog visibility, pricing rules, and enterprise governance are central to the operating model.

**Does every Adobe Commerce migration require Custom Service?**

No. The right service approach depends on the Source Platform, available migration path, data structure, customization level, Add-on needs, and the business rules that must be preserved. However, Custom Platform sources, custom migration logic adjustment, extension-heavy behavior, and bespoke B2B or pricing requirements are strong signals for Custom Service review.

**What should be validated first after migrating to Adobe Commerce?**

Validation should prioritize the behaviors that carry the most commercial risk: company access, shared catalog visibility, pricing logic, product type behavior, scope-specific storefront behavior, customer-group interpretation, URL continuity, staged content assumptions, and any extension or integration data needed for operations.
