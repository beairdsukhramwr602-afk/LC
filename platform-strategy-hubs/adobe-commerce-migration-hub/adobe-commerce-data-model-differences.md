# Adobe Commerce Data Model Differences

A migration into Adobe Commerce can preserve the visible storefront while still changing the commercial meaning behind it.

That usually happens because Adobe Commerce is not only a more feature-rich storefront target. It is a platform where companies, shared catalogs, customer groups, staged content behavior, scope hierarchy, and native route governance can carry more explicit business meaning than they did in the source store. Products, customers, and orders may still move successfully, but the target can behave very differently once those structures become part of how the business is expected to operate.

This matters because Adobe Commerce data-model differences are rarely just technical translation questions. They change what the store believes a business customer relationship is, how product access and pricing should be controlled, how scheduled merchandising changes should behave, and what the business must validate before it can trust launch readiness.

### The Commercial Unit Often Changes from Customer to Company

One of the biggest Adobe Commerce data-model differences is that the important commercial unit is often no longer only the individual customer record.

In standard direct-to-consumer models, a customer account is often the main identity unit that matters most. In Adobe Commerce B2B structures, the more important unit may be:

* the company
* the customer’s role inside that company
* the shared catalog attached to that company
* the product access and pricing rules that follow that structure

That means customer data in Adobe Commerce often has to be understood through a broader business relationship model. A customer profile may still exist, but the commercial meaning of that customer is shaped by the company structure and the catalog logic tied to it.

### Shared Catalogs Change What Product Access and Pricing Mean

Shared catalogs are one of the clearest Adobe Commerce structural differences.

Adobe Commerce uses shared catalogs to control which products business customers can access and what prices they see. That makes product visibility and pricing a more explicit target structure than in many source stores.

This is a meaningful data-model difference because a source store may have carried those outcomes through:

* customer groups
* negotiated pricing workarounds
* restricted-category logic
* custom account conditions
* informal sales-team rules
* extension-driven visibility logic

Adobe Commerce can carry those outcomes more natively in some cases, but only when the business defines clearly which company should receive which access and pricing structure and why.

### Shared Catalogs and Customer Groups Interact More Directly Than Many Teams Expect

Another important Adobe Commerce difference is the relationship between shared catalogs and customer groups.

Adobe Commerce documents that when a shared catalog is created, a corresponding customer group is also created. That means customer groups and shared catalogs should not be treated as separate, loosely related administrative features. They can become part of one commercial-control model.

This matters because a migration can preserve customer groups and shared catalogs at a technical level while still being commercially wrong if the business has not defined how those layers should work together. The important question is not only whether the customer group survived. It is whether the intended access, pricing, and company relationship still make sense after launch.

### Content Staging Changes How Content and Merchandising Are Modeled

One of the clearest Adobe Commerce-only differences is Content Staging.

Adobe Commerce allows teams to create, preview, and schedule content and merchandising changes directly in the platform. That means the target model may need to preserve not only the visible storefront state, but also the timing and sequencing of future storefront behavior.

This changes migration planning because some storefront meaning may now depend on:

* scheduled promotional changes
* campaign timing
* future product-visibility updates
* timed content launches
* preview-based review workflows

In many source platforms, those behaviors may have been managed more loosely or through surrounding tools. In Adobe Commerce, they can become a more native part of the commercial model.

### Scope Still Matters, but It Carries Heavier Commercial Meaning

Adobe Commerce still uses the websites, stores, and store views hierarchy. That is shared with Magento, but in Adobe Commerce the scope model often interacts more heavily with companies, customer groups, shared catalogs, pricing visibility, and staged content.

That means scope is not only a storefront-variation tool. It can become part of how commercial rules are governed.

A value may therefore carry both a scope meaning and a commercial meaning. A migration can preserve the value itself while still misrepresenting the intended behavior if the value lands at the wrong scope or if the scope hierarchy is not aligned with the company and catalog model.

### Product Structure Still Inherits the Magento Baseline

Adobe Commerce adds more enterprise-native structure, but it does not replace the Magento product baseline.

Products still rely on:

* native product types
* attributes
* attribute sets
* websites, stores, and store views
* customer groups
* native URL rewrites
* extension-aware surrounding logic

That means Adobe Commerce does not remove the need to judge whether complex product behavior still fits the underlying platform model clearly enough. The B2B and staged-content layers add more structure around the storefront, but they do not automatically solve product-translation problems inside it.

This is one reason Adobe Commerce migrations can still fail quietly if teams focus on higher-level enterprise logic while underestimating product, attribute, or scope translation risk.

### Native URL Rewrites Mean Route Governance Is Part of the Model

Adobe Commerce includes native URL rewrite capability, including rewrites for products, categories, and CMS pages.

That means route continuity is not only a technical patching problem. It is part of the native platform model. This matters because the target can govern redirects and path continuity more explicitly than many teams expect.

But native rewrites do not remove the need for path planning. A rewrite can exist while still landing customers on a weaker destination if product, category, content, or campaign meaning changed during migration.

The important target question is therefore not only whether a rewrite exists. It is whether the destination still supports the customer intent the original route used to serve.

### Validation Scope Becomes More Commercially Contextual

Because Adobe Commerce changes how the store is structured, it also changes what the data must prove after migration.

The target can no longer be judged only by checking whether products, customers, and orders exist. It also needs to prove that:

* companies are structured correctly
* shared catalogs are assigned correctly
* pricing and product visibility reflect the intended business rules
* customer groups still carry the intended meaning
* staged content behavior makes sense where it matters
* scope-aware storefront behavior still reflects the business model
* routes still support the intended journey

This is one of the most important data-model differences of all. Adobe Commerce changes not just the data structure, but the evidence structure the business needs before it can trust launch readiness.

### What Usually Needs the Earliest Review

The highest-risk Adobe Commerce data-model differences usually deserve early review in:

* company structure
* shared catalog assignment and pricing visibility
* customer-group interaction
* staged content and campaign-sensitive behavior
* websites, stores, and store-view scope logic
* product families where the Magento baseline still creates structural pressure
* route governance and destination logic

These are the areas most likely to expose whether the target structure is commercially clear enough rather than only technically complete.

### How Custom Cart as a Source Changes Adobe Commerce Data-Model Review

When the source platform is a Custom Cart, Adobe Commerce data-model review usually needs a more bespoke translation lens.

That is because the source may carry company logic, pricing rules, customer segmentation, content-timing behavior, or route logic in structures that do not align neatly with Adobe Commerce companies, shared catalogs, customer groups, Content Staging, or scope hierarchy. In those cases, the key review question is not only what data exists. It is how that source meaning should be interpreted and rebuilt so the Adobe Commerce target remains commercially coherent.

In this context, earlier expert review and a more tailored migration path often become especially important.

### Conclusion

Adobe Commerce data-model differences matter because they change the commercial meaning of migrated data, not only its storage location.

The target often moves from a looser product-and-customer model into a more explicit structure built around companies, shared catalogs, customer-group interaction, staged content behavior, scope-aware rules, and native route governance. That can be a major strength when the business genuinely needs that structure. It becomes riskier when the business has not yet defined how those layers should work after the move.

Review the company, catalog, customer-group, staged-content, route, and scope logic that matters most before treating the target model as settled. If those structures still feel unclear, Live Chat can help determine whether the issue is target fit, translation risk, or a sign that more guided handling is needed before full execution.

### FAQs

#### What is one of the biggest Adobe Commerce data-model differences?

One of the biggest differences is that the important commercial unit often shifts from the individual customer account to the company relationship and the shared-catalog logic attached to it.

#### Are shared catalogs only a merchandising tool in Adobe Commerce?

No. In Adobe Commerce, shared catalogs can directly control product access and pricing visibility for different company contexts.

#### Why do customer groups matter more in Adobe Commerce than many teams expect?

Because Adobe Commerce ties them more directly to company and shared-catalog logic. A shared catalog also creates a corresponding customer group, so the two layers should be treated as part of one commercial model.

#### Does Content Staging change how data should be reviewed?

Yes. Because timed and scheduled merchandising or content behavior can be part of the operating model, the business may need to validate not only the storefront state, but also the timing logic that matters after launch.
