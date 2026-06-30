# AmeriCommerce Pre-Migration Preparation Checklist

AmeriCommerce preparation works best when the store is reviewed as a commerce system with account relationships, catalog rules, storefront boundaries, and operational history. A clean export is helpful, but it does not prove that products, customers, pricing, content, and orders are ready to become usable in the target store.

The preparation phase should turn uncertain source-store behavior into clear migration inputs. For AmeriCommerce, that usually means confirming how buyers are organized, how catalog access and pricing are controlled, which records still matter, and which legacy structures should be migrated, rebuilt, archived, or excluded.

### Confirm the Target Store Structure <a href="#confirm-the-target-store-structure" id="confirm-the-target-store-structure"></a>

Start by defining what the AmeriCommerce target store must represent after migration. The target structure should not be treated as a blank container for imported records. It needs a clear operating model: one storefront or several storefront-like experiences, one shared catalog or segmented catalogs, one buyer model or multiple buyer groups, one pricing approach or rule-based pricing by customer type.

This review is especially important when the source store has B2B, wholesale, dealer, distributor, school, nonprofit, employee, private portal, or account-managed buyer flows. A merchant may describe the migration as a catalog move, but the real complexity often comes from who can see each product, which price they receive, and which checkout or payment expectations apply.

| Target-store question | What to confirm before migration                                                                              | Why it matters for AmeriCommerce planning                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Storefront ownership  | Whether the target store needs one storefront, multiple storefront experiences, or separate catalog views     | Storefront decisions affect URL planning, content grouping, and product visibility.       |
| Buyer model           | Whether buyers are retail customers, companies, contacts under accounts, dealers, members, or mixed audiences | Buyer structure affects customer mapping, pricing, tax treatment, and validation samples. |
| Catalog boundaries    | Whether all buyers can see all products or whether catalogs vary by buyer type                                | Catalog boundaries shape product visibility and post-migration review.                    |
| Pricing model         | Whether pricing is simple, tiered, customer-specific, quantity-based, or externally owned                     | Pricing rules may require configuration, Add-ons, or Custom Service review.               |
| Operational ownership | Whether AmeriCommerce, ERP, CRM, accounting, or fulfillment systems own key records                           | System ownership determines which fields should migrate and which should be rebuilt.      |

A practical preparation output is a short target-store map. It should name the main buyer groups, storefront or catalog boundaries, pricing expectations, content areas, and systems that remain connected after launch. Without that map, the migration may import records accurately while still failing to recreate the way the business sells.

### Prepare Catalog and Product Data <a href="#prepare-catalog-and-product-data" id="prepare-catalog-and-product-data"></a>

Product preparation should go beyond checking SKU counts. AmeriCommerce-bound catalog data needs review for product relationships, product types, options, pricing conditions, category placement, visibility, and content quality. The goal is not to polish every record manually. The goal is to identify which product patterns are safe to migrate as ordinary records and which patterns need deeper mapping.

Start with a representative product inventory. Include simple products, option-heavy products, configurable or variant-style products, kits or bundles, discounted products, restricted-access products, products with custom fields, and products connected to external inventory or fulfillment systems. These samples reveal more than a random SKU list because they show the behaviors that could fail after migration.

| Catalog preparation area | Preparation action                                                                           | Evidence to collect                                                                 |
| ------------------------ | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Product identifiers      | Confirm SKU, product ID, supplier code, UPC, or external item identifiers                    | Export columns, ERP references, fulfillment references, and sample product records. |
| Product options          | Identify options that change price, inventory, image, fulfillment, or buyer selection        | Option samples, pricing examples, and screenshots from product pages.               |
| Product grouping         | Separate ordinary variants from kits, bundles, assembled products, or custom product forms   | Source product relationships and fulfillment rules.                                 |
| Category structure       | Review category depth, duplicates, retired categories, and product placement                 | Category tree, top-selling category samples, and URLs.                              |
| Visibility rules         | Confirm products hidden by customer group, storefront, membership, region, or manual control | Buyer examples and access screenshots.                                              |
| Product content          | Review descriptions, images, downloads, specifications, SEO fields, and related content      | Exported content, image paths, media files, and product-page samples.               |

Catalog cleanup should preserve business meaning. Removing duplicate products is useful when records are truly obsolete. Flattening option behavior, buyer-specific visibility, or product bundles into plain text fields can create a cleaner export but a weaker store after launch.

### Prepare Customer, Account, and Order Data <a href="#prepare-customer-account-and-order-data" id="prepare-customer-account-and-order-data"></a>

Customer and order preparation should focus on how records are used, not only whether they exist. AmeriCommerce migrations often involve customer records that represent buyer rules, account relationships, pricing eligibility, tax status, purchasing authority, sales workflows, or service history. These relationships must be identified before migration because they influence mapping, validation, and support readiness.

Customer preparation should classify buyer records by real business role. A retail customer, wholesale buyer, dealer, company contact, tax-exempt buyer, employee purchaser, or account-managed customer should not be reviewed as the same kind of record if the business treats them differently.

| Data area           | Preparation focus                                                                         | Common AmeriCommerce migration concern                                        |
| ------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Customers           | Names, emails, addresses, login state, groups, company relationship, account labels       | Customer records may control pricing, catalog access, or tax behavior.        |
| Customer groups     | Wholesale, dealer, retail, VIP, trade, tax-exempt, or custom group usage                  | Group names may be inconsistent or may overlap with pricing rules.            |
| Addresses           | Billing, shipping, company address, branch location, or default address                   | Address meaning affects checkout, tax, shipping, and customer-service review. |
| Orders              | Order status, payment method, fulfillment status, buyer identity, items, taxes, discounts | Order history must remain useful for service and accounting reference.        |
| Order relationships | Quotes, invoices, shipments, returns, purchase orders, or external references             | Operational history may depend on records outside the standard order table.   |

Order records should be sampled by business scenario. Include completed orders, canceled orders, partially fulfilled orders, discounted orders, tax-exempt orders, wholesale orders, high-value orders, orders with unusual shipping, and orders tied to external systems. A small set of well-chosen samples can expose mapping problems that a full export count cannot show.

### Prepare Content, URLs, and SEO Inputs <a href="#prepare-content-urls-and-seo-inputs" id="prepare-content-urls-and-seo-inputs"></a>

Content and SEO preparation should protect discoverability, buyer trust, and support continuity. AmeriCommerce migrations may involve product pages, category pages, static pages, blog content, landing pages, forms, downloadable resources, images, redirects, and legacy URLs. Some content should migrate directly, some should be rebuilt, and some should be retired.

The preparation task is to separate content that supports current business value from content that only exists because the source store accumulated old pages over time. Pages that rank in search, support paid campaigns, explain B2B ordering, document policies, or answer product questions deserve different treatment from obsolete announcement pages or duplicated landing pages.

| Content or SEO input        | Preparation action                                                                | Migration decision to support                               |
| --------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Product URLs                | Export current URLs for representative products and high-value products           | Preserve, redirect, or intentionally change routes.         |
| Category URLs               | Identify traffic-driving categories and retired categories                        | Preserve taxonomy where useful and redirect obsolete paths. |
| CMS pages                   | Review policy pages, buying guides, landing pages, brand pages, and support pages | Migrate, rebuild, merge, or exclude pages.                  |
| Blog or educational content | Identify posts with traffic, backlinks, or buyer-support value                    | Preserve SEO value or rebuild as updated content.           |
| Metadata                    | Review titles, descriptions, slugs, canonical expectations, and image alt text    | Avoid losing search context during the move.                |
| Redirects                   | Prepare old-to-new URL mapping for products, categories, and content pages        | Reduce broken links and post-launch SEO disruption.         |

Content preparation should produce a route list, not only a page export. A page can migrate successfully at content level but still lose value if the URL, internal linking, metadata, or redirect plan is missing.

### Review Apps, Extensions, Integrations, or Custom Data <a href="#review-apps-extensions-integrations-or-custom-data" id="review-apps-extensions-integrations-or-custom-data"></a>

AmeriCommerce preparation should identify every external dependency before migration work begins. Source stores often rely on ERP, accounting, CRM, tax, payment, shipping, inventory, marketplace, email marketing, analytics, product information management, or fulfillment systems. These systems may own identifiers or behaviors that are not obvious inside normal commerce exports.

Custom data should be classified by business purpose. Some custom fields are useful labels. Others are the only place where the source store records buyer rules, product restrictions, supplier data, tax treatment, sales-rep ownership, warehouse logic, or external system IDs. Migrating every custom field without understanding ownership can make the target store harder to operate. Excluding them without review can break reporting or integrations.

| Dependency type          | What to document                                                      | Why it affects migration scope                                               |
| ------------------------ | --------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| ERP or accounting        | Customer IDs, item IDs, order numbers, tax status, invoice references | These values may need to remain searchable or integration-ready.             |
| Inventory or fulfillment | Warehouse codes, supplier IDs, dropship rules, stock ownership        | Product migration may need operational identifiers beyond storefront fields. |
| CRM or sales tools       | Company accounts, sales reps, lead source, contract terms             | Customer records may need relationship context, not only contact data.       |
| Tax and shipping tools   | Rules, zones, exemptions, carrier logic, service levels               | Some behaviors should be configured rather than imported as raw data.        |
| Marketing tools          | Segments, coupon history, newsletter status, campaign landing pages   | Marketing continuity may require selective data handling.                    |
| Custom source logic      | Scripts, custom tables, hidden fields, or manual workflows            | Custom Service may be needed if the data is business-critical.               |

The output should be a dependency register. It does not need to solve every integration before migration, but it should identify what each system owns, which fields must remain available, and which records should be validated with external-system users.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Migration preparation depends on reliable access and stable inputs. AmeriCommerce planning can be delayed when store credentials, export permissions, admin roles, API access, file access, DNS details, image folders, or third-party system access are incomplete. These details should be confirmed before the Demo Migration phase.

Backups should be treated as a safety control rather than a formality. The source store should be backed up in a way that preserves core entities, media files, export files, configuration references, and any custom data that may not appear in standard exports. If the source store is old, customized, or partially undocumented, backups become even more important because they protect against missing evidence.

| Input type             | What to prepare                                                                                      | Readiness signal                                  |
| ---------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| Admin access           | Source store admin and target store access with required permissions                                 | Migration team can view and export required data. |
| Export files           | Products, Customers, Orders, Coupons, CMS, URLs, media references, and custom exports where relevant | Files are complete, current, and labeled by date. |
| Media access           | Product images, category images, downloadable files, documents, and content media                    | Media paths can be matched to records.            |
| API or database access | Access method, credentials, limits, and technical owner                                              | Required records can be read safely.              |
| Backup evidence        | Full backup, export archive, media archive, and configuration notes                                  | Source state can be reviewed if questions appear. |
| Stakeholder access     | Commerce, marketing, operations, finance, and integration contacts                                   | Business meaning can be confirmed during review.  |

A useful preparation rule is to freeze the evidence set used for Demo Migration. If data keeps changing while samples are being reviewed, validation becomes harder because reviewers cannot tell whether a result is wrong or simply based on a different source state.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo Migration samples should be chosen deliberately. A random sample can prove that records move, but it may not prove that AmeriCommerce can represent the store’s real business model. Sample planning should cover the records most likely to reveal mapping, configuration, or service-scope issues.

The sample set should include ordinary records and edge cases. Ordinary records prove that baseline migration works. Edge cases prove whether the migration plan can handle the records that carry real business risk.

| Sample group        | Records to include                                                                                        | What the sample should prove                                              |
| ------------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Catalog samples     | Simple products, option-heavy products, bundles or kits, restricted products, products with custom fields | Product meaning, options, visibility, pricing, and content remain usable. |
| Customer samples    | Retail buyers, wholesale buyers, dealer accounts, tax-exempt buyers, company contacts                     | Buyer rules and account context can be reviewed.                          |
| Order samples       | Completed, canceled, discounted, tax-exempt, wholesale, and externally referenced orders                  | Order history keeps operational value.                                    |
| Content samples     | Product URLs, category URLs, CMS pages, landing pages, images, redirects                                  | SEO and content continuity can be checked.                                |
| Integration samples | Records with ERP IDs, CRM ownership, fulfillment references, or accounting links                          | External-system identifiers remain available where needed.                |

Reviewers should know what each sample is supposed to prove. A sample list without expected outcomes turns Demo Migration into casual browsing rather than structured validation.

### Final Preparation Check <a href="#final-preparation-check" id="final-preparation-check"></a>

The final preparation check should confirm that the migration is ready for execution, not merely that exports have been collected. The merchant should be able to explain the target-store structure, confirm which data types are included, identify exceptions, provide access, and review Demo Migration samples with the right stakeholders.

A concise final check can prevent avoidable rework. If the team cannot answer these readiness questions, the migration may still proceed technically, but validation will be slower and riskier.

| Final check                               | Pass condition                                                                                |
| ----------------------------------------- | --------------------------------------------------------------------------------------------- |
| Target-store structure is defined         | Buyer groups, catalog boundaries, storefront assumptions, and pricing expectations are clear. |
| Data scope is documented                  | Included, excluded, rebuilt, and archived records are identified.                             |
| Product complexity is sampled             | Options, bundles, visibility, pricing, and custom product records are represented.            |
| Customer and order meaning is clear       | Buyer rules and order-history use cases are documented.                                       |
| Content and URLs are prepared             | Important routes, CMS pages, metadata, and redirect needs are listed.                         |
| Integrations and custom data are reviewed | External ownership and business-critical fields are identified.                               |
| Access and backups are ready              | Required credentials, exports, media files, and backup evidence are available.                |
| Demo Migration samples are selected       | Samples cover normal records and high-risk cases.                                             |

Preparation is complete when the migration team can use the collected evidence to make scope decisions, not when every possible record has been inspected manually.

### Conclusion <a href="#conclusion" id="conclusion"></a>

AmeriCommerce preparation should turn uncertain source-store behavior into clear migration inputs. Catalog structure, buyer relationships, pricing rules, content routes, order history, integrations, and custom data all need enough review to decide what should migrate, what should be rebuilt, and what should be excluded.

The strongest preparation does not try to perfect the source store before migration. It identifies the records and relationships that matter most, prepares representative samples, and gives the migration plan enough context to preserve business usefulness in AmeriCommerce.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before an AmeriCommerce migration?**

Start with target-store structure, buyer models, catalog boundaries, pricing expectations, and integration ownership. These decisions shape how Products, Customers, Orders, Coupons, and CMS records should be reviewed.

**Should every old AmeriCommerce source record be cleaned before migration?**

No. Cleanup should focus on records that affect usability, reporting, SEO, buyer access, pricing, and operations. Cleaning records without understanding their business role can remove useful context.

**What samples are most important for Demo Migration?**

Use samples that represent both normal records and high-risk records: option-heavy products, restricted products, wholesale buyers, tax-exempt customers, discounted orders, high-value pages, and externally referenced records.

**How should custom fields be prepared?**

Custom fields should be classified by purpose. Fields used only for old notes may be excluded, while fields used for ERP IDs, buyer rules, tax status, product restrictions, or fulfillment logic may need migration or Custom Service review.

**Why are content and URL inputs part of preparation?**

Content and URLs affect discoverability, customer trust, and post-launch continuity. Products and categories can migrate correctly while SEO value still suffers if routes, metadata, redirects, or important CMS pages are not prepared.
