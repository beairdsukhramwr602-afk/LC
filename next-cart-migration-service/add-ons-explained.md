# Add-ons

Add-ons are optional service features that give customers more control over focused parts of a Next-Cart migration. They are useful when the selected migration path is supported, but the customer needs additional control over which store data is migrated, how source-store values are mapped into the Target Platform, or how selected data values should be configured before they appear in the target store.

Add-ons should be understood as focused migration enhancements, not as a general label for every custom requirement. A Standard Add-on can support common filtering, mapping, or configuration needs when its available settings and supported behavior are enough. When the expected result requires modified logic, project-specific handling, or an Add-on that does not exist as a standard option, the requirement should be reviewed through Custom Service.

### What Add-ons Help Customers Control <a href="#what-add-ons-help-customers-control" id="what-add-ons-help-customers-control"></a>

A migration can be technically supported and still need more control over how store data is selected, interpreted, or adjusted. Add-ons help customers handle those focused decisions before migration execution, especially when the expected target-store result depends on more than moving all scanned records with default settings.

Add-ons are most useful when customers need to answer questions such as:

* Should all scanned records migrate, or should only selected records move to the target store?
* Do source-store values need more deliberate mapping into the Target Platform?
* Do selected data values need to be adjusted before or during migration?
* Does the target store require a cleaner data arrangement than the default migration configuration would produce?
* Can the expected result be achieved through an available Add-on, or does it require custom handling?

A strong Add-on requirement describes the expected outcome clearly. For example, “migrate only orders created after January 1, 2025” is more actionable than “migrate fewer orders.” “Map source order statuses into these target-store statuses” is more useful than “fix order statuses.” Add-ons work best when the customer can identify what should be filtered, mapped, configured, or adjusted and why that result matters for the target store.

### Standard Add-ons Currently Available <a href="#standard-add-ons-currently-available" id="standard-add-ons-currently-available"></a>

Next-Cart currently provides three Standard Add-ons:

| Standard Add-on         | Main purpose                                                             | Typical use case                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Select which source-store records should be migrated.                    | Migrating only selected products, orders, customers, or content records instead of all scanned records.               |
| Advanced Data Mapping   | Control how source-store values should map into target-store structures. | Aligning customer groups, order statuses, attributes, or other supported values with the Target Platform.             |
| Advanced Data Configure | Adjust selected data values before or during migration.                  | Normalizing, changing, or preparing selected values so the migrated data better fits the intended target-store setup. |

These Standard Add-ons can be used with Standard Service, Managed Service, or Custom Service when their available settings and supported behavior fit the migration requirement.

#### Data Filter Add-on <a href="#data-filter-add-on" id="data-filter-add-on"></a>

The Data Filter Add-on helps customers migrate selected source-store records instead of migrating all scanned records by default.

This Add-on is useful when the customer wants to limit migration scope based on clear business criteria, such as:

* products from selected categories;
* orders from a specific time range;
* customers matching defined conditions;
* CMS Pages, Blog Posts, or other content records needed for the new store plan;
* selected records for a staged migration or partial migration strategy.

The Data Filter Add-on is especially important because purchase estimates are not migration filters. Entity counts entered during purchase support Entity Points Plan selection and pricing. They do not instruct the migration process to move only that number of records. If the customer wants only selected records to move, filtering should be planned before execution.

#### Advanced Data Mapping <a href="#advanced-data-mapping" id="advanced-data-mapping"></a>

Advanced Data Mapping helps customers control how source-store values are mapped into target-store structures within the supported capability of the Source Platform, Target Platform, and selected migration path.

This Add-on is useful when default mapping needs more deliberate control, such as:

* aligning source values with target-supported fields;
* mapping customer groups more carefully;
* mapping order statuses more deliberately;
* aligning selected attributes with target-supported structures;
* adjusting how source-store values should be interpreted in the target store.

Advanced Data Mapping does not remove Target Platform limitations. It helps create a more controlled result within what the Target Platform can reasonably represent.

#### Advanced Data Configure <a href="#advanced-data-configure" id="advanced-data-configure"></a>

Advanced Data Configure helps customers adjust selected data values so the migrated data better fits the intended target-store setup.

This Add-on is useful when the customer knows which values should change and why the change matters. Examples may include:

* normalizing selected field values;
* updating labels or values before migration;
* adjusting selected data content for the target-store environment;
* applying planned data modifications during migration.

Advanced Data Configure should not be treated as a vague cleanup request. It works best when the customer can identify the data to adjust, the desired value or rule, and the reason the adjustment is needed.

### Standard, Tailored, and Custom Add-ons <a href="#standard-tailored-and-custom-add-ons" id="standard-tailored-and-custom-add-ons"></a>

Next-Cart uses three Add-on categories so customers can distinguish between ready-made service features and project-specific Add-on work.

| Add-on category  | What it means                                                                                    | How it is handled                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Standard Add-ons | Ready-made optional service features available when the default capability fits the requirement. | Can be used with Standard Service, Managed Service, or Custom Service. |
| Tailored Add-ons | Modified versions of Standard Add-ons created for a specific requirement.                        | Handled through Custom Service because modification work is required.  |
| Custom Add-ons   | Project-specific Add-ons requested when available Standard Add-ons do not fit the requirement.   | Reviewed and quoted through Custom Service.                            |

A Standard Add-on is enough when the customer’s intended result can be achieved through the Add-on’s available settings and supported behavior. Using a Standard Add-on within its available capability does not automatically make the migration a Custom Service case.

A Tailored Add-on is needed when a Standard Add-on is close to the desired result but must be modified, expanded, or adjusted to support the customer’s requirement. Examples include filtering logic more complex than the Data Filter Add-on supports by default, mapping logic beyond standard Advanced Data Mapping behavior, or data configuration rules that require modification beyond the standard Add-on.

A Custom Add-on is used when none of the available Standard Add-ons fit the required outcome. It is not merely a modified version of a listed Add-on. It is a new or project-specific service feature reviewed according to the customer’s expected result, data structure, migration path, and technical complexity.

### Configuration Support and Add-on Modification <a href="#configuration-support-and-add-on-modification" id="configuration-support-and-add-on-modification"></a>

Configuration support and Add-on modification are different.

Configuration support applies when an available Add-on can already produce the intended result, but the customer needs help understanding, correcting, or reviewing the Add-on settings. For example, if a customer selects the Data Filter Add-on and sets a filter condition incorrectly, support may help review the setting. The Add-on remains standard because its existing capability is enough.

Add-on modification applies when the Add-on itself must be changed, expanded, or tailored to produce a result that the standard version does not support. Modification requires Custom Service review because the work changes the standard Add-on behavior or creates project-specific logic.

This distinction matters for planning and pricing. A customer may need help configuring a Standard Add-on without needing Custom Service. A customer may also have a requirement that sounds like a standard Add-on request but actually needs Tailored Add-on or Custom Add-on handling because the available behavior is not enough.

### Add-ons and Custom Service Boundaries <a href="#add-ons-and-custom-service-boundaries" id="add-ons-and-custom-service-boundaries"></a>

Add-ons solve focused feature-level needs. Custom Service handles broader requirements where the migration approach, migration logic, unsupported data, or project-specific handling must be customized.

Some needs belong directly under Custom Service rather than the Add-on feature set, such as:

* Custom Platform as the Source Platform or Target Platform;
* third-party app, plugin, module, or extension data;
* custom fields outside standard supported handling;
* outside-system identifiers;
* custom migration logic adjustment;
* platform capability limitations requiring bespoke handling;
* unsupported source-store structures;
* requirements where the migration approach itself must be tailored.

Add-ons and Custom Service can still work together. A Custom Service plan may include a Standard Add-on, Tailored Add-on, or Custom Add-on when that Add-on supports part of the required result. The important distinction is that Add-ons focus on filtering, mapping, or configuration needs, while Custom Service covers the broader customized scope when the standard migration approach is not enough.

### How Add-ons Affect Pricing and Service Responsibility <a href="#how-add-ons-affect-pricing-and-service-responsibility" id="how-add-ons-affect-pricing-and-service-responsibility"></a>

A Standard Add-on has a default price. When selected, that price is added to the migration total. The Add-on price is separate from Entity Points Plan capacity, which defines counted migration capacity for Product, Customer, Order, and Blog Posts data.

If a Standard Add-on needs modification, the tailored version is quoted through Custom Service. If the customer already purchased the Standard Add-on and later needs a tailored version, the customer pays only the top-up difference between the default Add-on price and the tailored quote.

For example:

| Pricing item          | Amount |
| --------------------- | ------ |
| Standard Add-on price | $50    |
| Tailored Add-on quote | $75    |
| Top-up amount         | $25    |

Custom Add-ons are quoted individually because the expected result, data structure, migration path, and required work can vary.

Add-ons affect how the migration is configured and performed, but they do not decide who performs the migration by themselves. With Standard Service, the customer performs migration actions and uses purchased Add-ons within the available service flow. With Managed Service, Next-Cart experts can integrate purchased Add-ons based on the customer’s request and agreed service scope. With Custom Service, Add-ons may be included as part of a broader custom plan, especially when the Add-on is tailored or created as a Custom Add-on.

Customers of any service model can access and perform available migration actions manually if they choose. The selected service model determines responsibility, expert handling, and service scope, not whether the customer can access the purchased service license.

### How to Decide Whether an Add-on Is Needed <a href="#how-to-decide-whether-an-add-on-is-needed" id="how-to-decide-whether-an-add-on-is-needed"></a>

A customer should consider Add-ons when the migration needs focused control over filtering, mapping, or data configuration. The decision should start from the target-store outcome, not only from the Add-on name.

Useful questions include:

| Decision question                                                                                   | What the answer may indicate                              |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Should all scanned records migrate, or only selected records?                                       | The Data Filter Add-on may be needed.                     |
| Do source-store values need more controlled mapping into the Target Platform?                       | Advanced Data Mapping may be needed.                      |
| Do selected data values need to be adjusted before migration?                                       | Advanced Data Configure may be needed.                    |
| Can the expected result be handled through available settings and supported behavior?               | A Standard Add-on may be enough.                          |
| Does the expected result require modification beyond the standard Add-on?                           | A Tailored Add-on may be required through Custom Service. |
| Is the needed Add-on unavailable as a Standard Add-on?                                              | A Custom Add-on may be reviewed through Custom Service.   |
| Does the requirement involve unsupported data, Custom Platform handling, or custom migration logic? | Broader Custom Service review may be needed.              |

The clearest Add-on decisions come from defining the desired result before purchase or execution. Customers should identify what should be filtered, mapped, configured, or adjusted; which store data is affected; and how the target-store result should look after migration.

### Common Add-on Misunderstandings <a href="#common-add-on-misunderstandings" id="common-add-on-misunderstandings"></a>

#### “Entity counts entered during purchase filter the migration.” <a href="#entity-counts-entered-during-purchase-filter-the-migration" id="entity-counts-entered-during-purchase-filter-the-migration"></a>

No. Entered counts support Entity Points Plan selection and pricing. They do not automatically limit which records are migrated. Filtering should be planned through the Data Filter Add-on or reviewed as custom filtering scope when standard filtering capability is not enough.

#### “Using any Add-on means the migration needs Custom Service.” <a href="#using-any-add-on-means-the-migration-needs-custom-service" id="using-any-add-on-means-the-migration-needs-custom-service"></a>

No. A Standard Add-on can be used with Standard Service, Managed Service, or Custom Service when its available settings and supported behavior fit the requirement. Custom Service becomes relevant when the Add-on must be modified, a Custom Add-on is requested, or the broader migration requirement needs bespoke handling.

#### “Advanced Data Mapping can force the Target Platform to support any source structure.” <a href="#advanced-data-mapping-can-force-the-target-platform-to-support-any-source-structure" id="advanced-data-mapping-can-force-the-target-platform-to-support-any-source-structure"></a>

No. Advanced Data Mapping helps control supported mapping behavior. It does not remove the Target Platform’s data model, capability, or structural limitations.

#### “Advanced Data Configure is general data cleanup.” <a href="#advanced-data-configure-is-general-data-cleanup" id="advanced-data-configure-is-general-data-cleanup"></a>

No. Advanced Data Configure is most useful when the customer knows which data values should be adjusted and what the intended result should be. Vague cleanup requests may require closer review before the right service path can be identified.

#### “Custom Add-ons and Tailored Add-ons are the same.” <a href="#custom-add-ons-and-tailored-add-ons-are-the-same" id="custom-add-ons-and-tailored-add-ons-are-the-same"></a>

No. A Tailored Add-on modifies a Standard Add-on. A Custom Add-on is a project-specific Add-on requested when the available Standard Add-ons do not fit the requirement.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Add-ons give customers focused control over filtering, advanced mapping, and data configuration needs during migration. The current Standard Add-ons are the Data Filter Add-on, the Advanced Data Mapping, and the Advanced Data Configure. They can support Standard Service, Managed Service, or Custom Service when their available settings and supported behavior fit the requirement.

When a Standard Add-on needs modification, the requirement becomes a Tailored Add-on and is handled through Custom Service. When the available Standard Add-ons do not fit the expected result, the customer can request a Custom Add-on, which is also reviewed and quoted through Custom Service.

Add-ons are most effective when the customer can clearly describe the intended target-store result. If the available Add-ons do not clearly match the expected outcome, Live Chat can help clarify whether the right next step is a Standard Add-on, Tailored Add-on, Custom Add-on, or broader Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**What are Add-ons?**

Add-ons are optional service features that help customers control focused migration needs such as data filtering, advanced mapping, or data configuration.

**Which Standard Add-ons are currently available?**

The current Standard Add-ons are Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure.

**Can Add-ons be used with every service model?**

Yes. Standard Add-ons can be used with Standard Service, Managed Service, and Custom Service when their available settings and supported behavior fit the requirement.

**Does using a Standard Add-on make my migration a Custom Service case?**

No. Using a Standard Add-on within its available settings and supported behavior does not automatically make the migration a Custom Service case.

**What is a Tailored Add-on?**

A Tailored Add-on is a modified version of a Standard Add-on. It is handled through Custom Service because customization or modification work is required.

**What is a Custom Add-on?**

A Custom Add-on is a new or project-specific Add-on requested when the available Standard Add-ons do not fit the customer’s requirement. It is reviewed and quoted through Custom Service.

**When does an Add-on require Custom Service?**

An Add-on requires Custom Service when it needs modification beyond its available settings and supported behavior, or when the customer requests a Custom Add-on that is not currently available.

**Is Add-on pricing the same as Entity Points pricing?**

No. Entity Points Plans define counted migration capacity. Add-ons are optional service features added when the customer needs filtering, advanced mapping, or data configuration support.
