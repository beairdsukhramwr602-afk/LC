# Metadata, Custom Fields, and Extensions

A migration can look successful on the storefront and still fail where the business actually depends on it.

That usually happens when important store meaning lives outside the default product, customer, order, or content model. Many stores rely on metadata, custom fields, apps, plugins, modules, and extensions to hold product specifications, visibility logic, operational identifiers, fulfillment behavior, customer eligibility, reporting signals, or other business-critical information. When that layer is not preserved correctly, core records may still move while the store behaves differently after launch.

The most important data in a store is not always the most visible data. Some values only need to appear for reference. Others must continue controlling storefront display, filtering, pricing, automation, segmentation, operational workflows, or external-system recognition. A migration should therefore be judged by what those values must still do after launch, not only by whether they appear somewhere in the Target Platform.

### What metadata and custom fields usually represent <a href="#what-metadata-and-custom-fields-usually-represent" id="what-metadata-and-custom-fields-usually-represent"></a>

Metadata and custom fields often hold business meaning that the default platform model does not fully express.

Common examples include:

* product specifications added outside the default product model
* product badges, labels, compatibility notes, care instructions, or sizing details
* customer fields tied to wholesale, VAT, loyalty, approval, or account-status logic
* order metadata needed for invoices, shipping, subscriptions, returns, or reporting
* custom pricing indicators or rule inputs
* product videos, attachments, downloadable files, or media relationships added outside the default model
* external-system identifiers used by ERP, CRM, automation, fulfillment, PIM, marketplace, or reporting systems

Some of this information is informational only. Some of it controls behavior. That distinction is one of the most important planning questions in a metadata-heavy migration.

### The key question is not only whether the field can be stored <a href="#the-key-question-is-not-only-whether-the-field-can-be-stored" id="the-key-question-is-not-only-whether-the-field-can-be-stored"></a>

A Target Platform can often store additional values somewhere. That does not automatically preserve the field’s original meaning.

The more important questions are:

* Does the field still control the behavior it controlled before?
* Does the storefront still display the information where customers need it?
* Do filters, search, merchandising, or personalization rules still understand the field?
* Do connected systems still recognize the identifiers they depend on?
* Do support, fulfillment, pricing, segmentation, reporting, or approval workflows still behave as expected?

A field can survive migration technically while failing commercially or operationally. That is why metadata and custom fields should be evaluated through outcomes, not only through field presence.

### Informational metadata and behavior-driving metadata are different <a href="#informational-metadata-and-behavior-driving-metadata-are-different" id="informational-metadata-and-behavior-driving-metadata-are-different"></a>

A useful planning distinction is whether the field only stores context or whether it still needs to control something after launch.

#### Informational metadata <a href="#informational-metadata" id="informational-metadata"></a>

Informational metadata is preserved for reference, lookup, content completeness, historical context, or internal administration. It can still matter, but the business risk is usually lower if the field does not drive storefront or workflow behavior.

Examples include internal notes, care instructions, secondary specifications, supplier references, or historical labels that staff may need after launch.

#### Behavior-driving metadata <a href="#behavior-driving-metadata" id="behavior-driving-metadata"></a>

Behavior-driving metadata must continue controlling an outcome after launch. It can affect:

* pricing
* visibility
* eligibility
* filtering
* search relevance
* personalization
* tax treatment
* fulfillment steps
* automation triggers
* customer-specific experiences
* external-system matching or reporting behavior

Behavior-driving metadata usually carries more migration risk because it depends on how the Target Platform, theme, app stack, and connected systems interpret the field after the move.

### Why extension-driven meaning becomes risky <a href="#why-extension-driven-meaning-becomes-risky" id="why-extension-driven-meaning-becomes-risky"></a>

Many stores use apps, plugins, modules, or custom extensions because the native platform model does not fully match how the business works.

That added flexibility is useful, but it can distribute important meaning across several layers:

* extension-managed fields
* module-specific tables or structures
* theme-driven output
* custom role or membership systems
* app-based pricing, filtering, or visibility logic
* external-system identifiers
* automation rules outside default entity handling
* custom source behavior that the Target Platform does not reproduce natively

In those cases, migration may preserve the main record while leaving behind the logic that made the record useful. A product can move without the extension-managed specifications that power filters. A customer can move without the metadata that controls wholesale eligibility. An order can move without operational metadata needed by downstream systems.

### Where metadata problems usually appear <a href="#where-metadata-problems-usually-appear" id="where-metadata-problems-usually-appear"></a>

Metadata and extension-related issues usually appear in a few recurring forms.

#### The field survives, but not in usable form <a href="#the-field-survives-but-not-in-usable-form" id="the-field-survives-but-not-in-usable-form"></a>

A value may exist in the Target Platform while no longer being readable by the theme, app, extension, workflow, or external system that previously depended on it.

#### The field is preserved, but behavior changes <a href="#the-field-is-preserved-but-behavior-changes" id="the-field-is-preserved-but-behavior-changes"></a>

This often happens when the Source Platform and Target Platform use different role systems, metadata structures, extension models, or theme expectations. The field exists, but it no longer drives the intended pricing, filtering, visibility, eligibility, or operational behavior.

#### The field matters because another system needs it <a href="#the-field-matters-because-another-system-needs-it" id="the-field-matters-because-another-system-needs-it"></a>

Some metadata is not important on the storefront at all. It matters because ERP, CRM, shipping, fulfillment, automation, marketplace, PIM, or reporting systems need exact identifiers or exact field logic after launch. If those values are missing, mismapped, renamed, or transformed incorrectly, business continuity weakens even when the storefront appears correct.

### The requirement is often transformation, not transfer <a href="#the-requirement-is-often-transformation-not-transfer" id="the-requirement-is-often-transformation-not-transfer"></a>

Sometimes the business does not only need the value moved. It needs the field reshaped, filtered, converted, normalized, or remapped so the Target Platform can preserve the intended outcome.

Common examples include:

* converting product attributes into Target Platform metafields or custom fields
* converting customer tags into customer groups, segments, or account states
* migrating only records that meet defined field-based criteria
* restructuring custom values so target-side filtering, display, or automation can use them
* remapping identifiers so connected systems continue to recognize records correctly
* separating one source field into multiple target fields
* merging several source values into a cleaner target-side structure

This is one of the clearest places where migration planning improves when the business describes what the field must still do after launch, instead of only listing which field should exist.

### When Custom Service becomes the right boundary <a href="#when-custom-service-becomes-the-right-boundary" id="when-custom-service-becomes-the-right-boundary"></a>

Metadata and custom fields do not automatically make a project Custom Service. Some values can fit within standard service capability or supported Add-on behavior, especially when they only need straightforward mapping or display-preserving handling.

Custom Service becomes the right boundary when the expected outcome depends on customization, modification, broader bespoke handling, or custom migration logic adjustment.

Common Custom Service signals include:

* custom fields are not part of the default supported model
* extension-managed data must continue controlling storefront or workflow behavior
* the Target Platform cannot use the source structure without transformation
* outside systems require exact identifiers or exact field logic
* filtering, segmentation, pricing, or visibility depends on custom structures
* a Custom Platform or heavily customized platform is involved
* the requirement needs field conversion, restructuring, conditional handling, or non-standard interpretation

Add-ons may help when the need is focused on filtering, mapping, or data configuration within available settings and supported behavior. Tailored Add-ons, Custom Add-ons, and broader custom logic belong under Custom Service because they require customization or modification work.

### What to define before execution <a href="#what-to-define-before-execution" id="what-to-define-before-execution"></a>

Before approving a Full Migration, the business should define which added fields and extension-owned behaviors are truly important.

#### Which fields must continue to drive behavior after launch? <a href="#which-fields-must-continue-to-drive-behavior-after-launch" id="which-fields-must-continue-to-drive-behavior-after-launch"></a>

These are the highest-risk fields because they do more than store information. They influence pricing, filtering, visibility, eligibility, workflow behavior, or external-system continuity.

#### Which fields are only needed for reference? <a href="#which-fields-are-only-needed-for-reference" id="which-fields-are-only-needed-for-reference"></a>

This separates informational preservation from behavior-critical continuity. Informational fields still need review, but they usually do not require the same level of behavioral testing.

#### Which fields belong to native platform behavior, and which belong to apps, plugins, modules, or custom logic? <a href="#which-fields-belong-to-native-platform-behavior-and-which-belong-to-apps-plugins-modules-or-custom-l" id="which-fields-belong-to-native-platform-behavior-and-which-belong-to-apps-plugins-modules-or-custom-l"></a>

This distinction helps determine whether standard service capability is likely to be enough or whether extension-aware handling may be required.

#### Which outside systems depend on exact identifiers or exact field structure? <a href="#which-outside-systems-depend-on-exact-identifiers-or-exact-field-structure" id="which-outside-systems-depend-on-exact-identifiers-or-exact-field-structure"></a>

This is where hidden continuity risk often appears. A field may be invisible to shoppers but critical for ERP, CRM, fulfillment, automation, or reporting workflows.

#### Does the business need transfer, transformation, filtering, or remapping? <a href="#does-the-business-need-transfer-transformation-filtering-or-remapping" id="does-the-business-need-transfer-transformation-filtering-or-remapping"></a>

Those are materially different requirements. Transfer moves a value. Transformation changes its structure or meaning so the target environment can still use it. Filtering selects which records or values should move. Remapping connects source-side meaning to target-side representation.

### What to validate first <a href="#what-to-validate-first" id="what-to-validate-first"></a>

Metadata and custom fields should be validated through the outcomes they control, not only through field existence.

A practical first review should focus on:

* products with extension-driven specifications, labels, badges, compatibility notes, or filtering behavior
* customers with role, tier, wholesale, VAT, approval, loyalty, or segmentation logic
* orders that depend on operational metadata
* entities linked to external systems through identifiers
* fields that affect pricing, visibility, tax treatment, fulfillment, search, filtering, or workflow continuity
* any transformed field where the target structure differs from the source structure

The first validation questions should be:

* Does the field still appear where it is needed?
* Does it still drive the expected behavior?
* Do apps, extensions, themes, and connected systems still recognize it?
* If the field was transformed, does the new structure preserve the intended result?
* Can support and operations still rely on the field without manual workarounds?

A useful validation sample is usually representative rather than random. It should include the records where business meaning depends most heavily on non-standard handling. A Demo Migration can help expose whether the target environment can preserve that meaning before the project scales further.

### When standard handling may not be enough <a href="#when-standard-handling-may-not-be-enough" id="when-standard-handling-may-not-be-enough"></a>

Risk is higher when:

* key behavior depends on app-managed, plugin-managed, module-managed, or custom data
* important fields are not part of the default supported model
* outside systems require exact identifiers
* filtering or segmentation depends on custom structures
* the Target Platform can store values but not use them in the same way
* the requirement involves transformation, filtering, or remapping rather than simple transfer

In these situations, the issue is not only whether the data can move. It is whether the Target Platform and connected systems can still use that data clearly enough through standard service capability alone.

If the main need is stronger execution support and closer review within standard service capability, Managed Service may be appropriate. If the required outcome depends on transformation, non-standard structures, Custom Platform handling, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment, Custom Service is the clearer path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Metadata, custom fields, and extensions are one of the clearest examples of how a migration can look complete while the store still behaves differently in the places that matter most. The issue is not only whether extra fields survive. It is whether the Target Platform still understands those fields well enough to preserve pricing, visibility, eligibility, workflow behavior, reporting, and connected-system continuity after launch.

The safest way to reduce that risk is to separate informational metadata from behavior-driving metadata, identify which fields live outside native platform behavior, and validate representative high-impact cases through the outcomes those fields control rather than through field presence alone. When that work is done early, hidden continuity risk becomes easier to judge before broader launch commitments are made.

Review the fields and extension-owned behaviors that still need to drive something important after launch, not just the values that appear in administration. If the target representation may weaken field meaning, extension logic, or connected-system usability, Live Chat is a practical way to clarify whether standard service capability is enough or whether Custom Service should be reviewed.

### FAQs <a href="#faqs" id="faqs"></a>

**Why can a custom field survive migration while the store still behaves differently?**

Because field survival is not the same as behavioral continuity. The field may still exist, but it may no longer drive pricing, filtering, visibility, workflow logic, or connected-system behavior in the same way.

**What is the difference between informational metadata and behavior-driving metadata?**

Informational metadata is mainly preserved for reference or context. Behavior-driving metadata still needs to control something important after launch, such as eligibility, visibility, automation, tax treatment, pricing, filtering, or external-system recognition.

**Do custom fields always require Custom Service?**

No. Some custom fields can be handled within standard service capability or supported Add-on behavior when the required outcome is straightforward. Custom Service becomes relevant when the field requires customization, transformation, Custom Platform handling, extension-aware logic, custom migration logic adjustment, or other non-standard handling.

**What should be reviewed first in metadata-heavy stores?**

Start with the fields that control real outcomes: extension-driven product specifications, customer roles or tiers, operational order metadata, exact identifiers for external systems, and any field set that affects pricing, visibility, tax treatment, filtering, or workflow continuity.
