# Shopify Plus Pre-Migration Preparation Checklist

Shopify Plus preparation is strongest when the business defines the target behavior before migration is judged by transferred records. This platform can support more commercial structure than standard Shopify, but that added structure does not remove ambiguity on its own. It increases the importance of deciding how business customers, account access, catalogs, pricing visibility, storefront boundaries, and high-value paths should work after launch.

A strong preparation checklist is therefore not a generic cleanup exercise. It is a way to make the future store explicit early enough to reduce false confidence later. For Shopify Plus, the most useful preparation work usually sits in six areas: B2B structure, store architecture, account continuity, product representation, app-owned behavior, and continuity of the storefront paths that matter most.

### 1. Define the target B2B model before mapping begins

The first preparation task is to define what the business-customer structure should look like after migration. In Shopify Plus, that usually means deciding how companies, company locations, contacts, catalogs, pricing visibility, payment expectations, and order context should relate to one another. If those relationships are still vague, the migration can move large amounts of data while still weakening the commercial logic the business depends on.

Before execution, the business should define:

* which customers belong to which companies
* which company locations need distinct treatment
* which catalogs should apply to which locations
* which pricing and payment differences are commercially essential
* which B2B rules must still hold true after launch

This is one of the highest-value places to use a Demo Migration. A representative sample built around real company-account scenarios usually reveals structural weakness faster than broad customer transfer alone.

### 2. Decide early whether the target should be blended or store-separated

Shopify Plus can support B2B and direct-to-consumer selling in one store or through a separate B2B-only store. That decision should be treated as a preparation priority because it affects customer segmentation, catalog scope, domain behavior, governance, and validation coverage. Leaving it unresolved too long often creates confusion later around where customers belong, how products should be exposed, and which paths need separate review.

Before execution, the business should define:

* whether B2B and direct-to-consumer should share one store
* whether separate storefronts are commercially necessary
* which differences belong in one store through segmentation and catalogs
* which differences justify independent storefront contexts
* who owns each storefront context operationally after launch

This is also where inherited multi-store patterns should be questioned rather than preserved automatically. A separate store is justified by a real commercial or governance need, not by habit alone.

### 3. Plan customer continuity as an access experience

Customer continuity in Shopify Plus should be prepared as an account-access experience, not as legacy credential preservation. The most important early questions are how customers will sign in after launch, what first-login experience they should expect, whether a social or identity-provider model is relevant, and how account access should behave for business customers in company context. Shopify customer accounts use passwordless sign-in by default, and Shopify Plus can connect an OpenID Connect identity provider where a more controlled sign-in experience is required.

Before execution, the business should define:

* what the first-login journey should feel like
* which customer groups need the most controlled access experience
* whether social sign-in is useful
* whether external identity-provider integration is materially necessary
* which account scenarios must be reviewed before launch

This is one of the clearest cases where imported records are not enough to prove readiness. The account experience itself has to be planned and validated.

### 4. Confirm the intended product model before detailed mapping

Shopify Plus adds more native structure around the buyer, but it still inherits Shopify’s core product model. Products remain structured through products, options, and variants, with up to three options and up to 2,048 variants per product. That means preparation should still begin with the sellable outcome rather than with raw product count. The business needs to decide which attributes must remain customer-selectable, which should stay descriptive, and which products are most likely to expose representation weakness early.

Before execution, the business should define:

* which product families carry the highest representation risk
* which attributes must remain selectable
* which variation should stay descriptive or move outside variant logic
* which products should anchor the first representative review
* which B2B pricing or catalog rules intersect with complex product structure

A good early sample should include products that are commercially important and structurally difficult, especially where B2B access and product complexity interact.

### 5. Identify where important business meaning lives outside the native core

Many Shopify Plus migrations become riskier where important behavior lives in apps, custom data, or legacy enterprise logic rather than in the native platform model. Preparation should therefore identify which outcomes are truly native and which ones depend on extensions, custom storefront behavior, search or merchandising tools, subscriptions, loyalty programs, or other specialized logic. If those dependencies remain vague, the migration scope may look cleaner than it really is.

Before execution, the business should define:

* which app-owned behaviors are commercially non-negotiable
* which custom data drives discovery, filtering, merchandising, or operations
* which storefront blocks or logic depend on theme or extension behavior
* which legacy enterprise behaviors still need a current-platform equivalent
* which outcomes can weaken safely and which cannot

This is often where Live Chat becomes especially useful. It helps distinguish between ordinary migration uncertainty and situations where Managed Migration Service, Custom Migration Service, or a Custom Job is the safer path.

### 6. Define what continuity matters most across storefront paths

Shopify Plus preparation should identify the storefront paths that carry the most commercial value before redirect or domain review begins. Native redirect support is available, but continuity still depends on choosing the right paths, storefront contexts, and post-launch destinations to protect. This becomes more important when the business has multiple domains, region-sensitive entry points, or separate storefront contexts that customers experience differently.

Before execution, the business should define:

* which legacy product, collection, landing, and informational paths matter most
* which domains or region-specific entry points need protection
* which market-sensitive customer journeys should be preserved
* which redirects need to be validated first after launch
* which paths can change safely without weakening performance or trust

The most useful early redirect list is usually selective, not exhaustive. High-value paths usually reveal risk faster than large-volume URL handling.

### 7. Choose a representative review sample before full execution

A representative review sample should be designed before detailed execution begins. The goal is not broad coverage. The goal is early signal. Shopify Plus preparation is strongest when the first sample includes the combinations most likely to expose structural weakness in B2B logic, account continuity, store boundaries, product representation, and high-value storefront behavior.

A high-signal Shopify Plus sample usually includes:

* representative companies and company locations
* B2B customers with different pricing or catalog conditions
* one-store and multi-store scenarios where relevant
* products with the highest representation complexity
* app-dependent or custom-data-dependent outcomes
* priority storefront paths and account journeys

This is usually the clearest point at which the business can decide whether the target model is ready for a broader migration run or still needs structural clarification.

### 8. Define launch-readiness in behavior terms, not record terms

Preparation is not complete when the fields to migrate are known. It is complete when the business can explain what must still work after launch. For Shopify Plus, that usually means defining who can buy what, under which account context, at which price, through which storefront path, with which operational expectations. If those outcomes are still not explicit, then the migration is being asked to solve a planning problem it cannot solve safely on its own.

Before execution, the business should define:

* which commercial outcomes must remain unchanged
* which changes are acceptable if the business gains a cleaner target model
* which scenarios represent pass or fail most clearly
* who reviews the result and approves readiness
* which unresolved questions must be answered before launch planning advances

This is the point where preparation turns into a realistic validation strategy rather than a hopeful execution plan.

### Conclusion

Shopify Plus preparation is strongest when it makes the future business model explicit before the migration is judged by transferred records. Companies, locations, catalogs, customer access, store boundaries, product structure, extension-driven behavior, and high-value paths all need deliberate definition early enough to guide mapping and validation with confidence.

The most useful preparation work usually identifies where commercial meaning is likely to weaken first. A representative Demo Migration built around those areas is often the clearest way to test whether the target structure is ready. If the result still leaves uncertainty around B2B structure, account behavior, multi-store design, or app-dependent outcomes, Live Chat can help determine whether Standard Migration Service remains sufficient or whether Managed Migration Service or Custom Migration Service is the safer path.

### FAQs

<details>

<summary><strong>What should be prepared first in a Shopify Plus migration?</strong></summary>

Usually the B2B and storefront structure. That includes company relationships, location-level rules, catalog logic, account-access expectations, and whether the business should run in one store or in separate storefront contexts.

</details>

<details>

<summary><strong>Why is Shopify Plus preparation more than a data-cleanup task?</strong></summary>

Because the main preparation challenge is not only moving records. It is defining how commercial behavior should work after launch, especially around pricing visibility, customer access, store boundaries, and app-dependent outcomes.

</details>

<details>

<summary><strong>Should Shopify Plus preparation focus on every product and customer equally?</strong></summary>

Usually no. Preparation is most useful when it starts with the products, customers, company-account scenarios, and storefront paths most likely to reveal structural weakness early.

</details>

<details>

<summary><strong>When does preparation usually point toward a more tailored migration path?</strong></summary>

Usually when B2B structure is still unclear, multi-store design is unresolved, account continuity needs tighter control, or important business outcomes still depend on under-defined apps, custom data, or legacy enterprise logic.

</details>
