# Reconciling Migration Results

Reconciliation is the part of the migration review that explains the differences between the Source Platform and the Target Platform.

A migration result should not be judged only by whether the two stores look identical or whether record totals match. Some differences are expected because platforms structure data, relationships, storefront behavior, URLs, and operational rules differently. Other differences come from intentional scope choices, accepted mapping decisions, Add-ons, Custom Service handling, or Target Platform limitations. A smaller group of differences may reveal real continuity problems that should be corrected before launch.

The purpose of reconciliation is to separate those outcomes clearly. It helps the business understand what changed, why it changed, whether the change is acceptable, and whether the difference should affect launch confidence.

### What reconciliation is trying to prove <a href="#what-reconciliation-is-trying-to-prove" id="what-reconciliation-is-trying-to-prove"></a>

Reconciliation is not the same as general validation.

Validation asks whether the Target Platform result is usable, trustworthy, and acceptable for the business. Reconciliation explains the differences found during that review. It turns mismatches, changed behavior, missing-looking details, and platform-specific differences into practical launch judgment.

#### The core reconciliation questions <a href="#the-core-reconciliation-questions" id="the-core-reconciliation-questions"></a>

A useful reconciliation process answers four questions:

* Which differences were expected?
* Which differences are explainable?
* Which differences are acceptable for the business outcome?
* Which differences reveal a real issue that should be corrected, escalated, or treated as a launch blocker?

Those questions make reconciliation more useful than a simple comparison table. The goal is not to force the Target Platform to look exactly like the Source Platform. The goal is to understand whether the Target Platform result preserves the business meaning that matters.

**Reconciliation is interpretation, not only detection**

Finding a difference is only the first step. The stronger review work is explaining the difference and deciding whether it is acceptable, correctable, or blocking.

### Why matching totals do not prove migration success <a href="#why-matching-totals-do-not-prove-migration-success" id="why-matching-totals-do-not-prove-migration-success"></a>

Matching record totals can be reassuring, but they do not prove that the migration result is launch-ready.

Products may exist but appear in weaker category paths. Customers may be present but not support the intended account experience. Orders may be migrated, but it is harder for support teams to interpret. Reviews, coupons, CMS Pages, Blog Posts, or product relationships may be present but disconnected from the way shoppers or teams need to use them.

#### What matching totals can hide <a href="#what-matching-totals-can-hide" id="what-matching-totals-can-hide"></a>

Matching totals can still hide problems such as:

* products attached to incomplete categories or weaker browsing paths
* variants, options, or attributes that no longer support the expected buying choice
* customers disconnected from meaningful order or account context
* orders that are present but difficult to interpret operationally
* reviews, coupons, CMS Pages, or Blog Posts that no longer support the intended storefront or customer journey
* SEO-sensitive pages that exist but no longer lead visitors to the right destination
* external identifiers or custom fields that no longer support connected systems

Record counts are useful evidence, but they are not enough. Reconciliation should use totals as one signal and then test the meaning behind the records.

### Why count differences do not always mean failure <a href="#why-count-differences-do-not-always-mean-failure" id="why-count-differences-do-not-always-mean-failure"></a>

A mismatch does not automatically mean the migration failed.

Some differences are normal when the Target Platform stores, organizes, or displays information differently from the Source Platform. Some are caused by intentional scope decisions. Some are the result of accepted mapping choices or supported Target Platform behavior. Others may reflect data that was excluded, transformed, merged, split, or represented differently for a valid business reason.

#### Acceptable difference depends on context <a href="#acceptable-difference-depends-on-context" id="acceptable-difference-depends-on-context"></a>

A difference may be acceptable when it is:

* caused by normal Target Platform behavior
* part of the approved migration scope
* caused by an intentional cleanup or simplification decision
* the result of a known mapping choice
* compatible with the expected customer, operational, SEO, or reporting outcome
* documented clearly enough for the business to understand after launch

A difference becomes risky when nobody can explain it, when it weakens a critical customer or business workflow, or when the team discovers it too late to decide calmly.

**The difference between variance and risk**

A variance is a difference. A risk is a difference that may weaken the business outcome. Reconciliation should prevent the team from treating every variance as a defect while still identifying the differences that actually matter.

### How to classify reconciliation findings <a href="#how-to-classify-reconciliation-findings" id="how-to-classify-reconciliation-findings"></a>

A strong reconciliation process classifies differences into a small number of practical categories.

The categories do not need to be complicated. They should help the business decide whether a finding is expected, acceptable, needs correction, or should block launch confidence.

#### Expected platform differences <a href="#expected-platform-differences" id="expected-platform-differences"></a>

These differences come from the way the Target Platform represents data, relationships, storefront behavior, URLs, account structures, or operational settings differently from the Source Platform.

Expected platform differences may be acceptable when the business outcome remains intact. They should still be documented so teams do not confuse them with defects during launch review.

#### Scope differences <a href="#scope-differences" id="scope-differences"></a>

Scope differences occur when data, content, behavior, or historical detail was intentionally excluded from the migration plan.

These differences should not be treated as surprises if the scope was defined clearly. They become a problem when the business assumes something will move, but the migration scope does not include it.

#### Mapping or transformation differences <a href="#mapping-or-transformation-differences" id="mapping-or-transformation-differences"></a>

Mapping or transformation differences occur when the source data's meaning must be represented differently in the Target Platform.

Some mapping differences are harmless. Others weaken product choice, filtering, customer segmentation, order interpretation, SEO continuity, or external-system behavior. When a mapping difference changes business meaning, it may need correction, Advanced Data Mapping, Advanced Data Configure, a Tailored Add-on, a Custom Add-on, or broader Custom Service handling, depending on the requirement.

#### True defects or continuity risks <a href="#true-defects-or-continuity-risks" id="true-defects-or-continuity-risks"></a>

These are findings that weaken the result in a way the business cannot accept.

They may affect revenue-critical products, important categories, customer trust, order usability, support workflows, SEO-sensitive destinations, external integrations, or launch readiness. These findings should be corrected, escalated, or treated as launch blockers depending on severity.

**Keep the classification business-facing**

A reconciliation category should help the business decide what to do next. If a label does not explain whether the finding is acceptable, correctable, or blocking, the label is not useful enough.

### Reconcile by business impact, not only by data type <a href="#reconcile-by-business-impact-not-only-by-data-type" id="reconcile-by-business-impact-not-only-by-data-type"></a>

Reconciliation should start with the areas where differences would matter most.

Reviewing every record at the same level of detail is rarely practical or useful. The better approach is to reconcile high-impact samples first, then expand the review where the findings show additional risk.

#### High-impact areas to reconcile first <a href="#high-impact-areas-to-reconcile-first" id="high-impact-areas-to-reconcile-first"></a>

Useful reconciliation samples often include:

* best-selling products and complex products
* top categories and high-value browse paths
* important customer scenarios
* representative orders with operational value
* SEO-sensitive pages and legacy paths
* promotions, coupons, pricing behavior, or discount rules that affect purchase decisions
* reviews or user-generated content that support trust
* data connected to apps, plugins, modules, extensions, or external systems
* custom fields, outside-system identifiers, or Custom Platform structures that affect business workflows

This approach gives the team a clearer view of launch risk. If the most important products, paths, customers, orders, and dependencies reconcile well, the business has stronger evidence than it would get from a broad but shallow review.

### Reconcile relationships, not just records <a href="#reconcile-relationships-not-just-records" id="reconcile-relationships-not-just-records"></a>

Many migration issues are relationship issues.

A record can exist and still fail to support the intended outcome if it is no longer connected to the right structure, page, customer, order, category, media, metadata, or external identifier. Reconciliation should therefore review connected behavior, not only isolated records.

#### Relationship questions to ask <a href="#relationship-questions-to-ask" id="relationship-questions-to-ask"></a>

Useful questions include:

* Do products still appear in the categories that support real browsing intent?
* Do variants, options, images, attributes, and pricing still support the expected product choice?
* Do customers still connect meaningfully to the right orders and account context?
* Do orders still reflect the right product, customer, status, payment, shipping, tax, and fulfillment context?
* Do reviews, coupons, CMS Pages, Blog Posts, and other supporting records still connect to the right storefront or operational use?
* Do priority URLs and page destinations still support traffic continuity?
* Do outside-system identifiers still support the systems that depend on them?

Relationship reconciliation is especially important when the Source Platform uses custom fields, extensions, app/plugin/module data, or Custom Platform structures. In those cases, the data may need more interpretation before the business can decide whether the Target Platform result is acceptable.

### How to reconcile Custom Platform or custom-service results <a href="#how-to-reconcile-custom-platform-or-custom-service-results" id="how-to-reconcile-custom-platform-or-custom-service-results"></a>

A migration involving a Custom Platform, custom fields, third-party data, outside-system identifiers, or custom migration logic adjustment usually requires more careful reconciliation.

The reason is not that every difference is automatically wrong. The reason is that standard expectations may not fully explain why the difference exists. The business may need to decide whether a result reflects an approved custom interpretation, a Target Platform limitation, a tailored Add-on requirement, a broader Custom Service requirement, or a true defect.

#### What to document for custom-sensitive findings <a href="#what-to-document-for-custom-sensitive-findings" id="what-to-document-for-custom-sensitive-findings"></a>

For custom-sensitive findings, reconciliation should document:

* what source behavior or structure the business expected to preserve
* how the result appears in the Target Platform
* whether the difference was approved during scope or service planning
* whether the difference affects customer experience, operations, reporting, SEO, or external-system behavior
* whether the result is acceptable, needs adjustment, or should be escalated

This documentation helps prevent custom requirements from being judged too casually. It also prevents the team from demanding exact duplication where the Target Platform requires a different representation.

**Custom Service does not remove validation responsibility**

Custom Service can support customization, modification, Custom Platform handling, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment, but the business still needs to review whether the final result fits the intended outcome.

### Build a practical reconciliation record <a href="#build-a-practical-reconciliation-record" id="build-a-practical-reconciliation-record"></a>

Reconciliation works best when findings are recorded in a simple, decision-ready format.

The record should help the team understand the difference quickly, assign the right next action, and avoid re-discussing the same issue repeatedly.

#### Useful reconciliation fields <a href="#useful-reconciliation-fields" id="useful-reconciliation-fields"></a>

A practical reconciliation record may include:

| Field            | Purpose                                                                                                                                 |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Review area      | Identifies whether the finding affects products, customers, orders, content, SEO, integrations, or another area.                        |
| Source reference | Shows the Source Platform record, page, behavior, or sample being compared.                                                             |
| Target result    | Shows what appears or behaves differently in the Target Platform.                                                                       |
| Difference type  | Classifies the finding as expected platform difference, scope difference, mapping or transformation difference, or continuity risk.     |
| Business impact  | Explains whether the finding affects customer clarity, purchasability, support, reporting, SEO, external systems, or launch confidence. |
| Decision         | Marks the finding as accepted, needs correction, needs monitoring, or launch-blocking.                                                  |
| Owner            | Identifies who should review, correct, approve, or monitor the finding.                                                                 |
| Notes            | Captures context that prevents the same difference from being reinterpreted later.                                                      |

This format keeps reconciliation practical. It does not require a heavy internal process, but it does require enough evidence for the launch decision to be defensible.

### Common reconciliation mistakes <a href="#common-reconciliation-mistakes" id="common-reconciliation-mistakes"></a>

Reconciliation becomes weaker when the team treats it as a mechanical comparison exercise.

The most common mistakes are predictable and preventable.

#### Mistake 1: Treating every mismatch as a defect <a href="#mistake-1-treating-every-mismatch-as-a-defect" id="mistake-1-treating-every-mismatch-as-a-defect"></a>

Some differences are expected. Treating every mismatch as a defect slows the review and makes real risks harder to prioritize.

#### Mistake 2: Treating every explanation as acceptance <a href="#mistake-2-treating-every-explanation-as-acceptance" id="mistake-2-treating-every-explanation-as-acceptance"></a>

Explaining a difference does not automatically make it acceptable. A difference can be understood and still be too damaging for launch.

#### Mistake 3: Comparing records without checking behavior <a href="#mistake-3-comparing-records-without-checking-behavior" id="mistake-3-comparing-records-without-checking-behavior"></a>

A product, customer, order, page, coupon, or review may exist but still fail to support the business outcome. Reconciliation should check behavior and relationships, not only record presence.

#### Mistake 4: Ignoring scope decisions <a href="#mistake-4-ignoring-scope-decisions" id="mistake-4-ignoring-scope-decisions"></a>

If scope was not defined clearly, reconciliation can become a debate about what should have moved. Strong scope planning makes reconciliation more objective.

#### Mistake 5: Waiting until launch pressure is high <a href="#mistake-5-waiting-until-launch-pressure-is-high" id="mistake-5-waiting-until-launch-pressure-is-high"></a>

Reconciliation should begin during Demo Migration review and continue through broader validation. Waiting until go-live creates avoidable stress and makes decisions less disciplined.

### How reconciliation supports go-live decisions <a href="#how-reconciliation-supports-go-live-decisions" id="how-reconciliation-supports-go-live-decisions"></a>

Reconciliation gives the business a clearer basis for launch judgment.

A launch decision should not depend on whether the team found zero differences. It should depend on whether the important differences have been explained, corrected, accepted, or clearly assigned for monitoring.

#### What should be true before launch <a href="#what-should-be-true-before-launch" id="what-should-be-true-before-launch"></a>

Before launch, the business should be able to say:

* critical findings have been reviewed by the right people
* expected platform differences are documented and accepted
* scope differences are understood and not mistaken for defects
* mapping or transformation differences have been accepted or corrected
* true continuity risks have been resolved or treated as blockers
* unresolved items have clear ownership and monitoring plans
* the remaining result is trustworthy enough for real customers and business operations

If the team cannot explain the most important differences, the migration result may need more review before go-live.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Reconciling migration results turns differences into informed judgment.

A migrated store does not need to be identical to the Source Platform, but the business should understand why important differences exist and whether they affect the intended outcome. Matching counts can miss meaningful continuity problems, while count differences can be acceptable when they are expected, documented, and compatible with the Target Platform environment.

The strongest reconciliation process classifies findings by cause and business impact, reviews relationships as well as records, and turns every important difference into a clear decision: accepted, needs correction, needs monitoring, or launch-blocking.

Before treating migration results as ready for go-live, review the most important differences with the people who understand the affected business area. If a difference is difficult to interpret, use Demo Migration evidence, validation findings, and Live Chat to clarify whether it reflects expected Target Platform behavior, scope choice, Custom Service handling, or a real continuity risk.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the difference between validation and reconciliation?**

Validation checks whether the Target Platform result is usable and acceptable. Reconciliation explains the differences found between the Source Platform and the Target Platform so the business can decide whether each difference is expected, acceptable, correctable, or blocking.

**Do matching record counts mean the migration result is correct?**

No. Matching counts are useful evidence, but they do not prove that product behavior, customer continuity, order usability, SEO-sensitive paths, relationships, or external-system dependencies still work as expected.

**Does a count mismatch always mean the migration failed?**

No. A mismatch may come from platform-normal behavior, approved scope decisions, intentional cleanup, mapping choices, or Target Platform representation. The important question is whether the difference is understood and acceptable for the business outcome.

**How should we decide whether a difference is acceptable?**

Classify the difference by cause and business impact. If it does not weaken customer experience, operations, SEO continuity, reporting, or launch confidence, it may be acceptable. If it affects a critical outcome, it should be corrected, escalated, or treated as a blocker.

**Are Custom Platform results harder to reconcile?**

They can be more sensitive because standard expectations may not fully explain custom structures, custom fields, third-party data, or outside-system identifiers. These findings should be reviewed against the approved scope and Custom Service expectations before they are accepted.

**Should reconciliation happen only after Full Migration?**

No. Reconciliation should begin during Demo Migration review when representative differences first appear. It should continue through broader validation and become more detailed as the business moves closer to go-live.
