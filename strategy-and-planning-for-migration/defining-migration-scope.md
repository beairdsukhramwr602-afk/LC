# Defining Migration Scope: What Must Move and What Can Change

Migration scope is often defined too late and too loosely. Many teams begin with an export list, a set of entity counts, or the assumption that everything should move. That can feel cautious, but it usually avoids the more important planning question: what must the business still be able to do after the move?

A store does not depend on record presence alone. It depends on products remaining commercially usable, browse paths remaining understandable, customer and order history still supporting operations, and continuity-sensitive pages still serving their purpose. If scope is defined only by totals, important losses can remain invisible until late review.

A stronger scope definition starts with preserved business meaning. Before deciding what belongs in scope, the business should decide what must remain true after launch, which differences are acceptable, and which areas need closer review before execution begins.

### Scope Is a Planning Boundary, Not Just a Data List <a href="#scope-is-a-planning-boundary-not-just-a-data-list" id="scope-is-a-planning-boundary-not-just-a-data-list"></a>

Migration scope should define the boundary of what the project is responsible for preserving, changing, excluding, or reviewing. That boundary is broader than a list of record types because useful store data usually depends on relationships, behavior, and business context.

A practical scope definition should clarify:

* which business outcomes must remain usable after launch;
* which entities, content types, and supporting structures are included;
* which records or historical ranges can be excluded intentionally;
* which platform differences are acceptable if the business meaning survives;
* which areas require sample review before the migration approach is considered safe;
* which owners should confirm whether the result is acceptable.

This makes scope a governance tool. It gives the project a basis for deciding what must move, what can change, what can be cleaned up, and what should not be treated as a launch requirement.

### Start With Preserved Outcomes <a href="#start-with-preserved-outcomes" id="start-with-preserved-outcomes"></a>

Useful scope planning begins with outcomes rather than export categories. The most important question is not simply whether products, customers, orders, categories, or content can be transferred. The question is whether the migrated store can still support the activities that matter.

Common preserved outcomes include:

| Outcome area            | What scope must protect                                   | Example review focus                                                         |
| ----------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Product buying behavior | Customers can choose and purchase the intended products   | Variants, options, prices, stock meaning, images, product status             |
| Catalog discovery       | Customers can find products through expected browse paths | Categories, collections, filters, search fields, landing pages               |
| Customer continuity     | Staff can understand customer context after launch        | Accounts, addresses, order references, consent state, segmentation relevance |
| Operational usability   | Internal teams can continue key workflows                 | Order history, fulfillment references, support notes, external identifiers   |
| Commercial continuity   | Revenue-critical logic remains intentional                | Promotions, coupons, price rules, tax context, priority customer groups      |
| SEO continuity          | Important pages remain reachable and purposeful           | URLs, redirects, metadata, content pages, high-value landing paths           |

Starting with outcomes prevents scope from becoming either too broad or too shallow. It helps the business identify which data is essential, which data is useful but non-critical, and which historical or obsolete information can be excluded without damaging launch readiness.

### Identify Core Entities and Their Supporting Structures <a href="#identify-core-entities-and-their-supporting-structures" id="identify-core-entities-and-their-supporting-structures"></a>

Scope usually starts with core entities, but it should not stop there. Core records often carry value only when their supporting structures move with enough meaning intact.

Common core categories include:

* products;
* customers;
* orders;
* categories or collections;
* reviews;
* coupons and promotions;
* taxes and related configuration references;
* CMS Pages;
* Blog Posts where traffic, conversion, or continuity depends on them.

Supporting structures often need explicit scope treatment as well:

* variants and product options;
* product and variant images;
* product attributes used for filtering, comparison, or merchandising;
* customer addresses and account status;
* product relationships, bundles, grouped items, or cross-sell logic;
* category assignment rules and browse paths;
* promotion eligibility rules and coupon conditions;
* SEO-sensitive URLs, metadata, redirects, and landing paths;
* operational metadata needed for reporting, support, fulfillment, or external systems;
* app, plugin, module, or extension-managed fields that shape storefront or admin behavior.

A smaller store can still have broad scope if its commercial behavior depends on layered structures. A larger store can have a narrower launch scope if the business intentionally excludes unused historical data and defines what must remain usable.

### Separate Must-Preserve, Transformable, Optional, and Excluded Scope <a href="#separate-must-preserve-transformable-optional-and-excluded-scope" id="separate-must-preserve-transformable-optional-and-excluded-scope"></a>

Scope is easier to manage when every major data area is assigned a planning status. Not all included data needs identical preservation, and not all excluded data represents a loss.

| Scope classification | Meaning                                                                      | Example                                                                             |
| -------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Must preserve        | The business outcome cannot safely change                                    | Top-selling products must keep their buying logic and order meaning intact          |
| Can transform        | The structure may change if the business meaning remains acceptable          | Category trees may become collections or navigation groups on the Target Platform   |
| Can clean up         | Data should be corrected or consolidated before or during migration planning | Duplicate attribute values can be normalized before they affect filtering review    |
| Can exclude          | Data is not required for launch or ongoing operations                        | Obsolete products, expired campaigns, old test customers, unused content drafts     |
| Needs special review | The requirement may exceed standard platform-to-platform handling            | Custom fields, outside-system identifiers, extension-owned data, unusual rule logic |

This classification protects the project from treating every difference as a defect. Some differences are acceptable. Some are improvements. Others are genuine continuity risks. Scope planning should make that distinction visible before review begins.

### Define What Must Remain Functionally Equivalent <a href="#define-what-must-remain-functionally-equivalent" id="define-what-must-remain-functionally-equivalent"></a>

The highest-priority scope layer contains data and behavior that must remain functionally equivalent after migration. Functional equivalence does not always mean identical structure. It means the migrated store still supports the same practical business outcome.

Examples often include:

* best-selling products with their real buying logic intact;
* customer and order relationships needed for support;
* category or collection structures that drive browse intent;
* revenue-critical promotions and pricing rules;
* customer groups or segments that affect pricing, access, communication, or service workflows;
* high-value pages that carry meaningful traffic, conversion, or brand credibility.

These areas should shape sample selection and validation priority. They should not be reviewed only after all data has moved. If a must-preserve area behaves differently in the Target Platform, the team needs an early decision about whether the difference is acceptable, transformable, or a scope issue.

### Decide What Can Change in Representation <a href="#decide-what-can-change-in-representation" id="decide-what-can-change-in-representation"></a>

Some elements still need to be preserved even when the Target Platform expresses them differently. A direct one-to-one structure may not exist, especially when moving between platforms with different catalog, customer, content, or promotion models.

Common examples include:

* category logic represented as collections, menus, tags, or landing pages;
* customer groups represented as segments, tags, lists, or rules;
* product attributes represented as fields, metafields, specifications, option values, or filter sources;
* CMS content represented through a different page builder, theme, or block model;
* promotion logic represented through a different rule engine or discount model.

These changes are not automatically failures. They are scope decisions. The important question is whether the business meaning survives the new representation. If customers can still find, evaluate, and purchase products correctly, a structural difference may be acceptable. If the difference changes pricing, eligibility, product discovery, support usability, or reporting meaning, it needs closer review.

### Name Relationship-Sensitive Areas Early <a href="#name-relationship-sensitive-areas-early" id="name-relationship-sensitive-areas-early"></a>

Many scope issues are caused by relationships, not by missing records. Products, customers, orders, reviews, coupons, and content often depend on other records to remain meaningful.

Relationship-sensitive examples include:

* orders needing the correct customer and product references;
* reviews needing the correct products, customers, rating state, and moderation status;
* coupons needing the correct product, category, customer, or date conditions;
* products needing meaningful category, manufacturer, tax, inventory, and media context;
* customer records needing addresses, order history, consent state, or account status to remain interpretable;
* content pages needing URL, redirect, image, metadata, and navigation context to remain useful.

Scope planning does not need to describe every relationship in technical depth. That level belongs in deeper data-entity analysis. But the scope plan should identify where connected meaning matters. Otherwise, a project can preserve expected record counts while losing the context that makes those records usable.

### Treat Third-Party and Custom Logic as Scope Signals <a href="#treat-third-party-and-custom-logic-as-scope-signals" id="treat-third-party-and-custom-logic-as-scope-signals"></a>

Scope is often understated because teams inventory visible storefront content but overlook the hidden fields, rules, identifiers, and extension-owned data that make the store work.

That hidden layer may include:

* custom product fields used for display, filtering, merchandising, or reporting;
* app, plugin, module, or extension-managed loyalty, review, subscription, search, or personalization behavior;
* order metadata required for support, refunds, fulfillment, or reporting;
* identifiers required by ERP, CRM, shipping, tax, marketing automation, or marketplace systems;
* custom collection, landing-page, or browse logic;
* business rules that live outside the platform but influence store behavior.

If those elements materially affect revenue, discoverability, operations, or customer continuity, they belong in scope planning early. They should not appear for the first time during final validation.

Important custom logic should also be classified by business value. Some fields are only historical. Some are useful for administration. Others are essential to customer experience, pricing, fulfillment, or external-system continuity. Only the essential and operationally meaningful parts should expand the scope.

### Use Selective Migration Carefully <a href="#use-selective-migration-carefully" id="use-selective-migration-carefully"></a>

Selective migration can be a strong planning choice. Many businesses do not need every historical record to support launch readiness.

A selective scope may prioritize:

* active products and current catalog structures;
* active customers;
* recent orders needed for support or accounting reference;
* high-value CMS Pages and Blog Posts;
* priority categories, collections, URLs, and landing pages;
* records needed by external systems or post-launch workflows.

But selective migration is not automatically simple. It becomes more complex when the selection rule is precise, relationship-sensitive, or likely to change the meaning of connected records. For example, migrating recent orders without the related customers, products, coupons, or fulfillment references may reduce the practical value of the order history.

Selective scope should therefore be defined through business outcomes, not only through reduction targets.

### Plan Filtering Rules Before Execution <a href="#plan-filtering-rules-before-execution" id="plan-filtering-rules-before-execution"></a>

Filtering decisions should be planned before execution. Estimated entity counts help with planning and Entity Points Plan selection, but they do not automatically define which records should move.

A filtering decision should clarify:

* which records should be included;
* which records should be excluded;
* why the selection rule supports the business objective;
* whether the rule affects connected data;
* whether the selection can be validated after migration;
* who accepts the consequences of excluded history.

Some filtering requirements are simple, such as excluding inactive products or moving only orders after a specific date. Others are more complex, especially when they depend on multiple conditions, custom fields, third-party status values, external identifiers, or relationship rules. When filtering needs exceed standard selection logic, the requirement may need review through the Data Filter Add-on or a Custom Service path.

### Document Acceptable Change Before Review Begins <a href="#document-acceptable-change-before-review-begins" id="document-acceptable-change-before-review-begins"></a>

A scope plan should not only define what is included. It should also define what differences are acceptable.

Acceptable changes may include:

* internal administrative organization changing while workflows remain workable;
* category naming or grouping adjustments that do not weaken browse intent;
* content layout differences that do not damage reachability, clarity, or conversion;
* platform-native field placement replacing an older custom field arrangement;
* retired products or outdated content being intentionally excluded;
* old campaign rules being rebuilt rather than migrated exactly.

Documenting acceptable change reduces review friction. Reviewers can distinguish between expected Target Platform differences and true scope failures. Without this distinction, every difference can become a late-stage dispute.

### Turn Scope Into Review Priorities <a href="#turn-scope-into-review-priorities" id="turn-scope-into-review-priorities"></a>

Scope should prepare the next planning decisions. It should help the business identify what makes the migration complex, which approach fits the requirement, and what validation must prove.

A useful review priority list includes:

| Priority level | Scope area                                                              | Review purpose                                     |
| -------------- | ----------------------------------------------------------------------- | -------------------------------------------------- |
| Critical       | Revenue, checkout, support, SEO, external-system continuity             | Confirm that launch-blocking outcomes still work   |
| High           | Catalog discovery, customer continuity, priority content                | Confirm that important workflows remain usable     |
| Medium         | Administrative convenience, historical reference, internal organization | Confirm that changes are understood and acceptable |
| Low            | Obsolete, duplicate, or unused data                                     | Confirm intentional exclusion or cleanup           |

This avoids equal-weight review, where low-value historical data consumes as much attention as launch-critical behavior. Scope should tell reviewers where to spend the most time and what level of proof is needed.

### What a Strong Scope Definition Should Include <a href="#what-a-strong-scope-definition-should-include" id="what-a-strong-scope-definition-should-include"></a>

A strong migration scope definition should make the following points clear:

1. what the business cannot afford to lose after launch;
2. which entities and content types are included;
3. which supporting structures and relationships need explicit treatment;
4. which data can be transformed, cleaned up, excluded, or deferred;
5. which platform differences are understood and acceptable;
6. which areas require special review or custom handling;
7. which records should be selected or filtered and why;
8. which review priorities prove that the scope has been met.

This level of clarity does not require perfect documentation. It requires disciplined judgment about what the migrated store must still be able to do.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Migration scope is not simply the answer to “what data should move?” It is the answer to “what must still work after the move, which structures support that outcome, and which changes are acceptable?” When scope is defined through preserved outcomes, supporting structures, relationship-sensitive behavior, selective migration rules, and intentional acceptance of Target Platform differences, later planning becomes easier to control.

Define scope around what the business must still be able to do after launch. Then use that scope to decide where complexity is concentrated, which migration approach is appropriate, and what validation must prove before the store is considered ready.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Does migration scope always mean migrating everything?**

No. Selective migration can be valid if the business defines the scope clearly and understands the effect on connected behavior, support usability, reporting, customer continuity, and launch goals. The important issue is not whether every record moves. It is whether the chosen scope still supports the outcomes the business depends on.

**What is the biggest mistake in scope planning?**

One of the most common mistakes is defining scope as “everything” without deciding what actually needs to be preserved. That delays the harder judgment about non-negotiable continuity, acceptable change, exclusions, cleanup, and review priority.

**Are products, customers, and orders enough to define scope?**

Not usually. Supporting structures such as variants, attributes, browse logic, images, promotions, URLs, operational metadata, customer addresses, order references, and app, plugin, module, or extension-managed behavior often carry the business meaning that makes the core entities usable.

**When does scope planning point toward Custom Service?**

Scope planning points toward Custom Service when the required outcome depends on customization, modification, Custom Platform handling, Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, third-party data, custom fields, outside-system identifiers, or other requirements that exceed standard service capability.
