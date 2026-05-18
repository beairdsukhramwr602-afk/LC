# Defining Migration Scope: What Must Move and What Can Change

Migration scope is often defined too late and too loosely. Many teams begin with a data export, a list of entities, or the assumption that everything should move. That can sound cautious, but it usually hides the more important planning question: what must the business still be able to do after the move?

A store does not depend on record presence alone. It depends on products remaining commercially usable, browse paths remaining understandable, customer and order history still supporting operations, and continuity-sensitive pages still serving their purpose. If scope is defined only by totals, important losses can remain invisible until late review.

A stronger scope definition starts with preserved business meaning. Before deciding what belongs in scope, the business should decide what must remain true after launch.

### Start with preserved outcomes, not export categories <a href="#start-with-preserved-outcomes-not-export-categories" id="start-with-preserved-outcomes-not-export-categories"></a>

Useful scope planning begins with business outcomes such as:

* customers can still find products through the right browse paths
* products still support the intended buying decision
* order history remains usable enough for support and operations
* customer continuity still aligns with business expectations
* high-value pages remain reachable and relevant
* important relationships still support how the store works

These outcomes give the project a practical basis for deciding what must move, what can change, and what requires closer review.

Without that starting point, scope easily becomes unbounded. Teams include more and more data without deciding which elements are commercially critical, which ones are useful but not essential, and which changes are acceptable if the core outcome remains intact.

#### Scope should connect "business meaning" to migration planning <a href="#scope-should-connect-business-meaning-to-migration-planning" id="scope-should-connect-business-meaning-to-migration-planning"></a>

A migration scope is not only a content inventory. It is a planning boundary. It should tell the project which data, structures, relationships, and continuity-sensitive elements need to be protected because they support real business use after launch.

This is why scope planning belongs before approach selection. A business cannot confidently choose a migration approach until it knows what must be preserved, where the Target Platform may represent data differently, and which requirements may need closer handling.

### What usually belongs in migration scope <a href="#what-usually-belongs-in-migration-scope" id="what-usually-belongs-in-migration-scope"></a>

Scope usually starts with core entities, but it should not stop there. The obvious categories matter, yet the planning risk usually grows when teams fail to define the structures that make those entities usable.

Common core categories include:

* products
* customers
* orders
* categories
* reviews
* coupons
* taxes
* CMS Pages
* Blog Posts where traffic, conversion, or continuity depends on them

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
* app, plugin, module, or extension-managed fields that shape storefront or support behavior

A smaller store can still have broad scope. If its buying logic, discovery logic, customer continuity, or support workflows depend on layered structures, the scope is larger than the entity list suggests.

#### Core data should not be separated from its supporting context <a href="#core-data-should-not-be-separated-from-its-supporting-context" id="core-data-should-not-be-separated-from-its-supporting-context"></a>

Products are not only product records. Customers are not only profile records. Orders are not only transaction records. Their value often depends on attributes, relationships, historical references, display logic, and operational context.

A scope plan should make those dependencies visible early. Otherwise, the project may appear simple at the entity level while carrying hidden complexity in the structures that make the migrated store usable.

### Separate what must remain equivalent from what can change <a href="#separate-what-must-remain-equivalent-from-what-can-change" id="separate-what-must-remain-equivalent-from-what-can-change"></a>

Not every element needs the same level of preservation. Scope becomes easier to control when it is divided into three planning groups.

#### What must move and remain functionally equivalent <a href="#what-must-move-and-remain-functionally-equivalent" id="what-must-move-and-remain-functionally-equivalent"></a>

This is the highest-priority layer. It includes the data and behavior that the business cannot afford to lose.

Examples often include:

* best-selling products with their real buying logic intact
* customer and order relationships needed for support
* category structures that drive browse intent
* revenue-critical promotions
* top landing pages that carry meaningful traffic or conversion value

These are the outcomes that should shape later review priorities.

#### What must move, but may change in representation <a href="#what-must-move-but-may-change-in-representation" id="what-must-move-but-may-change-in-representation"></a>

Some elements still need to be preserved even when the Target Platform expresses them differently.

Examples include:

* category or collection structure on a platform with a different navigation model
* segmentation logic on a platform with a different customer-group structure
* content presentation on a platform with a different CMS or template model
* field placement that changes while the underlying business use remains intact

These are not necessarily migration failures. They are planning decisions. The important question is whether the business meaning survives the Target Platform difference.

#### What can change without harming the business <a href="#what-can-change-without-harming-the-business" id="what-can-change-without-harming-the-business"></a>

Some differences are acceptable if the store still supports the same commercial and operational outcome.

Examples may include:

* internal administrative organization changing while workflows remain workable
* category naming adjustments that do not weaken browse intent
* content layout differences that do not damage reachability, clarity, or conversion
* presentation-level variation that does not change the customer decision path

This distinction matters because projects become much easier to govern once the business stops treating every difference as equally important.

### Scope includes behavior, not just records <a href="#scope-includes-behavior-not-just-records" id="scope-includes-behavior-not-just-records"></a>

A store can migrate the expected totals and still fail in practice. Scope planning is stronger when it includes questions such as:

* Do variants and options still behave correctly?
* Do category pages still support discovery?
* Does order history still support support-team workflows?
* Do promotions still preserve the intended revenue logic?
* Do priority URLs and landing pages still support continuity?
* Do customer-facing pathways still align with expectations?

If those questions are not part of scope planning, the project can move a large amount of data and still deliver a weaker store.

#### Behavior should be judged from the customer and business view <a href="#behavior-should-be-judged-from-the-customer-and-business-view" id="behavior-should-be-judged-from-the-customer-and-business-view"></a>

Scope should not be judged only by whether data appears in the Target Platform. It should also consider whether customers can still make buying decisions, staff can still support customers, and the business can still interpret migrated records correctly.

This keeps the scope definition practical. The goal is not to preserve every old platform behavior exactly. The goal is to define which outcomes need equivalent meaning, which differences are acceptable, and which areas need deeper review before the migration approach is chosen.

### Relationship-sensitive areas should be named early <a href="#relationship-sensitive-areas-should-be-named-early" id="relationship-sensitive-areas-should-be-named-early"></a>

Some outcomes depend on connected records remaining usable together. Scope planning should identify these areas explicitly, especially when the business depends heavily on support history, browse logic, reviews, or coupon rules.

Typical examples include:

* orders needing the correct customers and products
* reviews needing the correct products and customers
* coupons needing the correct product or category context
* products needing meaningful category, manufacturer, or tax context

This does not require re-explaining all entity relationships in full. It does require recognizing that some outcomes depend on connected behavior, not just on individual records being present.

### Third-party and custom logic can expand scope quietly <a href="#third-party-and-custom-logic-can-expand-scope-quietly" id="third-party-and-custom-logic-can-expand-scope-quietly"></a>

Scope is often understated because teams inventory the visible storefront and overlook the fields, rules, and identifiers that make the storefront usable.

That hidden layer may include:

* custom product fields used for filtering, display, or merchandising
* app, plugin, module, or extension-managed loyalty, review, subscription, or search behavior
* order metadata needed for support or reporting
* identifiers required by ERP, CRM, shipping, or automation systems
* custom collection, landing-page, or browse logic

If those elements materially affect revenue, discoverability, operations, or customer continuity, they belong in scope planning early. Otherwise, the project may preserve the main entities while losing the business meaning attached to them.

#### Custom handling should be identified before scope becomes fixed <a href="#custom-handling-should-be-identified-before-scope-becomes-fixed" id="custom-handling-should-be-identified-before-scope-becomes-fixed"></a>

When important meaning depends on custom logic, outside-system identifiers, third-party data, or behavior that exceeds standard service capability, the requirement should be identified before the project treats the scope as fixed.

That does not mean every custom field creates the same level of risk. It means the business should decide whether the field or rule is merely historical, operationally useful, or essential to the expected migration outcome. Requirements that need customization, modification, Custom Platform handling, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment belong under Custom Service review.

### Selective migration is valid only when it is well defined <a href="#selective-migration-is-valid-only-when-it-is-well-defined" id="selective-migration-is-valid-only-when-it-is-well-defined"></a>

A smaller scope can be a strong planning choice. Many businesses do not need every historical record to support launch readiness.

A selective scope may prioritize:

* essential products
* active customers
* recent orders
* high-value content
* categories most important to launch readiness

But selective migration is not automatically simple. It becomes harder when the selection rule is precise, transformation-heavy, or likely to change the meaning of related records. A smaller scope can still carry high risk if excluded data affects connected behavior, support usability, or decision-making context.

Selective scope should therefore be defined through business outcomes, not only through reduction targets.

#### Filtering decisions should be planned before execution <a href="#filtering-decisions-should-be-planned-before-execution" id="filtering-decisions-should-be-planned-before-execution"></a>

If the business wants only selected records to move, the selection logic should be planned before execution. Estimated entity counts are used for pricing and Entity Points Plan selection; they are not migration filters.

When filtering is needed, the scope plan should clarify which records should be moved, why they are selected, and whether the selection rule can be handled through the Data Filter Add-on or requires Custom Service because the requirement exceeds the Standard Add-on's capabilities.

### What a strong scope definition usually makes clear <a href="#what-a-strong-scope-definition-usually-makes-clear" id="what-a-strong-scope-definition-usually-makes-clear"></a>

A useful migration scope definition should clarify:

1. what the business cannot afford to lose after launch
2. which entities and content types are in scope
3. which supporting structures also need explicit planning
4. which platform-driven differences are understood and acceptable
5. which areas carry the highest business risk and must be reviewed first

This level of clarity does not require perfect documentation. It requires disciplined judgment about what the store must still be able to do.

#### Scope should prepare the next planning decisions <a href="#scope-should-prepare-the-next-planning-decisions" id="scope-should-prepare-the-next-planning-decisions"></a>

A good scope definition should make the next articles easier to use. It should help the business identify what makes the migration complex, which migration approach best fits the requirements, and what later validation must be demonstrated.

If the scope remains vague, every later planning decision becomes weaker. Complexity is harder to assess, service fit is harder to judge, and acceptance criteria become subjective.

### Conclusion

Migration scope is not simply the answer to “what data do we want to move?” It is the answer to “what must still work after the move, which structures support that outcome, and which changes are acceptable?” When scope is defined through preserved outcomes, supporting structures, relationship-sensitive behavior, and intentional acceptance of Target Platform differences, later planning becomes much easier to control.

Define scope around what the business must still be able to do after launch, then use a representative early sample to test whether those assumptions hold. If you need help deciding whether a requirement is standard scope, selective scope, or a sign that more specialized handling may be needed, Live Chat is a practical way to reduce ambiguity before scope creep becomes harder to control.

### FAQs

**Does migration scope always mean migrating everything?**

No. In many cases, a selective migration is valid if the business defines the scope clearly and understands the effect on connected behavior, support usability, and launch goals. The important issue is not whether every record moves. It is whether the chosen scope still supports the outcomes the business depends on.

**What is the biggest mistake in scope planning?**

One of the most common mistakes is defining scope as “everything” without deciding what actually needs to be preserved. That usually delays the harder judgment about non-negotiable continuity, acceptable change, and review priority. The result is broader activity with weaker control.

**Are products, customers, and orders enough to define scope?**

Not usually. Supporting structures such as variants, attributes, browse logic, images, promotions, URLs, operational metadata, and app, plugin, module, or extension-managed behavior often carry the business meaning that makes the core entities usable. If they matter to revenue, discovery, support, or continuity, they belong in scope planning early.

**When does scope planning point toward Custom Service?**

Scope planning points toward Custom Service when the scope cannot be described as standard data movement with available settings and supported behavior. Typical signals include Custom Platform handling, project-specific transformation rules, third-party or outside-system data, custom fields that must remain operationally meaningful, or selective migration rules that need service-side adjustment rather than normal filtering.
