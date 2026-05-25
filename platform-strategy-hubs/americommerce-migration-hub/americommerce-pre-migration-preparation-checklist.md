# AmeriCommerce Pre-Migration Preparation Checklist

AmeriCommerce migrations need preparation before data is moved because the platform is often selected for stores with more than a simple retail catalog. Many AmeriCommerce projects involve B2B buyer relationships, customer types, portals, multi-store or microstore structures, product groups, kits, subscription products, advanced discounts, budgets, fulfillment rules, vendor workflows, integrations, or custom storefront behavior.

Preparation should clarify how those structures need to work in AmeriCommerce after migration. A clean product count or customer count is not enough when the store depends on business-specific rules, buyer permissions, catalog separation, or workflow logic. The safest preparation work defines the commercial meaning behind the data before the migration is configured and reviewed.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation helps separate records that can be moved as standard store data from behavior that depends on configuration, rules, integrations, custom fields, or platform-specific interpretation.

For AmeriCommerce, this usually means confirming how the store sells, who it sells to, how pricing is controlled, how storefronts are separated, how repeat or subscription purchases work, and which operational workflows must remain usable after launch. The preparation phase should also identify which sample records need to be included in Demo Migration so the result can be judged against real business cases rather than generic records.

### 1. Define the AmeriCommerce business model before reviewing data <a href="#id-1-define-the-americommerce-business-model-before-reviewing-data" id="id-1-define-the-americommerce-business-model-before-reviewing-data"></a>

Start by identifying the primary operating model for the target store. AmeriCommerce can support B2B, wholesale, portals, multi-store selling, subscription products, complex products, and customer-specific commerce patterns. Those capabilities are useful only when the migration team understands which model the store actually needs to preserve.

Clarify whether the migrated store is mainly expected to support:

* wholesale or distributor ordering
* customer-specific catalogs or buyer access
* employee, school, medical, franchise, or organization portals
* multiple storefronts managed from one environment
* subscription or repeat-purchase products
* multi-vendor or marketplace-style workflows
* rule-driven discounts, budgets, or rewards
* a more conventional catalog with selected advanced features

This step prevents the migration from being judged only by whether products, customers, and orders appear. The important question is whether those records still support the selling model AmeriCommerce is being chosen to handle.

### 2. Map customer types, B2B buyers, and portal relationships <a href="#id-2-map-customer-types-b2b-buyers-and-portal-relationships" id="id-2-map-customer-types-b2b-buyers-and-portal-relationships"></a>

Customer preparation is especially important when the source store has more than standard consumer accounts. AmeriCommerce fit often depends on customer segmentation, B2B portals, organization-level purchasing, allowances, budgets, catalog access, or buyer-specific rules.

Before migration, define how customer records should be interpreted:

* standard consumer accounts
* wholesale buyers
* dealer, distributor, or reseller accounts
* organization or company-level buyers
* employee or internal ordering accounts
* portal users with specific permissions
* customer types with different pricing, access, or discount behavior
* historical customers that should remain searchable but do not need full account behavior

If the source store uses custom fields, tags, customer groups, account notes, approval statuses, or outside-system identifiers to explain buyer meaning, those fields should be documented before migration. Some of that information may move as standard customer data. Broader transformation, outside-system identifiers, or custom buyer logic should be reviewed as Custom Service requirements.

### 3. Clarify multi-store, microstore, and portal scope <a href="#id-3-clarify-multi-store-microstore-and-portal-scope" id="id-3-clarify-multi-store-microstore-and-portal-scope"></a>

AmeriCommerce can be used for multiple storefronts, microstores, and specialized portal experiences. A migration should not assume that all stores, categories, customers, products, and content belong in one undifferentiated structure.

Prepare a store-scope map that explains:

* which storefronts or portals should exist after migration
* which products belong to each storefront or portal
* which customers or customer types should access each area
* whether pricing or discounts vary by storefront, portal, or buyer group
* whether content, navigation, or branding differs by storefront
* whether inventory, fulfillment, or order review differs by business line

This map is important even when the source system does not use the same multi-store model as AmeriCommerce. If the old store handled separation through categories, separate installations, custom logic, subdomains, or manual staff processes, those assumptions need to be translated into the AmeriCommerce planning model.

### 4. Prepare product structure beyond the base product record <a href="#id-4-prepare-product-structure-beyond-the-base-product-record" id="id-4-prepare-product-structure-beyond-the-base-product-record"></a>

AmeriCommerce product preparation should include more than product names, SKUs, descriptions, prices, and images. The platform is often chosen because the catalog uses product flexibility, variants, attributes, groups, kits, subscriptions, or special product relationships.

Review product data for:

* variants and option choices
* attributes and product specifications
* product groups or grouped purchasing logic
* kits, bundles, or assembled product structures
* subscription products and recurring purchase rules
* customer-specific or portal-specific product access
* products with unusual pricing, inventory, or fulfillment behavior
* products that depend on custom fields or integrations

A strong preparation sample should include simple products and complex products. If only simple products are reviewed during Demo Migration, the migration can look successful while the most important catalog structures remain untested.

### 5. Document pricing, discount, reward, and budget logic <a href="#id-5-document-pricing-discount-reward-and-budget-logic" id="id-5-document-pricing-discount-reward-and-budget-logic"></a>

Pricing is often one of the highest-risk areas in an AmeriCommerce migration because the visible product price may not explain the whole selling rule. Discounts, rule engine behavior, budgets, customer types, rewards, subscription terms, or portal-specific pricing can all affect what buyers see and how orders are placed.

Before migration, document the pricing rules that matter commercially:

* customer-type pricing
* wholesale or dealer price levels
* quantity or volume-based discounts
* product-specific promotions
* portal-specific pricing
* recurring or subscription pricing
* rewards, loyalty, or budget behavior
* custom payment terms or invoice-based purchasing
* exceptions that staff currently manage manually

The preparation goal is not to recreate every rule in article form. It is to identify which pricing logic must be preserved, which rules are historical, and which rules need Custom Service review because they depend on custom behavior or non-standard source data.

### 6. Review subscription, repeat-order, and account-based purchasing expectations <a href="#id-6-review-subscription-repeat-order-and-account-based-purchasing-expectations" id="id-6-review-subscription-repeat-order-and-account-based-purchasing-expectations"></a>

Stores that use subscription products, repeat ordering, saved buyer behavior, budgets, or account-based purchasing need more preparation than stores with one-time checkout only.

Clarify whether the migrated AmeriCommerce store needs to preserve:

* subscription product records
* recurring billing references
* repeat-order expectations
* buyer budgets or allowances
* customer-specific payment permissions
* saved business purchasing context
* historical subscription orders
* operational notes used by service or fulfillment teams

Not every historical subscription or account workflow can be judged by record presence alone. The review should confirm what must remain actionable after launch and what only needs to remain visible for reference.

### 7. Prepare order, fulfillment, shipping, and vendor context <a href="#id-7-prepare-order-fulfillment-shipping-and-vendor-context" id="id-7-prepare-order-fulfillment-shipping-and-vendor-context"></a>

Order history should be prepared as operational context, not only as a transaction archive. In B2B, wholesale, multi-vendor, or fulfillment-sensitive stores, staff may use order history to answer customer questions, review purchase patterns, repeat prior orders, confirm fulfillment expectations, or coordinate vendor workflows.

Before migration, identify sample orders that include:

* standard retail orders
* wholesale or B2B orders
* customer-type or portal-specific orders
* subscription or recurring orders
* orders affected by discounts, budgets, or rewards
* orders with unusual shipping or fulfillment requirements
* vendor-related or multi-vendor context
* orders with custom fields, staff notes, or integration references

This helps the migration review prove whether order history remains useful in AmeriCommerce, not just whether order records were imported.

### 8. Identify integrations, custom fields, and extension-shaped behavior early <a href="#id-8-identify-integrations-custom-fields-and-extension-shaped-behavior-early" id="id-8-identify-integrations-custom-fields-and-extension-shaped-behavior-early"></a>

AmeriCommerce projects may involve payment services, shipping systems, accounting tools, ERP workflows, inventory systems, vendor feeds, CRM data, marketing tools, or custom features. These surrounding systems often explain why certain fields, statuses, identifiers, or workflows matter.

Prepare a list of integrations and custom data dependencies that influence the migration:

* external product identifiers
* customer account numbers
* ERP or accounting references
* vendor identifiers
* fulfillment or warehouse codes
* custom order statuses
* custom product fields
* custom customer fields
* payment or shipping rules
* API or headless commerce dependencies

If these details are required for the migrated store to operate correctly, they should not be treated as secondary cleanup. Broader transformation, outside-system identifiers, custom fields, and custom workflow logic belong in Custom Service review.

### 9. Select Demo Migration samples that represent real complexity <a href="#id-9-select-demo-migration-samples-that-represent-real-complexity" id="id-9-select-demo-migration-samples-that-represent-real-complexity"></a>

Demo Migration should include records that show how AmeriCommerce will handle the store’s most important business cases. A weak sample with only simple products, standard customers, and ordinary orders will not reveal whether the migration is ready for a B2B, portal, subscription, or multi-store launch.

A stronger sample should include:

* simple and complex products
* products with variants, attributes, groups, kits, or subscriptions
* B2B and standard customers
* customer types with different pricing or access expectations
* orders affected by discounts, rewards, budgets, subscriptions, or special fulfillment
* storefront or portal-specific records
* SEO-sensitive categories, products, and content pages
* records tied to integrations, custom fields, or outside-system identifiers

The sample should be small enough to review carefully but broad enough to expose the migration risks that matter most.

### 10. Decide which requirements need Standard Service, Add-ons, or Custom Service review <a href="#id-10-decide-which-requirements-need-standard-service-add-ons-or-custom-service-review" id="id-10-decide-which-requirements-need-standard-service-add-ons-or-custom-service-review"></a>

Preparation should also identify which needs can stay within standard service capability and which ones need additional handling.

Standard Service can be suitable when the source data is well structured, the AmeriCommerce target model is clear, and the customer can review and configure the migration process with support. Managed Service is more appropriate when the customer wants Next-Cart-led execution using standard service capability and any purchased Standard Add-ons.

Add-ons can support selected filtering, mapping, or data configuration needs. For example, the Data Filter Add-on may be useful when only selected records should move, while Advanced Data Mapping or Advanced Data Configure may be relevant when source and target data need clearer alignment within supported platform capability.

Custom Service is required when the project involves customization or modification work. This includes Custom Platform sources, custom fields, outside-system identifiers, third-party app or integration data, bespoke transformation rules, custom migration logic adjustment, or tailored Add-ons. Custom Service does not automatically mean Next-Cart performs the migration process; migration management is included only when it is part of the final plan.

### Conclusion <a href="#conclusion" id="conclusion"></a>

AmeriCommerce preparation should make the store’s business structure clear before migration begins. The safest projects define buyer relationships, storefront scope, product complexity, pricing logic, subscriptions, fulfillment context, integrations, and sample records early enough for the migration plan to reflect how the business actually operates.

Before moving forward with a full AmeriCommerce migration, use Demo Migration to test the records that carry the most business meaning: complex products, B2B buyers, portal-specific access, pricing rules, subscriptions, fulfillment-sensitive orders, and integration-dependent fields. If those examples cannot be reviewed clearly, the migration scope should be refined before launch planning continues.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to AmeriCommerce?**

Start with the business model, not the data count. Clarify whether the store depends on B2B buyers, portals, multi-store selling, product groups, subscriptions, pricing rules, budgets, fulfillment workflows, or integrations. Those decisions shape how the migrated data should be interpreted in AmeriCommerce.

**Should I include complex products in Demo Migration?**

Yes. Demo Migration should include products with variants, attributes, groups, kits, subscriptions, customer-specific access, or unusual pricing behavior. Simple products alone do not prove whether an AmeriCommerce migration can support the catalog structures that matter most.

**Do customer types and B2B buyer relationships need preparation?**

Yes. Customer types, buyer groups, portal access, budgets, permissions, account identifiers, and special pricing rules should be documented before migration. They help determine whether customer data remains commercially useful after it reaches AmeriCommerce.

**How should multi-store or portal scope be prepared?**

Prepare a store-scope map that explains which storefronts, microstores, or portals should exist after migration; which products and customers belong to each area; and whether pricing, content, navigation, or fulfillment differs across those areas.

**When should AmeriCommerce preparation move into Custom Service review?**

Custom Service review is needed when the project requires customization or modification work, such as Custom Platform source handling, custom fields, outside-system identifiers, third-party integration data, bespoke transformation, custom migration logic adjustment, or tailored Add-ons. Custom Service does not automatically include migration management unless that work is part of the final plan.
