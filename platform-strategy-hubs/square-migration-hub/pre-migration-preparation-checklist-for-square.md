# Pre-migration Preparation Checklist for Square

A Square migration should be prepared around how the business will actually sell, fulfill, track inventory, support customers, and preserve important customer journeys after launch. The safest preparation work does not only ask whether product, customer, and order records can be moved. It asks whether those records will still support the operating model the business expects to run in Square.

Square can be a strong Target Platform when catalog structure, locations, inventory behavior, fulfillment rules, customer profiles, order history, websites, and priority routes are planned together. It becomes riskier when those areas are treated as separate export tasks. This checklist helps clarify the decisions that should be made before migration execution begins.

### What This Preparation Checklist Is For <a href="#what-this-preparation-checklist-is-for" id="what-this-preparation-checklist-is-for"></a>

This checklist is not a setup guide or a technical operating manual. It is a planning framework for deciding what must be clarified before the Square migration result can be judged confidently.

A strong Square preparation process should answer five practical questions:

* how products, services, variations, options, and modifiers should work in the Target Platform
* how inventory and location behavior should support real fulfillment workflows
* what customer and historical-order information must remain useful after launch
* which Square Online websites, browse paths, and legacy URLs deserve deliberate governance
* which records should be included in a representative Demo Migration sample because they are most likely to reveal operational mismatch

The purpose is to make Square’s operating model explicit before migration decisions become harder to change.

### Preparation Priority 1: Confirm the Square Target Operating Model <a href="#preparation-priority-1-confirm-the-square-target-operating-model" id="preparation-priority-1-confirm-the-square-target-operating-model"></a>

Before reviewing individual records, confirm what role Square should play after migration.

#### What to prepare <a href="#what-to-prepare" id="what-to-prepare"></a>

Identify:

* whether Square will support online selling only or a broader unified commerce model
* how many locations are in scope
* which fulfillment methods matter at launch
* whether one Square Online website or multiple websites are needed
* which teams need customer, order, inventory, or catalog visibility
* what must work on day one for the migration result to be considered acceptable

#### Why this matters <a href="#why-this-matters" id="why-this-matters"></a>

Square is strongest when catalog, inventory, locations, fulfillment, customers, and orders are treated as connected operational layers. If the Target Platform is planned only as a storefront, the migration can appear complete while still failing to support daily business activity.

### Preparation Priority 2: Normalize Products Around Items and Variations <a href="#preparation-priority-2-normalize-products-around-items-and-variations" id="preparation-priority-2-normalize-products-around-items-and-variations"></a>

Square catalog preparation should begin with the sellable structure of products and services.

#### What to prepare <a href="#what-to-prepare-1" id="what-to-prepare-1"></a>

Create a focused list of products that are commercially important or structurally complex, including:

* best-selling items
* products with many choices
* products with price differences by choice
* products with stock differences by choice
* products with location-specific availability
* products or services with custom configuration behavior
* products whose source-side structure may not fit Square cleanly

For each group, identify what should become the main item and what should become a distinct variation.

#### Why this matters <a href="#why-this-matters-1" id="why-this-matters-1"></a>

Square’s item and variation model should preserve how a product is actually sold. If variation structure is unclear, the migrated catalog may technically contain the right records but still make pricing, inventory, fulfillment, or staff handling harder to trust.

### Preparation Priority 3: Separate Variations, Options, and Modifiers <a href="#preparation-priority-3-separate-variations-options-and-modifiers" id="preparation-priority-3-separate-variations-options-and-modifiers"></a>

One of the most important Square preparation decisions is whether a customer-facing choice belongs in the core sellable variation structure or should remain a modifier or add-on-style choice.

#### What to prepare <a href="#what-to-prepare-2" id="what-to-prepare-2"></a>

Classify source-side product choices into practical groups:

* choices that define a distinct sellable unit
* choices that affect price or inventory
* choices that affect fulfillment or availability
* choices that are add-ons, extras, or sale-time customization
* personalization details that should not create separate stock-managed variations
* choices that exist only because the Source Platform used a looser option model

#### Why this matters <a href="#why-this-matters-2" id="why-this-matters-2"></a>

A choice may be visible to the customer but still play a different operational role in Square. Treating too many choices as variations can create an oversized catalog. Treating true sellable differences as modifiers can weaken inventory, reporting, or fulfillment accuracy.

### Preparation Priority 4: Define Inventory Behavior by Location <a href="#preparation-priority-4-define-inventory-behavior-by-location" id="preparation-priority-4-define-inventory-behavior-by-location"></a>

Inventory preparation for Square should focus on where inventory is counted, how it changes, and which teams depend on accurate availability.

#### What to prepare <a href="#what-to-prepare-3" id="what-to-prepare-3"></a>

Document:

* which items require inventory tracking
* which variations require distinct stock control
* whether inventory is central or location-specific
* which locations fulfill which products or services
* which products should not be available from every location
* which SKU or identifier rules must remain clear after migration
* which source-side inventory issues should be cleaned before migration

#### Why this matters <a href="#why-this-matters-3" id="why-this-matters-3"></a>

Square’s operational value depends heavily on whether inventory, variations, and locations support the same real-world selling model. If location rules are vague, validation may miss problems that only appear after staff begin selling, fulfilling, or reconciling stock.

### Preparation Priority 5: Clarify Fulfillment Expectations <a href="#preparation-priority-5-clarify-fulfillment-expectations" id="preparation-priority-5-clarify-fulfillment-expectations"></a>

Fulfillment should be defined before catalog quality is judged as complete.

#### What to prepare <a href="#what-to-prepare-4" id="what-to-prepare-4"></a>

Identify:

* which items support shipping
* which items support pickup
* which items support local delivery
* which locations support each fulfillment method
* which fulfillment differences are visible to customers
* which fulfillment rules are operationally important but not obvious from product data alone

#### Why this matters <a href="#why-this-matters-4" id="why-this-matters-4"></a>

A Square catalog can look correct while still failing to support the intended buying and fulfillment journey. Preparation should therefore connect item structure with how orders will actually be completed.

### Preparation Priority 6: Define Useful Customer Profiles <a href="#preparation-priority-6-define-useful-customer-profiles" id="preparation-priority-6-define-useful-customer-profiles"></a>

Customer preparation should focus on what customer records need to help staff and customers do after launch.

#### What to prepare <a href="#what-to-prepare-5" id="what-to-prepare-5"></a>

Clarify:

* which customer fields are still useful
* which tags, notes, groups, or segmentation signals matter commercially
* what support teams need to see quickly
* what returning-customer behavior should be expected
* which source-side customer fields are no longer useful
* which customer-related data depends on apps, extensions, custom fields, or outside systems

#### Why this matters <a href="#why-this-matters-5" id="why-this-matters-5"></a>

A migrated customer record is not automatically a useful customer profile. Square preparation should define the customer information that supports service, retention, reordering, and support decisions.

### Preparation Priority 7: Define What Historical Orders Should Support <a href="#preparation-priority-7-define-what-historical-orders-should-support" id="preparation-priority-7-define-what-historical-orders-should-support"></a>

Historical orders should be prepared around interpretation, not only record movement.

#### What to prepare <a href="#what-to-prepare-6" id="what-to-prepare-6"></a>

Decide:

* why historical orders are being migrated
* what staff should use them for after launch
* which order details must remain understandable
* which refund, cancellation, payment, or fulfillment cases need special review
* which operational actions should not be assumed safe on imported history
* which order samples should be reviewed during Demo Migration

#### Why this matters <a href="#why-this-matters-6" id="why-this-matters-6"></a>

Square order history is closely connected to payments, fulfillment, customer context, and inventory behavior. Imported historical orders should usually be treated as reference-sensitive records until validation confirms what they can safely support.

### Preparation Priority 8: Plan Website and Browse Governance <a href="#preparation-priority-8-plan-website-and-browse-governance" id="preparation-priority-8-plan-website-and-browse-governance"></a>

If Square Online website structure matters, prepare it before URL or navigation decisions are made.

#### What to prepare <a href="#what-to-prepare-7" id="what-to-prepare-7"></a>

Identify:

* whether one website or multiple Square Online websites are needed
* which items should appear on which website
* which categories, navigation paths, or landing pages matter most
* which website differences are commercially necessary
* which structures would create avoidable management burden
* which browse journeys should be tested during Demo Migration

#### Why this matters <a href="#why-this-matters-7" id="why-this-matters-7"></a>

Multiple websites or unclear browse paths can create governance risk. Preparation should make clear which online structures support real commercial needs and which should be simplified before migration.

### Preparation Priority 9: Prioritize Legacy URLs by Business Value <a href="#preparation-priority-9-prioritize-legacy-urls-by-business-value" id="preparation-priority-9-prioritize-legacy-urls-by-business-value"></a>

URL preparation should focus on the paths that still carry traffic, conversion, customer trust, or support value.

#### What to prepare <a href="#what-to-prepare-8" id="what-to-prepare-8"></a>

Prioritize:

* high-traffic product URLs
* category or browse paths that support discovery
* landing pages tied to campaigns or external links
* pages customers still use for trust, policies, service, or support
* URLs connected to email, ads, affiliates, social posts, or backlinks
* destinations that should preserve the intent of the original page

#### Why this matters <a href="#why-this-matters-8" id="why-this-matters-8"></a>

A redirect can be technically present but commercially weak if it sends visitors to a destination that no longer matches the original purpose. Square preparation should identify the routes that deserve deliberate mapping and later validation.

### Preparation Priority 10: Select a Representative Demo Migration Sample <a href="#preparation-priority-10-select-a-representative-demo-migration-sample" id="preparation-priority-10-select-a-representative-demo-migration-sample"></a>

A useful Demo Migration sample should include records that expose Square-specific risk, not only records that are easy to migrate.

#### What to prepare <a href="#what-to-prepare-9" id="what-to-prepare-9"></a>

Include samples such as:

* products with meaningful variation structure
* products where the variation-versus-modifier decision is not obvious
* products with inventory differences by location
* products with fulfillment restrictions
* customer records with useful profile detail
* historical orders with support or operational value
* important browse paths, websites, and legacy URLs
* data connected to apps, extensions, custom fields, or outside systems

#### Why this matters <a href="#why-this-matters-9" id="why-this-matters-9"></a>

A simple sample can create false confidence. Square preparation is stronger when Demo Migration tests whether operational meaning survives in the Target Platform.

### Preparation Priority 11: Identify Findings That May Affect the Service Path <a href="#preparation-priority-11-identify-findings-that-may-affect-the-service-path" id="preparation-priority-11-identify-findings-that-may-affect-the-service-path"></a>

Preparation should also make visible whether the Square migration appears suitable for standard handling or whether customization may be required.

#### What to prepare <a href="#what-to-prepare-10" id="what-to-prepare-10"></a>

Flag findings involving:

* Custom Platform source structures
* custom product configuration rules
* app/plugin/module/extension data that affects selling or operations
* custom fields or outside-system identifiers
* unusual inventory, location, or fulfillment logic
* source behavior that does not map cleanly into Square’s item, variation, modifier, customer, order, or website model
* transformation, custom migration logic adjustment, or bespoke target representation

#### Why this matters <a href="#why-this-matters-10" id="why-this-matters-10"></a>

The goal is not to force a service decision too early. The goal is to collect enough evidence to decide whether the migration can remain within standard service capability, whether Managed Service would reduce execution burden, or whether Custom Service is needed for customization or modification work.

### A Practical Square Preparation Sequence <a href="#a-practical-square-preparation-sequence" id="a-practical-square-preparation-sequence"></a>

A practical preparation sequence usually works best when it moves from operating model to proof sample.

#### 1. Define the target operating model <a href="#id-1-define-the-target-operating-model" id="id-1-define-the-target-operating-model"></a>

Confirm whether Square will be used as a storefront-only destination or as a broader commerce, inventory, location, customer, and order environment.

#### 2. Review the catalog structure <a href="#id-2-review-the-catalog-structure" id="id-2-review-the-catalog-structure"></a>

Identify important products, services, variations, modifiers, options, categories, and catalog relationships that must remain commercially understandable.

#### 3. Clarify operational behavior <a href="#id-3-clarify-operational-behavior" id="id-3-clarify-operational-behavior"></a>

Review inventory, locations, fulfillment, and customer-facing availability rules before judging the catalog as ready.

#### 4. Review customer and order usefulness <a href="#id-4-review-customer-and-order-usefulness" id="id-4-review-customer-and-order-usefulness"></a>

Decide what migrated customer profiles and historical orders must support after launch.

#### 5. Prioritize websites, browse paths, and URLs <a href="#id-5-prioritize-websites-browse-paths-and-urls" id="id-5-prioritize-websites-browse-paths-and-urls"></a>

Identify the routes and online journeys that deserve focused protection.

#### 6. Build the Demo Migration sample around risk <a href="#id-6-build-the-demo-migration-sample-around-risk" id="id-6-build-the-demo-migration-sample-around-risk"></a>

Choose records that reveal whether Square can preserve the operating model, not only records that are easy to transfer.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Square preparation is strongest when it clarifies how the future business should operate before the migration is treated as execution work. The important question is not whether records can be moved into Square, but whether items, variations, modifiers, inventory, locations, customers, orders, websites, and priority routes will still support the way the business expects to sell and serve customers.

Before moving forward, review the Square preparation checklist against the records that matter most to revenue, fulfillment, support, and search continuity. If the sample exposes unclear variation logic, location-sensitive inventory behavior, custom data, outside-system identifiers, or source behavior that does not fit Square cleanly, use those findings to decide whether standard service capability is enough or whether Custom Service should be reviewed before full migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Should Square preparation start with products or with the operating model?**

It should start with the operating model. Product structure matters, but Square preparation is safer when the business first confirms how selling, inventory, fulfillment, locations, customers, orders, and websites should work together after migration.

**Why is the variation-versus-modifier decision important before migration?**

Because the same source-side choice can have different meaning in Square. Some choices define a distinct sellable unit, while others are sale-time modifiers or add-ons. The wrong classification can weaken pricing, stock control, fulfillment clarity, or reporting.

**Do all historical orders need the same level of preparation?**

No. Orders that are needed only for reference may require a different level of review than orders that staff rely on for support, customer history, fulfillment interpretation, refunds, cancellations, or reporting context.

**When should a Square migration be reviewed for Custom Service?**

A Square migration should be reviewed for Custom Service when the source includes Custom Platform structures, app/plugin/module/extension data, custom fields, outside-system identifiers, unusual inventory or fulfillment logic, custom product configuration, or any requirement that needs transformation, custom migration logic adjustment, or bespoke target representation.

**Is Demo Migration enough if the sample only includes simple products?**

No. A Demo Migration sample is most useful when it includes records that can reveal Square-specific risk, such as complex variations, modifier ambiguity, location-sensitive inventory, important customer profiles, historical orders, priority websites, and high-value URLs.
