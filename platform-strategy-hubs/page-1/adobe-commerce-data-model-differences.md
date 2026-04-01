# Adobe Commerce Data Model Differences

A migration into Adobe Commerce succeeds when the target still preserves the storefront behavior and operating meaning that made the original store usable before the move. This page focuses on the structural differences that most often change that outcome: how products are configured, how configurable behavior differs from customizable options, how company accounts and shared catalogs shape customer context, how layered scope affects storefront meaning, how native route control influences continuity, and how surrounding services or extension-driven storefront logic can carry meaning beyond the visible catalog.

Adobe Commerce is structured enough to represent sophisticated commerce models clearly, but that structure does not remove the need for disciplined translation. The most important shift is that migration meaning often depends less on whether the target can hold the records and more on whether the target can still express what those records do in practice. That changes what “product,” “customer,” “catalog visibility,” “scope,” “route continuity,” and even “the same storefront” mean in migration planning.

### The Adobe Commerce data model in plain language

The Adobe Commerce model is easiest to understand through eight structural ideas:

* Products still sit at the center of the sellable catalog.
* Configurable behavior is used for customer-selectable product states.
* Customizable options support customer-entered or product-specific purchase customization rather than core configurable state.
* Customer context can be shaped more deeply through company-account and shared-catalog structures.
* Catalog visibility can be conditional rather than universally identical for every customer.
* Website, store, and store-view layers can change what one commerce environment means in practice.
* Native URL rewrite behavior makes route continuity part of the target model.
* Surrounding ecosystem or service layers can materially affect how the real store behaves.

These differences matter because a migration can recreate products, customers, categories, and content successfully while still changing how customers choose, access, discover, and interpret the storefront.

A useful way to read this model is to ask not only what each structure stores, but what job it performs in the storefront. That is where the migration meaning becomes visible. The same data can still exist after launch while doing the wrong job in practice if it has been translated into the wrong part of the Adobe Commerce model.

### Products still sit at the center of Adobe Commerce’s sellable model

Adobe Commerce builds store meaning around products, but those products often depend on surrounding structures to become usable in the storefront. A product is not only a row in the catalog. It is the center point through which configurable behavior, customizable options, account context, visibility rules, scope, routes, images, and surrounding storefront logic are all interpreted together.

This matters because a source platform may spread product meaning across multiple layers. In Adobe Commerce, those layers still come back to the product and the structures attached to it. That can make the target feel more structured, but it also means migration planning has to decide clearly which pieces of meaning belong in the core product model and which belong in supporting product, account, or storefront logic.

A store can therefore migrate products successfully while still weakening storefront usability if the product record remains present but the surrounding configurable behavior, customization, catalog visibility, route structure, or ecosystem-driven meaning no longer supports how customers actually buy.

In practical terms, this means the Adobe Commerce product record often acts as a convergence point. If source-side meaning is scattered across plugins, fields, catalogs, visibility rules, or storefront behavior, the migration has to decide how that meaning should be reassembled around the product in a way customers can still understand.

### Configurable products change what a product can become in the storefront

One of the most important Adobe Commerce data-model differences is how it uses configurable product behavior. Configurable structures are not simply descriptive product data. They are central to how the customer selects among defined product states.

In migration terms, that makes configurable behavior important because it influences what the product becomes at the point of selection. When size, color, style, or another defined variation matters to the final purchasable result, those differences usually need to be understood through configurable logic rather than through descriptive fields or surrounding custom storefront behavior.

This changes migration planning in two ways.

First, product translation becomes a state-modeling problem. The business has to decide which differences should remain selectable defined states and which ones should not.

Second, Adobe Commerce requires clearer separation between buyable product state and surrounding product information. If that separation is weak, the target can preserve records while confusing the storefront.

A good way to think about this is simple: in Adobe Commerce, configurable behavior should support the decisions the customer is expected to make in order to buy the correct version of the product, not merely hold information that existed somewhere in the source store.

The operating consequence matters too. When configurable behavior is modeled cleanly, the storefront becomes easier to understand, merchandise, and validate. When it is modeled poorly, the product page may still function, but internal teams often lose confidence in what the customer is actually choosing and why the resulting buying behavior no longer feels trustworthy.

### Customizable options are not the same as configurable state

A common migration mistake is to treat customizable options as if they perform the same job as configurable product behavior. They do not.

In Adobe Commerce, customizable options usually support product-specific customer-entered or product-level purchasing customization rather than the core selectable state of the product itself. In storefront terms, this means they usually support how a customer modifies or specifies part of the purchase without changing the product into a different defined variant.

This matters in migration because some source platforms blur the line between “what the customer selects as the product state” and “what the customer adds, enters, or customizes as part of the purchase.” Adobe Commerce makes that distinction more visible.

If customizable options are used where configurable behavior should have been used, the storefront can lose clarity. If configurable behavior is used where customization should have stayed a supporting purchase layer, the storefront can become harder to understand and harder to govern.

That is why the Adobe Commerce model often forces a more disciplined translation of product meaning. The business has to decide what belongs in defined selectable state and what belongs in supporting customization.

### Customer context can become a structural part of storefront meaning

One of the most important Adobe Commerce differences is that customer context can materially shape what the storefront means. Company-account logic and shared-catalog structures can influence who sees what, under which conditions, and with what commercial expectations attached.

This changes migration meaning because customers are not always just account records. In some businesses, the more important question is what kind of customer context the storefront believes it is serving and what visibility, pricing, or catalog conditions follow from that. That can affect what products are visible, how the catalog should be interpreted, and how different customer types move through the store.

A migration can therefore preserve customer records successfully while still weakening commercial accuracy if the customer-context model no longer reflects the intended storefront logic after launch.

The operating consequence matters here too. If customer context loses its meaning, internal teams often become less certain about why a customer is seeing a specific catalog, pricing posture, or storefront experience. That uncertainty can weaken trust in the migrated store even when the accounts themselves are present.

### Shared catalogs change catalog visibility from a universal assumption into a controlled condition

Adobe Commerce can support shared-catalog logic, which means catalog visibility is not always a single universal storefront condition. This matters in migration planning because the catalog is not only a list of products. It can also be a controlled commercial layer shaped by customer context.

That changes how the business should think about product presence. A product can exist in the target and still fail commercially if the wrong customers see it, if the right customers do not see it, or if the visibility conditions no longer match the intended buying model.

This is one of the clearest reasons Adobe Commerce migrations must be judged by more than product transfer alone. The real question is not only what was moved. It is how that moved product is exposed, interpreted, and sold in the target environment.

### Scope changes what one commerce environment can mean

Adobe Commerce can support layered scope structures, and that makes scope assignment part of the model rather than an afterthought. Products, categories, routes, language context, and storefront behavior may need to be understood through website, store, or store-view logic rather than through one flat storefront assumption.

This matters because a scope decision changes more than deployment. It changes content ownership, route continuity, catalog behavior, customer experience, and validation scope. A business can use one Adobe Commerce environment while still needing more than one storefront context. That makes scope part of how migration meaning is reconstructed after the move.

The central lesson is that scope should be treated as part of the future-state model, not simply as a technical capability that can be enabled later without changing how the storefront is interpreted.

In practical terms, this means the business is not only deciding whether multiple contexts can exist. It is deciding how many distinct storefront experiences it is willing to govern, and whether those experiences will preserve clarity or create more operational ambiguity after launch.

### Native URL rewrites change continuity expectations structurally

Adobe Commerce supports native URL rewrite behavior, which means route continuity belongs directly inside the platform model rather than only inside a separate redirect solution. That changes migration planning because continuity becomes tied to how the target wants products, categories, and content pages to appear after launch.

This matters because a migration can recreate content successfully while still weakening discovery and trust if the storefront routes no longer support the same commercial journeys. URL rewrites therefore affect more than search visibility. They affect how customers interpret and trust the structure of the store.

In migration terms, that means route planning belongs in the target model itself, not only in a late redirect checklist.

The practical consequence is that route structure becomes part of storefront meaning. If customers, search engines, or internal teams can no longer predict how important routes should behave, the storefront may still be technically valid while becoming less coherent and less trusted over time.

### Surrounding ecosystem and service layers may sit outside the core catalog but still define the real store

One of the most important Adobe Commerce truths is that the real store may depend on more than native catalog and account structures alone. Search services, extensions, integrations, and surrounding experience layers can all influence what the customer sees and how internal teams operate the storefront.

This means migration planning has to distinguish between the native Adobe Commerce model and the actual business model of the store. In some cases, the difference is small. In others, much of the commercial meaning lives in those supporting layers rather than in products, customers, categories, or scope alone.

That distinction matters especially when the source platform is a Custom Cart. Source-side structures may not map neatly into Adobe Commerce’s native model, which increases the translation burden. The target may still be viable, but the business has to decide what meaning belongs in native Adobe Commerce structures and what would still depend on tailored handling or surrounding service reconstruction.

This is one of the clearest reasons Adobe Commerce migrations must be judged by more than core data transfer. The real storefront may depend on supporting layers strongly enough that preserving the catalog alone tells only part of the truth.

### The combined effect: stronger native structure, but not automatic migration simplicity

The biggest mistake in Adobe Commerce modeling is assuming that because the platform is more structured and more capable, the migration can preserve any source structure without forcing clearer decisions.

The reality is more specific.

Adobe Commerce can support meaningful control over products, configurable behavior, customization, customer context, catalog visibility, scope, routes, and surrounding commerce behavior. At the same time, that structure often pushes more responsibility onto the business to define what the storefront should actually become.

That combination creates a distinct migration challenge. The target can become more governable and more explicit than many lighter systems, but only if the business is willing to translate source meaning into structures that Adobe Commerce can still support clearly and maintainably over time.

The key point is that Adobe Commerce gives the business a stronger target language, but it does not decide on the business’s behalf which parts of the source structure deserve to remain. That is where model translation becomes a strategic task rather than only a technical one.

### What these differences change in practice

In practical migration terms, Adobe Commerce data-model differences usually change seven things.

#### 1. Product migration becomes product-meaning translation

The important question is no longer only how many products moved. It is whether products still support the correct storefront understanding and buyable outcome.

#### 2. Defined product state and supporting customization must stay separate

The important question is no longer only whether configurable structures and customizable options both exist. It is whether the storefront still separates what customers choose from what customers customize.

#### 3. Customer context becomes more than account transfer

The important question is no longer only whether customers migrated. It is whether the right account and catalog conditions still hold after launch.

#### 4. Catalog visibility becomes part of commercial meaning

The important question is no longer only whether products exist. It is whether the right customers see the right catalog conditions in the intended way.

#### 5. Scope becomes part of the future-state architecture

The important question is no longer only whether the platform can support layered contexts. It is whether the business has defined how those contexts should differ and what each one should own.

#### 6. Route continuity becomes part of storefront meaning

The important question is no longer only whether rewrites exist. It is whether they still support the storefront paths customers and search engines rely on.

#### 7. Ecosystem-driven behavior becomes part of structural success

The important question is no longer only whether services or extensions still exist. It is whether their real storefront and operational outcomes still hold after launch.

### Conclusion

Adobe Commerce data-model differences matter most where the business depends on structured customer context, product logic, catalog control, route continuity, and future-state governance rather than only on basic catalog transfer. Products, configurable behavior, customizable options, customer-account structures, catalog visibility, scope, routes, and surrounding ecosystem logic all change how migration meaning should be interpreted.

The platform does not make migration simpler by default. It makes different kinds of structure possible. That is why Adobe Commerce migrations should be planned around preserved customer behavior, account meaning, product understanding, visibility logic, route continuity, and future-state governability rather than around transferred records alone.

A useful next step is to test these model differences through a representative Demo Migration built around configurable products, purchase paths where configurable and customizable behavior both matter, customer-context scenarios, scope-sensitive storefront behavior, route-sensitive paths, and any source-side complexity most likely to create translation pressure. Those areas usually reveal more about whether the target model is really working than broad low-risk product transfer ever could.

If those parts of the store still behave unclearly after the first review, the issue is usually not only technical execution. It is a target-model question that needs clearer decisions before broader migration is treated as safe. That is where early interpretation becomes especially valuable. A focused Live Chat discussion around those representative outcomes can help distinguish between a target that is already structurally viable, a target that mainly needs more guided execution through Managed Migration Service, and a source-to-target translation problem that may justify Custom Migration Service, especially when the source is a Custom Cart.

### FAQs

#### What is the biggest data-model difference in an Adobe Commerce migration?

One of the biggest differences is that Adobe Commerce forces a clearer distinction between defined product state, supporting purchase customization, customer context, and controlled catalog visibility. That changes how migration meaning should be interpreted after the move.

#### Why do configurable products and customizable options matter so much in Adobe Commerce?

Because they do different jobs. Configurable behavior supports customer choice among defined product states, while customizable options support supporting purchase customization. When those jobs are confused, the storefront can become harder to shop and harder to govern.

#### Why do customer context and shared catalogs matter in the data model?

Because they change storefront meaning, not only account administration. They can affect visibility, catalog conditions, and how different customers experience the store after launch.

#### Why can an Adobe Commerce store migrate successfully but still feel weaker after launch?

Because the records can move while the storefront meaning changes. Product behavior, account context, visibility logic, route continuity, scope structure, or ecosystem-driven outcomes can all weaken even when the underlying data looks complete.
