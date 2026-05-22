# Adobe Commerce Validation Priorities

An Adobe Commerce migration should not be validated evenly across the whole storefront. It should be validated where Adobe Commerce is most likely to change commercial context, product access, pricing visibility, staged behavior, scope behavior, and route meaning.

That matters because Adobe Commerce can look structurally complete before the migrated store is commercially trustworthy. Products may appear present, companies may exist, shared catalogs may be assigned, customer groups may be visible, staged campaigns may be configured, and URL rewrites may resolve. Those signals are useful, but they do not prove that the target store still supports the business rules, customer access, pricing outcomes, and storefront journeys that matter after launch.

A stronger validation approach tests the areas where Adobe Commerce most often reshapes meaning: company structure, shared-catalog logic, customer-group interaction, staged content behavior, website/store/store-view scope, high-value URLs, and surrounding enterprise workflows.

### What Adobe Commerce Validation Is Trying to Prove <a href="#what-adobe-commerce-validation-is-trying-to-prove" id="what-adobe-commerce-validation-is-trying-to-prove"></a>

For Adobe Commerce, validation is not only a completeness check. It is a proof exercise around commercial meaning.

A strong review should confirm five outcomes.

#### Company structure still supports the intended business model <a href="#company-structure-still-supports-the-intended-business-model" id="company-structure-still-supports-the-intended-business-model"></a>

The target may show company accounts, company users, and account relationships. Validation should go further and confirm whether those relationships still support the intended buyer organization, internal account structure, permissions, and business-customer context.

#### Shared-catalog access and pricing still behave correctly <a href="#shared-catalog-access-and-pricing-still-behave-correctly" id="shared-catalog-access-and-pricing-still-behave-correctly"></a>

Shared catalogs may be assigned, but the real test is whether the right company or customer context sees the right products at the right prices. Access and pricing must be validated together because a catalog can be present while still exposing the wrong product set or commercial rule.

#### Customer-group interaction still makes sense <a href="#customer-group-interaction-still-makes-sense" id="customer-group-interaction-still-makes-sense"></a>

Customer groups can interact with catalog visibility, pricing, tax class, and access behavior. Validation should prove that the customer-group layer still supports the intended Adobe Commerce outcome instead of carrying over old segmentation in a way that conflicts with the target structure.

#### Staged content and campaign behavior still work where it matters <a href="#staged-content-and-campaign-behavior-still-work-where-it-matters" id="staged-content-and-campaign-behavior-still-work-where-it-matters"></a>

A storefront may look correct at one moment but still fail if scheduled promotions, campaign updates, CMS Pages, category changes, or merchandising behavior do not work at the right time. Adobe Commerce validation should include time-sensitive review when staged behavior is commercially important.

#### High-value routes and scope-sensitive behavior still support the customer journey <a href="#high-value-routes-and-scope-sensitive-behavior-still-support-the-customer-journey" id="high-value-routes-and-scope-sensitive-behavior-still-support-the-customer-journey"></a>

A URL rewrite, category assignment, or store-view value can exist and still be weak if it sends customers to the wrong destination, shows the wrong localized value, or behaves inconsistently by website, store, or store view. Validation should prove that the intended journey still works in the right context.

### Validation Priority 1: Company Structure <a href="#validation-priority-1-company-structure" id="validation-priority-1-company-structure"></a>

The first Adobe Commerce validation priority is usually the company model itself.

Company structure should be reviewed through the business relationships it is meant to support, not only through record presence. Useful checks include:

* whether the right customers are associated with the right company context
* whether company users, account relationships, and internal structure remain understandable
* whether permissions or approval-sensitive expectations still match business use
* whether company-level access and pricing context still reflect business expectations
* whether support, sales, or account teams can interpret the migrated company structure after launch

This matters because company records can exist in Adobe Commerce while the real buyer relationship becomes harder to operate. A structurally imported company does not automatically prove that the target supports the intended B2B model.

### Validation Priority 2: Shared Catalog Assignment, Product Access, and Pricing Context <a href="#validation-priority-2-shared-catalog-assignment-product-access-and-pricing-context" id="validation-priority-2-shared-catalog-assignment-product-access-and-pricing-context"></a>

Shared catalogs are one of the most commercially sensitive Adobe Commerce validation priorities.

The review should focus on the shared catalogs most likely to expose risk: catalogs tied to strategic customers, negotiated pricing, restricted products, special assortments, or company-specific access rules.

Useful checks include:

* whether the correct shared catalog is assigned to the correct company or customer context
* whether the intended products are visible and unintended products remain restricted
* whether custom pricing, tiered pricing, and access-sensitive pricing behave as expected
* whether category permissions and catalog access remain coherent after migration
* whether the business can explain why a customer sees a specific product set and price

This is one of the clearest places where Adobe Commerce can look enterprise-ready while still being commercially wrong. The target must prove that catalog visibility and pricing are correct together.

### Validation Priority 3: Customer-Group Interaction <a href="#validation-priority-3-customer-group-interaction" id="validation-priority-3-customer-group-interaction"></a>

Customer groups should be validated as part of the commercial model, not as a separate administrative list.

In Adobe Commerce, customer groups may interact with shared catalogs, tax classes, price visibility, promotional logic, and customer-specific behavior. Validation should therefore review group behavior in the contexts where it affects the storefront or commercial outcome.

Useful checks include:

* whether customer groups still reflect meaningful business segments
* whether customers and companies are aligned to the right group behavior
* whether shared-catalog assignment and customer-group logic reinforce each other rather than conflict
* whether inherited group behavior is still useful or now redundant
* whether group-based pricing, visibility, or tax expectations remain acceptable

This priority is especially important when the source store used customer groups loosely, inconsistently, or as a workaround for B2B behavior that Adobe Commerce now handles more natively.

### Validation Priority 4: Staged Content and Campaign Behavior <a href="#validation-priority-4-staged-content-and-campaign-behavior" id="validation-priority-4-staged-content-and-campaign-behavior"></a>

Adobe Commerce validation should review staged behavior when campaigns, scheduled updates, or time-sensitive merchandising matter to the launch.

The target should not only show the right current content. It should also prove that future content and campaign states behave in a commercially acceptable way.

Useful checks include:

* whether scheduled updates exist for the correct products, categories, CMS Pages, CMS Blocks, price rules, or merchandising assets
* whether campaign timing reflects the intended business calendar
* whether preview-based review gives the team enough confidence before launch
* whether the storefront behaves correctly before, during, and after a scheduled change
* whether campaign logic is understandable to the team that will maintain it after launch

This is one of the clearest places where Adobe Commerce validation becomes more than storefront review. It becomes proof that the future operating model still works.

### Validation Priority 5: Website, Store, and Store-View Scope Behavior <a href="#validation-priority-5-website-store-and-store-view-scope-behavior" id="validation-priority-5-website-store-and-store-view-scope-behavior"></a>

Adobe Commerce uses a scope hierarchy that can affect content, configuration, language, pricing context, catalog behavior, URLs, and administrative interpretation.

Validation should review the scope levels most likely to expose mismatch. Useful checks include:

* whether values appear at the intended website, store, or store-view level
* whether localized content, CMS Pages, category names, and product attributes display correctly by store view
* whether pricing, catalog, or customer behavior does not leak into the wrong scope
* whether URL and navigation behavior remain coherent across relevant scopes
* whether internal teams understand where future edits should be made

This matters because one of the most common Adobe Commerce validation failures is not missing data. It is commercially wrong scope behavior that looks technically complete.

### Validation Priority 6: High-Value Legacy URLs and Destination Quality <a href="#validation-priority-6-high-value-legacy-urls-and-destination-quality" id="validation-priority-6-high-value-legacy-urls-and-destination-quality"></a>

Adobe Commerce has native URL rewrite behavior, but that does not remove the need for route validation.

A technically valid redirect can still fail if the destination no longer supports the customer intent, search value, or commercial purpose of the original path. Validation should therefore focus on priority URLs rather than every low-value path equally.

Useful checks include:

* best-selling product URLs
* high-value category or landing-page URLs
* CMS Pages that support trust, service, policy, or buying decisions
* URLs tied to paid campaigns, organic traffic, backlinks, or customer support workflows
* routes whose meaning changes because of shared-catalog access, store-view scope, or staged content behavior

The review question is not only whether the old URL resolves. It is whether the destination still supports the purpose that made the old URL valuable.

### Validation Priority 7: Enterprise App, Extension, and Workflow Behavior <a href="#validation-priority-7-enterprise-app-extension-and-workflow-behavior" id="validation-priority-7-enterprise-app-extension-and-workflow-behavior"></a>

Many Adobe Commerce storefronts depend on more than native catalog, customer, and order structures.

Validation should include enterprise behavior that the business still treats as commercially or operationally important, including:

* extension-dependent pricing, visibility, approval, checkout, or merchandising behavior
* custom fields that still drive company, customer, product, order, or reporting logic
* outside-system identifiers used by ERP, PIM, CRM, fulfillment, finance, or analytics systems
* workflows that affect account handling, merchandising, promotions, operations, or reporting
* storefront elements that shape trust, navigation, or customer decision-making

This priority is important because Adobe Commerce can support more native structure than many lighter platforms, but enterprise stores often still depend on a surrounding app, extension, integration, and custom-data layer. If those layers are not validated, the storefront can look complete while important business behavior remains unclear.

### What Makes an Adobe Commerce Validation Sample Strong <a href="#what-makes-an-adobe-commerce-validation-sample-strong" id="what-makes-an-adobe-commerce-validation-sample-strong"></a>

A strong Adobe Commerce validation sample is built around meaning, not randomness.

The sample should usually include:

* the companies and customer relationships most important commercially
* shared catalogs with sensitive pricing, product access, or category permission logic
* customer groups most likely to affect pricing, visibility, tax class, or access behavior
* staged campaigns or scheduled updates that matter to launch readiness
* website, store, and store-view cases likely to expose scope mismatch
* high-value routes where destination quality matters
* enterprise workflows, extension behavior, custom fields, and external identifiers that still affect business interpretation

This is stronger than broad random checking because it tests the areas where Adobe Commerce most often changes business meaning rather than merely confirming that records survived.

### What Often Gets Missed in Adobe Commerce Validation <a href="#what-often-gets-missed-in-adobe-commerce-validation" id="what-often-gets-missed-in-adobe-commerce-validation"></a>

Several patterns weaken Adobe Commerce validation.

Common mistakes include:

* treating company creation as proof that company logic is correct
* treating shared-catalog assignment as proof that pricing and access are commercially right
* validating customer groups separately from shared-catalog behavior
* checking staged content only as current state instead of timed behavior
* reviewing website, store, and store-view values without checking real storefront context
* validating URL rewrites without checking destination quality
* ignoring extension-owned or integration-dependent behavior because native Adobe Commerce records look complete
* relying on broad record-count checks instead of representative commercial scenarios

These mistakes create the illusion of a mature Adobe Commerce launch while leaving the most important commercial questions unresolved.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce validation is strongest when it focuses first on the areas where the platform is most likely to change commercial meaning: company structure, shared catalogs, customer groups, staged content, scope behavior, high-value URLs, and enterprise workflow dependencies.

That is what makes validation useful. A migrated Adobe Commerce store can look polished while still being commercially weaker in exactly those areas. The safest review does not treat every record equally. It tests the scenarios that prove whether the Target Platform is ready to support the business model after launch.

Use Demo Migration and post-migration review to validate the Adobe Commerce scenarios that matter most before launch decisions are locked. If a result leaves uncertainty around whether a difference is acceptable target-platform formalization or a real continuity problem, Live Chat can help interpret the evidence before the next migration decision.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first in an Adobe Commerce migration?**

Start with the areas most likely to affect commercial correctness: company structure, shared catalog access, pricing visibility, customer-group behavior, staged content, scope-sensitive storefront behavior, high-value URLs, and enterprise workflows that still affect business operations.

**Why are shared catalogs such an important Adobe Commerce validation priority?**

Shared catalogs can control product access and custom pricing for specific company contexts. Validation should prove that the right customers see the right catalog, the right products, and the right prices, rather than only confirming that shared catalog records exist.

**Should Adobe Commerce validation include staged content?**

Yes, when staged campaigns, scheduled promotions, or time-sensitive merchandising matter to launch readiness. The storefront should be checked not only in its current state, but also before, during, and after important scheduled changes where those changes affect customer experience or revenue.

**Do Adobe Commerce URL rewrites prove SEO continuity by themselves?**

No. URL rewrites and redirects reduce one technical barrier, but validation still needs to confirm that high-value legacy routes lead to destinations that preserve the original customer intent, search value, and commercial purpose.

**How should custom fields, extensions, and integrations be validated?**

They should be validated through the business outcomes they support. If a custom field, extension, or external identifier affects pricing, visibility, account handling, reporting, fulfillment, or customer trust, the review should prove that the migrated result remains understandable and usable after launch.
