# URL Structure Changes and Redirect Planning

URL structure changes can be one of the most visible migration risks after an e-commerce store moves to a new platform. Product pages, category pages, CMS Pages, Blog Posts, campaign landing pages, filtered paths, regional paths, and internal links may all use different URL patterns in the Target Platform. Even when the migrated store looks complete, customers and search engines may still try to reach the old paths through bookmarks, search results, backlinks, email campaigns, advertisements, affiliates, social posts, and internal navigation.

Redirect planning protects that continuity. It determines how important old URLs should resolve after migration and whether the new destination still matches the original page intent. The goal is not to avoid every 404 at any cost. The goal is to preserve meaningful access to the pages and pathways that matter for traffic, revenue, customer trust, and search continuity.

URL planning should begin before go-live, not after launch problems appear. Priority URLs should be identified, mapped, implemented, and tested while there is still time to correct weak destinations, redirect chains, missing internal links, or platform limitations.

### Why URL Structure Changes Matter During Migration <a href="#why-url-structure-changes-matter-during-migration" id="why-url-structure-changes-matter-during-migration"></a>

A URL is more than a page address. For customers, it is often a saved route back to a product, category, content page, or campaign. For search engines, it is a signal connected to crawl history, page purpose, backlinks, internal links, and accumulated page value.

During migration, URLs can change because the Target Platform may use different routing rules, product handles, category structures, collection paths, blog paths, CMS Page paths, language paths, store-view patterns, filter logic, or app-generated landing pages. The page may still exist, but the path used to reach it may no longer be the same.

Common URL changes include:

* product page paths changing because product handles, slugs, IDs, or routing rules differ;
* category or collection paths changing because the Target Platform uses a different hierarchy;
* CMS Pages and Blog Posts moving into different content structures;
* campaign landing pages being renamed, rebuilt, archived, or consolidated;
* multilingual, regional, or store-view paths being represented differently;
* filtered, faceted, tag-based, or search-result pages behaving differently;
* internal links inside menus, banners, product descriptions, blog content, footers, and promotional blocks still pointing to old paths.

These changes are not automatically wrong. Migration often creates a cleaner, more sustainable URL structure. Risk appears when high-value old URLs are not mapped to relevant new destinations before the store launches.

### Identify Priority URLs Before Mapping Redirects <a href="#identify-priority-urls-before-mapping-redirects" id="identify-priority-urls-before-mapping-redirects"></a>

Redirect planning should begin with a priority URL set. A store may have thousands or millions of historical URLs, but not all of them carry the same business or SEO value. Reviewing every path with equal depth can waste effort while the most important URLs receive too little attention.

A priority URL set usually includes:

* product pages with organic traffic, sales history, backlinks, or campaign value;
* category, collection, or department pages that support discovery and revenue;
* CMS Pages and Blog Posts with search value, customer education value, or brand importance;
* landing pages used in paid campaigns, email campaigns, affiliates, partnerships, or seasonal promotions;
* pages with strong external links or frequent customer bookmarks;
* pages that appear in important menus, guides, buying paths, or internal-link structures;
* pages that will be merged, renamed, discontinued, or rebuilt during migration.

The priority set does not need to include every old URL at the beginning. It should include the URLs where a broken path, weak redirect, or poor destination would create a measurable business problem.

### Map Old URLs to Relevant New Destinations <a href="#map-old-urls-to-relevant-new-destinations" id="map-old-urls-to-relevant-new-destinations"></a>

The strongest redirect model is path-to-path continuity. Each important old URL should be mapped to the most relevant new destination based on page purpose, not only on URL similarity.

| Old URL type                | Preferred destination                                                         | Planning risk                                                        |
| --------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Product page                | Matching new product page                                                     | Product is renamed, merged, discontinued, or represented differently |
| Category or collection page | Matching new category, collection, or closest browse destination              | Category hierarchy or collection logic changes                       |
| CMS Page                    | Matching new CMS Page or equivalent content page                              | Content is merged, rewritten, or omitted                             |
| Blog Post                   | Matching new Blog Post or consolidated content destination                    | Blog structure, authoring system, or slug pattern changes            |
| Campaign page               | Current equivalent campaign or landing page                                   | Campaign expires or moves into a new promotional structure           |
| Discontinued product        | Replacement product, parent category, or relevant collection when appropriate | Forced redirect creates a weak customer experience                   |

The practical question is: if a customer or search engine reaches this old path after launch, where should that request land so the destination still makes sense?

A technically working redirect is not enough if the destination no longer matches the old intent. An old product URL that redirects to a generic homepage may avoid a visible 404, but it does not preserve the customer journey. A high-value category URL that redirects to a broad, unrelated collection may also weaken continuity because the visitor no longer reaches the expected browse context.

### Avoid Weak Redirect Patterns <a href="#avoid-weak-redirect-patterns" id="avoid-weak-redirect-patterns"></a>

Some redirect patterns look efficient but create poor outcomes. They may reduce the number of broken links while weakening traffic quality, customer trust, and search continuity.

Weak redirect patterns include:

* redirecting many priority product pages to the homepage;
* redirecting old category pages to broad destinations that do not match the original browse intent;
* redirecting discontinued products to unrelated products only because they are available;
* redirecting CMS Pages or Blog Posts to generic information pages;
* creating redirect chains where an old URL points to an intermediate URL before reaching the final page;
* using temporary redirects where permanent redirects are required for a stable move;
* leaving internal links to rely on redirects instead of updating them where practical;
* applying broad pattern rules without checking high-value exceptions.

Homepage redirects may be acceptable for a small number of low-value expired pages where no useful destination exists. They should not become the default for pages with traffic, backlinks, sales history, customer-intent value, or campaign relevance.

### Plan for Pages Without Exact Equivalents <a href="#plan-for-pages-without-exact-equivalents" id="plan-for-pages-without-exact-equivalents"></a>

Not every old URL will have a one-to-one replacement. Products may be retired. Categories may be merged. Campaigns may end. Content may be consolidated. A clean redirect plan needs decision rules for these cases instead of forcing every path into a weak destination.

When no exact equivalent exists, consider:

* a replacement product when the customer intent remains close;
* a parent category or collection when the product is no longer available;
* a consolidated guide, CMS Page, or Blog Post when content has been merged;
* a current campaign or promotion when an old landing page has ended;
* a clear customer-facing alternative when the old page purpose still matters;
* no redirect when there is no relevant destination and forcing one would mislead customers.

The decision should balance reachability and relevance. Avoiding a 404 is not always better than sending users to an unrelated page. For priority URLs, the stronger destination is the one that preserves the most useful customer intent.

### Separate Domain Changes From Path Changes <a href="#separate-domain-changes-from-path-changes" id="separate-domain-changes-from-path-changes"></a>

A migration may involve a domain change, a path change, or both. These are different planning problems.

A domain change affects the site address, such as moving from one domain, subdomain, or regional structure to another. Domain continuity requires confirming that requests to the old domain reach the correct new site and that ownership, DNS, SSL, hosting, and launch routing are handled properly.

A path change affects individual page locations within the domain. Path continuity requires mapping old product, category, CMS Page, Blog Post, and campaign paths to relevant new destinations.

Many migration projects over-focus on the domain move and under-plan the page-level paths. Customers and search engines often land directly on product, category, content, and campaign URLs rather than the homepage. For SEO and traffic continuity, path-level planning usually needs the deeper review.

### Confirm Target Platform Redirect Capabilities <a href="#confirm-target-platform-redirect-capabilities" id="confirm-target-platform-redirect-capabilities"></a>

Redirect planning must match what the Target Platform can actually support. Some platforms provide native redirect management. Others may require an app, plugin, module, server-level configuration, CDN rule, hosting rule, or Custom Service review.

Before finalizing launch readiness, confirm whether the Target Platform can support:

* permanent redirects for changed URLs;
* bulk redirect import or manageable redirect creation;
* product, category, CMS Page, Blog Post, and campaign path mapping;
* multilingual, regional, store-view, or multi-store URL behavior;
* redirects from old filter, tag, or faceted paths when those paths matter;
* avoidance of redirect chains and loops;
* pre-launch testing of priority redirects;
* post-launch updates if unexpected old URLs appear in traffic data.

If standard platform capability cannot support the required redirect outcome, the project may need additional technical planning. Add-ons may support mapping or configuration needs in specific cases. Custom Service applies when the requirement involves broader customization, Custom Platform handling, unsupported extension data, outside-system identifiers, or custom migration logic adjustment.

### Clean Internal Links Instead of Relying Only on Redirects <a href="#clean-internal-links-instead-of-relying-only-on-redirects" id="clean-internal-links-instead-of-relying-only-on-redirects"></a>

Redirects help old URLs recover. They should not become a substitute for clean internal links. A migrated store should not unnecessarily keep pointing customers and crawlers through old paths when the correct new paths are known.

Internal-link cleanup should include:

* main navigation and footer links;
* category, collection, and product links;
* links inside product descriptions, category copy, CMS Pages, and Blog Posts;
* promotional banners, image links, and landing-page blocks;
* related-product, upsell, cross-sell, and recommendation pathways;
* links used in store policies, buying guides, help content, and brand pages;
* campaign links that remain active after launch.

Priority internal links should point directly to final URLs wherever practical. This reduces unnecessary redirect hops, improves customer experience, and makes the new store structure clearer.

### Validate Redirects Before and After Launch <a href="#validate-redirects-before-and-after-launch" id="validate-redirects-before-and-after-launch"></a>

Redirect validation should focus on the URLs that matter most. A launch can pass broad technical checks while still failing on the pages that carry the most traffic or revenue.

Before launch, test whether:

* priority old URLs reach the intended new destinations;
* product URLs resolve to the correct product pages;
* category and collection URLs preserve browse intent;
* CMS Pages and Blog Posts reach equivalent or intentionally consolidated content;
* campaign landing pages still support active campaigns;
* redirects do not create chains, loops, or irrelevant destinations;
* internal links point to final URLs where practical;
* multilingual, regional, or store-view URLs behave as expected;
* important pages return the expected live status in the Target Platform environment.

After launch, monitor for unexpected 404s, high-value old URLs that were missed, redirect chains, traffic drops to priority pages, and search-console signals related to moved or unavailable URLs. Post-launch monitoring should not replace pre-launch planning, but it is useful for catching paths that historical exports or planning files missed.

### Conclusion <a href="#conclusion" id="conclusion"></a>

URL structure changes are normal during e-commerce platform migration, but unmanaged URL changes can weaken traffic continuity even when store data has migrated successfully. The safest approach is to identify priority old URLs, map them to relevant new destinations, confirm Target Platform redirect capability, clean important internal links, and validate the result before launch.

Redirect planning should protect customer intent, not simply suppress broken paths. A strong redirect plan makes important old URLs lead to useful new pages, avoids weak generic destinations, and gives the migrated store a cleaner foundation for traffic, search visibility, and customer trust.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Should every old URL be redirected during migration?**

Not always. Priority URLs with traffic, backlinks, revenue value, campaign use, or customer-intent value should be reviewed carefully. Low-value historical URLs may not need the same level of manual mapping, especially when no relevant destination exists.

**Is redirecting old URLs to the homepage acceptable?**

It can be acceptable for a small number of low-value expired pages where no better destination exists. It should not be the default for priority product, category, content, or campaign URLs because it usually breaks the original customer intent.

**What is the best redirect destination for a discontinued product?**

The best destination depends on customer usefulness. A replacement product, parent category, related collection, or clear alternative may be appropriate. An unrelated product or generic homepage redirect is usually weak for high-value product URLs.

**Do redirects preserve SEO by themselves?**

No. Redirects preserve reachability, but they do not guarantee page quality, destination relevance, internal-link strength, metadata quality, or commercial usefulness. Priority destinations still need page-level review.

**When should redirect planning start?**

Redirect planning should start before launch planning becomes fixed. Priority URL exports, destination mapping, platform capability checks, internal-link cleanup, and pre-launch validation all need time for review and correction.
