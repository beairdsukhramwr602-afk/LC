# Magento Pre-Migration Preparation Checklist

Magento is easiest to govern when the business prepares for the structure it wants to operate after migration, not only for the data it wants to transfer.

This matters because Magento can support detailed product modeling, attribute governance, attribute sets, website/store/store-view scope, customer groups, URL rewrites, extensions, and custom workflows. Those strengths are useful only when the business defines how they should work before execution pressure increases.

This checklist helps merchants prepare for a Magento migration by clarifying the structural decisions, source-data questions, and validation samples that should be resolved before the migration result is judged ready.

### What This Checklist Is For <a href="#what-this-checklist-is-for" id="what-this-checklist-is-for"></a>

A Magento preparation checklist should reduce ambiguity before migration execution begins.

The goal is to clarify:

* which product families require Magento-specific product-type decisions
* which attributes and attribute sets carry real commercial or operational meaning
* where website, store, and store-view scope must remain different
* which customer groups affect pricing, tax, access, segmentation, or B2B context
* which extensions, custom fields, or external-system identifiers still influence storefront or operational behavior
* which URLs, customer-account scenarios, and priority workflows need early validation

This is not a generic export checklist. It is a planning tool for deciding what Magento must preserve, what Magento should formalize, and where the migration path may need closer review.

### Magento Preparation Priorities <a href="#magento-preparation-priorities" id="magento-preparation-priorities"></a>

#### 1. Define the product types that matter most <a href="#id-1-define-the-product-types-that-matter-most" id="id-1-define-the-product-types-that-matter-most"></a>

Magento product structure should be prepared around sellable behavior, not only product names.

Before migration, identify:

* high-revenue product families
* products that depend on configurable, grouped, bundle, virtual, or downloadable behavior
* products whose options affect SKU, price, stock, fulfillment, or customer choice
* product structures that were handled loosely in the Source Platform
* product families that would become weaker if represented with the wrong Magento product type

The preparation goal is to make Magento product behavior clear enough that the migration result can be judged by commercial accuracy, not only by product count.

#### 2. Clarify attributes by purpose <a href="#id-2-clarify-attributes-by-purpose" id="id-2-clarify-attributes-by-purpose"></a>

Magento attributes can affect storefront display, layered navigation, search, comparison, merchandising, catalog administration, and product-family governance.

Before migration, separate attributes into practical groups:

* attributes customers use to compare or filter products
* attributes required for product administration
* attributes that belong only to specific product families
* attributes that are duplicated, outdated, unclear, or inherited from source-side workarounds
* custom fields that should become Magento attributes versus extension-owned behavior

A cleaner attribute plan helps prevent migrated data from becoming technically present but difficult to manage.

#### 3. Define attribute sets around real product families <a href="#id-3-define-attribute-sets-around-real-product-families" id="id-3-define-attribute-sets-around-real-product-families"></a>

Attribute sets should reflect how Magento products will be governed after launch.

Before migration, decide:

* which product families genuinely need different attribute structures
* which attributes are common across most products
* which attributes should appear only for specific product groups
* whether inherited source categories are being mistaken for product-family logic
* whether the future team can maintain the proposed attribute-set structure

A product may migrate successfully while the catalog becomes harder to manage if attribute-set planning is weak.

#### 4. Decide website, store, and store-view scope early <a href="#id-4-decide-website-store-and-store-view-scope-early" id="id-4-decide-website-store-and-store-view-scope-early"></a>

Magento scope decisions can affect content, language, configuration, catalog visibility, price context, localized storefront behavior, and administration.

Before migration, define:

* what should differ by website
* what should differ by store
* what should differ by store view
* what should remain global
* which localized product, category, CMS, or metadata values must remain distinct
* whether the future hierarchy reflects a real business need or unnecessary complexity

Scope decisions should not be left until late validation. They shape how data should be interpreted from the beginning.

#### 5. Review customer groups as commercial logic <a href="#id-5-review-customer-groups-as-commercial-logic" id="id-5-review-customer-groups-as-commercial-logic"></a>

Magento customer groups can carry business meaning beyond simple customer classification.

Before migration, identify:

* which customer groups are still commercially meaningful
* which groups affect pricing, tax behavior, discounts, visibility, or account context
* which source-side groups should be simplified or retired
* which customer-group scenarios should be included in Demo Migration review
* whether any B2B, wholesale, membership, regional, or tax-sensitive logic depends on correct group assignment

Customer records may exist after migration while customer behavior is still wrong if group meaning is not prepared clearly.

#### 6. Document extension-owned and custom behavior <a href="#id-6-document-extension-owned-and-custom-behavior" id="id-6-document-extension-owned-and-custom-behavior"></a>

Magento stores often rely on extensions, custom modules, theme logic, integrations, or custom fields to support business behavior that is not visible as ordinary catalog data.

Before migration, identify:

* extensions that affect product meaning, pricing, filtering, checkout, search, content, or customer context
* custom fields that influence storefront display or operational workflows
* outside-system identifiers used by ERP, CRM, fulfillment, marketplace, or reporting systems
* theme-dependent layouts or product-detail structures that affect how migrated data appears
* extension-owned behavior that may need Custom Service review or custom migration logic adjustment

The business does not need to preserve every installed extension. It needs to know which extension-owned meanings still matter.

#### 7. Prioritize legacy URLs by business value <a href="#id-7-prioritize-legacy-urls-by-business-value" id="id-7-prioritize-legacy-urls-by-business-value"></a>

Magento can support URL rewrite planning, but route continuity still depends on business judgment.

Before migration, identify:

* product URLs that carry traffic, revenue, backlinks, or customer trust
* category paths that support discovery or organic visibility
* CMS or landing pages that still matter to conversion or brand confidence
* legacy paths that should not be redirected to generic destinations
* source-side URL patterns that may not map cleanly into Magento’s future structure

The strongest preparation focuses on preserving intent. A technically working URL is not enough if the destination no longer satisfies the original customer purpose.

#### 8. Define customer-account continuity expectations <a href="#id-8-define-customer-account-continuity-expectations" id="id-8-define-customer-account-continuity-expectations"></a>

Customer-account continuity should be prepared honestly before launch planning begins.

Before migration, clarify:

* whether password continuity is realistic for the selected migration path
* what returning customers should experience at first login
* whether account reset or communication planning is needed
* which customer groups or account types are most sensitive
* which support scenarios may become urgent if expectations are unclear

This helps prevent customer-account continuity from being treated as an assumption.

#### 9. Build the Demo Migration sample around structural risk <a href="#id-9-build-the-demo-migration-sample-around-structural-risk" id="id-9-build-the-demo-migration-sample-around-structural-risk"></a>

A Magento Demo Migration is more useful when the sample is chosen to expose the areas most likely to fail.

Include samples such as:

* complex configurable, grouped, bundle, virtual, or downloadable products
* products with high-value attributes and attribute sets
* multi-store or store-view-specific content
* customer groups with pricing, tax, access, or segmentation implications
* extension-sensitive products, checkout paths, or workflows
* high-value legacy URLs
* customer-account scenarios that need realistic review

A convenient sample may confirm that data can move. A risk-based sample helps prove whether the Magento target is structurally credible.

#### 10. Decide what Magento should formalize and what must remain unchanged <a href="#id-10-decide-what-magento-should-formalize-and-what-must-remain-unchanged" id="id-10-decide-what-magento-should-formalize-and-what-must-remain-unchanged"></a>

Magento often gives businesses an opportunity to make structure clearer. That does not mean every source-side detail should be preserved exactly.

Before migration, decide:

* which product structures should be formalized into Magento product types
* which attributes should be cleaned, consolidated, or reorganized
* which attribute sets should be created for long-term governance
* which store-view differences are essential and which are unnecessary
* which customer-group logic must remain intact
* which extension-owned behavior requires specialized handling
* which URL and customer-continuity outcomes are non-negotiable

This decision reduces the risk of trying to preserve source-side complexity that Magento should instead make more governable.

### Practical Magento Preparation Sequence <a href="#practical-magento-preparation-sequence" id="practical-magento-preparation-sequence"></a>

#### Start with high-risk product families <a href="#start-with-high-risk-product-families" id="start-with-high-risk-product-families"></a>

Begin with the products most likely to expose wrong product-type decisions. This usually includes configurable, bundle, grouped, downloadable, virtual, option-heavy, or custom-built product experiences.

#### Clarify attributes and attribute sets <a href="#clarify-attributes-and-attribute-sets" id="clarify-attributes-and-attribute-sets"></a>

Then classify the fields that affect customer choice, catalog management, filtering, comparison, administration, and product-family structure.

#### Define scope hierarchy <a href="#define-scope-hierarchy" id="define-scope-hierarchy"></a>

Next, decide what must differ by website, store, and store view before localized values or multi-store behavior become difficult to judge.

#### Review customer-group behavior <a href="#review-customer-group-behavior" id="review-customer-group-behavior"></a>

Prepare the customer groups that affect commercial outcomes, especially pricing, tax, access, membership, wholesale, B2B, or regional logic.

#### Separate native Magento structure from extension-owned meaning <a href="#separate-native-magento-structure-from-extension-owned-meaning" id="separate-native-magento-structure-from-extension-owned-meaning"></a>

Identify what belongs inside native Magento data structures and what depends on extensions, custom modules, custom fields, or external systems.

#### Choose representative validation samples <a href="#choose-representative-validation-samples" id="choose-representative-validation-samples"></a>

Build the Demo Migration sample from structural risk, not convenience. The sample should help the business decide whether the planned approach is strong enough.

### When Custom Platform Sources Need Extra Preparation <a href="#when-custom-platform-sources-need-extra-preparation" id="when-custom-platform-sources-need-extra-preparation"></a>

When the Source Platform is a Custom Platform, Magento preparation usually needs earlier interpretation.

That is because source-side product behavior, attribute logic, customer grouping, pricing context, scope-like variation, identifiers, or custom database structures may not align neatly with Magento’s native model.

#### What should be reviewed earlier <a href="#what-should-be-reviewed-earlier" id="what-should-be-reviewed-earlier"></a>

A Custom Platform source usually requires earlier review of:

* how source product logic should become Magento product types
* which source fields should become attributes, attribute-set logic, extension-owned behavior, or excluded legacy data
* whether customer groups, pricing, tax, or access logic can be represented natively
* whether source-side identifiers are needed for external systems
* whether custom migration logic adjustment is required to preserve meaningful behavior
* which samples must be included before full migration confidence is possible

#### How this affects service-path thinking <a href="#how-this-affects-service-path-thinking" id="how-this-affects-service-path-thinking"></a>

Custom Platform sources commonly point toward **Custom Service** when interpretation, transformation, custom fields, outside-system identifiers, app/plugin/module data, or custom migration logic adjustment is required.

This does not automatically mean Next-Cart performs the full migration execution. It means the standard migration path should not be assumed sufficient until the custom structures are reviewed and the required service responsibility is clear.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento migration preparation is strongest when it defines the target structure before execution pressure begins.

The business should prepare product types, commercial attributes, attribute sets, website/store/store-view scope, customer groups, extension-owned behavior, URL priorities, customer-account expectations, and representative Demo Migration samples. Those decisions make Magento easier to validate and reduce the risk of launching a technically migrated store that is difficult to govern.

Before moving deeper into execution, build the checklist around the Magento structures that matter most to revenue, operations, customer experience, and long-term administration. If those structures are still difficult to classify, Live Chat can help determine whether the issue is routine Magento preparation, a Managed Service planning concern, or a Custom Service requirement.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating into Magento?**

Start with the product families most likely to expose product-type ambiguity. Then review commercial attributes, attribute sets, website/store/store-view scope, customer groups, extension-owned behavior, high-value URLs, and customer-account expectations.

**Why are attribute sets important before migrating into Magento?**

Attribute sets help define how different product families are structured and managed. A Magento migration can preserve products and attributes while still weakening catalog governance if attribute-set logic is not prepared clearly.

**Should Magento preparation focus mainly on products?**

No. Products are central, but Magento preparation is also sensitive around attributes, attribute sets, scope hierarchy, customer groups, extensions, custom fields, URL rewrites, and customer-account continuity.

**When does Magento preparation usually require Custom Service?**

Custom Service is usually relevant when the migration depends on Custom Platform interpretation, custom fields, extension-owned behavior, outside-system identifiers, bespoke transformation, or custom migration logic adjustment that cannot be handled through the standard migration path alone.
