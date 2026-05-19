# Customer Data Models and Segmentation

## Customer Data Models and Segmentation <a href="#customer-data-models-and-segmentation" id="customer-data-models-and-segmentation"></a>

Customer data can migrate successfully while the account experience still feels different to returning buyers, support teams, or sales teams.

That happens because customer records are not only contact profiles. They can also carry account access, addresses, customer groups, tax treatment, pricing eligibility, marketing status, B2B or wholesale logic, support context, and relationship history. When the Source Platform and Target Platform define those layers differently, the customer may still exist in the new store while the business meaning of that customer changes.

A strong migration plan should therefore treat customer continuity as both a data question and an account-behavior question. The practical goal is not only to move customer records, but to make sure the Target Platform can still recognize customers in the way the business needs after launch.

### Customer data is more than a profile record <a href="#customer-data-is-more-than-a-profile-record" id="customer-data-is-more-than-a-profile-record"></a>

A customer profile is the visible starting point, but it rarely contains the full account meaning.

Customer data can include names, email addresses, phone numbers, billing and shipping addresses, tax identifiers, account status, tags, groups, segments, marketing consent, support notes, customer-specific fields, and relationship signals such as wholesale status or loyalty eligibility. Some of these are stored directly on the customer record. Others are calculated, assigned by rules, managed by extensions, or interpreted by connected systems.

#### Common customer data layers <a href="#common-customer-data-layers" id="common-customer-data-layers"></a>

Customer-related migration scope may include:

* profile fields such as name, email, phone number, and account identifiers
* billing and shipping addresses
* account status and access-related fields
* customer groups, tags, tiers, or segments
* tax classification or exemption-related fields
* B2B, wholesale, retail, or restricted-access classifications
* marketing consent or communication preferences
* support-relevant notes or customer attributes
* loyalty, subscription, membership, or approval-related status
* app, plugin, module, or extension-driven customer data

**Why this matters in migration**

A customer record can appear complete in the Target Platform while still failing to support the same account experience. The right review question is not only “did the customer move?” It is “does the customer still behave correctly for login, checkout, pricing, visibility, support, and communication?”

### Customer profiles and login continuity are separate concerns <a href="#customer-profiles-and-login-continuity-are-separate-concerns" id="customer-profiles-and-login-continuity-are-separate-concerns"></a>

One of the most common customer-data misunderstandings is assuming that migrated profiles automatically preserve login continuity.

Customer profile data and authentication behavior are different layers. A migration can preserve the customer profile while still requiring customers to reset passwords, activate accounts, or follow a new first-login flow. This is often caused by platform security design, password-hash handling, or Target Platform restrictions rather than by missing customer records.

#### What usually remains separate <a href="#what-usually-remains-separate" id="what-usually-remains-separate"></a>

The following items should be reviewed separately:

* whether the customer profile exists
* whether the email address is recognized
* whether account status is active or requires activation
* whether passwords can be preserved under the selected migration path
* whether customers need a reset or invitation flow
* whether support teams know how to explain the first-login experience

**Why password continuity should be planned early**

Password continuity should not be assumed. When it is not feasible, the better planning approach is to prepare a clear first-login or password-reset experience and make sure support teams understand what customers will see after launch.

### Addresses are dependency structures under customer accounts <a href="#addresses-are-dependency-structures-under-customer-accounts" id="addresses-are-dependency-structures-under-customer-accounts"></a>

Customer addresses should be treated as account dependencies, not isolated records.

An address matters because it supports checkout, delivery, billing, tax handling, account convenience, and support. If customer profiles migrate but addresses do not appear where the Target Platform expects them, the customer account can still feel incomplete.

#### Address continuity needs practical validation <a href="#address-continuity-needs-practical-validation" id="address-continuity-needs-practical-validation"></a>

Address review should check whether:

* billing and shipping addresses remain attached to the right customer
* default addresses behave correctly where the Target Platform supports defaults
* address fields fit the Target Platform’s country, region, state, postcode, and phone-number requirements
* address formatting remains usable in checkout and admin views
* imported addresses still support tax, shipping, and support workflows

**Why address structure can change**

Different platforms can use different required fields, address formats, country/region models, and checkout rules. A technically migrated address can still require cleanup if the Target Platform stores or validates address components differently.

### Segmentation gives customer records commercial meaning <a href="#segmentation-gives-customer-records-commercial-meaning" id="segmentation-gives-customer-records-commercial-meaning"></a>

Customer segmentation is where customer data often becomes business logic.

A segment, group, tag, or customer type can decide what a customer sees, which prices apply, whether tax rules change, whether a promotion is available, or whether a restricted catalog is visible. If segmentation changes during migration, the customer record may still exist while the commercial treatment changes.

#### Segmentation can control several outcomes <a href="#segmentation-can-control-several-outcomes" id="segmentation-can-control-several-outcomes"></a>

Customer segmentation may affect:

* retail versus wholesale treatment
* B2B account eligibility
* customer-group pricing
* tax treatment or exemption status
* catalog visibility
* restricted products or collections
* promotion eligibility
* loyalty, subscription, or membership logic
* marketing audience selection
* support priority or account handling

**Why labels are not enough**

Migrating a customer group name, tag, or segment label does not guarantee that the Target Platform will apply the same behavior. The business should validate the result through real customer scenarios, not only by checking that the label appears.

### Customer models differ across platforms <a href="#customer-models-differ-across-platforms" id="customer-models-differ-across-platforms"></a>

Platforms can represent customers and segmentation in different ways.

Some platforms rely on groups or customer classes. Others use tags, rule-based segments, customer attributes, B2B company structures, apps, plugins, modules, or external CRM logic. The same customer may therefore need to be represented differently in the Target Platform to preserve the intended business outcome.

#### Common model differences <a href="#common-model-differences" id="common-model-differences"></a>

Customer model differences may include:

* one account versus multiple contacts under a company
* individual buyers versus company buyers
* customer groups versus tags or rule-based segments
* stored segment membership versus dynamic segment membership
* native B2B features versus extension-driven B2B logic
* account approval workflows versus open registration
* customer-specific fields stored natively versus in extensions
* customer eligibility calculated by external systems

**Why model fit matters**

A customer model mismatch can affect pricing, catalog access, tax treatment, order visibility, communication, and support workflows. When the Target Platform cannot represent the same structure natively, the migration may need configuration, mapping decisions, or Custom Service handling.

### Extension-driven customer logic needs special attention <a href="#extension-driven-customer-logic-needs-special-attention" id="extension-driven-customer-logic-needs-special-attention"></a>

Many stores rely on apps, plugins, modules, extensions, or external systems to give customer data its real operational meaning.

This is common in B2B, wholesale, subscription, membership, loyalty, approval, tax, CRM, and support workflows. In those cases, the customer record may only be one part of the customer experience. The rest may depend on rules or connected systems that are not part of a standard customer profile.

#### Customer logic may depend on systems outside the core platform <a href="#customer-logic-may-depend-on-systems-outside-the-core-platform" id="customer-logic-may-depend-on-systems-outside-the-core-platform"></a>

Risk is higher when customer behavior depends on:

* B2B or company-account extensions
* wholesale pricing modules
* loyalty or reward systems
* subscription or membership apps
* CRM or support-desk integrations
* tax exemption or VAT validation systems
* account approval workflows
* custom customer fields
* ERP, POS, or external customer identifiers

**When Custom Service becomes relevant**

If the required customer outcome depends on custom fields, extension-driven account behavior, outside-system identifiers, custom segmentation logic, or non-standard account handling, the requirement should be reviewed as Custom Service work. The issue is not only moving the customer record. The issue is preserving the customer behavior the business depends on.

### Marketing and communication status should not be treated casually <a href="#marketing-and-communication-status-should-not-be-treated-casually" id="marketing-and-communication-status-should-not-be-treated-casually"></a>

Customer migration can affect marketing, consent, and communication workflows.

Marketing status is sensitive because it can influence which customers receive messages, how audiences are built, and how the business communicates after launch. A migrated customer list is not automatically a safe or complete marketing audience.

#### Communication-related fields need careful review <a href="#communication-related-fields-need-careful-review" id="communication-related-fields-need-careful-review"></a>

Before launch, businesses should check whether:

* email and phone fields are usable in the Target Platform
* marketing consent or subscription status is represented clearly
* customer tags or segments used for campaigns still work as intended
* inactive or suppressed customers are not incorrectly reactivated
* support teams understand the first-login or password-reset communication plan

**Why this belongs in planning**

Customer communication affects trust. If returning customers receive confusing login instructions, wrong campaign messages, or unexpected access changes, the migration can create support pressure even when the customer records are technically present.

### What to define before execution <a href="#what-to-define-before-execution" id="what-to-define-before-execution"></a>

Customer-data planning should define the account outcomes that matter most after launch.

The business does not need to preserve every historical customer detail in the same way, but it should decide which account behaviors must remain dependable. That decision should happen before Full Migration, not during launch review.

#### Planning questions for customer continuity <a href="#planning-questions-for-customer-continuity" id="planning-questions-for-customer-continuity"></a>

Useful planning questions include:

* What should a returning customer be able to do on launch day?
* Which customer groups, tags, tiers, or segments affect pricing or visibility?
* Which customers need access to order history, addresses, or account context?
* Is password continuity realistic under the selected migration path?
* Which customer fields are essential for support, sales, tax, or operations?
* Which customer behavior depends on apps, plugins, modules, extensions, or external systems?
* Which customer types should be included in the Demo Migration sample?

**How this reduces migration risk**

Clear customer-outcome planning helps the migration team distinguish between simple profile preservation, configuration needs, Add-on-relevant mapping or data configuration, and broader Custom Service requirements.

### What to validate first <a href="#what-to-validate-first" id="what-to-validate-first"></a>

Customer validation should focus on representative account scenarios, not only record counts.

A useful review sample includes the customer types that carry the most commercial or operational meaning. For many stores, that means repeat customers, wholesale accounts, customers with multiple addresses, customers with tax or pricing differences, and customers whose account status depends on extensions or external systems.

#### High-priority validation scenarios <a href="#high-priority-validation-scenarios" id="high-priority-validation-scenarios"></a>

Review should include:

* returning customers with normal retail accounts
* B2B or wholesale customers, if applicable
* customers with multiple billing or shipping addresses
* customers with customer-group pricing or catalog visibility rules
* customers with tax classification or exemption logic
* customers with meaningful support or account fields
* customers tied to loyalty, subscription, membership, or approval workflows
* customers whose records depend on external identifiers

**What a successful review should prove**

A good customer-data review should prove that the account can be found, interpreted, and used correctly in the Target Platform. It should also confirm whether customers can follow the intended login or recovery path and whether customer classifications produce the expected pricing, visibility, communication, and support outcomes.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Customer data models and segmentation can make a migration look complete while leaving the customer experience weaker than expected. The core risk is not only whether profiles, addresses, and labels move. The deeper question is whether the Target Platform still recognizes the customer in the right way and supports the same account, pricing, visibility, support, and communication outcomes.

The safest approach is to define essential customer outcomes early, separate profile migration from login continuity, identify segmentation rules that carry business meaning, and validate representative customer scenarios before launch. When customer behavior depends on extension logic, Custom Platform structure, outside-system identifiers, or custom fields, that dependency should be reviewed before it becomes a post-launch support issue.

Review the customer types that matter most to repeat purchasing, support, pricing, visibility, and account trust. If those outcomes depend on non-standard segmentation, custom fields, B2B logic, or outside systems, Live Chat can help clarify whether standard service capability is enough or whether Custom Service review is the safer path.

### FAQs <a href="#faqs" id="faqs"></a>

**Can customer records migrate successfully even if login continuity changes?**

Yes. Customer profiles and login behavior are separate concerns. A customer can exist in the Target Platform even when the launch plan requires a password reset, account activation, or new first-login flow.

**Are customer groups and segments the same across platforms?**

Not always. One platform may use groups, another may use tags, dynamic segments, customer attributes, company accounts, or extension-driven logic. The label can migrate while the behavior still needs configuration or custom handling.

**Should customer addresses be reviewed separately?**

Yes. Addresses should be reviewed as dependencies under the customer account. The review should confirm that billing and shipping addresses remain attached correctly and remain usable in checkout, tax, shipping, and support workflows.

**When does customer segmentation become a Custom Service concern?**

Customer segmentation becomes a Custom Service concern when the required outcome depends on custom fields, non-standard customer logic, extension-driven behavior, outside-system identifiers, Custom Platform handling, or customer-specific rules that standard service capability cannot represent clearly.

**What customer records should be included in a Demo Migration review?**

The sample should include representative customer types, not only simple records. Include repeat customers, customers with multiple addresses, B2B or wholesale accounts, customers with pricing or visibility differences, and customer records tied to important support, tax, loyalty, membership, or external-system behavior.
