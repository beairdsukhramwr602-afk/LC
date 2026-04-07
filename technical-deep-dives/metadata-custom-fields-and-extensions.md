# Metadata, Custom Fields, and Extensions

A migration can look successful on the storefront and still fail where the business actually depends on it.

That usually happens when important store meaning lives outside the default product, customer, order, or content model. Many stores rely on metadata, custom fields, plugins, apps, modules, and extensions to carry pricing rules, product specifications, visibility logic, operational identifiers, fulfillment behavior, customer eligibility, reporting signals, or other business-critical information. When that added layer is not preserved correctly, the core records may still migrate while the store behaves differently after launch.

This matters because the most important data in a store is not always the most visible data. Some fields exist mainly so the storefront can display the right information. Others exist so outside systems, workflows, or rules continue to operate correctly. A migration, therefore, needs to be judged by what the data must still do after launch, not only by whether it appears somewhere in the target environment.

### What metadata and custom fields usually represent

Metadata and custom fields often hold business meaning that the default platform model does not fully express.

Common examples include:

* product specifications added by extensions
* customer fields tied to wholesale, VAT, loyalty, or approval logic
* order metadata needed for invoices, shipping, subscriptions, or reporting
* custom price types
* product videos, attachments, or media relationships added outside the default model
* external-system identifiers used by ERP, CRM, automation, fulfillment, or reporting tools

Some of this information is informational only. Some of it drives storefront behavior, customer eligibility, operational workflows, or outside-system continuity. That distinction is one of the most important planning questions in a migration project.

### The key question is not “Can we store it?”

A target platform can often store additional values somewhere.

That is not the same as preserving their original meaning.

The more important questions are:

* does the field still control the behavior it used to control?
* does the store still display the information where customers need it?
* do connected systems still recognize the identifiers they depend on?
* do support, fulfillment, pricing, segmentation, or reporting workflows still behave as expected?

A field can therefore survive migration technically while failing commercially or operationally. That is why metadata should be evaluated through outcomes, not just field presence.

### Informational metadata and behavior-driving metadata are not the same

A useful planning distinction is:

#### Informational metadata

These are values the business wants preserved for reference, lookup, context, or historical completeness. They may matter, but they do not necessarily need to continue driving storefront or workflow behavior.

#### Behavior-driving metadata

These are values that must continue to control something important after launch, such as:

* pricing
* visibility
* eligibility
* filtering
* tax treatment
* fulfillment steps
* automation triggers
* customer-specific experiences
* external-system matching or reporting behavior

Behavior-driving metadata usually carries more migration risk because it depends on how the target platform and extension stack interpret the field after the move.

### Why extension-driven meaning becomes risky

Many stores rely on extensions because the native platform model is not enough for the business.

That added flexibility is valuable, but it also means important meaning may be distributed across:

* plugin-managed fields
* module-specific structures
* theme-driven output
* custom role systems
* app-based pricing or visibility logic
* external-system identifiers
* rule layers that sit outside default entity handling

In those cases, a migration may preserve the main entity record while leaving behind the logic that made the record useful. A product can migrate without the extension-driven specifications that support filtering. A customer can migrate without the metadata that controls pricing or account eligibility. An order can migrate without the operational metadata that downstream systems need to function correctly.

### Where the most common problems appear

Metadata and extension-related issues usually appear in a few recurring forms.

#### The field survives, but not in usable form

A value may exist in the target store while no longer being readable by the theme, extension, or workflow that previously depended on it.

#### The field is preserved, but behavior changes

This often happens when the source and target platforms use different role systems, metadata structures, or extension expectations. The field exists, but it no longer drives the intended pricing, filtering, visibility, or operational behavior.

#### The field matters only because another system needs it

Some metadata is not important on the storefront at all. It matters because ERP, CRM, shipping, fulfillment, automation, or reporting systems need exact identifiers or exact field logic after launch. If those values are missing, mismapped, or transformed incorrectly, business continuity weakens even when the storefront appears fine.

### The requirement is really transformation, not transfer

Sometimes the business does not just need the field moved. It needs the field reshaped, filtered, converted, or remapped so the target environment can preserve the intended outcome.

Common examples include:

* converting product attributes into categories
* converting customer tags into customer groups
* migrating only entities that meet defined criteria
* changing how custom values are structured so target-side behavior still works
* remapping identifiers so connected systems continue to recognize the record correctly

This is one of the clearest places where migration planning improves when the business describes what the field must still do after launch, rather than only listing what field should exist.

### What a Custom Job usually addresses

A Custom Job becomes relevant when standard handling can move records but cannot reliably preserve the result the business needs.

Common Custom Job patterns include:

* migrating custom fields for a specific entity type
* customizing default fields during migration
* filtering entities according to defined criteria
* transforming values so they continue to support the intended business outcome after launch

This is especially relevant when:

* custom fields affect storefront behavior
* extension-managed data matters operationally
* non-standard structures do not translate cleanly
* transformation rules are needed to preserve meaning
* identifiers must remain usable for connected systems

### What merchants should define before execution

Before approving a full migration, the business should be able to define which added fields and extension-owned behaviors are truly important.

The most important questions are:

#### 1. Which fields must continue to drive behavior after launch?

These are the highest-risk fields because they do more than store information.

#### 2. Which fields are only needed for reference?

This helps separate informational preservation from behavior-critical continuity.

#### 3. Which fields belong to native platform behavior, and which belong to extensions or custom logic?

This distinction usually determines whether standard handling is likely to be enough.

#### 4. Which outside systems depend on exact identifiers or exact field structure?

This is often where hidden continuity risk appears.

#### 5. Does the business need transfer, transformation, filtering, or remapping?

Those are materially different requirements and should be defined early.

### What to validate first

Metadata and custom fields should be validated through the outcomes they control, not only through field existence.

A practical first review should focus on:

* products with extension-driven specifications or filtering behavior
* customers with role, tier, wholesale, VAT, or approval logic
* orders that depend on operational metadata
* entities linked to external systems through identifiers
* any field set that affects pricing, visibility, tax treatment, or workflow continuity

The first questions to ask are:

* does the field still appear where it is needed?
* does it still drive the expected behavior?
* do extensions and connected systems still recognize it?
* if the field was transformed, does the new structure preserve the intended result?
* can support and operations still rely on it without manual workarounds?

A useful validation sample is usually representative rather than random. It should include the fields and entities where business meaning depends most heavily on non-standard handling. A Demo Migration is often the fastest way to expose whether the target environment can preserve that meaning before the project scales further.

### When standard handling may not be enough

Not every store with custom fields requires bespoke handling. But some signals should raise the threshold for confidence.

Risk is higher when:

* key behaviors depend on extension-managed data
* important fields are not part of the default supported model
* outside systems require exact identifiers
* filtering or segmentation depends on custom structures
* the target platform can store the values but not use them in the same way
* the requirement involves transformation, filtering, or remapping rather than simple transfer

In those situations, the real issue is not whether the data can move. It is whether the target store and connected systems can preserve the same behavior clearly enough through standard handling alone.

If the main need is stronger expert execution and more controlled review of behavior-driving metadata, Managed Migration Service may be sufficient. If preserving the intended result depends on transformation, identifier-sensitive continuity, non-standard structures, or more exclusive handling of how metadata should work after migration, Custom Migration Service may be the safer path, with Custom Jobs used where scoped adaptation is required.

A migration from or to a Custom Cart always belongs to Custom Migration Service. In these cases, metadata meaning may require more specialized interpretation because field structures, extension-owned behavior, identifier logic, or custom business rules may not fit a predictable supported-cart pattern cleanly enough for standard handling.

### Conclusion

Metadata migration succeeds when the fields that matter still drive the same business meaning after launch, not when additional values simply appear somewhere in the target environment.

That is why metadata, custom fields, and extensions should be judged through the behaviors, workflows, and connected-system outcomes they control. When important meaning lives outside the default platform model, a migration can preserve core records while silently weakening the logic that makes the store commercially and operationally usable.

Start with the fields and extension-owned behaviors that affect pricing, visibility, eligibility, operational continuity, reporting, or connected-system recognition. Then review whether the target environment still uses them in a way that preserves the intended outcome before scaling further. If you need help deciding whether the issue is standard field alignment, transformation need, identifier sensitivity, or a requirement for more exclusive handling, Live Chat is a practical way to align validation priorities and the safest migration path.

### FAQs

#### Why are metadata and custom fields so risky in migration?

Because they often hold business meaning that the default platform model does not express directly. The field can survive while the behavior it used to control stops working.

#### What is the difference between informational metadata and behavior-driving metadata?

Informational metadata is mainly kept for reference or historical completeness. Behavior-driving metadata must continue to control something important after launch, such as pricing, visibility, eligibility, filtering, or external-system recognition.

#### Why is “field exists” not a strong enough validation standard?

Because a field can still be present while no longer driving the intended storefront, workflow, or system behavior.

#### When does metadata migration become a transformation problem instead of a transfer problem?

When the target environment needs the field reshaped, remapped, filtered, or converted so the intended outcome still works after launch.

#### Can metadata and extension logic require more than standard handling?

Yes. If preserving the intended outcome depends on transformation, custom structures, exact identifiers, or extension-owned behavior, more exclusive handling may be needed.

#### How does a Custom Cart affect metadata preservation?

A migration from or to a Custom Cart is always a Custom Migration Service project. Metadata meaning, field structure, identifier logic, and extension-owned behavior may require more specialized interpretation, restructuring, or migration-tool adjustment than a more predictable supported-cart pairing.
