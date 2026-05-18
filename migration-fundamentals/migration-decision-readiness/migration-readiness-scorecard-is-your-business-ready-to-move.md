---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/EwOn3si2UOVRL65zVOMg/getting-started/quickstart-5
---

# Migration Readiness Scorecard: Is Your Business Ready to Move?

A business can have strong reasons to migrate and still be underprepared for a safe e-commerce data migration. The issue is rarely motivation. More often, the risk comes from unclear scope, limited visibility into important data, weak review ownership, or timing pressure that leaves too little room to test and correct the result.

A readiness scorecard helps turn those uncertainties into visible planning signals. It does not decide whether migration is possible. It helps the business understand whether the project is ready for deeper scoping, Demo Migration review, service planning, and launch preparation.

### What migration readiness means <a href="#what-migration-readiness-means" id="what-migration-readiness-means"></a>

Migration readiness is the degree to which the business can make sound migration decisions without relying too heavily on assumptions.

A ready business usually has:

* a clear reason for migration
* a defined migration scope
* enough visibility into important data, platform behavior, and business logic
* realistic expectations about what the Target Platform can support
* clear responsibility for review and launch decisions
* enough timing flexibility to validate results before go-live

Readiness does not mean every detail is already solved. It means the team understands the main risks well enough to make informed decisions and knows which areas still need proof.

### How to use the readiness scorecard <a href="#how-to-use-the-readiness-scorecard" id="how-to-use-the-readiness-scorecard"></a>

For each area, score the current business position:

* **0 points = Not ready**
* **1 point = Partly ready**
* **2 points = Ready**

The goal is not to achieve a perfect score before taking any action. The goal is to expose weak areas early enough to reduce migration risk.

A low score does not mean the project should stop. It means the business should clarify core assumptions before deeper commitments become harder to change.

### Migration readiness scorecard <a href="#migration-readiness-scorecard" id="migration-readiness-scorecard"></a>

| Readiness area                       | 0 points: Not ready                                                                    | 1 point: Partly ready                                                                               | 2 points: Ready                                                                                                                       |
| ------------------------------------ | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Reason for migration**             | The business reasons are vague or still being debated.                                 | There are reasons to move, but they are not yet prioritized.                                        | The reason for migration is specific, practical, and clearly understood.                                                              |
| **Migration scope**                  | It is unclear what must be migrated.                                                   | There is a partial scope list, but important decisions are still missing.                           | Must-have data and must-have outcomes are clearly defined.                                                                            |
| **Data awareness**                   | The team does not know where important data lives.                                     | Some important data is understood, but app-based, extension-based, or custom data is still unclear. | The business has identified native data, third-party data, custom fields, and outside-system dependencies.                            |
| **Catalog complexity**               | Variant, attribute, category, and product-relationship complexity is still unclear.    | Some catalog complexity drivers are understood, but they are not well documented.                   | The main catalog complexity drivers are documented and understood.                                                                    |
| **Order history requirements**       | The business does not know how much order history it needs or why.                     | Some order history needs are known, but the purpose is not fully clear.                             | Order history requirements are tied to customer service, reporting, operations, or compliance needs.                                  |
| **Customer continuity expectations** | There is no clear plan for account continuity or customer support impact.              | The team understands customer continuity matters, but the plan is still incomplete.                 | There is a practical plan for account continuity, customer communication, and likely support impact.                                  |
| **SEO and redirect responsibility**  | No one is clearly responsible for SEO continuity.                                      | Someone is responsible, but the redirect or review plan is incomplete.                              | The business has a defined redirect plan and a clear SEO review responsibility.                                                       |
| **Third-party logic visibility**     | Important app, plugin, module, extension, or outside-system logic has not been mapped. | Some third-party logic is understood, but important gaps remain.                                    | The business has identified third-party layers that affect buying behavior, discovery, customer continuity, operations, or reporting. |
| **Review responsibility**            | It is unclear who will judge whether the migration result is acceptable.               | Some reviewers are known, but review responsibility is still weak.                                  | The right people are identified and prepared to review the result by business area.                                                   |
| **Timing flexibility**               | The project leaves very little room for review or correction.                          | The timing allows some review, but pressure remains high.                                           | The timing leaves enough room to evaluate results and correct issues before launch.                                                   |

### How to interpret the score <a href="#how-to-interpret-the-score" id="how-to-interpret-the-score"></a>

#### 0 to 7 points: low readiness <a href="#id-0-to-7-points-low-readiness" id="id-0-to-7-points-low-readiness"></a>

The project still has major uncertainty.

This usually means the business has not clearly defined what must still work after launch, which data is most important, where third-party or custom logic lives, who will review the result, or what the timeline must realistically support.

The fastest improvement usually comes from reducing uncertainty, not from pushing harder on execution.

#### 8 to 14 points: moderate readiness <a href="#id-8-to-14-points-moderate-readiness" id="id-8-to-14-points-moderate-readiness"></a>

The project has a usable foundation, but important decisions are still incomplete.

This often means the business knows why it wants to migrate and understands some risks, but still needs stronger scope decisions, clearer review responsibility, better visibility into third-party data, or more realistic timing before deeper commitments are made.

Moderate readiness is common. It usually means the business can continue planning, but should avoid treating assumptions as confirmed facts.

#### 15 to 20 points: high readiness <a href="#id-15-to-20-points-high-readiness" id="id-15-to-20-points-high-readiness"></a>

The business is in a stronger position to move safely.

A high score does not guarantee a simple migration. It means the team is more likely to interpret Demo Migration results productively, recognize risk early, choose the right migration path, and define launch expectations in a way the business can actually review.

High readiness should still be tested against evidence. It should not replace validation.

### Where low readiness usually improves fastest

Low readiness usually improves fastest when the business focuses on a few must-protect outcomes instead of trying to define everything at once.

Start with the areas that cannot quietly fail:

* product buying behavior
* catalog navigation and search paths
* customer account continuity
* operationally important order history
* important content, landing pages, and SEO entry points
* app-driven, plugin-driven, module-driven, extension-driven, or outside-system business logic

Once those outcomes are clearer, the business can identify which areas need standard migration handling, which may need Add-ons, and which require Custom Service because they involve customization, modification, Custom Platform handling, custom migration logic adjustment, or third-party data requirements.

### How Demo Migration supports readiness <a href="#how-demo-migration-supports-readiness" id="how-demo-migration-supports-readiness"></a>

Demo Migration is useful because it gives the business visible evidence before broader execution.

A representative sample can help show:

* what transfers cleanly
* what changes more than expected
* where hidden complexity is concentrated
* whether the selected migration path still looks appropriate
* how much review work the final migration may require
* whether Add-ons or Custom Service should be discussed before launch pressure increases

This makes the scorecard more practical. Readiness should not depend only on internal confidence. It should improve as the team reviews real migration evidence.

### How Custom Platform and custom logic affect readiness <a href="#how-custom-platform-and-custom-logic-affect-readiness" id="how-custom-platform-and-custom-logic-affect-readiness"></a>

If a Custom Platform is involved, readiness depends more heavily on early clarification and expert review.

Custom Platform projects may involve non-standard data structures, custom fields, outside-system identifiers, third-party data, or custom migration logic adjustments. Those requirements should not be treated as ordinary platform differences. They need clearer expectations, stronger sample-based proof, and earlier discussion about whether Custom Service is required.

The same principle applies when a standard platform has heavily customized behavior. The platform name alone does not prove readiness. The business needs to understand how the actual store structure works.

### What a stronger readiness position looks like

A stronger readiness position usually means:

* the business can explain why migration is needed
* the must-protect outcomes are visible
* the most important data and logic are understood
* the highest-risk parts of the store are no longer hidden
* the right reviewers are identified
* the project has enough room for evidence-based correction
* the selected migration path is being judged against real complexity, not only convenience

This does not remove risk. It makes the risk easier to manage before launch decisions become urgent.

### Conclusion

Migration readiness is the difference between wanting migration and being prepared to guide it well.

A business is more ready when it can explain what migration is trying to improve, what cannot quietly fail after launch, where the most important data and logic live, and who will judge whether the result is acceptable. That is what makes scope, timing, migration path, and launch decisions more trustworthy.

Use this scorecard to expose uncertainty early. If important answers are still missing, Demo Migration and Live Chat can help turn vague confidence into clearer evidence about what the migration must prove before the project moves further.

### FAQs

**Can a business want migration and still have low readiness?**

Yes. Wanting change is not the same as being ready to migrate safely. A business can have strong reasons to move while still lacking the planning clarity needed to scope, review, and launch responsibly.

**What is the most important readiness question to answer first?**

Usually: what must still work after launch? That question helps the business define the outcomes that matter most and gives the rest of the planning work a clearer standard.

**Why is review responsibility part of readiness?**

Because migration quality depends on whether the right people can judge the result in the areas they understand best, such as buying behavior, customer continuity, operations, reporting, and SEO continuity.

**Does low readiness mean the project should stop?**

Not necessarily. It usually means the project needs more clarification before deeper commitments are made. The goal is to reduce uncertainty early, not delay the project for its own sake.

**Why is Demo Migration useful before the business feels fully ready?**

Demo Migration can expose hidden complexity and turn abstract planning into something visible. That often makes readiness easier to improve because the business can review real examples instead of relying only on assumptions.

**How does Custom Platform affect readiness?**

Custom Platform usually requires earlier clarification, stronger sample-based proof, and clearer expectations because the migration may involve non-standard structures, custom fields, outside-system identifiers, third-party data, or custom migration logic adjustment.
