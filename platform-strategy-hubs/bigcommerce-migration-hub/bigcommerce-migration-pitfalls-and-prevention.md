# BigCommerce Migration Pitfalls and Prevention

BigCommerce migration pitfalls often appear when the Target Platform looks orderly but the store’s commercial behavior has not been proven. Product records may exist, categories may load, customer groups may be present, redirects may resolve, and content may appear complete while customers still lose the ability to choose the right product, see the intended price, browse the right storefront, or reach the right destination.

Prevention should focus on the areas where BigCommerce formalizes business meaning: product options, variants, variant options, modifiers, customer groups, price lists, bulk pricing, channels, storefront assignments, category trees, redirects, custom fields, metafields, apps, and external identifiers. A safe migration review should confirm that these structures preserve buying behavior and operational meaning, not only that records are present.

### Pitfall 1: Treating Product Presence as Product-Choice Continuity <a href="#pitfall-1-treating-product-presence-as-product-choice-continuity" id="pitfall-1-treating-product-presence-as-product-choice-continuity"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

Products appear in BigCommerce, but the buying path no longer reflects how customers selected, priced, personalized, or fulfilled products in the original store.

This often happens when a product family depends on option combinations, variant-specific SKUs, modifier-style selections, personalization inputs, app-supported configuration, add-on choices, or custom product fields. BigCommerce can represent structured product behavior, but the migration has to clarify which choices are true variants, which choices are modifiers, which values belong in custom fields or metafields, and which behavior depends on surrounding apps or Custom Service handling.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* Product validation focuses on whether products exist rather than whether customers can choose the intended outcome.
* High-value products still have unresolved variant, option, modifier, or personalization rules.
* Product choices that affect SKU, image, price, stock, fulfillment, or reporting are reviewed only visually.
* Demo Migration samples avoid the most complex product families.
* App-supported product behavior is assumed to migrate as ordinary product data.

#### Prevention <a href="#prevention" id="prevention"></a>

Classify product-choice meaning before approving the product catalog. Separate sellable variants, modifier-style choices, custom fields, metafields, app-owned behavior, and external workflow dependencies. Use real product families where product options affect price, stock, image, SKU, fulfillment, or customer understanding.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

Select a high-revenue configurable or option-heavy product and test the complete path: product page, option selection, price response, SKU or inventory behavior, cart result, checkout readiness, and fulfillment implication.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

Customers can choose and purchase the intended product outcome in BigCommerce without losing important buying, pricing, inventory, personalization, or fulfillment meaning.

### Pitfall 2: Preserving Categories While Weakening Storefront Discovery <a href="#pitfall-2-preserving-categories-while-weakening-storefront-discovery" id="pitfall-2-preserving-categories-while-weakening-storefront-discovery"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Categories migrate, but customers can no longer discover products through the intended paths.

BigCommerce category and category tree structures can carry navigation, merchandising, search, SEO, campaign, and storefront-discovery meaning. A category tree may look complete while product assignments, menu placement, landing-page context, storefront visibility, or channel-specific behavior becomes weaker.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* Category review is based mainly on record count or category names.
* Important category paths are not ranked by revenue, traffic, SEO value, campaign use, or customer intent.
* Products assigned to several categories or storefronts are reviewed only once.
* Menu, landing-page, or merchandising context is treated as theme work rather than migration evidence.
* Redirects from old category paths land on generic destinations.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Treat categories as customer-path assets. Identify the category paths that influence revenue, search demand, campaign traffic, support navigation, or buyer intent. Confirm that product assignments, category depth, storefront visibility, navigation placement, and destination quality still support the intended journey.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Review several high-value category paths from entry point to product selection. Include category hierarchy, product assignment, storefront/channel visibility, landing-page meaning, filters or sorting expectations, and redirect destination quality.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Priority category paths still guide customers toward the right products and preserve the commercial purpose of the original discovery structure.

### Pitfall 3: Reviewing Customer Groups and Price Lists in Isolation <a href="#pitfall-3-reviewing-customer-groups-and-price-lists-in-isolation" id="pitfall-3-reviewing-customer-groups-and-price-lists-in-isolation"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Customer groups, price lists, or bulk pricing rules appear configured, but the wrong customer sees the wrong commercial result.

This risk is common for wholesale, reseller, loyalty, regional, B2B, account-specific, or negotiated-pricing models. A migrated price field can be technically present while the intended pricing outcome fails because customer assignment, price-list relationship, product scope, storefront context, discount behavior, or bulk-pricing logic is incomplete.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* Customer groups are checked by name rather than by pricing outcome.
* Price lists are reviewed separately from products, customers, and storefront context.
* Wholesale, reseller, loyalty, or special-pricing customers are absent from the sample set.
* Bulk pricing is checked as product data rather than customer-facing behavior.
* The business cannot explain which buyers should see which pricing conditions after migration.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate pricing as a relationship between customer groups, price lists, products, discounts, storefront context, and business rules. Include sensitive customer and product combinations before launch. If pricing depends on external systems, app logic, or unsupported custom rules, classify the work before approval rather than treating it as ordinary data cleanup.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Test a retail customer, a wholesale customer, and a special-pricing customer against the same high-value product. Confirm product visibility, list price, adjusted price, bulk price, cart result, and checkout readiness in the intended storefront context.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Sensitive pricing examples produce the intended result for the intended buyer, product, and storefront context without hidden assignment or discount errors.

### Pitfall 4: Underestimating Channel and Storefront Assignment Risk <a href="#pitfall-4-underestimating-channel-and-storefront-assignment-risk" id="pitfall-4-underestimating-channel-and-storefront-assignment-risk"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Products, categories, content, or pricing logic appear correct globally, but the wrong storefront or channel receives the wrong experience.

BigCommerce storefront and channel structure can affect product availability, category visibility, content placement, redirect destination quality, app behavior, and commercial expectations. The pitfall is assuming that a correct global record automatically means each storefront presents the right catalog, customer path, and business rule.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* Shared versus storefront-specific behavior is not defined before review.
* Product and category checks do not include storefront/channel context.
* Pricing behavior is tested in one context and assumed safe in all others.
* Redirect validation ignores whether the destination belongs to the right storefront experience.
* App, theme, or integration behavior is expected to behave consistently without evidence.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Define storefront governance before approving migration results. Clarify which products, categories, content, price logic, routes, and apps should be shared and which should vary. Build review samples around storefront-specific business outcomes, not only global data presence.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

For each commercially important storefront or channel, test one complex product, one priority category, one customer or pricing case, one important content page, and one high-value redirect.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Each important storefront or channel presents the right product visibility, discovery path, pricing context, content, route destination, and customer experience for its intended audience.

### Pitfall 5: Treating Redirects as a Technical Checkbox <a href="#pitfall-5-treating-redirects-as-a-technical-checkbox" id="pitfall-5-treating-redirects-as-a-technical-checkbox"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Redirects exist, but the destination no longer preserves customer intent, SEO value, campaign purpose, or support usefulness.

BigCommerce redirect capability can support route continuity, but a redirect is only useful when the destination still serves the purpose of the original URL. A technically working redirect can still weaken conversion if it lands on a broad category, a less relevant product, the wrong storefront context, or a generic page.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* Redirect review checks status only and not destination quality.
* High-value URLs are not prioritized by traffic, revenue, SEO value, campaign use, or support need.
* Old product and category URLs are mapped broadly without considering customer intent.
* CMS Pages, Blog Posts, policy pages, campaign pages, and support routes are treated as low-priority.
* Storefront-specific routes are not reviewed for audience and context.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Build a priority URL sample before launch. Include top products, top categories, campaign pages, support pages, trust pages, CMS Pages, Blog Posts, and storefront-specific routes. Review whether the new destination still answers the same customer need.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Select the top traffic and top revenue routes, then validate redirect destination quality instead of only redirect status. Include product, category, content, policy, campaign, and storefront-specific URLs.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Priority routes resolve to destinations that preserve customer intent, commercial value, search purpose, campaign meaning, or support usefulness closely enough for launch confidence.

### Pitfall 6: Treating Custom Data and Apps as Later Configuration <a href="#pitfall-6-treating-custom-data-and-apps-as-later-configuration" id="pitfall-6-treating-custom-data-and-apps-as-later-configuration"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Core records look acceptable, but important storefront or operational behavior fails because custom fields, metafields, apps, external IDs, or integration references were not classified early.

Many BigCommerce migrations involve behavior that lives around the migrated records: subscriptions, reviews, loyalty, ERP or CRM links, fulfillment references, shipping logic, product badges, recommendations, trust elements, reporting keys, or app-owned storefront behavior. When these dependencies are postponed, the migration can look complete while business workflows remain weak.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* Custom fields or metafields are checked by presence rather than by the outcome they support.
* App-dependent behavior is excluded from Demo Migration interpretation.
* External identifiers are not tested against operational systems.
* Theme-shaped or app-shaped behavior is treated as design work only.
* The team cannot distinguish standard BigCommerce behavior from custom, app-owned, or external-system behavior.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Classify custom data and app dependency before launch. Identify which outcomes fit standard BigCommerce structures, which may require Add-ons for filtering, mapping, or data configuration, and which require Custom Service because they involve bespoke transformation, unsupported app data, external identifiers, or custom migration logic adjustment.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

Choose the app-owned and custom-data behaviors most important to buying, fulfillment, reporting, support, and customer trust. Validate whether the migrated fields, identifiers, or related configuration still support the intended workflow.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Important custom-field, metafield, app, and external-identifier behaviors still support the intended storefront or operational outcome after migration.

### Pitfall 7: Approving Customer Continuity by Record Presence <a href="#pitfall-7-approving-customer-continuity-by-record-presence" id="pitfall-7-approving-customer-continuity-by-record-presence"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Customer records migrate, but returning customers experience confusion after launch.

Customer continuity depends on more than names, emails, addresses, and order history. It can also depend on account access expectations, reset-first communication, customer-group assignment, price-list behavior, storefront context, support readiness, and order-history usability.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* Customer review stops after confirming customer records exist.
* The first-login or reset-first path has not been reviewed.
* Customer-group and price-list behavior is not tested through realistic customer accounts.
* Customer communication is left until late in launch preparation.
* Support teams do not know how to explain account continuity after migration.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Define the returning-customer experience before launch. Validate representative customer profiles, including customers with order history, multiple addresses, customer-group pricing, special account expectations, or storefront-specific access needs. Confirm the support and communication plan before customers encounter the new store.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

Test a returning-customer journey from login or reset handling through account review, address review, order-history review, customer-group pricing, and checkout readiness.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Returning customers can re-enter the BigCommerce store through a realistic, well-communicated path that matches the account-continuity method available after migration.

### Pitfall 8: Treating Additional Migration Options as a Validation Substitute <a href="#pitfall-8-treating-additional-migration-options-as-a-validation-substitute" id="pitfall-8-treating-additional-migration-options-as-a-validation-substitute"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Follow-up migration activity is treated as a way to postpone validation decisions rather than a way to handle changed or newly available data after the main migration work.

Additional Migration Options can support practical migration follow-up needs, but they do not prove that the BigCommerce store is ready for launch. If the first migration pass leaves unresolved product-choice, pricing, storefront, redirect, customer, or custom-data issues, later migration activity may carry those weaknesses forward unless the affected areas are reviewed again.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* Teams assume later migration activity will fix unclear mapping or validation gaps.
* New or changed records are migrated without renewed product, pricing, storefront, or redirect review.
* The same high-risk samples are not rechecked after follow-up migration activity.
* Entity Points calculation is confused with launch-readiness approval.
* Stakeholders approve the store before changed records have been reviewed in context.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Use Additional Migration Options as part of controlled migration follow-up handling, not as a substitute for validation. Recheck the areas affected by new or changed records, especially product choices, customer groups, price lists, categories, storefront assignments, redirects, custom fields, metafields, apps, and external IDs. Remember that Entity Points consumption depends on whether eligible records are new to the service license record, not on whether follow-up activity occurs.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

After additional migration activity, review the affected sample set again: recently changed products, customer groups, price lists, priority URLs, storefront assignments, and app-dependent records.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Changed or newly added records are reviewed in BigCommerce context before launch approval, and follow-up migration activity does not replace product, pricing, storefront, redirect, customer, or custom-data validation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce migration pitfalls usually come from approving structure before proving behavior. A store can look complete while customers lose product-choice clarity, pricing accuracy, storefront relevance, discovery quality, route intent, account continuity, or app-supported workflow meaning.

The safest prevention approach is to review BigCommerce as a governed Target Platform where commercial behavior matters as much as record presence. Product-choice examples, sensitive pricing cases, storefront-specific journeys, priority redirects, returning-customer paths, and custom-data workflows should all be tested before launch confidence is treated as reliable.

For BigCommerce migrations with complex product choices, segmented pricing, multiple storefronts, app-owned behavior, or Custom Platform records, review the highest-risk examples before Full Migration approval. If uncertainty remains, discuss the migration path with Next-Cart before launch so the plan can separate standard supported behavior, Add-ons, and Custom Service needs.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is one of the most common BigCommerce migration mistakes?**

One common mistake is treating a complete-looking storefront as proof that the migration is safe. BigCommerce migration review should also prove product-choice behavior, pricing context, storefront assignment, redirect destination quality, customer continuity, and custom-data outcomes.

**Why are variants, options, and modifiers common BigCommerce pitfalls?**

Because each layer can carry different commercial meaning. A product can migrate successfully while the customer-facing choice path becomes weaker if true variants, modifier-style choices, personalization inputs, custom fields, and app-managed selections are not classified clearly.

**Are BigCommerce redirects enough to prevent SEO or traffic problems?**

No. Redirects help with route continuity, but destination quality still matters. Priority URLs should resolve to pages that preserve the original customer intent, search value, campaign purpose, or support purpose.

**Why do customer groups and price lists need special attention?**

Because pricing continuity depends on customer context, product context, and storefront context. The right buyer should see the intended price or buying condition under the intended circumstances, not only a technically migrated price field.

**How should Additional Migration Options be handled after a BigCommerce migration?**

Additional Migration Options should be treated as controlled follow-up handling for new or changed records. They do not replace validation, and affected BigCommerce areas should be reviewed again before launch or before a major post-launch update is approved.
