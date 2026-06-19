# Reconciling Migration Results

Reconciliation explains the differences found during migration validation. It helps the business understand what changed between the source store and the target store, why the difference exists, whether the result is acceptable, and what decision should be made before launch.

A migrated store does not need to be identical to the source store to be successful. Different e-commerce Platforms can structure products, variants, customer accounts, orders, URLs, CMS Pages, Blog Posts, promotions, and operational settings in different ways. Some differences are expected. Some reflect approved migration scope, Add-ons, mapping decisions, Custom Service handling, or Target Platform behavior. Other differences may reveal real continuity risks that need correction or escalation.

Reconciliation turns those findings into launch judgment. It prevents the team from treating every mismatch as a defect while still identifying the differences that could weaken customer experience, operations, SEO continuity, reporting, support, or connected business workflows.

### What Reconciliation Should Prove <a href="#what-reconciliation-should-prove" id="what-reconciliation-should-prove"></a>

Reconciliation should prove that important differences have been reviewed with enough context to support a decision. It is not a search for perfect visual or numerical sameness between the source store and the target store.

A strong reconciliation process answers four questions:

* What difference was found?
* Why does the difference exist?
* Does the difference affect a customer, operational, SEO, reporting, or external-system outcome?
* Should the difference be accepted, corrected, monitored, or treated as launch-blocking?

These questions make reconciliation more useful than a comparison table. The goal is to preserve business meaning, not to force the Target Platform to duplicate every source-store structure exactly.

#### Reconciliation is not the same as validation <a href="#reconciliation-is-not-the-same-as-validation" id="reconciliation-is-not-the-same-as-validation"></a>

Validation checks whether the target store is usable, trustworthy, and ready for launch decisions. Reconciliation explains the differences discovered during that review.

Validation may show that a product exists, a customer record is present, an order can be reviewed, or a priority page is reachable. Reconciliation asks whether any differences behind those results are expected, acceptable, or risky.

#### Reconciliation is interpretation, not only detection <a href="#reconciliation-is-interpretation-not-only-detection" id="reconciliation-is-interpretation-not-only-detection"></a>

Finding a mismatch is only the first step. The stronger work is interpreting the mismatch.

A category count may differ because the Target Platform uses category structures differently. A URL may change because the Target Platform handles routing differently. A custom field may appear in a different location because it was transformed through Custom Service. A migrated order may use different status labels because the Target Platform does not mirror the source-store status model.

Those differences need interpretation before they can be judged. An explained difference can be acceptable, but explanation alone does not make it safe. The final decision should depend on business impact.

### Why Matching Counts Do Not Prove the Result Is Correct <a href="#why-matching-counts-do-not-prove-the-result-is-correct" id="why-matching-counts-do-not-prove-the-result-is-correct"></a>

Matching totals can be useful, but they do not prove migration success by themselves. Counts show scale. They do not show usability, relationships, behavior, interpretation, SEO continuity, or operational readiness.

A target store can show expected record totals while still containing problems that matter after launch. Products may be present but assigned to weaker category paths. Customers may exist but not support the intended account experience. Orders may be migrated but difficult for support teams to interpret. Reviews, coupons, CMS Pages, Blog Posts, or product relationships may be present but disconnected from the storefront or operational context that gives them value.

#### What matching totals can hide <a href="#what-matching-totals-can-hide" id="what-matching-totals-can-hide"></a>

Matching totals can hide issues such as:

* products attached to incomplete categories or weaker browsing paths;
* variants, options, or attributes that no longer support the expected buying choice;
* customers disconnected from meaningful account or order context;
* orders that are present but difficult for support, reporting, or operations to interpret;
* reviews, coupons, CMS Pages, or Blog Posts that no longer support the intended customer journey;
* SEO-sensitive pages that exist but no longer guide visitors to the right target-store destination;
* custom fields, outside-system identifiers, or integration-related values that no longer support connected workflows.

Counts are supporting evidence. Reconciliation should use them to identify areas for review, then test whether the records still support the business purpose behind them.

### Why Count Differences Do Not Always Mean Failure <a href="#why-count-differences-do-not-always-mean-failure" id="why-count-differences-do-not-always-mean-failure"></a>

A count difference does not automatically mean the migration failed. Some differences are expected because the Target Platform stores, organizes, or displays data differently from the Source Platform. Some differences come from approved scope decisions, intentional cleanup, mapping choices, filtering rules, or accepted transformations.

The question is not only whether a number changed. The question is whether the difference is explainable and whether the resulting target-store outcome is acceptable.

#### Acceptable differences depend on business impact <a href="#acceptable-differences-depend-on-business-impact" id="acceptable-differences-depend-on-business-impact"></a>

A difference may be acceptable when it is:

* caused by expected Target Platform behavior;
* consistent with the approved migration scope;
* caused by an intentional cleanup, filtering, or simplification decision;
* the result of an accepted mapping or transformation choice;
* compatible with the expected customer, operational, SEO, reporting, or external-system outcome;
* documented clearly enough that the business can understand it after launch.

A difference becomes risky when it cannot be explained, weakens a critical workflow, affects priority customer paths, damages operational interpretation, or appears too late for calm decision-making.

#### Separate variance from risk <a href="#separate-variance-from-risk" id="separate-variance-from-risk"></a>

A variance is a difference. A risk is a difference that may weaken the migration outcome.

Reconciliation should prevent both extremes: treating every variance as a defect, and accepting every variance just because someone can describe it. The decision should be based on cause, scope, business impact, and launch confidence.

### Classify Reconciliation Findings by Cause <a href="#classify-reconciliation-findings-by-cause" id="classify-reconciliation-findings-by-cause"></a>

Reconciliation becomes easier when findings are grouped into a small number of decision-ready categories. The categories should help reviewers decide whether a difference is expected, accepted, needs correction, needs monitoring, or blocks launch.

#### Expected platform differences <a href="#expected-platform-differences" id="expected-platform-differences"></a>

Expected platform differences come from the way the Target Platform represents data, relationships, storefront behavior, URLs, account structures, payment context, tax handling, order statuses, content, or operational settings differently from the Source Platform.

These differences may be acceptable when the business outcome remains intact. They should still be documented so launch reviewers do not confuse them with migration defects.

#### Scope differences <a href="#scope-differences" id="scope-differences"></a>

Scope differences occur when data, content, behavior, or historical detail was intentionally excluded from the migration scope.

A scope difference may be acceptable when it was planned and understood. It becomes risky when the team discovers during validation that an excluded area is actually needed for customer experience, support, reporting, SEO continuity, or connected operations.

#### Mapping and transformation differences <a href="#mapping-and-transformation-differences" id="mapping-and-transformation-differences"></a>

Mapping and transformation differences occur when source-store data is converted into a Target Platform structure, field, format, option, status, URL pattern, or relationship model.

These differences should be reviewed against the intended business meaning. A transformed value can be acceptable when it remains understandable and usable. It needs correction or escalation when the transformation changes meaning, weakens workflow continuity, or makes the target-store result difficult to use.

#### Configuration and behavior differences <a href="#configuration-and-behavior-differences" id="configuration-and-behavior-differences"></a>

Some findings are caused by target-store configuration rather than migrated data. Search behavior, filtering, navigation, checkout settings, tax rules, shipping settings, payment methods, theme behavior, redirects, account behavior, and storefront display may all affect how migrated data appears or functions.

These findings should not be judged only as migration issues. The team should identify whether the concern belongs to data migration, Target Platform configuration, theme setup, app or extension behavior, or operational setup.

#### Continuity risks <a href="#continuity-risks" id="continuity-risks"></a>

Continuity risks are differences that may damage the business outcome after launch.

They may affect priority products, buying paths, customer accounts, historical orders, support workflows, SEO-sensitive pages, reporting, external systems, or custom business logic. Continuity risks need clear ownership and a decision before launch. Some can be corrected. Some can be monitored. Some should block launch until resolved.

### Review Differences Through Business Outcomes <a href="#review-differences-through-business-outcomes" id="review-differences-through-business-outcomes"></a>

Reconciliation should not stop at record-level comparison. It should connect each important difference to the business outcome it may affect.

A product difference matters more when it affects purchasability, variant selection, pricing clarity, category placement, search visibility, or merchandising. A customer difference matters more when it affects account access, order context, support history, or segmentation. An order difference matters more when it affects support interpretation, fulfillment records, tax visibility, payment context, or reporting.

#### Customer experience impact <a href="#customer-experience-impact" id="customer-experience-impact"></a>

Differences that affect shoppers need careful review. Priority areas include product discovery, product-detail clarity, variant and option selection, images, pricing visibility, coupons, checkout-related context, account experience, content pages, and priority landing paths.

A target-store result may be acceptable even when it looks different, but it should not confuse customers, weaken trust, or prevent the expected buying journey.

#### Operational impact <a href="#operational-impact" id="operational-impact"></a>

Differences that affect internal teams should be judged by whether the migrated result remains usable for support, merchandising, fulfillment, reporting, finance, marketing, or store administration.

Orders are especially important because their value depends on interpretation. A migrated order should be useful enough for teams to understand customer, product, payment, tax, shipping, status, and fulfillment context where those details are required after launch.

#### SEO and traffic impact <a href="#seo-and-traffic-impact" id="seo-and-traffic-impact"></a>

Differences that affect URLs, redirects, metadata, content hierarchy, CMS Pages, Blog Posts, priority landing pages, or internal linking can influence traffic continuity. Reconciliation should identify whether the difference is expected Target Platform behavior, an approved URL or content decision, a configuration issue, or a launch-sensitive risk.

SEO-sensitive findings should be documented clearly because they may require monitoring after launch even when they do not block launch.

#### External-system impact <a href="#external-system-impact" id="external-system-impact"></a>

Some stores depend on values used outside the storefront, including custom fields, outside-system identifiers, app data, plugin data, module data, extension data, CRM references, ERP identifiers, fulfillment references, reporting keys, or marketplace-related values.

When those values are included in scope, reconciliation should verify that the target-store representation still supports the connected workflow. When they are outside standard migration support, they may require Custom Service handling or a separate business decision.

### Reconcile Add-ons and Custom Service Results Carefully <a href="#reconcile-add-ons-and-custom-service-results-carefully" id="reconcile-add-ons-and-custom-service-results-carefully"></a>

Add-ons and Custom Service can change what the team should expect to see during reconciliation. They should make reconciliation more specific, not less necessary.

A Data Filter Add-on may intentionally reduce what is migrated. Advanced Data Mapping may change how values or relationships are represented. Advanced Data Configure may adjust how selected data is handled during migration. Tailored Add-ons, Custom Add-ons, and Custom Service may introduce store-specific logic, transformations, or custom handling.

#### Add-on-related findings <a href="#add-on-related-findings" id="add-on-related-findings"></a>

When a finding relates to an Add-on, review whether the result matches the Add-on purpose and approved configuration.

Useful questions include:

* Was the result intentionally filtered, mapped, configured, or transformed?
* Does the target-store result match the approved setup?
* Does the result still support the expected customer or operational outcome?
* Is the finding an Add-on configuration issue, an expected outcome, or a separate migration concern?

Add-ons should not be used as a vague explanation for unclear differences. The reconciliation record should state which Add-on affected the result and how.

#### Custom Service-related findings <a href="#custom-service-related-findings" id="custom-service-related-findings"></a>

Custom Service results should be reconciled against the agreed custom scope, not against an assumption that the target store must duplicate every source-store behavior exactly.

For custom fields, app data, plugin data, module data, extension data, outside-system identifiers, Custom Platform handling, or custom migration logic, reconciliation should document:

* what source-store data or behavior was included;
* how it was expected to appear or function in the target store;
* how the result appears or functions after migration;
* whether the difference reflects approved custom handling or a new concern;
* whether the business accepts the result, needs correction, or needs monitoring.

Custom Service can support customization and complex migration requirements, but it does not remove the customer’s responsibility to review whether the final target-store outcome fits the intended business use.

### Build a Practical Reconciliation Record <a href="#build-a-practical-reconciliation-record" id="build-a-practical-reconciliation-record"></a>

Reconciliation works best when important findings are recorded in a simple, consistent format. The record should help reviewers understand the difference, assign the next action, and avoid reinterpreting the same issue repeatedly.

The record does not need to become a heavy internal process. It needs enough evidence to support a defensible launch decision.

#### Useful reconciliation fields <a href="#useful-reconciliation-fields" id="useful-reconciliation-fields"></a>

| Field            | Purpose                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Review area      | Identifies whether the finding affects products, customers, orders, content, SEO, integrations, configuration, or another area.                               |
| Source reference | Shows the source-store record, page, behavior, or sample being compared.                                                                                      |
| Target result    | Shows what appears or behaves differently in the target store.                                                                                                |
| Difference type  | Classifies the finding as expected platform difference, scope difference, mapping or transformation difference, configuration difference, or continuity risk. |
| Business impact  | Explains whether the finding affects customer clarity, purchasability, support, reporting, SEO, external systems, operations, or launch confidence.           |
| Decision         | Marks the finding as accepted, needs correction, needs monitoring, or launch-blocking.                                                                        |
| Owner            | Identifies who should review, correct, approve, escalate, or monitor the finding.                                                                             |
| Notes            | Captures context that prevents the same difference from being reinterpreted later.                                                                            |

A consistent record keeps reconciliation practical. It helps the business make decisions based on cause and impact, not repeated debate.

#### Useful decision labels <a href="#useful-decision-labels" id="useful-decision-labels"></a>

The same labels used in validation work can support reconciliation decisions:

* **Accepted difference**: the cause is understood, the business impact is acceptable, and no correction is required before launch.
* **Needs correction**: the result should be adjusted before launch or before the affected workflow is relied on.
* **Needs monitoring**: the result is acceptable for launch only if it is watched after launch.
* **Launch blocker**: the difference affects a critical outcome and should be resolved before launch.

These labels make findings easier to transfer into go-live readiness review.

### Common Reconciliation Mistakes to Avoid <a href="#common-reconciliation-mistakes-to-avoid" id="common-reconciliation-mistakes-to-avoid"></a>

Reconciliation becomes weaker when the team treats it as a mechanical comparison exercise. The most common mistakes are predictable and preventable.

#### Treating every mismatch as a defect <a href="#treating-every-mismatch-as-a-defect" id="treating-every-mismatch-as-a-defect"></a>

Some differences are expected because the Target Platform works differently or because the migration scope intentionally changed the result. Treating every mismatch as a defect slows the review and makes true risks harder to prioritize.

#### Treating every explanation as acceptance <a href="#treating-every-explanation-as-acceptance" id="treating-every-explanation-as-acceptance"></a>

Explaining a difference does not automatically make it acceptable. A difference can be understood and still be too damaging for launch.

#### Comparing records without checking behavior <a href="#comparing-records-without-checking-behavior" id="comparing-records-without-checking-behavior"></a>

A product, customer, order, page, coupon, or review may exist but still fail to support the business outcome. Reconciliation should review behavior, relationships, and practical usability, not only record presence.

#### Ignoring approved scope decisions <a href="#ignoring-approved-scope-decisions" id="ignoring-approved-scope-decisions"></a>

If scope decisions are not considered, reconciliation can become a debate about what should have moved. Approved scope, Add-ons, service decisions, and Custom Service requirements should guide how differences are interpreted.

#### Waiting until launch pressure is high <a href="#waiting-until-launch-pressure-is-high" id="waiting-until-launch-pressure-is-high"></a>

Reconciliation should begin during Demo Migration review and continue through broader validation. Waiting until go-live creates avoidable pressure and makes decisions less disciplined.

### How Reconciliation Supports Go-Live Readiness <a href="#how-reconciliation-supports-go-live-readiness" id="how-reconciliation-supports-go-live-readiness"></a>

Reconciliation gives the business a clearer basis for go-live judgment. A launch decision should not depend on finding zero differences. It should depend on whether important differences have been explained, corrected, accepted, assigned for monitoring, or treated as blockers.

Before launch, the business should be able to confirm that:

* critical findings have been reviewed by the right people;
* expected platform differences are documented and accepted;
* scope differences are understood and not mistaken for defects;
* mapping, transformation, and configuration differences have been accepted or corrected;
* true continuity risks have been resolved, assigned, or treated as blockers;
* unresolved items have clear ownership and monitoring plans;
* the remaining target-store result is trustworthy enough for real customers and business operations.

If the team cannot explain the most important differences, the migration result needs more review before go-live.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Reconciling migration results turns differences into informed judgment.

A migrated store does not need to be identical to the source store, but the business should understand why important differences exist and whether they affect the intended outcome. Matching counts can hide meaningful continuity problems, while count differences can be acceptable when they are expected, documented, and compatible with the Target Platform environment.

The strongest reconciliation process classifies findings by cause and business impact, reviews relationships as well as records, and turns every important difference into a clear decision: accepted, needs correction, needs monitoring, or launch-blocking.

Before treating migration results as ready for launch, review the most important differences with the people who understand the affected business area. If a difference is difficult to interpret, use Demo Migration evidence, validation findings, and Next-Cart support guidance to clarify whether it reflects expected Target Platform behavior, approved scope, Add-ons, Custom Service handling, configuration, or a true continuity risk.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the difference between validation and reconciliation?**

Validation checks whether the target store is usable, trustworthy, and acceptable for launch decisions. Reconciliation explains the differences found between the source store and target store so the business can decide whether each difference is expected, acceptable, correctable, monitorable, or launch-blocking.

**Do matching record counts mean the migration result is correct?**

No. Matching counts are useful evidence, but they do not prove that product behavior, customer continuity, order usability, SEO-sensitive paths, relationships, custom fields, or external-system dependencies still work as expected.

**Does a count mismatch always mean the migration failed?**

No. A mismatch may reflect expected Target Platform behavior, approved scope, filtering, mapping, transformation, configuration, or Custom Service handling. The mismatch should be explained and judged by business impact.

**When should a reconciliation finding block launch?**

A finding should block launch when it affects a critical customer, operational, SEO, reporting, support, fulfillment, or external-system outcome and cannot be accepted or safely monitored after launch.

**Should Add-on results still be reconciled?**

Yes. Add-ons make reconciliation more specific. The business should confirm that filtered, mapped, configured, or transformed results match the approved Add-on setup and still support the intended outcome.

**Does Custom Service remove the need for reconciliation?**

No. Custom Service can support complex handling, custom logic, Custom Platform work, or non-standard data requirements, but the customer still needs to verify whether the final target-store result fits the intended business use.
