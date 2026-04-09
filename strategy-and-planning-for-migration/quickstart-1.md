---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/EwOn3si2UOVRL65zVOMg/data-processing-and-behavior/quickstart-1
---

# Planning Migration Validation and Acceptance Criteria

Migration validation is weakest when it begins after the data has already moved. By that stage, the project is usually under more pressure, more people are involved, and the cost of ambiguity is higher. That is why validation should be planned before execution, not improvised afterward.

A strong validation plan defines what the business needs to confirm, who is responsible for checking it, how representative review will be performed, and what acceptable actually means before launch pressure begins to distort judgment.

This article is about designing that review framework in advance. It is not about running post-migration checks step by step. Its purpose is to help the business decide how it will judge success before execution makes that judgment harder.

### Validation Planning Is About Defining Acceptable Before the Project Gets Rushed

A migration project does not succeed because data appears in the target store. It succeeds when the migrated store still supports the outcomes the business depends on.

That means validation planning should begin with questions such as:

* what must still work after launch
* what differences are acceptable
* what differences would create a real business problem
* who is responsible for checking each outcome area
* what must be confirmed before the result can be accepted

This is what acceptance criteria are for. They turn review from a vague reaction into a structured decision process.

### Why Record Counts Are Not Enough

Record counts are useful, but they are only a surface check.

A store can show the expected totals for products, customers, and orders and still fail in important ways. Products may no longer support the intended buying behavior. Category pages may weaken discovery. Order history may become harder to use. Customer continuity may no longer match expectations. Connected records may no longer preserve the same business meaning.

That is why a validation plan should be built around business outcomes and usable behavior, not only around entity presence.

### Acceptance Criteria Should Be Outcome-Based

The strongest acceptance criteria describe what the business must still be able to do after migration.

That usually includes outcomes such as:

* products can still be bought in the intended way
* customers can still discover products through the right browse paths
* customer continuity still behaves as expected
* order history remains usable enough for support and operations
* priority landing pages remain reachable and credible
* business-critical extension-driven logic still supports the required result

This is far more useful than saying only that products, customers, or orders are present. A good acceptance criterion defines what usable means, not just what visible means.

### What Should Be Included in a Validation Plan

A practical validation plan usually makes five things clear:

1. Validation areas
2. Acceptance criteria
3. Validation responsibility
4. Review sample
5. Escalation threshold

Without these elements, review often becomes inconsistent and overly subjective.

### Organize Validation by Outcome Area

Validation becomes much clearer when it is divided into the business areas that matter most.

#### Product Validation Criteria

Product validation usually needs to confirm that:

* variants and options still behave correctly
* pricing remains understandable
* important media and product information still support purchase confidence
* product attributes still support discovery where they matter
* extension-driven product behavior still supports the intended result

A useful standard is not just "the product exists." It is "the product still supports the intended customer buying decision."

#### Category and Discovery Validation Criteria

Category and browse validation usually needs to confirm that:

* customers can still reach products through the expected pathways
* category logic still supports discovery
* filtering or attribute-driven navigation still behaves acceptably
* key browse entry points still make sense as landing pages or discovery paths

A category page can remain visible and still fail if it no longer supports the browse intent the business depends on.

#### Customer Continuity Validation Criteria

Customer validation usually needs to confirm that:

* continuity behaves as expected
* customer records remain usable
* customer-linked history still supports the intended experience
* segmentation or review ownership remains acceptable where relevant

This matters because customer continuity is rarely only about record presence. It is about whether the customer-facing and support-facing experience still aligns with business expectations.

#### Order-History Validation Criteria

Order validation usually needs to confirm that:

* order records are usable for support and operations
* product references inside orders remain understandable
* customer references remain meaningful
* discounts, taxes, or other critical order context still support intended use

This area becomes especially important when order history matters to support, reconciliation, reporting, or post-purchase workflows.

#### SEO and Page Continuity Validation Criteria

SEO-sensitive validation usually needs to confirm that:

* priority pages remain reachable
* important page intent is preserved
* key landing pages remain credible and useful
* high-value paths still support continuity after migration

This does not require reviewing every page equally. It requires a clear priority set for pages that materially affect traffic, discovery, or conversion.

#### Relationship-Sensitive Validation Criteria

Some outcomes depend on connected records remaining usable together.

Validation in this area usually needs to confirm that:

* orders still relate meaningfully to the correct customers and products
* reviews still connect to the right products and customers
* products still preserve meaningful category, tax, or manufacturer context
* coupons still preserve the intended relationship to products or categories where relevant

This is one of the clearest examples of why counts alone are not enough.

### Use Representative Samples, Not Random Checks

Validation is stronger when it tests the records and pathways most likely to expose real risk.

A useful review sample usually includes:

* best-selling products with meaningful complexity
* category paths that matter most to discovery
* representative customers and orders
* pages with strong traffic or conversion value
* records affected by apps, plugins, extensions, or outside systems

Random samples can help with surface checking. Representative samples are much better for judging whether the migration is truly acceptable.

### Validation Responsibility Should Be Clear Before Review Begins

A common cause of weak validation is that everyone assumes someone else will judge the result.

A stronger plan makes clear who is responsible for checking each area, including:

* product behavior
* category and browse logic
* customer continuity
* order usability
* SEO-critical pages
* final launch-readiness review

Different outcome areas require different kinds of business knowledge. The person best placed to judge product purchase behavior may not be the same person best placed to judge support usability or page continuity.

### Acceptance Criteria Should Distinguish Acceptable Difference from Unacceptable Loss

Not every change is a failure.

A strong validation plan should make clear which differences are:

* acceptable platform-driven differences
* manageable presentation differences
* meaningful degradations that must be corrected
* business-critical failures that should block acceptance

Migration almost always introduces some differences. The project becomes easier to govern when the team already knows which ones are understood and acceptable, and which ones are not.

### Validation Planning Should Begin Before Execution Commitment

The strongest time to define acceptance criteria is before the project commits to broader execution.

That is because a representative early sample often reveals:

* what the business will need to review carefully
* what kinds of differences are likely to appear
* where the hardest pass-fail judgments will be
* whether current review capacity is strong enough for the project’s risk level

This makes validation planning much more realistic. Instead of guessing what to check later, the business can shape its criteria around behavior it already understands.

### Freshness Alignment Does Not Replace Validation

If the source store continues changing during the project, data freshness must still be managed before launch. But freshness alignment and outcome validation are separate decisions.

The project still needs to confirm that:

* the latest important data is present as expected
* the highest-risk behaviors still work acceptably
* the completed target store is ready in the ways that matter most

Freshness supports launch readiness. It does not prove acceptable business behavior by itself.

### Common Validation Planning Mistakes

Common mistakes include:

* waiting until late review to define what acceptable means
* using totals as the main proof of success
* letting review stay too broad or too vague
* failing to assign validation responsibility by outcome area
* treating every difference as equally important
* failing to distinguish acceptable change from real business loss
* assuming an early positive sample removes the need for disciplined final review

These mistakes usually slow the project down at the exact point where clarity is most needed.

### What a Strong Acceptance Decision Looks Like

A strong acceptance decision usually means:

* the agreed validation areas were reviewed
* representative samples showed that critical outcomes still work
* known differences were classified intentionally
* unresolved issues were either corrected or consciously accepted
* the people responsible for final review can explain why the result is acceptable

That is much stronger than saying only that the migration "looks good."

### Conclusion

Planning migration validation and acceptance criteria is really about defining how the business will judge success before execution pressure makes that judgment harder. The strongest validation plans are built around business outcomes, representative samples, clear responsibility, and a disciplined distinction between acceptable difference and unacceptable loss.

Define your validation areas before the project reaches full execution pressure, then write acceptance criteria in terms of what the business must still be able to do after the move. If you need help deciding whether a difference is an accepted platform change, a mapping issue, or a real blocker, Live Chat is a practical way to reduce ambiguity before review becomes rushed.

### FAQs

#### What is the difference between validation and acceptance criteria?

Validation is the review process. Acceptance criteria are the standards used to decide whether the result is acceptable.

#### Why are record counts not enough to approve a migration?

Because a store can show the expected totals and still fail in product behavior, category discovery, customer continuity, order usability, relationship integrity, or page continuity. Counts are useful, but they are not proof that the store still works correctly.

#### When should acceptance criteria be defined?

Before broader execution pressure takes over. The business should define them early enough that review areas, responsible reviewers, and pass-fail expectations are already clear when the project reaches heavier execution and launch preparation.

#### Who should be responsible for validation?

Validation responsibility should be assigned by outcome area. Different people may need to review product behavior, order usability, customer continuity, page continuity, or final launch readiness depending on who best understands each area.
