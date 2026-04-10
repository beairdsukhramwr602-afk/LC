# When Custom Job Is Required: Common Scenarios

Most migration projects work well with standard capabilities when the source and target platforms can represent the same store meaning in similar ways. A Custom Job becomes necessary when standard migration can move the records, but cannot preserve a business-critical requirement, special rule, or non-standard data structure the store depends on.

That is why a Custom Job should not be understood as general extra help. It is targeted customization of the migration process used when standard handling cannot reliably preserve the outcome the business needs.

### What a Custom Job Is

A Custom Job is a modification or extension of the migration tool designed to handle a requirement that standard capabilities do not cover by default.

In practice, a Custom Job is used when one or more of these conditions are true:

* the data exists, but the target platform cannot represent it the same way by default
* the data lives in a third-party module, plugin, extension, custom field set, or outside system rather than in standard supported entities
* the data must be filtered, transformed, or reshaped to preserve business meaning after migration

A Custom Job is most valuable when it preserves business-critical meaning, not when it is used to avoid basic scoping decisions or routine cleanup.

### Why Some Migration Requirements Go Beyond Standard Handling

Standard migration is strongest when the source and target stores share a reasonably compatible model for the data that matters most. Custom handling becomes necessary when the requirement depends on something more specific than standard entity transfer.

That often means:

* custom fields that affect storefront behavior
* extension-managed product or customer data
* rule-based filtering inside an entity type
* transformation logic needed to preserve meaning
* non-standard platform structures
* relationship-sensitive behaviors that rely on custom logic
* identifiers or metadata needed by external systems after launch

The key question is not whether the data exists. The key question is whether standard migration can preserve the outcome the business actually needs.

### Scenario 1: Custom Fields That Affect Storefront or Operational Behavior

Some stores rely on custom product, customer, or order fields that are not part of the standard supported entity model. These fields may carry specifications, special pricing types, media relationships, operational metadata, or other information that affects real store behavior.

#### Why standard migration may not be enough

Standard migration can transfer the core entity while leaving the business-critical field set behind or preserving it in a form that is no longer usable in the target environment.

#### What usually makes this requirement more complex

Common complexity drivers include:

* product price types added by an extension
* product attributes added by an extension
* product specifications added by an extension
* product images or videos added by an extension
* custom fields that influence buying decisions, operations, or downstream systems

#### What a Custom Job may need to do

A Custom Job may need to:

* migrate the custom field set itself
* place it into a usable target structure
* adapt the data so it still supports storefront display, filtering, reporting, or operational workflows after migration

#### What the customer should clarify early

The customer should identify:

* which custom fields are genuinely business-critical
* where those fields appear today
* what outcome they must still support after migration
* whether the target platform needs the same field behavior or an adapted equivalent

### Scenario 2: Third-Party App, Plugin, or Extension Data

Many stores depend on data created or managed by third-party modules, plugins, or extensions rather than by the platform’s native model. That can include loyalty context, subscription data, search or filtering logic, bundled-product behavior, merchandising rules, or extension-managed attributes.

#### Why standard migration may not be enough

The storefront may make the feature look native, but the actual data may live outside the default platform model. Standard migration may move the core entities while leaving the extension-driven meaning behind.

#### What usually makes this requirement more complex

This becomes more complex when:

* the extension affects revenue-critical behavior
* the extension shapes discovery or filtering
* the data is stored in module-specific structures
* the target platform cannot represent the same behavior natively

#### What a Custom Job may need to do

A Custom Job may need to:

* extract extension-driven data that is not part of standard support
* remap it into a usable target structure
* preserve the relationship between the extension-driven data and the core entity it depends on

#### What the customer should clarify early

The customer should clarify:

* which extensions materially affect revenue, operations, discoverability, or customer continuity
* whether those extensions are only cosmetic or business-critical
* what the target store must still be able to do after migration

### Scenario 3: Rule-Based Filtered Migration Requirements

Some projects do not want a full-scope migration. They need defined rules for which records should move and which should not.

Typical examples include:

* only active products
* only orders from a certain date range
* only customers who have placed at least one order
* only valid or unused coupons
* only blog posts published after a certain date
* only products from selected categories

Choosing whole entity types is not the same as filtering records within those entity types. Excluding entire entities can be standard, but rule-based filtering inside an entity often requires more precise logic than standard handling provides.

#### Why standard migration may not be enough

Standard migration may not preserve the filtered result consistently if the project depends on explicit inclusion or exclusion rules inside an entity type.

#### What usually makes this requirement more complex

This becomes more complex when:

* the rule must be repeatable and precise
* the rule affects business continuity or reporting
* the rule depends on status, date, validity, or relationship conditions
* the filtered scope could weaken the meaning of connected records if handled loosely

#### What a Custom Job may need to do

A Custom Job may need to:

* apply defined inclusion or exclusion conditions
* preserve the filtered outcome consistently across the migration run
* make sure the resulting scoped dataset still supports the intended business use

#### What the customer should clarify early

The customer should clarify:

* exactly which records should be included
* the rule that decides inclusion or exclusion
* why the filtered result is needed
* whether filtering changes how related data should still behave after migration

### Scenario 4: Data Transformation Requirements

Sometimes the data is present, but it needs to be transformed so the target store can use it meaningfully.

Examples include:

* removing HTML code or special characters from descriptions
* converting product attributes into product categories
* converting customer tags into customer groups
* reshaping category logic so the target browse experience matches business intent
* normalizing option values so variants behave predictably

#### Why standard migration may not be enough

Standard migration is designed to transfer and map supported data. It is not automatically designed to reshape business logic or reinterpret field meaning when the target platform needs a different structure to preserve the desired outcome.

#### What usually makes this requirement more complex

This becomes more complex when:

* the old store uses workarounds that do not translate cleanly
* the target platform supports the concept differently
* the target store would become confusing or weaker if the data were copied as-is
* the required outcome depends on interpretation rather than one-to-one transfer

#### What a Custom Job may need to do

A Custom Job may need to:

* transform values between field types
* clean or standardize data during migration
* reshape structures so the target platform can preserve the intended behavior more effectively

#### What the customer should clarify early

The customer should clarify:

* what the data means originally
* what it needs to mean after migration
* whether the target platform needs an exact match or a usable equivalent
* what business behavior must still work after the transformation

### Scenario 5: Custom Cart or Non-Standard Platform Structure

Some migration projects involve a platform not currently on the standard supported list, a heavily customized self-hosted implementation, or a store with unique data storage patterns.

#### Why standard migration may not be enough

Standard migration assumes recognizable source and target structures. When the platform is heavily customized or non-standard, the migration may need to interpret or map structures that do not behave like a typical platform pairing.

A migration from or to a Custom Cart always proceeds through Custom Migration Service. In these cases, the migration often needs more exclusive handling to fit structural differences, data modifications, migration-tool adjustments, interpretation demands, validation sensitivity, and other bespoke requirements.

#### What usually makes this requirement more complex

This becomes more complex when:

* the source platform is proprietary or unusual
* the store uses heavily modified database structures
* the data model differs significantly from standard expectations
* important business behavior depends on those non-standard structures

#### What a Custom Job may need to do

A Custom Job may need to:

* interpret non-standard data structures
* adapt the migration logic for that platform pairing
* preserve required data meaning where standard mappings do not apply cleanly

#### What the customer should clarify early

The customer should clarify:

* whether the platform itself is non-standard
* whether key data lives in unusual structures
* which outcomes are non-negotiable if the platform behavior is custom or proprietary

### Scenario 6: Relationship-Sensitive Special Handling

Some requirements are especially risky because they affect how connected records remain usable after migration. Even when the records move, the result can still fail if relationship-heavy meaning is weakened by filtering, transformation, platform differences, or extension-driven logic.

#### Why standard migration may not be enough

Standard handling may preserve the records but not the special conditions needed to preserve how those records continue working together in buying paths, discovery, promotions, or operations.

#### What usually makes this requirement more complex

This becomes more complex when:

* products and variants are structured in non-standard ways
* categories or collections are being used as operational tags rather than browse pathways
* extensions store relationship data outside the default model
* the requirement depends on preserving behavior across multiple connected entities

#### What a Custom Job may need to do

A Custom Job may need to:

* preserve non-standard relationship logic
* adapt how related data is mapped or filtered
* make sure the target store preserves the connected behavior the business depends on

#### What the customer should clarify early

The customer should clarify:

* which connected behaviors must still work after launch
* whether the requirement depends on more than core entity presence
* where relationship-heavy logic lives today, especially if it is extension-driven or custom

### Scenario 7: Integration-Dependent Migration Requirements

Some stores rely on data that matters mainly because outside systems need it after migration. That can include ERP identifiers, CRM-linked customer fields, shipping or fulfillment metadata, subscription keys, automation identifiers, or reporting artifacts.

#### Why standard migration may not be enough

Standard migration may preserve the visible storefront data while missing the metadata or identifiers that external systems need to keep operating correctly after launch.

#### What usually makes this requirement more complex

This becomes more complex when:

* the external system depends on exact identifiers
* the data is not visible in the storefront but is operationally critical
* the target platform does not expose the same data structure by default
* the business uses several connected systems with shared dependencies

#### What a Custom Job may need to do

A Custom Job may need to:

* preserve or transform external-system identifiers
* remap fields needed by connected systems
* make sure key operational metadata remains usable after migration

#### What the customer should clarify early

The customer should clarify:

* which external systems must keep working immediately after launch
* what data those systems depend on
* whether the dependency is optional, rebuildable, or truly business-critical

### How to Tell Whether Your Requirement Is a Custom Job Case

The safest approach is to classify each concern shown by a representative demo as one of four types:

* mapping decision
* scope decision
* platform capability difference
* custom requirement

Strong signals of a likely Custom Job case include:

* custom fields driving storefront display or filtering
* third-party extension data that matters operationally
* non-standard structures that do not translate cleanly
* transformation rules needed to preserve required behavior
* rule-based filtering within an entity type
* platform pairings with non-standard or Custom Cart structures

A demo is most useful when it contains representative complexity on purpose. It helps distinguish between something that needs clearer mapping and something that truly requires custom handling.

### Conclusion

A Custom Job is required when standard migration capabilities cannot preserve the outcome your business needs, especially when important data lives in extensions, custom fields, filtered rules, non-standard structures, relationship-sensitive logic, or integration-dependent metadata.

The safest way to identify that need is to run a representative Demo Migration, review the result through an outcome lens, and classify the requirement carefully before deciding what kind of handling is truly necessary. When a Custom Job is needed, it works best as a planned requirement identified early, not as a late fix under launch pressure.

If your store depends on extension-driven data, filtered rules, field transformations, outside-system identifiers, or a non-standard or Custom Cart structure, build a demo sample that includes those exact cases and review the outcome against what must still work after migration. If you need help deciding whether the issue is mapping, scope, platform capability, or a true Custom Job requirement, Live Chat is a practical way to confirm the safest path before timelines tighten.

### FAQs

#### Does needing a Custom Job mean the migration cannot be done normally?

Not necessarily. Many stores can migrate core data successfully, but a Custom Job is needed when the requirement goes beyond standard capability and the business still needs that requirement preserved safely.

#### Are filtered migrations always Custom Job cases?

Not always. Excluding entire entity types can be standard. The higher-risk cases are rule-based filtering conditions within an entity type, especially when the logic must be precise and repeatable.

#### Is every custom field a Custom Job case?

No. The key question is whether the field is business-critical and whether standard migration can preserve it in a usable target-side form. Some custom fields matter little. Others directly affect storefront behavior, operations, or connected systems.

#### When should a business identify a likely Custom Job requirement?

As early as possible, ideally through a representative Demo Migration and requirement review before the project moves too far into execution.
