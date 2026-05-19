# Demo Migration Explained

Demo Migration is the early proof stage of a Next-Cart migration. It gives customers a limited but useful view of how representative source-store data may appear in the Target Platform before the project moves into broader execution.

Its purpose is not only to show that data can move. Its purpose is to help the customer see whether the migrated sample still makes sense in the target environment, whether important relationships remain usable, and whether the project needs standard configuration, Add-ons, or Custom Service.

A well-designed Demo Migration turns migration planning from assumption into evidence.

### What Demo Migration Is  <a href="#what-demo-migration-is" id="what-demo-migration-is"></a>

Demo Migration is a sample migration performed before the full project scope is executed.

It helps customers review how selected data from the Source Platform is translated into the Target Platform. The sample is intentionally limited, but it should still be meaningful enough to reveal whether the target result is likely to support the business expectations that matter most.

A useful Demo Migration helps answer questions such as:

* can important product data appear in a usable target structure?
* do customers and orders remain understandable?
* do relationships between records still make sense?
* do mapped values need adjustment?
* does the Source Platform structure fit the Target Platform clearly enough?
* does the project show signs of needing Add-ons or Custom Service?

The demo result should be reviewed as an early signal, not as a final guarantee.

### Why Demo Migration Matters  <a href="#why-demo-migration-matters" id="why-demo-migration-matters"></a>

Many migration risks are not visible from record counts alone.

A store may have a manageable number of products, customers, and orders but still contain complexity that affects the migration outcome. Product options may behave differently in the Target Platform. Category relationships may change meaning. Customer and order history may become harder to interpret. App-driven or custom data may not appear through standard structures.

Demo Migration helps reveal those issues before the customer relies on the full migration path.

It is especially useful because it shows the customer real migrated examples instead of only describing likely outcomes in theory.

### A Good Demo Sample Is Representative  <a href="#a-good-demo-sample-is-representative" id="a-good-demo-sample-is-representative"></a>

The value of Demo Migration depends heavily on the sample.

A weak sample can create false confidence. If the sample includes only simple products, clean customers, or easy orders, the result may look safe while the harder parts of the store remain untested.

A stronger sample usually includes:

* top-selling or commercially important products
* products with complex options or variants
* important category or collection paths
* representative customers
* representative orders with real operational meaning
* CMS Pages or Blog Posts that matter to the store
* records affected by apps, plugins, extensions, custom fields, or outside systems
* examples that reflect the highest-risk parts of the source store

A good sample does not need to be large. It needs to be revealing.

### What to Review in Demo Migration Results  <a href="#what-to-review-in-demo-migration-results" id="what-to-review-in-demo-migration-results"></a>

The most useful review mindset is not only:

> Did the records appear?

It is:

> Do the migrated examples still support the business meaning they need to carry?

That usually means reviewing several areas without trying to turn the demo into a full-store audit.

**Product behavior**

Products should be reviewed for whether they still support the expected buying experience.

Important checks include:

* product titles, descriptions, SKUs, prices, and images
* option and variant behavior
* product relationships with categories or collections
* attributes or fields used for search, filtering, or merchandising
* product data affected by apps, extensions, or custom structures

A product can appear present in the Target Platform and still fail if the customer cannot buy or understand it in the expected way.

**Category and browse logic**

Categories, collections, filters, and navigation-related structures should be reviewed for whether customers can still find products through the intended paths.

Important checks include:

* category hierarchy
* product assignments
* collection or grouping behavior
* filtering-related fields where relevant
* category-page meaning for important browse paths

A catalog can look complete while becoming weaker as a discovery system.

**Customer and order usability**

Customer and order data should be reviewed together because they often support customer service, account continuity, operational history, and reporting.

Important checks include:

* customer contact information
* customer addresses where relevant
* order line items
* customer-to-order relationships
* order-to-product relationships
* order statuses or mapped order values
* operational fields used by support or fulfillment teams

The goal is to confirm whether customer and order data remain usable, not only whether they exist.

**Relationship integrity**

Migration quality often depends on whether related records still refer to one another correctly.

Important checks include:

* products connected to the right categories
* orders connected to the right customers
* orders connected to the right purchased products
* reviews linked to the right products and customers where supported
* coupons connected to the intended products or categories where relevant
* supporting structures such as manufacturers, taxes, CMS Pages, or Blog Posts appearing in the expected context

Relationship issues can be hard to detect from totals alone.

**Content and SEO-sensitive records**

If CMS Pages, Blog Posts, URLs, or metadata matter to the business, the demo should include examples that show how those records appear in the Target Platform.

Important checks include:

* page content and formatting
* page structure in the target environment
* basic metadata behavior where supported
* URL behavior for important pages
* links between content and product or category paths where relevant

This review is especially important when content supports organic traffic, customer education, or conversion.

### What Demo Migration Can Reveal  <a href="#what-demo-migration-can-reveal" id="what-demo-migration-can-reveal"></a>

Demo Migration can reveal several kinds of findings.

**The Sample Maps Cleanly**

Some projects show that representative records move into the Target Platform with expected structure and behavior. That is a good sign, but it still needs broader validation later.

A clean demo usually means the project has fewer visible early risks, not that the full migration can skip careful review.

**The Result Needs Configuration Adjustment**

Some differences may be corrected through entity selection, migration settings, or mapping adjustments.

Examples may include mapped values that need clarification, order statuses that should align differently, or fields that need a more deliberate source-to-target relationship.

These findings are useful because they appear early enough to adjust before Full Migration.

**The Project Needs an Add-on**

Some demo findings show that the project needs more control over a focused migration need.

Examples include:

* only selected records should be migrated
* source data needs more controlled mapping into target-supported fields
* data values should be configured before reaching the Target Platform

These findings may point to the Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure.

**The Project Needs Custom Service**

Some findings go beyond standard service capability or standard Add-on capability.

Custom Service is required when the project needs tailored work, such as a Tailored Add-on, Custom Add-on, Custom Platform handling, custom migration logic adjustment, third-party app or extension data, custom fields, outside-system identifiers, or bespoke transformation rules.

The demo is useful because it can reveal these needs before full execution makes them harder to address.

### Demo Migration and Service Fit  <a href="#demo-migration-and-service-fit" id="demo-migration-and-service-fit"></a>

Demo Migration often gives the clearest early signal for service fit.

The result may suggest that the customer can continue with **Standard Service** if the sample behaves predictably, the customer can manage the migration process confidently, and required adjustments remain within standard service capability.

It may suggest **Managed Service** if the migration appears feasible through standard service capability, but the customer wants Next-Cart to perform the migration process and reduce the internal execution burden.

It requires **Custom Service** if the result shows that customization or modification work is needed.

This distinction matters because service choice should be based on what the sample proves, not only on the customer’s first expectation before seeing migrated data.

### Self-Run and Expert-Assisted Demo Paths  <a href="#self-run-and-expert-assisted-demo-paths" id="self-run-and-expert-assisted-demo-paths"></a>

Customers may approach Demo Migration in two practical ways.

**Self-Run Demo Migration**

A self-run demo is useful when the customer wants to explore the migration outcome directly and has enough internal confidence to review the sample result.

If the result differs from expectations, the customer can use Live Chat to clarify what the sample may be revealing about the source data, Target Platform, configuration, Add-ons, or service fit.

**Expert-Assisted Demo Migration**

An expert-assisted demo is useful when the customer wants help shaping the sample, interpreting the result, and deciding what the findings mean for the broader migration path.

This path can be especially useful when the store has complex product behavior, important customer or order-history requirements, Custom Platform involvement, third-party logic, or sensitive launch timing.

In both paths, the purpose is the same: use the demo result to make better decisions before the project moves deeper into execution.

### What Demo Migration Does Not Prove  <a href="#what-demo-migration-does-not-prove" id="what-demo-migration-does-not-prove"></a>

Demo Migration is limited by design.

A good demo does not prove that:

* every record will behave identically during Full Migration
* every edge case has been reviewed
* every platform limitation has been resolved
* every Add-on or Custom Service need has already been identified
* validation can be skipped after Full Migration
* launch readiness has already been confirmed

Demo Migration should reduce uncertainty, not create overconfidence.

### Common Mistakes When Reviewing a Demo  <a href="#common-mistakes-when-reviewing-a-demo" id="common-mistakes-when-reviewing-a-demo"></a>

Common mistakes include:

* choosing a sample that is too simple
* checking only whether records appear
* ignoring product behavior and relationship integrity
* overlooking customer and order usability
* failing to include content or SEO-sensitive examples when they matter
* assuming a clean demo removes the need for full validation
* choosing a service model before interpreting the demo result carefully
* treating Add-on or Custom Service signals as minor details

These mistakes usually create false confidence. The best demo review focuses on whether the sample still supports the business outcomes that matter after launch.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

Migration is valuable because it gives customers an early, evidence-based view of how representative source-store data behaves in the Target Platform. It helps reveal what maps cleanly, what needs adjustment, what may require Add-ons, and what points toward Custom Service.

The strongest Demo Migration is not the largest sample or the easiest sample. It is the sample that shows whether the target result can preserve the business meaning the customer needs to protect.

Choose demo records that reflect the store’s real complexity, then review the result against the behaviors your business cannot afford to lose. If the findings are unclear, reveal Add-on needs, or suggest Custom Service requirements, Live Chat can help interpret the result and clarify the safest next step before Full Migration.

### FAQs  <a href="#faqs" id="faqs"></a>

**What is Demo Migration?**

Demo Migration is a sample migration used to preview how selected source-store data may appear in the Target Platform before the broader migration is executed.

**What should be included in a Demo Migration sample?**

A useful sample should include records that reveal real migration meaning, such as complex products, important category paths, representative customers and orders, key CMS Pages or Blog Posts, and records affected by apps, extensions, custom fields, or outside systems.

**Does a good Demo Migration prove the full migration will work the same way?**

No. A good demo provides early evidence, but it does not prove every record, edge case, or later-stage requirement. Full validation is still needed after broader migration activity.

**Can Demo Migration show whether Add-ons are needed?**

Yes. Demo Migration can reveal needs such as selective migration, advanced mapping, or data configuration. Those needs may point to the Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure.

**Can Demo Migration show whether Custom Service is needed?**

Yes. If the demo reveals requirements beyond standard service capability or standard Add-on capability, such as Custom Platform handling, custom fields, third-party data, or bespoke transformation, the project requires Custom Service.

**Should service choice happen before or after Demo Migration?**

Service expectations may exist before Demo Migration, but the demo result often gives the clearest evidence for confirming whether Standard Service, Managed Service, or Custom Service is the safest fit.
