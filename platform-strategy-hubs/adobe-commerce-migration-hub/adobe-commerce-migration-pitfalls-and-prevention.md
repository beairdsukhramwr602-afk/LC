# Adobe Commerce Migration Pitfalls and Prevention

Adobe Commerce migration pitfalls are often harder to detect than ordinary data-transfer mistakes because many of them do not look broken at first.

A migrated Adobe Commerce store may show products, categories, customers, companies, shared catalogs, customer groups, staged content, and working URLs. That visible completeness can create false confidence. The real pitfall is that Adobe Commerce often formalizes commercial meaning more deeply than the previous store did. Company relationships, product access, negotiated pricing, customer-group behavior, staged campaigns, store-view scope, URL destinations, and enterprise workflow logic all need to keep working in a way the business can understand and trust.

The safest prevention approach is not to inspect Adobe Commerce as a larger storefront with more features. It is to review it as a structured commercial system. The store should prove that the right customer context receives the right catalog, price, content, route, and operating behavior after migration.

### Pitfall 1: Choosing Adobe Commerce Without Defining the Commercial Structure <a href="#pitfall-1-choosing-adobe-commerce-without-defining-the-commercial-structure" id="pitfall-1-choosing-adobe-commerce-without-defining-the-commercial-structure"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The business chooses Adobe Commerce because it appears more enterprise-ready, but the future operating model is still vague.

This usually creates a target store with broader capability but unclear structure. Companies may exist, shared catalogs may be available, staged content may be possible, and store views may be created, but the team still cannot explain how those layers should work together after launch.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* Adobe Commerce is described as more advanced without naming the commercial structures that matter
* company, shared-catalog, customer-group, and scope decisions are still being discussed separately
* staged content is treated as a future benefit rather than a defined operating need
* route and URL decisions are deferred until late in the project
* teams can describe available features, but not the business rules those features must support

#### Prevention <a href="#prevention" id="prevention"></a>

Define the commercial structure Adobe Commerce must support before migration execution becomes the focus.

The planning should clarify:

* which company relationships need to be represented
* which product-access and pricing differences matter
* how customer groups should interact with shared catalogs
* which website, store, and store-view distinctions are commercially necessary
* which staged campaigns or timed content changes need to remain usable
* which routes carry search value, customer intent, or account-specific meaning

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

Before launch planning becomes detailed, identify the commercial structures Adobe Commerce must preserve or formalize. This usually includes company relationships, shared catalogs, pricing rules, customer groups, staged content, scope behavior, and priority URL destinations.

**Pass condition:** the team can explain why Adobe Commerce is the right target structure, not only why it is a broader platform.

### Pitfall 2: Creating Companies Without Preserving the Real Business Relationship <a href="#pitfall-2-creating-companies-without-preserving-the-real-business-relationship" id="pitfall-2-creating-companies-without-preserving-the-real-business-relationship"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Company records are created in Adobe Commerce, but they do not represent the actual business relationships customers depend on.

This often happens when the source store used tags, customer groups, sales-team notes, account conventions, or external systems to represent B2B relationships. If that meaning is imported too literally, Adobe Commerce may contain company records that look organized while still assigning the wrong customers, permissions, or account context.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* company creation is treated as an administrative import result rather than a business-model decision
* important customers appear under company records, but account logic still feels questionable
* no one can clearly explain which rules belong to the company, the individual customer, or a surrounding workflow
* sales, support, or account teams still need outside knowledge to understand the migrated company structure
* the review focuses on company presence rather than customer experience inside the company context

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Review companies through representative business relationships, not only imported records.

Useful prevention checks include:

* whether strategic customers are assigned to the right company context
* whether company users and account relationships remain understandable
* whether account-level expectations still make sense after migration
* whether company context connects correctly to product access and pricing behavior
* whether internal teams can interpret the result without relying on undocumented source-store assumptions

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Use the highest-value or most complex company accounts as early review cases. If those relationships do not translate clearly, broader company migration should not be treated as stable.

**Pass condition:** the most important business customers appear in the right company structure and experience the intended account, access, and pricing context.

### Pitfall 3: Treating Shared-Catalog Assignment as Proof of Correct Access and Pricing <a href="#pitfall-3-treating-shared-catalog-assignment-as-proof-of-correct-access-and-pricing" id="pitfall-3-treating-shared-catalog-assignment-as-proof-of-correct-access-and-pricing"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Shared catalogs are assigned, but product visibility and pricing do not reflect the intended commercial model.

This is a high-risk Adobe Commerce pitfall because shared catalogs can control who sees which products and which prices. A shared catalog can exist and be assigned while still exposing the wrong products, hiding the wrong products, or applying pricing that does not match the business relationship.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* the team checks whether shared catalogs exist, but not whether they behave correctly
* product access and custom pricing are reviewed separately even though they affect the same commercial outcome
* sensitive customers or negotiated-pricing cases have not been prioritized
* inherited source-store workarounds are copied into Adobe Commerce without deciding whether they still belong
* catalog assignment looks complete, but business teams cannot explain why a customer sees a specific product set or price

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate shared catalogs through the customer and company outcomes they control.

The review should confirm:

* which company or customer context should see each important product set
* which prices should appear for negotiated or restricted catalogs
* which products should remain hidden from public or unrelated customer contexts
* which category permissions affect commercial access
* which shared-catalog cases would create margin, trust, or account-management risk if wrong

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Start with the shared catalogs that carry the highest pricing sensitivity or access restriction. Those cases reveal more risk than generic catalog presence checks.

**Pass condition:** the correct company or customer context sees the correct products at the correct prices, and restricted catalog behavior remains commercially defensible.

### Pitfall 4: Letting Customer Groups and Shared Catalogs Drift Apart <a href="#pitfall-4-letting-customer-groups-and-shared-catalogs-drift-apart" id="pitfall-4-letting-customer-groups-and-shared-catalogs-drift-apart"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Customer groups and shared catalogs both exist, but their roles are not coordinated.

Adobe Commerce can make customer groups part of broader commercial behavior, while shared catalogs can control access and pricing for company contexts. If the business keeps inherited customer groups without rethinking their relationship to shared catalogs, the target can carry overlapping or conflicting commercial-control layers.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* customer groups are validated separately from shared catalogs
* inherited group logic is preserved without checking whether it still has a clear purpose
* shared catalogs control one access rule while customer groups imply another
* pricing, visibility, tax, or promotional behavior depends on a group structure no one fully owns
* the team cannot explain which layer should control which commercial rule

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Treat customer groups and shared catalogs as one coordinated commercial model.

Clarify:

* what the shared catalog should control
* what the customer group should still mean
* where inherited group logic is redundant
* where group behavior still affects pricing, tax, promotions, or access
* which combined scenarios should be reviewed before launch

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Review the most commercially sensitive shared-catalog and customer-group combinations before validating lower-risk customers.

**Pass condition:** shared catalogs and customer groups reinforce the intended access and pricing model instead of creating hidden conflicts.

### Pitfall 5: Treating Content Staging as a Feature Instead of an Operating Model <a href="#pitfall-5-treating-content-staging-as-a-feature-instead-of-an-operating-model" id="pitfall-5-treating-content-staging-as-a-feature-instead-of-an-operating-model"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Content Staging exists in Adobe Commerce, but the business has not defined which timed content, merchandising, campaign, or promotional behavior must continue after migration.

The target may look strong because scheduled changes are possible, but the operating model is still weak if teams have not decided what should be staged, when it should change, who reviews it, and how campaign states should behave before, during, and after the scheduled moment.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* staged behavior is mentioned as a benefit, but not tied to specific launch or campaign scenarios
* only the current storefront state is reviewed
* promotion timing matters, but future campaign behavior has not been tested
* preview, approval, and ownership expectations remain vague
* scheduled content or merchandising changes are treated as post-launch cleanup

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Define Content Staging as part of the operating model, not only as a feature to preserve.

The review should clarify:

* which products, categories, CMS Pages, CMS Blocks, promotions, or merchandising assets need timing control
* which future campaign states matter commercially
* who reviews staged changes before they go live
* whether the team understands how scheduled changes will be maintained after launch
* which staged scenarios should be included in Demo Migration or final validation

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Choose representative staged-content scenarios rather than checking only static launch content. A store that looks correct today can still fail if a critical campaign changes incorrectly tomorrow.

**Pass condition:** the most important timed content and campaign scenarios behave acceptably before, during, and after their scheduled changes.

### Pitfall 6: Letting Scope Hierarchy and Commercial Rules Fall Out of Alignment <a href="#pitfall-6-letting-scope-hierarchy-and-commercial-rules-fall-out-of-alignment" id="pitfall-6-letting-scope-hierarchy-and-commercial-rules-fall-out-of-alignment"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Websites, stores, and store views are created, but the hierarchy does not match how content, pricing, access, language, URLs, or customer context should behave.

Adobe Commerce scope can be powerful, but it becomes risky when hierarchy decisions and commercial rules are made separately. The storefront may appear organized while values display in the wrong context or business rules leak into the wrong scope.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* the scope hierarchy is designed first and justified later
* localized content, pricing, access, or route behavior appears under the wrong website, store, or store view
* teams can describe the hierarchy technically, but not commercially
* scope behavior is validated separately from shared catalogs, customer groups, or content rules
* future editing responsibility is unclear because teams do not know where values should be maintained

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Review scope through business meaning.

Clarify:

* what should be global
* what should differ by website, store, or store view
* how scope affects product access, pricing, content, language, and URLs
* which scope distinctions are commercially necessary
* which scope decisions create maintenance risk after launch

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

Review high-risk scope decisions together with the pricing, catalog, content, and URL behavior they affect.

**Pass condition:** the most important values and commercial-rule differences appear in the intended scope and remain understandable to the team that will maintain the store.

### Pitfall 7: Validating URL Rewrites Without Validating Destination Quality <a href="#pitfall-7-validating-url-rewrites-without-validating-destination-quality" id="pitfall-7-validating-url-rewrites-without-validating-destination-quality"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

URL rewrites resolve, but the destination no longer supports the customer intent, search value, or commercial purpose of the old route.

Adobe Commerce can support URL rewrites for products, categories, CMS Pages, and custom routes. That reduces one technical barrier, but it does not prove that the redirected journey remains strong. A route may work technically while landing customers on a weaker product, a less relevant category, a gated catalog state, or content that no longer matches the old route’s purpose.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* rewrite setup is considered complete once the route resolves
* high-value URLs are not ranked by traffic, revenue, backlink value, or customer intent
* product access or shared-catalog visibility changes after the route destination is selected
* route validation ignores store-view context or staged-content behavior
* broad destination logic is applied to URLs that used to serve specific buying intent

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Validate URL rewrites by destination quality, not only technical resolution.

Prioritize:

* best-selling product URLs
* high-value category and landing-page URLs
* CMS Pages that support trust, policy, service, or buying decisions
* URLs tied to paid campaigns, organic traffic, backlinks, or customer support workflows
* routes whose destination changes because of shared catalog, customer group, store-view, or staged-content behavior

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

Review priority rewrites by customer intent. The question is not only whether the old URL redirects. It is whether the new destination still satisfies why the visitor used that path.

**Pass condition:** high-value legacy routes land on destinations that preserve the original commercial purpose well enough to support customer trust and search continuity.

### Pitfall 8: Treating a Polished Enterprise Storefront as Proof of Launch Readiness <a href="#pitfall-8-treating-a-polished-enterprise-storefront-as-proof-of-launch-readiness" id="pitfall-8-treating-a-polished-enterprise-storefront-as-proof-of-launch-readiness"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The Adobe Commerce storefront looks complete, so the team assumes the migration is ready before the underlying commercial scenarios have been proven.

This is one of the most dangerous Adobe Commerce migration pitfalls because it creates confidence from appearance. Products can display, companies can exist, catalogs can be assigned, staged content can be configured, and URL rewrites can work while the most important business behaviors remain unproven.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* validation is mostly page-based rather than scenario-based
* company, catalog, pricing, and staged-content outcomes are inferred from setup
* the launch decision is driven by visible completeness
* only low-risk storefront paths have been reviewed
* teams cannot explain why the target result is trustworthy for the most important commercial cases

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Validate Adobe Commerce through representative commercial scenarios.

The sample should include:

* strategic company and account scenarios
* shared-catalog and negotiated-pricing scenarios
* customer-group interaction scenarios
* staged-content and campaign-timing scenarios
* scope-sensitive storefront scenarios
* high-value route and destination scenarios
* enterprise workflow, extension, custom-field, and integration scenarios where they still affect business use

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

Build the final validation sample around cases most likely to expose ambiguity, not the pages easiest to inspect.

**Pass condition:** the most commercially sensitive Adobe Commerce scenarios behave acceptably enough that the business can explain why the target store is ready.

### How Custom Platform Sources Change Adobe Commerce Pitfall Prevention <a href="#how-custom-platform-sources-change-adobe-commerce-pitfall-prevention" id="how-custom-platform-sources-change-adobe-commerce-pitfall-prevention"></a>

When the Source Platform is a Custom Platform, Adobe Commerce pitfalls become more sensitive because company, pricing, customer-group, content-timing, route, scope, extension, or outside-system meaning may not map cleanly into Adobe Commerce native structures without interpretation.

That usually increases the need to clarify:

* which source-side company or account logic needs to become Adobe Commerce company structure
* which pricing and access behavior belongs in shared catalogs, customer groups, or Custom Service handling
* which custom fields or outside-system identifiers still affect account, product, order, reporting, or fulfillment workflows
* which routes, content rules, or merchandising behavior depend on custom source logic
* which surrounding workflows need custom migration logic adjustment before the result can be trusted

This does not mean every Custom Platform source requires Next-Cart-led migration management. It does mean that Custom Platform handling belongs under Custom Service because the source-side meaning usually needs bespoke interpretation before Adobe Commerce can represent it safely.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration pitfalls usually come from assuming that enterprise breadth automatically creates commercial clarity.

The most serious failures are often quiet: companies that exist but represent the wrong relationship, shared catalogs that are assigned but control the wrong products or prices, customer groups that conflict with catalog rules, staged content that exists without a clear operating model, scope hierarchy that does not match business rules, URL rewrites that resolve to weak destinations, and polished storefronts that have not been proven through real commercial scenarios.

The safest prevention strategy is to define the business meaning early, test the highest-risk commercial scenarios before launch, and judge Adobe Commerce by whether it preserves the intended customer, catalog, pricing, content, route, and workflow outcomes.

Before launch, review the Adobe Commerce scenarios where target-platform formalization can change business meaning: companies, shared catalogs, customer groups, staged content, scope behavior, URL destinations, custom fields, extensions, and external identifiers. If a result is technically present but commercially unclear, use Demo Migration evidence and Live Chat to decide whether the issue is acceptable target-platform behavior, a mapping concern, or a Custom Service requirement.

### FAQs <a href="#faqs" id="faqs"></a>

**What is one of the most common Adobe Commerce migration mistakes?**

A common mistake is treating Adobe Commerce as a broader platform without defining the commercial structure it is supposed to support. The business should clarify company relationships, catalog access, pricing behavior, staged content, scope, and route priorities before judging the migration successful.

**Why are shared catalogs such a common Adobe Commerce pitfall?**

Shared catalogs can control product access and custom pricing for specific company contexts. If they are assigned without clear business logic, the target store may show the wrong products, hide the wrong products, or apply pricing that does not match the intended customer relationship.

**Why can customer groups create problems during Adobe Commerce migration?**

Customer groups can interact with pricing, tax, visibility, promotions, and shared-catalog behavior. If inherited customer groups are preserved without reviewing their current purpose, they can conflict with the Adobe Commerce access and pricing model.

**Why is Content Staging often mishandled?**

Content Staging is often mishandled when teams treat it as a feature rather than an operating model. If staged campaigns, scheduled promotions, or future merchandising states matter, they should be reviewed as timed scenarios, not only as current storefront content.

**Do working URL rewrites prove that Adobe Commerce SEO continuity is safe?**

No. Working URL rewrites prove that routes resolve, but they do not prove destination quality. High-value legacy URLs should still be checked against customer intent, search value, catalog access, store-view behavior, and commercial relevance.

**How does a Custom Platform source affect Adobe Commerce pitfall prevention?**

A Custom Platform source often increases interpretation risk because company logic, pricing behavior, custom fields, outside-system identifiers, routes, or surrounding workflows may not fit Adobe Commerce native structures directly. That kind of bespoke handling belongs under Custom Service, even if migration management is not automatically included.
