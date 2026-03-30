# BigCommerce Data Model Differences

A BigCommerce migration succeeds when the target still preserves the store’s real buying logic after launch. This page focuses on the structural differences that most often change that outcome: how product choices are represented, how categories and browse paths shape discovery, how pricing and customer context affect the storefront, how custom data is carried, and how storefront scope changes when more than one storefront context matters.

BigCommerce can feel familiar at a high level because products, categories, customers, orders, and content still exist in recognizable forms. The migration challenge appears in how those elements are structured and how they work together in the storefront. A store can transfer records successfully while still changing selection flow, path clarity, pricing visibility, or merchandising behavior if the target model does not preserve the right relationships.

### The BigCommerce model in plain language

The BigCommerce model is easiest to understand through six structural ideas:

• products still sit at the center of the storefront, but product choice can be expressed in more than one way

• categories often carry more browse and merchandising meaning than teams expect

• pricing can change by customer or storefront context, so base price alone is not always the real commercial outcome

• custom data can live in more than one layer, and those layers do not all behave the same way in the storefront

• storefront scope can change when the business uses more than one storefront context

• extensions, theme behavior, and custom logic often carry meaning that is not obvious from exported catalog data alone

These differences matter because BigCommerce migrations are often won or lost at the point where data structure meets storefront behavior.

### Products still depend on a clear sellable outcome

BigCommerce does not solve product complexity automatically. It expects the business to define clearly what the customer is actually buying.

That matters because stores often come from source platforms where product meaning is spread across attributes, variations, add-ons, custom fields, or extension-driven logic that has grown over time. In BigCommerce, the target has to preserve the final purchasable outcome in a way that customers can still understand.

The first practical question is simple: which customer choices create a genuinely different sellable product, and which choices are only adjustments, personalization, or supporting inputs? That translation pressure becomes even stronger when the source platform is a Custom Cart, because source-side option systems often do not map cleanly into standard target structures without more deliberate classification.

If the answer is not clear, product migration can look successful while the product page becomes harder to use.

### Variants and modifiers change what product choice means

One of the most important BigCommerce model differences is the distinction between variants and modifiers.

Variants represent true product combinations. They are the structural choice when the customer is selecting among real sellable versions of the product. That usually affects SKU logic, inventory behavior, pricing, or the actual product being purchased.

Modifiers represent product customizations or additional inputs that do not need to become full variant combinations. They are often a better fit for personalization, optional upgrades, or customer-provided information that shapes the order without creating a separate inventory-tracked product.

This is a major migration decision because many source stores mix these two ideas together. A source platform may treat all customer-facing options as if they belong in one broad option system, even when some are true sellable combinations and others are only adjustments.

In practical migration terms, this changes five things:

• how many real purchasable combinations the target needs to preserve

• whether inventory belongs at the option-combination level or not

• whether price changes are tied to a true product variation or an optional adjustment

• whether the product page remains clear enough for confident selection

• whether downstream order meaning still reflects what the customer actually chose

A BigCommerce migration therefore has to separate product choice into the right structural buckets. If too many customizations are forced into variant logic, the catalog can become heavier and harder to manage. If too many true variants are treated as modifiers, the storefront can lose important product clarity, pricing logic, or inventory meaning.

This is why BigCommerce product migration is not only about moving options. It is about preserving the logic behind the choice.

### Shared options and repeated product logic can improve consistency, but they do not remove modeling work

BigCommerce can reuse option structures across products, which is useful when multiple products share similar choice logic. That can help a business create more consistent catalog behavior across a large range.

But shared structure does not eliminate the need to define the sellable outcome correctly. Repeating the same option pattern across many products only helps if the underlying model is already right. If the wrong option structure is copied widely, the migration can spread confusion faster instead of reducing it.

This is especially important for catalogs where many products look similar operationally but still differ in what should count as a true variant, a modifier, or a storefront-only informational field.

### Categories change more than navigation

BigCommerce category structure often carries more meaning than teams initially assume. Categories are not only a filing system for products. In many stores, they shape browsing logic, menu organization, landing behavior, filtering expectations, internal merchandising, and customer understanding of the catalog.

That means category migration is not only about whether the right products end up in the right groups. It is about whether the storefront still helps customers move through the catalog in a way that matches how they shop.

In practice, category structure affects:

• which browse paths customers use before they search

• how product families are understood in relation to one another

• how navigation menus and merchandising blocks are organized

• how category pages support discovery, filtering, and conversion

• how old paths map to new storefront journeys after launch

A source store may use categories lightly, heavily, or inconsistently. BigCommerce usually rewards more deliberate category thinking. That can be a strength, but it also means the migration has to preserve not only product-to-category assignment, but the commercial purpose behind the category tree.

Another important difference is that products can often belong to more than one category context. That creates flexibility, but it also means the team has to decide which category paths are operationally useful and which ones only add clutter.

### Pricing is not always a product-level fact

A common migration mistake is treating price as if it exists only at product level. In BigCommerce, the real commercial price a customer sees may depend on more than the base catalog record.

Pricing can change through customer groups, price lists, and storefront-specific context. That means the target model may need to preserve multiple pricing realities at once.

This becomes especially important in cases such as:

• wholesale-sensitive selling

• customer-group-specific pricing

• negotiated commercial relationships

• regional or storefront-specific pricing differences

• catalogs where list price is not the main price customers actually experience

In migration terms, that changes the question from “did the price import?” to “did the right customer see the right price in the right storefront context?”

This is one of the clearest ways a BigCommerce migration can appear correct in a spreadsheet while behaving incorrectly in the storefront.

### Customer groups change how commercial context is expressed

BigCommerce customer records do not only represent identity. In many stores, they also influence pricing visibility, buying conditions, or access expectations.

That means customer migration is not only about preserving names, addresses, and order history. It can also affect:

• which pricing rules should apply

• which storefront context the customer should experience

• how the business segments audiences commercially

• how support and account teams interpret the customer record after launch

This does not make BigCommerce identical to a full B2B account-structure model, but it does mean customer context can still carry important commercial meaning. Where the source store uses customer-group logic heavily, that structure has to be reviewed as part of the target model rather than assumed from account presence alone.

### Custom fields and metafields do different jobs

BigCommerce can carry specialized data through more than one custom-data layer, and those layers do not have the same purpose.

Custom fields are often used for additional product information that needs to appear directly in the storefront product page. They are useful when the business needs structured descriptive information that customers should see as part of the buying decision.

Metafields are broader and can carry specialized information across different objects, including products, variants, categories, brands, and other resources. They are often more useful when the data supports integrations, custom storefront behavior, internal logic, or structured metadata that does not belong in the visible product description by default.

This distinction matters because source stores often contain a large amount of “extra data” without a clear classification. During migration, teams may assume that all extra fields are equivalent. They are not.

The practical modeling questions are:

• which extra information must be visible to customers

• which extra information only supports internal or extension-driven behavior

• which data needs to exist at product level versus variant level

• which fields support discovery, filtering, merchandising, or trust signals

• which data can weaken safely and which cannot

If that classification is not done early, the target can end up populated with custom data that is technically present but commercially useless.

### Variant-level meaning can still matter even when the product looks simple

Another place where BigCommerce migrations often drift is variant-level meaning. Some stores appear simple at product level but carry crucial differences at the variant level, including images, pricing, descriptive attributes, or selection logic.

This is important because a product that looks correct at parent level can still fail the real storefront test if the right variant-level information is not preserved where the customer needs it.

That risk is especially visible when:

• color or size variants need distinct images

• variant-level pricing changes customer choice

• variant-level details affect buyability or trust

• filtering, comparison, or merchandising logic depends on information below the parent product level

A BigCommerce migration therefore needs to check not only that products exist, but that the right level of product meaning survives where it matters commercially.

### Storefront scope becomes part of the data model when Multi-Storefront matters

BigCommerce can support multiple storefront contexts, and when a business uses that capability, storefront structure becomes part of the target data model rather than only an operating setup.

That affects migration meaning because the business may need to decide:

• which products belong in which storefront context

• which categories or content are shared versus distinct

• which prices should vary by storefront

• which domains and entry paths should land in which storefront experience

• which customer groups or audiences belong to which storefront logic

A business may think of this primarily as a deployment choice, but in migration planning it is also a modeling choice. The same catalog may support multiple storefronts differently, and the target needs to preserve the intended commercial boundaries clearly enough to validate.

This is one of the places where BigCommerce can become significantly more complex than a simple single-store migration, even though the platform remains hosted.

### Extensions and theme logic often carry hidden model meaning

Many BigCommerce stores depend on search tools, merchandising extensions, custom theme components, widgets, scripts, or integration logic that are not obvious from product exports or customer records alone.

That means part of the real data model may live outside what looks like the core catalog.

For example, important business meaning may sit inside:

• custom product badges or trust indicators

• search and filtering behavior

• merchandising or recommendation logic

• content blocks tied to product or category context

• pricing displays shaped by storefront logic

• structured data used by extensions to influence the customer journey

This is why a BigCommerce migration should not treat the storefront layer as decoration. In many real stores, the storefront logic is where the catalog becomes commercially usable.

### The combined effect: structured commerce depends on clearer classification

The biggest BigCommerce data-model lesson is that the platform rewards cleaner classification.

The migration has to classify:

• which choices are true variants

• which are modifiers or custom inputs

• which category paths are commercially useful

• which prices belong to which customer or storefront context

• which custom data should be visible and which should remain structural

• which storefront differences belong inside one context and which justify separate storefronts

That does not make BigCommerce narrow. It makes it more dependent on clear modeling decisions.

When those decisions are strong, BigCommerce can provide a highly usable hosted storefront. When they are weak, the target can become technically complete but commercially less coherent.

### What these differences change in practice

In practical migration terms, BigCommerce data-model differences usually change six things.

#### 1. Product mapping becomes choice-logic mapping

The important question is no longer only how many products moved. It is whether the target still expresses the right buyable combinations, customizations, and customer inputs.

#### 2. Category migration becomes browse-logic migration

The important question is no longer only whether the right category names exist. It is whether customers can still discover products through useful browse paths.

#### 3. Price migration becomes context migration

The important question is no longer only whether a price field imported. It is whether the right customers and storefronts see the right commercial terms.

#### 4. Extra fields become a classification problem

The important question is no longer only whether custom data transferred. It is whether that data sits in the right layer and still supports the intended storefront or operational outcome.

#### 5. Storefront structure becomes a model decision

The important question is no longer only whether a second storefront can exist. It is whether the business has defined how commercial meaning is divided or shared across storefront contexts.

#### 6. Validation has to prove selection, discovery, and pricing behavior

The important question is no longer only whether data exists. It is whether customers can reach the right products, make the right selections, see the right prices, and move through the storefront in the intended way.

### Conclusion

BigCommerce data-model differences matter most where the business depends on storefront behavior that has to remain commercially clear after migration. Variants versus modifiers, category-led discovery, pricing context, customer-group behavior, custom fields and metafields, and storefront scope all change how migrated data should be interpreted. The platform does not only ask whether records can be transferred. It asks whether those records still work together in ways customers and internal teams can trust.

That is why this page matters beyond catalog mechanics. BigCommerce can look familiar at record level while still requiring more disciplined classification than many source stores ever used. Product choices have to stay buyable, categories have to stay navigable, prices have to stay contextually correct, and supporting data has to keep shaping the storefront in the right places. When the source is a Custom Cart, that translation challenge usually becomes even more pronounced because the source-side model may carry meaning in structures that are not standard enough to map cleanly without extra review.

A useful next step is to test these model differences through a representative Demo Migration built around choice-heavy products, browse-sensitive category paths, pricing-sensitive customer contexts, and any non-standard source-side structures most likely to distort translation into BigCommerce. If those outcomes still look uncertain, Live Chat can help determine whether the issue is mainly a modeling question, a validation question, or a sign that Managed Migration Service or Custom Migration Service is the safer path.

### FAQs

<details>

<summary><strong>What is the biggest BigCommerce data-model difference to watch during migration?</strong></summary>

Usually it is the distinction between true product variants and modifiers. That decision changes how customers make choices, how pricing behaves, how inventory meaning is preserved, and whether the product page remains clear after migration.

</details>

<details>

<summary><strong>Why do categories matter so much in BigCommerce migrations?</strong></summary>

Because categories often shape browse behavior, navigation structure, merchandising paths, and customer understanding of the catalog. A category tree can be technically complete while still weakening discovery if the commercial logic behind it is not preserved.

</details>

<details>

<summary><strong>Are custom fields and metafields basically the same thing in BigCommerce?</strong></summary>

No. They can both carry extra information, but they do not do the same job. One common migration challenge is deciding which data should appear directly in the storefront and which should remain structural, internal, or extension-driven.

</details>

<details>

<summary><strong>Why can a BigCommerce migration look correct in the data but still fail in the storefront?</strong></summary>

Because the most important model differences often affect behavior rather than counts. Products can exist while product choice becomes confusing, category records can exist while browse logic weakens, and pricing data can exist while the wrong commercial outcome appears to the wrong customer.

</details>
