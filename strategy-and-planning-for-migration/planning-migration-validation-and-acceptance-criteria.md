---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/EwOn3si2UOVRL65zVOMg/data-processing-and-behavior/quickstart-1
---

# Planning Migration Validation and Acceptance Criteria

Migration validation becomes strongest when the business defines what “acceptable” means before execution pressure begins. Waiting until data has already moved often turns review into a rushed reaction: more people become involved, launch expectations become stronger, and unclear standards become harder to resolve.

A strong validation plan gives the migration project a practical decision framework. It defines what must be reviewed, who should review it, which records or pages represent real risk, which differences are acceptable, and which issues should block approval until resolved.

Validation is not only a post-migration check. It is a planning discipline that helps the business decide how success will be judged before the final launch decision depends on it.

### Validation Planning Defines Success Before Review Begins <a href="#validation-planning-defines-success-before-review-begins" id="validation-planning-defines-success-before-review-begins"></a>

A migration project does not succeed only because records appear in the Target Platform. It succeeds when the migrated store still supports the business outcomes that matter after launch.

Validation planning should answer questions such as:

* what must still work after migration;
* which products, customers, orders, pages, and workflows carry the highest business value;
* which platform-driven differences are acceptable;
* which differences would create operational, customer-facing, SEO, reporting, or launch-readiness problems;
* who is responsible for judging each outcome area;
* what evidence must be reviewed before the migrated result can be accepted.

Acceptance criteria turn review from a vague reaction into a structured approval decision. They give reviewers a shared standard before the project reaches the point where every unresolved issue feels urgent.

### Record Counts Are Evidence, Not Acceptance Criteria <a href="#record-counts-are-evidence-not-acceptance-criteria" id="record-counts-are-evidence-not-acceptance-criteria"></a>

Record totals are useful as a surface check, but they do not prove that the migrated store works correctly.

A project can show the expected number of products, customers, orders, or content records and still fail in ways that matter. Products may lose important buying context. Category paths may become less useful. Order history may be harder for support teams to interpret. Customer records may exist but no longer support the same account, group, or segmentation behavior. SEO-sensitive pages may remain visible but no longer preserve the same search or conversion value.

Counts confirm presence. Acceptance criteria confirm whether the result is usable.

A better approval standard combines quantity checks with business-outcome checks. The question is not only whether expected data exists. The question is whether the migrated data still supports the store functions, customer experiences, operational workflows, and launch expectations the business depends on.

### Acceptance Criteria Should Be Written Around Outcomes <a href="#acceptance-criteria-should-be-written-around-outcomes" id="acceptance-criteria-should-be-written-around-outcomes"></a>

The strongest acceptance criteria describe what the business must still be able to do after migration.

Useful outcome-based criteria may include:

* customers can still buy priority products in the intended way;
* shoppers can still discover important products through meaningful category, collection, search, or filtering paths;
* customer records remain usable for customer-facing and support-facing needs;
* order history remains clear enough for service, reconciliation, reporting, and post-purchase workflows;
* priority landing pages remain reachable, credible, and aligned with their original intent;
* business-critical app, plugin, module, extension, custom-field, or outside-system context still supports the expected result.

This is stronger than approving a migration because data is visible. A usable validation standard defines what the migrated data must still enable.

### A Practical Validation Plan Needs Five Controls <a href="#a-practical-validation-plan-needs-five-controls" id="a-practical-validation-plan-needs-five-controls"></a>

A validation plan does not need to be complicated, but it should be specific enough to prevent late-stage confusion.

| Validation control    | What it defines                                           | Why it matters                                         |
| --------------------- | --------------------------------------------------------- | ------------------------------------------------------ |
| Validation area       | The part of the migrated result that needs review         | Prevents vague instructions such as “check everything” |
| Acceptance criteria   | What acceptable means for that area                       | Turns review into an approval decision                 |
| Reviewer ownership    | Who is best qualified to judge the area                   | Avoids unclear responsibility and delayed decisions    |
| Representative sample | Which records, pages, or workflows should be tested       | Exposes real risk instead of only easy examples        |
| Issue threshold       | Which differences are acceptable, corrective, or blocking | Prevents both over-approval and over-rejection         |

These controls help the project move from broad review to accountable review. They also make the final launch decision easier to explain because the business can show what was checked, who checked it, and what standard was used.

### Validation Areas Should Reflect How the Store Operates <a href="#validation-areas-should-reflect-how-the-store-operates" id="validation-areas-should-reflect-how-the-store-operates"></a>

Validation becomes clearer when it is organized around outcome areas instead of one broad review task.

#### Product Validation <a href="#product-validation" id="product-validation"></a>

Product validation should confirm whether important products still support the intended buying decision.

Useful criteria may include:

* variants and options behave clearly enough for customers;
* pricing, media, descriptions, and attributes remain understandable;
* product relationships, bundles, kits, or configurable options still support the intended purchase logic where relevant;
* product data affected by apps, plugins, modules, extensions, custom fields, or outside systems remains usable if it is business-critical.

The practical question is not only whether the product exists. It is whether the product still works as a sellable item in the Target Platform.

#### Category and Discovery Validation <a href="#category-and-discovery-validation" id="category-and-discovery-validation"></a>

Category and discovery validation should confirm whether customers can still reach important products through meaningful pathways.

Useful criteria may include:

* major category paths still make sense;
* key browse entry points still support product discovery;
* filtering, attributes, or navigation logic remains acceptable where it affects conversion;
* high-value category pages still support their intended landing-page role.

A category page can be visible and still fail if it no longer supports the browse behavior the business depends on.

#### Customer Continuity Validation <a href="#customer-continuity-validation" id="customer-continuity-validation"></a>

Customer validation should confirm whether customer records remain usable in the ways the business needs.

Useful criteria may include:

* customer profiles remain understandable;
* address records remain useful for account, support, and order-history review;
* customer-linked history is usable where expected;
* customer groups, segmentation, B2B account context, consent state, or ownership context remains acceptable where relevant.

Customer continuity is rarely just a record-presence issue. It is about whether the business can still interpret and use customer information after the move.

#### Order-History Validation <a href="#order-history-validation" id="order-history-validation"></a>

Order-history validation should confirm whether migrated orders remain useful for support, operations, reporting, or post-purchase workflows.

Useful criteria may include:

* order records remain readable and operationally useful;
* product references inside orders remain understandable;
* customer relationships remain meaningful;
* discounts, taxes, shipping, payment, fulfillment, and status information remains usable enough for the intended business purpose.

This area becomes especially important when historical orders are needed after launch for customer service, accounting reference, warranty handling, repeat purchase support, or internal reporting.

#### SEO and Page-Continuity Validation <a href="#seo-and-page-continuity-validation" id="seo-and-page-continuity-validation"></a>

SEO-sensitive validation should confirm whether priority pages still support traffic continuity and customer trust.

Useful criteria may include:

* high-value pages remain reachable;
* page intent is preserved where possible;
* priority landing pages remain credible and useful;
* important product and category paths support continuity after migration;
* redirect-sensitive pages are included in review when URLs change.

This does not mean every page needs the same review depth. It means pages with search, traffic, revenue, or customer-support value should be named clearly in the validation plan.

#### Relationship-Sensitive Validation <a href="#relationship-sensitive-validation" id="relationship-sensitive-validation"></a>

Some migration outcomes depend on connected records remaining meaningful together.

Useful criteria may include:

* orders still relate clearly to customers and products;
* reviews still connect to the right products or customers where supported;
* products still preserve meaningful category, manufacturer, tax, attribute, or collection context;
* coupons or promotions still retain usable relationships where relevant;
* CMS Pages and Blog Posts remain useful in the content context where they matter.

Relationship-sensitive validation is one of the clearest reasons record counts alone are not enough.

### Representative Samples Reveal More Risk Than Easy Checks <a href="#representative-samples-reveal-more-risk-than-easy-checks" id="representative-samples-reveal-more-risk-than-easy-checks"></a>

Validation should include records and pathways that are likely to reveal whether the migrated result is acceptable.

A useful representative sample may include:

* best-selling or high-margin products;
* products with variants, options, attributes, complex media, or pricing differences;
* important category paths, collections, menus, and landing pages;
* representative customers and order histories;
* records affected by apps, plugins, modules, extensions, custom fields, or outside-system identifiers;
* pages or records that matter to SEO, support, reporting, merchandising, or launch confidence.

Random checks can help catch obvious surface issues. Representative checks are better for judging whether the migrated store still supports the business.

A sample should also include edge cases. If the project only reviews simple records, the team may approve a result before seeing the records most likely to expose mapping, relationship, display, or operational issues.

### Reviewer Ownership Should Match Business Knowledge <a href="#reviewer-ownership-should-match-business-knowledge" id="reviewer-ownership-should-match-business-knowledge"></a>

Validation is weaker when one person is asked to approve every outcome area. Different parts of the migrated result require different business knowledge.

Product managers or merchandising teams are usually better positioned to judge product choice, media, attributes, collections, and sellability. Customer service teams may be better positioned to review customer records, order history, account context, and post-purchase usability. SEO or marketing stakeholders may need to review priority URLs, landing pages, redirects, metadata, and traffic-sensitive content. Operations, finance, or fulfillment stakeholders may need to review order status, tax, shipping, payment, and reconciliation context.

Reviewer ownership should be defined before review begins. Otherwise, issues can remain unresolved because no one is clearly responsible for judging whether the difference is acceptable.

### Issue Thresholds Should Separate Difference From Failure <a href="#issue-thresholds-should-separate-difference-from-failure" id="issue-thresholds-should-separate-difference-from-failure"></a>

Not every difference is a failure. Platform migration often changes presentation, structure, administrative workflows, or supported behavior because the Target Platform does not operate exactly like the Source Platform.

A strong validation plan separates differences into practical categories:

| Issue category                     | Meaning                                                                                         | Approval impact                                       |
| ---------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| Acceptable platform difference     | The Target Platform represents the outcome differently, but the business result remains usable  | Usually does not block acceptance                     |
| Manageable presentation difference | The visual or administrative presentation changes, but the business can work with it            | May need documentation or minor adjustment            |
| Corrective issue                   | The result does not meet an agreed criterion but can be corrected before approval               | Should be resolved or formally accepted before launch |
| Blocking failure                   | The issue prevents a critical business, customer-facing, SEO, operational, or reporting outcome | Should block acceptance until resolved                |

This distinction prevents two common problems: approving a result too loosely because the data is present, or rejecting manageable platform differences as if every change were a migration failure.

### Early Evidence Helps Shape the Validation Plan <a href="#early-evidence-helps-shape-the-validation-plan" id="early-evidence-helps-shape-the-validation-plan"></a>

Early review is useful because it helps the business discover what acceptance criteria should look like before broader execution begins. Demo Migration can provide representative evidence of how selected data may appear in the Target Platform and where review should be more careful.

Early evidence can help identify:

* which differences are likely to be platform-driven;
* which areas need more precise mapping, filtering, or configuration;
* which records expose relationship or compatibility issues;
* whether internal reviewers can judge the result confidently;
* whether customization or modification work may be needed.

Demo Migration is evidence, not final approval. A positive early sample does not remove the need for disciplined validation after broader execution.

### Custom Handling Needs More Explicit Acceptance Criteria <a href="#custom-handling-needs-more-explicit-acceptance-criteria" id="custom-handling-needs-more-explicit-acceptance-criteria"></a>

When a migration depends on configured filtering, mapping, data transformation, custom fields, outside-system identifiers, Custom Platform handling, or custom migration logic adjustment, acceptance criteria should be more explicit.

The validation plan should define the intended outcome of the custom handling, not only confirm that the work was attempted. For example, a mapping decision should be reviewed against the business meaning it was meant to preserve. A filtering decision should be checked against the intended inclusion or exclusion rule. A custom-field decision should be validated against where that information is expected to appear, remain available, or support downstream use.

The review standard should match the project’s real complexity. A simple migration and a customization-driven migration should not use the same acceptance criteria.

### Freshness Alignment Does Not Prove Launch Readiness <a href="#freshness-alignment-does-not-prove-launch-readiness" id="freshness-alignment-does-not-prove-launch-readiness"></a>

If the source store continues changing during the project, freshness must be managed before launch. Recent Data Migration can help reduce the gap between earlier migration activity and the final launch state where applicable.

Freshness and acceptance are separate decisions. The business still needs to confirm that:

* newly created important data is present as expected;
* high-risk behaviors still work acceptably;
* priority pages and records remain usable;
* known differences have been classified intentionally;
* the completed Target Platform result is ready in the ways that matter most.

Freshness supports launch readiness. It does not prove that the migrated result is acceptable by itself.

### A Strong Acceptance Decision Is Explainable <a href="#a-strong-acceptance-decision-is-explainable" id="a-strong-acceptance-decision-is-explainable"></a>

A strong acceptance decision usually means the business can explain why the migrated result is acceptable.

That decision is stronger when:

* agreed validation areas were reviewed;
* representative samples showed that critical outcomes still work;
* responsible reviewers checked the areas they understand best;
* known differences were intentionally classified;
* unresolved issues were either corrected or consciously accepted;
* launch-readiness judgment is based on evidence rather than pressure.

That is much stronger than saying the migration “looks good.”

### Common Validation Planning Mistakes <a href="#common-validation-planning-mistakes" id="common-validation-planning-mistakes"></a>

Validation becomes weaker when the project waits too long to define success.

Common mistakes include:

* treating validation as a late-stage task only;
* using record totals as the main proof of success;
* leaving review responsibility unclear;
* reviewing easy records instead of representative records;
* failing to classify acceptable differences separately from blockers;
* ignoring SEO-sensitive pages or relationship-sensitive records until late review;
* assuming Demo Migration removes the need for final validation;
* treating freshness alignment as proof that the store is ready.

These mistakes usually create friction at the point where the project needs clarity most. Validation planning reduces that friction by making acceptance standards visible before the project reaches the launch decision.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Planning migration validation and acceptance criteria turns migration review into a controlled business decision. The strongest plans define what must be checked, who should check it, which records or pages are representative, and what acceptable means before execution pressure makes those decisions harder.

Define acceptance criteria around the outcomes the business must preserve after migration. When a difference is difficult to classify as an accepted platform change, a mapping issue, a corrective issue, or a blocker, Next-Cart can help clarify the review path before approval becomes rushed.

### Common Questions <a href="#common-questions" id="common-questions"></a>

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
