# Customer Data Models and Segmentation

Customer records can migrate successfully and still leave the account experience feeling unfamiliar.

That usually happens when the source and target platforms do not treat customer identity, account access, profile structure, addresses, segmentation, and customer-specific business logic in the same way. The customer may still exist in the new store, but what that customer can see, how that customer logs in, and how the business recognizes that customer can change in ways that affect trust, support, and repeat purchasing.

This matters because customer data is more than a contact list. In many stores, customer records help determine pricing eligibility, account visibility, tax treatment, support context, reorder behavior, and what the business considers a continuing relationship. A migration can therefore preserve customer records while still changing how those records behave in the storefront and in daily operations.

### What customer data usually includes in practice

Customer data often includes several distinct layers:

* profile information such as name, email, phone number, and other customer fields
* billing and shipping addresses
* account status or access-related information
* customer groups, tags, tiers, or types
* tax-relevant or eligibility-related profile information
* account-visible history or support-relevant context, where that is part of the intended experience

These layers do not all behave the same way after migration. A customer profile can move successfully while login behavior changes. Addresses can appear correctly while account segmentation behaves differently. Groups can exist while customer-specific pricing or visibility rules no longer produce the same result.

### Customer profiles are not the same as login continuity

One of the most common expectation gaps in migration is the difference between customer existence and customer access.

A customer can still exist in the new store while the login experience changes. That is because account profile data and authentication behavior are separate concerns. Most modern platforms store passwords in hashed or encrypted forms designed not to be reversible, so password continuity is often limited by platform security design rather than by whether the customer record migrated.

In practical terms, the most common outcome is:

* customer profiles migrate
* customers still exist in the new store
* customers may need a password reset or a new access flow when the new site goes live

That is why customer continuity should be planned as an account experience, not assumed from the presence of migrated records alone.

### Addresses are dependency structures under customers

Customer addresses should be treated as dependency structures under the customer record, not as independent entities.

That distinction matters because address continuity depends on customer continuity. If customer records migrate but address handling changes, the customer may still exist while account usability becomes weaker for checkout, support, tax handling, or reorder workflows. Address presence alone is not enough. The addresses also need to appear where the target platform expects them and remain usable in the account and purchase journey.

### Segmentation changes customer meaning

Customer segmentation is often one of the most important behavior layers in a store.

Segmentation may include:

* retail versus wholesale distinctions
* customer groups or tiers
* restricted customer types
* customer-specific catalogs or visibility rules
* tax-related customer classification
* pricing rules tied to customer status or group membership

This matters because segmentation is rarely just a label. It often controls what customers can buy, what they can see, which prices they receive, or which workflows apply to them. A migration can therefore preserve the customer record while changing the commercial meaning attached to that customer.

### Why customer behavior changes after migration

Customer continuity usually weakens because platforms differ in how they define account behavior, not because customer data disappears entirely.

Common causes include:

#### Different account models

Some platforms center more of the customer journey inside logged-in accounts. Others rely more heavily on email-based recovery, guest behavior, or different definitions of account state. Even when profiles migrate, the expected account experience can still shift.

#### Different segmentation structures

Customer groups, tiers, tags, and visibility rules do not always map cleanly from one platform to another. This matters most when those classifications affect pricing, catalog access, or operational treatment.

#### Different pricing and eligibility behavior

A customer can be recognized correctly while still seeing the wrong price, the wrong catalog visibility, or the wrong promotion outcome because the target platform applies segmentation logic differently.

#### Different support context

Customer accounts often matter because support teams need to recognize the person, see enough account context, and respond without confusion. If the account exists but does not preserve the expected history or profile meaning, the customer relationship can still feel interrupted.

### Planning for password continuity realistically

Password continuity is the exception, not the default.

Where the target platform does not support password continuity through legacy hash verification, the safer assumption is that customers will need a password reset or account activation flow after launch. In those cases, the most important planning work is not technical recovery detail. It is defining a clear first-login experience, preparing customer communication, and ensuring the support team can explain what customers will experience.

Where the target platform supports password continuity through legacy hash verification and is compatible with Next-Cart Customer Password Plugin, continuity may be possible when the source platform is open-source. In that case, the plugin adds the source platform’s password verification method to the target so customers can continue logging in with their existing passwords.

Compatible targets include:

* Magento
* OpenCart
* PrestaShop
* WooCommerce
* WordPress
* Joomla
* VirtueMart
* Shopware

For cloud and SaaS targets, password continuity is typically not possible, so the safer planning path is a well-prepared first-login reset experience rather than assumed password continuity.

### Where extensions and custom logic raise the risk

Many stores rely on more than the default customer model.

Apps, plugins, modules, and custom fields may influence:

* customer groups and pricing tiers
* customer-specific visibility
* tax treatment
* B2B eligibility logic
* approval or restricted-access workflows
* support-relevant account fields
* subscription or loyalty behavior
* operational rules tied to customer identity

In those cases, the migration question is not only whether customer records move. The more important question is whether the target store can still use those records to support the same commercial and operational behavior.

Where customer meaning depends heavily on extension-driven logic, standard handling may preserve records without preserving the intended account outcome. The issue is not customer presence alone. It is whether the account still behaves in a way that is trustworthy for customers and usable for the business.

### What merchants should define before execution

Before approving a full migration, the business should be able to define which account outcomes must remain true after launch.

The most important questions are:

#### 1. What should a returning customer be able to do on day one?

This may include logging in, recognizing prior account information, seeing addresses, accessing order history, or receiving the right pricing and visibility.

#### 2. Which customer segments matter most commercially?

These are the groups whose pricing, access, or operational treatment must remain consistent.

#### 3. What login outcome is realistic on the target platform?

This should be decided early so the account experience is planned rather than discovered late.

#### 4. Which account fields are essential to support or operations?

These are the fields that help teams recognize customers, resolve issues, and maintain continuity.

#### 5. Which parts of customer behavior depend on apps, modules, plugins, or custom fields?

This is where apparently complete customer records can still fail to preserve the intended business outcome.

### What to validate first

Customer continuity should be validated as an account and behavior experience, not only as a list of imported customer records.

A practical first review should focus on:

* repeat customers
* customer segments with different pricing or visibility rules
* B2B and retail profiles if both exist
* accounts with meaningful address data
* support-relevant customer records
* customers whose account expectations are central to repeat purchasing

The first questions to ask are:

* can customers be found and recognized correctly?
* do core profile fields appear as expected?
* do billing and shipping addresses appear where needed?
* does the intended login or recovery flow behave clearly?
* do customer groups or segments still produce the right pricing and visibility outcomes?
* does the account experience feel explainable and trustworthy?

A useful validation sample is usually representative rather than random. It should reflect real customer types, not just easy test records. A Demo Migration is often the fastest way to expose whether the target representation still supports the intended account experience before the project scales further.

### When standard handling may not be enough

Not every customer migration requires bespoke handling. But some signals should raise the threshold for confidence.

Risk is higher when:

* account login continuity is central to customer trust
* customer groups affect pricing, visibility, or eligibility
* B2B and retail customers coexist
* support teams rely heavily on account context
* customer-specific workflows depend on modules or custom fields
* the target platform supports only a simplified version of the original customer behavior

In those situations, the real issue is not whether customer records can move. It is whether the target store can preserve the same customer meaning clearly enough through standard handling alone.

If the main need is stronger expert execution and more controlled review of customer groups, account experience, and support-visible continuity, Managed Migration Service may be sufficient. If the account model depends on special eligibility logic, approval workflows, customer-specific structures, or more exclusive handling of how customer meaning should be preserved, Custom Migration Service may be the safer path, with Custom Jobs used where scoped adaptation is required.

A migration from or to a Custom Cart always belongs to Custom Migration Service. In these cases, customer structure, segmentation behavior, approval logic, support context, or account expectations may require more specialized interpretation because customer meaning may not fit a predictable supported-cart pattern cleanly enough for standard handling.

### Conclusion

Customer migration succeeds when the account still feels understandable and usable to both the customer and the business, not when profile records simply appear in the target store.

That is why customer continuity should be judged as account behavior, segmentation meaning, and realistic login expectation, not just as successful record transfer. When platforms treat identity, access, groups, and customer-specific logic differently, the customer may still exist while the account experience becomes less trustworthy, less clear, or less commercially useful.

Start with the customer types and account behaviors that matter most to repeat purchasing, support clarity, pricing integrity, and launch trust. Then review whether the target store still supports those outcomes before scaling further. If you need help deciding whether the issue is standard account-model difference, password continuity limitation, segmentation mismatch, or a requirement for more exclusive handling, Live Chat is a practical way to align validation priorities and the safest migration path.

### FAQs

#### Why is a migrated customer record not the same thing as customer continuity?

Because continuity depends on more than record presence. It includes login expectations, address usability, support context, segmentation behavior, and how the business recognizes that customer after launch.

#### Why do customers often need a password reset even when their profiles migrated?

Because password behavior depends on platform security design, not only on whether the customer record moved. Most platforms store passwords in non-reversible hashed forms, so continuity is often limited unless compatible legacy hash verification is possible.

#### When can existing customer passwords sometimes be preserved?

Usually only when the target platform supports password continuity through legacy hash verification and is compatible with Next-Cart Customer Password Plugin, and the source platform is open-source.

#### Why is customer segmentation such a sensitive migration area?

Because groups, tiers, tags, and classifications often control pricing, visibility, eligibility, tax treatment, or workflow behavior. The customer can exist in the target store while still receiving the wrong commercial treatment.

#### When should customer continuity be treated as a high-risk migration area?

When login continuity matters to trust, customer groups affect pricing or access, B2B and retail customers coexist, or support and operations depend heavily on account context and extension-driven behavior.

#### How does a Custom Cart affect customer-data preservation?

A migration from or to a Custom Cart is always a Custom Migration Service project. Customer structure, segmentation logic, account behavior, and support-visible continuity may require more specialized interpretation, restructuring, or migration-tool adjustment than a more predictable supported-cart pairing.
