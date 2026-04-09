# Defining Migration Scope: What Must Move and What Can Change

Migration scope is often defined too late and too loosely. Many teams start with a data list, a full export, or the phrase "everything needs to migrate." That sounds cautious, but it usually hides the harder planning work. The real question is not how much data exists. It is what the business must still be able to do after the move.

A store does not depend on record presence alone. It depends on products remaining commercially usable, browse paths remaining understandable, customer-facing expectations remaining credible, support teams still being able to use customer and order history, and continuity-sensitive pages still serving their purpose. If scope is defined only as totals, important losses can remain invisible until late validation.

A stronger scope definition starts with preserved business meaning. Before deciding what data belongs in scope, the business should decide what must remain true after launch.

### Start with Preserved Outcomes, Not with Export Categories

Useful scope planning begins with business outcomes such as:

* customers can still find products through the right browse paths
* products still support the intended buying decision
* order history remains usable enough for support and operations
* customer continuity still aligns with business expectations
* high-value pages remain reachable and relevant
* important relationships still support how the store works

These outcomes give the project a practical basis for deciding what must move, what can change, and what requires closer review.

Without that starting point, scope easily becomes unbounded. Teams include more and more data without deciding which elements are commercially critical, which ones are only nice to preserve, and which changes are acceptable if the core outcome remains intact.

### What Usually Belongs in Migration Scope

Scope usually starts with core entities, but it should not stop there. The obvious categories matter, yet the planning risk usually grows when teams fail to define the structures that make those entities usable.

Common core categories include:

* products
* customers
* orders
* categories
* reviews
* coupons
* taxes
* CMS pages
* blog content where traffic or conversion depends on it

Supporting structures often need explicit scope treatment as well, including:

* variants and options
* product and variant images
* attributes used for filtering or comparison
* customer addresses
* product relationships
* category logic and browse paths
* promotions that materially affect revenue
* SEO-sensitive URLs and landing paths
* operational metadata needed after launch
* extension-managed fields that shape storefront or support behavior

This is why a smaller store can still be high-scope. If its buying logic, discovery logic, customer continuity, or support workflows depend on layered structures, the migration scope is broader than the entity list alone suggests.

### Separate What Must Stay Equivalent from What Can Change

Not every element needs the same level of preservation. Scope becomes easier to control when it is divided into three planning groups.

#### What Must Move and Remain Functionally Equivalent

This is the highest-priority layer. It includes the data and behavior the business cannot afford to lose.

Examples often include:

* best-selling products with their real buying logic intact
* customer and order relationships needed for support
* category structures that drive browse intent
* revenue-critical promotions
* top landing pages that carry meaningful traffic or conversion value

These are the outcomes that should shape later review priorities.

#### What Must Move, but May Change in Representation

Some elements still need to be preserved even when the target platform expresses them differently.

Examples include:

* category or collection structure on a platform with a different navigation model
* segmentation logic on a platform with a different customer-group structure
* content presentation on a platform with a different CMS or template model
* field placement that changes while the underlying business use remains intact

These are not necessarily migration failures. They are planning decisions. The important question is whether the business meaning survives the target-platform difference.

#### What Can Change Without Harming the Business

Some differences are acceptable if the store still supports the same commercial and operational outcome.

Examples may include:

* internal administrative organization changing while workflows remain workable
* category naming adjustments that do not weaken browse intent
* content layout differences that do not damage reachability, clarity, or conversion
* presentation-level variation that does not change the customer decision path

This distinction matters because projects become much easier to govern once the business stops treating every difference as equally important.

### Scope Includes Behavior, Not Just Records

A store can migrate the expected totals and still fail in practice. Scope planning is stronger when it includes questions such as:

* Do variants and options still behave correctly?
* Do category pages still support discovery?
* Does order history still support support-team workflows?
* Do promotions still preserve the intended revenue logic?
* Do priority URLs and landing pages still support continuity?
* Do customer-facing pathways still align with expectations?

If those questions are not part of scope planning, the project can move a large amount of data and still deliver a weaker store.

### Relationship-Sensitive Areas Should Be Named Early

Some outcomes depend on connected records remaining usable together. Scope planning should identify these areas explicitly, especially when the business depends heavily on support history, browse logic, reviews, or coupon rules.

Typical examples include:

* orders needing the correct customers and products
* reviews needing the correct products and customers
* coupons needing the correct product or category context
* products needing meaningful category, manufacturer, or tax context

This does not require re-explaining all entity relationships in full here. It does require recognizing that some outcomes depend on correct connected behavior, not just on individual records being present.

### Third-Party Logic Often Expands Scope Quietly

Scope is often understated because teams inventory the visible storefront and overlook the fields, rules, and identifiers that make the storefront usable.

That hidden layer may include:

* custom product fields used for filtering, display, or merchandising
* extension-managed loyalty, review, subscription, or search behavior
* order metadata needed for support or reporting
* identifiers required by ERP, CRM, shipping, or automation systems
* plugin-driven collection, landing-page, or browse logic

If those elements materially affect revenue, discoverability, operations, or customer continuity, they belong in scope planning early. Otherwise the project may preserve the main entities while losing the business meaning attached to them. Where materially important meaning depends on custom logic, filtered rules, or outside-system identifiers, a more specialized handling path may be safer than assuming standard handling will preserve the required result.

### Selective Migration Is Valid Only When It Is Well Defined

A smaller scope can be a strong planning choice. Many businesses do not need every historical record to support launch readiness.

A selective scope may prioritize:

* essential products
* active customers
* recent orders
* high-value content
* the categories most important to launch readiness

But selective migration is not automatically simple. It becomes harder when the selection rule is precise, transformation-heavy, or likely to change the meaning of related records. A smaller scope can still carry high risk if excluded data affects connected behavior, support usability, or decision-making context.

That is why selective scope should be defined through business outcomes, not just through reduction targets.

### What a Strong Scope Definition Usually Makes Clear

A useful migration scope definition should clarify:

1. What the business cannot afford to lose after launch.
2. Which entities and content types are in scope.
3. Which supporting structures also need explicit planning.
4. Which platform-driven differences are understood and acceptable.
5. Which areas carry the highest business risk and must be reviewed first.

This level of clarity does not require perfect documentation. It requires disciplined judgment about what the store must still be able to do.

### Conclusion

Migration scope is not simply the answer to “what data do we want to move?” It is the answer to “what must still work after the move, which structures support that outcome, and which changes are acceptable?” When scope is defined through preserved outcomes, supporting structures, relationship-sensitive behavior, and intentional acceptance of target-platform differences, later planning becomes much easier to control.

Define scope around what the business must still be able to do after launch, then use a representative early sample to test whether those assumptions hold. If you need help deciding whether a requirement is standard scope, selective scope, or a sign that more specialized handling may be needed, Live Chat is a practical way to reduce ambiguity before scope creep becomes harder to control.

### FAQs

#### Does migration scope always mean migrating everything?

No. In many cases, a selective migration is valid if the business defines the scope clearly and understands the effect on connected behavior, support usability, and launch goals. The important issue is not whether every record moves. It is whether the chosen scope still supports the outcomes the business depends on.

#### What is the biggest mistake in scope planning?

One of the most common mistakes is defining scope as “everything” without deciding what actually needs to be preserved. That usually delays the harder judgment about non-negotiable continuity, acceptable change, and review priority. The result is broader activity with weaker control.

#### Are products, customers, and orders enough to define scope?

Not usually. Supporting structures such as variants, attributes, browse logic, images, promotions, URLs, operational metadata, and extension-managed behavior often carry the business meaning that makes the core entities usable. If they matter to revenue, discovery, support, or continuity, they belong in scope planning early.
