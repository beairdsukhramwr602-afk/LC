---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/EwOn3si2UOVRL65zVOMg/data-processing-and-behavior/quickstart-1
---

# Planning Migration Validation and Acceptance Criteria

Migration validation is strongest when the business defines what “acceptable” means before the project reaches execution pressure. Waiting until data has already moved often turns review into a rushed reaction: more people are involved, launch expectations are stronger, and unclear standards become harder to resolve.

A strong validation plan gives the migration project a practical decision framework. It defines what must be reviewed, who should review it, what sample is representative, which differences are acceptable, and which issues should block approval.

Validation is not only a post-migration check. It is a planning discipline that helps the business decide how success will be judged before execution makes that judgment more difficult.

### Validation planning defines acceptable outcomes before review begins <a href="#validation-planning-defines-acceptable-outcomes-before-review-begins" id="validation-planning-defines-acceptable-outcomes-before-review-begins"></a>

A migration project does not succeed simply because records appear in the Target Platform. It succeeds when the migrated store still supports the business outcomes that matter after launch.

That means validation planning should answer questions such as:

* what must still work after migration
* which records, pages, and workflows carry the highest business value
* which platform-driven differences are acceptable
* which differences would create operational, customer-facing, SEO, or reporting problems
* who is responsible for judging each outcome area
* what must be confirmed before the migration result can be accepted

Acceptance criteria turn review from a vague reaction into a structured approval decision.

### Record counts are useful, but they are not acceptance criteria <a href="#record-counts-are-useful-but-they-are-not-acceptance-criteria" id="record-counts-are-useful-but-they-are-not-acceptance-criteria"></a>

Record totals are important as a surface check, but they do not prove that the migrated store works correctly.

A project can show the expected number of products, customers, orders, or content records and still fail in ways that matter. Products may lose important buying context. Category paths may become less useful. Order history may be harder for support teams to interpret. Customer continuity may not behave as expected. SEO-sensitive pages may remain visible but no longer preserve the same search or conversion value.

Counts confirm presence. Acceptance criteria confirm whether the result is usable.

### Acceptance criteria should be based on business outcomes <a href="#acceptance-criteria-should-be-based-on-business-outcomes" id="acceptance-criteria-should-be-based-on-business-outcomes"></a>

The strongest acceptance criteria describe what the business must still be able to do after migration.

Examples include:

* customers can still buy important products in the intended way
* shoppers can still discover products through meaningful categories or browse paths
* customer records remain usable for customer-facing and support-facing needs
* order history remains clear enough for service, reconciliation, reporting, or post-purchase workflows
* priority landing pages remain reachable, credible, and aligned with their original intent
* business-critical app, plugin, module, extension, custom-field, or outside-system context still supports the expected result

This is stronger than approving a project because the data is visible. A usable validation standard defines what the migrated data must still enable.

### A practical validation plan needs five elements <a href="#a-practical-validation-plan-needs-five-elements" id="a-practical-validation-plan-needs-five-elements"></a>

A validation plan does not need to be complicated, but it should be specific enough to prevent late-stage confusion.

#### Validation areas <a href="#validation-areas" id="validation-areas"></a>

Validation areas define what parts of the migrated result need review. They usually include products, categories, customers, orders, SEO-sensitive pages, relationship-sensitive records, and any business-critical custom or third-party context.

#### Acceptance criteria <a href="#acceptance-criteria" id="acceptance-criteria"></a>

Acceptance criteria define what is acceptable for each validation area. They should be written in outcome language, not only data-presence language.

#### Validation responsibility <a href="#validation-responsibility" id="validation-responsibility"></a>

Validation responsibility identifies who is best positioned to judge each area. Product behavior, customer-service usability, SEO continuity, and launch readiness may require different reviewers.

#### Review sample <a href="#review-sample" id="review-sample"></a>

The review sample should include records and pathways that are likely to expose real migration risk. A representative sample is more useful than an easy sample that only confirms simple records.

#### Escalation threshold <a href="#escalation-threshold" id="escalation-threshold"></a>

An escalation threshold defines which issues should be treated as acceptable differences, which should be corrected, and which should block acceptance until resolved.

### Validation areas should reflect how the business uses the store <a href="#validation-areas-should-reflect-how-the-business-uses-the-store" id="validation-areas-should-reflect-how-the-business-uses-the-store"></a>

Validation becomes clearer when it is organized around outcome areas instead of one broad “check everything” instruction.

#### Product validation <a href="#product-validation" id="product-validation"></a>

Product validation should confirm whether important products still support the intended buying decision.

Useful criteria may include:

* variants and options behave clearly enough for customers
* pricing, media, descriptions, and attributes remain understandable
* product relationships, options, or bundles still support the intended purchase logic where relevant
* product data affected by apps, plugins, modules, extensions, custom fields, or outside systems remains usable if it is business-critical

The practical question is not only whether the product exists. It is whether the product still works as a sellable item in the Target Platform.

#### Category and discovery validation <a href="#category-and-discovery-validation" id="category-and-discovery-validation"></a>

Category and discovery validation should confirm whether customers can still reach important products through meaningful pathways.

Useful criteria may include:

* major category paths still make sense
* key browse entry points still support product discovery
* filtering, attributes, or navigation logic remains acceptable where it affects conversion
* high-value category pages still support their intended landing-page role

A category page can be visible and still fail if it no longer supports the browse behavior the business depends on.

#### Customer continuity validation <a href="#customer-continuity-validation" id="customer-continuity-validation"></a>

Customer validation should confirm whether customer records remain usable in the ways the business needs.

Useful criteria may include:

* customer records remain understandable
* customer-linked history is usable where expected
* customer groups, segmentation, or ownership context remains acceptable where relevant
* the customer-facing or support-facing experience still matches business expectations

Customer continuity is rarely just a record-presence issue. It is about whether the business can still interpret and use customer information after the move.

#### Order-history validation <a href="#order-history-validation" id="order-history-validation"></a>

Order-history validation should confirm whether migrated orders remain useful for support, operations, reporting, or post-purchase workflows.

Useful criteria may include:

* order records remain readable and operationally useful
* product references inside orders remain understandable
* customer relationships remain meaningful
* discounts, taxes, shipping, payment, or fulfillment context remains usable enough for the intended business purpose

This area becomes especially important when historical orders are needed after launch.

#### SEO and page-continuity validation <a href="#seo-and-page-continuity-validation" id="seo-and-page-continuity-validation"></a>

SEO-sensitive validation should confirm whether priority pages still support traffic continuity and customer trust.

Useful criteria may include:

* high-value pages remain reachable
* page intent is preserved where possible
* priority landing pages remain credible and useful
* important product and category paths support continuity after migration
* redirect-sensitive pages are included in review when URLs change

This does not mean every page needs the same review depth. It means pages with search, traffic, revenue, or customer-support value should be named clearly in the validation plan.

#### Relationship-sensitive validation <a href="#relationship-sensitive-validation" id="relationship-sensitive-validation"></a>

Some migration outcomes depend on connected records remaining meaningful together.

Useful criteria may include:

* orders still relate clearly to customers and products
* reviews still connect to the right products or customers where supported
* products still preserve meaningful category, manufacturer, tax, or attribute context
* coupons or promotions still retain usable relationships where relevant
* CMS Pages and Blog Posts remain useful in the content context where they matter

Relationship-sensitive validation is one of the clearest reasons record counts alone are not enough.

### Representative samples reveal risk better than random checks <a href="#representative-samples-reveal-risk-better-than-random-checks" id="representative-samples-reveal-risk-better-than-random-checks"></a>

Validation should include records that are likely to reveal whether the migration result is acceptable.

A useful representative sample may include:

* best-selling or high-margin products
* products with variants, options, attributes, or complex media
* important category paths and landing pages
* representative customers and order histories
* records affected by apps, plugins, modules, extensions, custom fields, or outside-system identifiers
* pages or records that matter to SEO, support, reporting, or launch confidence

Random checks can help catch obvious surface issues. Representative checks are better for judging whether the migrated store still supports the business.

### Early evidence helps shape validation, but it does not replace final acceptance <a href="#early-evidence-helps-shape-validation-but-it-does-not-replace-final-acceptance" id="early-evidence-helps-shape-validation-but-it-does-not-replace-final-acceptance"></a>

Early review is useful because it helps the business discover what acceptance criteria should look like before broader execution begins. Demo Migration can provide representative evidence of how selected data may appear in the Target Platform and where review should be more careful.

That early evidence can help identify:

* which differences are likely to be platform-driven
* which areas need more precise mapping, filtering, or configuration
* which records expose relationship or compatibility issues
* whether internal reviewers can judge the result confidently
* whether customization or modification work may be needed

Demo Migration is evidence, not final approval. A positive early sample does not remove the need for disciplined validation after broader execution.

### Add-on and Custom Service outcomes should be validated when they affect the expected result <a href="#add-on-and-custom-service-outcomes-should-be-validated-when-they-affect-the-expected-result" id="add-on-and-custom-service-outcomes-should-be-validated-when-they-affect-the-expected-result"></a>

If the migration plan uses Add-ons for filtering, mapping, or data configuration, the validation plan should include the outcomes that those Add-ons are expected to support. The review should confirm whether the configured result matches the business intent, not only whether the Add-on was applied.

When the expected result depends on Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, bespoke transformation, or other customization or modification work, validation criteria should be more explicit. Custom Service work should be judged against the specific outcome it was intended to support.

The review standard should match the project’s real complexity. A simple data move and a customization-driven migration should not use the same acceptance criteria.

### Freshness alignment does not prove launch readiness <a href="#freshness-alignment-does-not-prove-launch-readiness" id="freshness-alignment-does-not-prove-launch-readiness"></a>

If the source store continues changing during the project, freshness must be managed before launch. Recent Data Migration can help reduce the gap between earlier migration activity and the final launch state where applicable.

Freshness and acceptance are separate decisions. The business still needs to confirm that:

* newly created important data is present as expected
* high-risk behaviors still work acceptably
* priority pages and records remain usable
* known differences have been classified intentionally
* the completed Target Platform result is ready in the ways that matter most

Freshness supports launch readiness. It does not prove that the migrated result is acceptable by itself.

### Acceptance criteria should separate acceptable difference from unacceptable loss <a href="#acceptance-criteria-should-separate-acceptable-difference-from-unacceptable-loss" id="acceptance-criteria-should-separate-acceptable-difference-from-unacceptable-loss"></a>

Not every difference is a failure. Platform migration often changes presentation, structure, administrative workflows, or supported behavior because the Target Platform does not operate exactly like the Source Platform.

A strong validation plan separates differences into practical categories:

* acceptable platform-driven differences
* manageable presentation differences
* issues that should be corrected before acceptance
* business-critical failures that should block approval

This distinction prevents two common problems: approving a result too loosely because the data is present, or rejecting manageable platform differences as if every change were a migration failure.

### A strong acceptance decision is explainable <a href="#a-strong-acceptance-decision-is-explainable" id="a-strong-acceptance-decision-is-explainable"></a>

A strong acceptance decision usually means the business can explain why the migrated result is acceptable.

That decision is stronger when:

* agreed validation areas were reviewed
* representative samples showed that critical outcomes still work
* responsible reviewers checked the areas they understand best
* known differences were intentionally classified
* unresolved issues were either corrected or consciously accepted
* launch-readiness judgment is based on evidence rather than pressure

That is much stronger than saying the migration “looks good.”

### Common validation planning mistakes <a href="#common-validation-planning-mistakes" id="common-validation-planning-mistakes"></a>

Validation becomes weaker when the project waits too long to define success.

Common mistakes include:

* using record totals as the main proof of success
* treating validation as a late-stage task only
* leaving review responsibility unclear
* reviewing easy records instead of representative records
* failing to classify acceptable differences separately from blockers
* ignoring SEO-sensitive pages or relationship-sensitive records until late review
* assuming that Demo Migration removes the need for final validation
* treating freshness alignment as proof that the store is ready

These mistakes usually create friction at the point where the project needs clarity most.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Planning migration validation and acceptance criteria turns migration review into a controlled business decision. The strongest plans define what must be checked, who should check it, which records or pages are representative, and what acceptable means before execution pressure makes those decisions harder.

Define acceptance criteria around the outcomes the business must preserve after migration. When a difference is difficult to classify as an accepted platform change, a mapping issue, or a blocker, Live Chat can help clarify the issue before review becomes rushed.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the difference between validation and acceptance criteria?**

Validation is the review process. Acceptance criteria are the standards used to decide whether the migration result is acceptable.

**Why are record counts not enough to approve a migration?**

Record counts confirm that expected records are present. They do not prove that products remain buyable, categories still support discovery, order history remains usable, customer continuity behaves as expected, or priority pages still support traffic and conversion.

**When should acceptance criteria be defined?**

Acceptance criteria should be defined before broader execution and launch pressure make review harder. They are most useful when validation areas, responsible reviewers, representative samples, and pass-fail expectations are already clear before heavy review begins.

**Who should be responsible for validation?**

Validation responsibility should be assigned by outcome area. Product behavior, category discovery, customer continuity, order usability, SEO-sensitive pages, and launch readiness may require different reviewers because each area depends on different business knowledge.

**Does Recent Data Migration replace validation?**

No. Recent Data Migration can help reduce the freshness gap before launch where applicable, but the business still needs to confirm that the migrated result is usable, connected, accurate enough for the intended outcome, and acceptable for launch.
