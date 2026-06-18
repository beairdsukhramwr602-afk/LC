# Additional Migration Options

After migration activity has already been performed under a purchased Next-Cart migration service license, customers may need another action for the same migration path. The source store may keep receiving orders, customers, products, or Blog Posts while the target store is being reviewed. A customer may also want to adjust configuration before another execution, or create a new migrated result when the earlier target-store result should no longer be used.

Next-Cart supports these needs through additional migration options inside the purchased service license. The right option depends on the customer’s goal: continue from the earlier setup, continue with revised settings, or perform a new migration for the selected migration path.

Additional migration options should be chosen for a clear business reason. The customer should understand whether the next action is meant to add later source-store data, change configuration before continuing, or create a fresh target-store result.

### When Additional Migration Options Matter <a href="#when-additional-migration-options-matter" id="when-additional-migration-options-matter"></a>

Additional migration options become relevant after migration activity has already taken place under the purchased service license. They are most useful when the customer needs to manage timing, configuration, or target-store result quality after the first migration activity.

Common situations include:

* the source store remains active while the target store is being reviewed;
* new orders, customers, products, or Blog Posts appear after earlier migration activity;
* the previous configuration is still suitable and should be reused;
* the customer wants to adjust configuration before another execution;
* the earlier target-store result should be replaced by a fresh migration result;
* validation shows that another action is needed before launch or continued business use.

The choice should not be based only on whether another action is available. The safer approach is to define the expected target-store result first, then select the option that matches that result.

### The Three Additional Migration Options <a href="#the-three-additional-migration-options" id="the-three-additional-migration-options"></a>

After a customer performs migration activity with the purchased migration service license, the customer may be able to access additional options for the same migration path, depending on migration history and service availability.

| Option                                                  | Best used when                                                                               | Expected result                                                                                                   |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | The previous configuration is still suitable and the customer wants to continue efficiently. | The next execution follows the last used configuration.                                                           |
| Continue the Migration with a new configuration         | The customer wants to continue migration activity but adjust settings before execution.      | The customer reviews or changes configuration before continuing.                                                  |
| Perform a new migration                                 | The customer wants a fresh migration result for the same migration path.                     | The migration is performed again for the selected scope and may replace the earlier migrated target-store result. |

These options are not interchangeable. Continuing the migration is usually appropriate when the previous migration result remains useful. Performing a new migration is more appropriate when the earlier result should be replaced by a fresh result.

### Continue the Migration with the Last Used Configuration <a href="#continue-the-migration-with-the-last-used-configuration" id="continue-the-migration-with-the-last-used-configuration"></a>

Continue the Migration with the last used configuration is useful when the previous configuration still matches the customer’s goal.

This option can help when the source store has changed after earlier migration activity and the customer wants the target store to receive later data without rebuilding configuration decisions from the beginning. It is strongest when the previous configuration was already reviewed, the target-store result was acceptable, and the next execution should follow the same setup.

Typical reasons to choose this option include:

* new orders were created in the source store after the earlier migration activity;
* new customers registered before launch;
* new products or Blog Posts were added;
* the last used mapping, filtering, and configuration choices remain suitable;
* the customer wants a faster continuation path based on already reviewed settings.

The main advantage is efficiency. The customer can continue migration activity with the previously used configuration instead of repeating configuration decisions that still fit the expected target-store result.

Before choosing this option, the customer should confirm that the previous setup still supports the intended outcome. If configuration, filtering, mapping, Add-ons, or target-store expectations have changed, continuing with a new configuration may be safer.

### Continue the Migration with a New Configuration <a href="#continue-the-migration-with-a-new-configuration" id="continue-the-migration-with-a-new-configuration"></a>

Continue the Migration with a new configuration is useful when the customer wants to continue migration activity but needs to adjust settings before execution.

This option fits situations where earlier migration activity provided useful evidence, but the next execution should use revised choices. The customer may need to adjust mapping, filtering, selected data types, Add-on settings, or other configuration details before continuing.

Typical reasons to choose this option include:

* Demo Migration or validation revealed that configuration should be adjusted;
* the customer wants to apply different filtering or mapping decisions;
* the target-store result needs a setting change before another execution;
* purchased Add-ons need to be configured differently for the next action;
* the customer wants additional control before continuing from earlier migration work.

The main advantage is flexibility. The customer can continue migration activity while making configuration choices that better fit the intended target-store result.

This option is usually more suitable than performing a new migration when the earlier result remains useful, but the next execution needs revised settings. It helps customers avoid replacing the target-store result when the real need is configuration adjustment.

### Perform a New Migration <a href="#perform-a-new-migration" id="perform-a-new-migration"></a>

Perform a new migration is useful when the customer wants a fresh migration result for the same migration path instead of continuing from the earlier migrated result.

This option may be appropriate when the previous result should no longer be used, when the configuration or scope needs a clean restart, or when the target store should reflect a newly selected migration setup.

Typical reasons to choose this option include:

* the earlier migrated target-store result should be replaced;
* the previous configuration no longer matches the intended outcome;
* the migration scope needs to be reconsidered from the beginning;
* the target store was used for testing and the customer now wants a cleaner result;
* validation shows that a fresh migration result is safer than continuing from earlier work.

The main advantage is a cleaner reset of the migration result for the selected path. Because a new migration can affect previously migrated target-store data, the customer should confirm the expected target-store outcome before execution.

Performing a new migration should not be used only because another execution is possible. It is most valuable when the customer wants the target store to reflect a fresh result rather than continue from the earlier migration activity.

### How Entity Points Apply <a href="#how-entity-points-apply" id="how-entity-points-apply"></a>

Entity Points are tied to counted records and their recorded migration status under the purchased service license.

If an additional migration option migrates new Product, Customer, Order, or Blog Posts records for the first time, the corresponding Entity Points are used. Counted records already recorded through the service license do not consume Entity Points again when migrated again, including when the customer performs a new migration.

For example, if new Product or Order records were created in the source store after earlier migration activity, those newly migrated counted records require available Entity Points capacity. If Product, Customer, Order, or Blog Posts records were already recorded through the service license, those same counted records do not consume Entity Points again simply because another migration option is selected.

This keeps additional migration planning focused on real counted-data needs. New counted records require available capacity, while already recorded counted records are not counted again only because the customer continues migration activity or performs a new migration.

### How Service Responsibility Works <a href="#how-service-responsibility-works" id="how-service-responsibility-works"></a>

Customers on any service model can access and manually perform available migration actions if they choose. The service model determines who is responsible for performing migration actions and how much expert handling is included.

| Service model                        | Who performs migration actions                                                                                                                                           | Customer responsibility                                       |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------- |
| Standard Service                     | The customer performs migration actions.                                                                                                                                 | The customer verifies the final result and migration outcome. |
| Custom Service without Expert Handle | The customer performs migration actions.                                                                                                                                 | The customer verifies the final result and migration outcome. |
| Managed Service                      | Next-Cart performs migration actions based on the customer’s request and agreed service scope. The customer can still perform available actions manually if they choose. | The customer verifies the final result and migration outcome. |
| Custom Service with Expert Handle    | Next-Cart performs migration actions based on the customer’s request and agreed custom scope. The customer can still perform available actions manually if they choose.  | The customer verifies the final result and migration outcome. |

The service model affects execution responsibility. It does not remove the customer’s responsibility to confirm that the target-store result matches the intended migration outcome.

### What to Decide Before Choosing an Option <a href="#what-to-decide-before-choosing-an-option" id="what-to-decide-before-choosing-an-option"></a>

The right additional migration option depends on the expected result, not only on the available button or action name. Customers should clarify the business goal before execution.

Useful questions include:

| Decision question                                                                                                             | Why it matters                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Should the next action add later source-store data to the target store?                                                       | This often points to continuing migration activity.                                      |
| Is the last used configuration still suitable?                                                                                | If yes, continuing with the last used configuration may be efficient.                    |
| Should mapping, filtering, selected data types, or Add-ons be adjusted first?                                                 | If yes, continuing with a new configuration may be safer.                                |
| Should the earlier target-store result be replaced?                                                                           | If yes, performing a new migration may be more suitable.                                 |
| Is there enough Entity Points capacity for newly migrated counted records?                                                    | New Product, Customer, Order, and Blog Posts records require available counted capacity. |
| Does the requirement involve custom fields, app data, extension data, plugin data, Custom Platform handling, or custom logic? | Custom Service review may be needed before execution.                                    |
| Who should perform the action under the selected service model?                                                               | Execution responsibility should be clear before the action starts.                       |
| What target-store result must be verified afterward?                                                                          | Validation remains required for every service model.                                     |

These questions help prevent customers from choosing an option only because it appears available. The safest option is the one that matches the intended target-store result and the customer’s service scope.

### What to Verify After Using an Additional Migration Option <a href="#what-to-verify-after-using-an-additional-migration-option" id="what-to-verify-after-using-an-additional-migration-option"></a>

Every additional migration option should be followed by target-store review. The validation focus should match the purpose of the option.

| Option used                               | What to verify                                                                                               |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Continue with the last used configuration | Later source-store records appear correctly, and the previous target-store result remains usable.            |
| Continue with a new configuration         | The revised configuration produced the expected target-store result.                                         |
| Perform a new migration                   | The target store reflects the intended fresh result and does not rely on unwanted previous migration output. |

Validation should include the records most important to the business: products, customers, orders, Blog Posts, CMS Pages, reviews, coupons, URLs, mappings, filtered records, Add-on-affected records, and Custom Service-related data where relevant.

A migration action is successful only when the customer can confirm that the target store supports the intended next business step.

### Common Mistakes to Avoid <a href="#common-mistakes-to-avoid" id="common-mistakes-to-avoid"></a>

#### Choosing continuation when the result should be replaced <a href="#choosing-continuation-when-the-result-should-be-replaced" id="choosing-continuation-when-the-result-should-be-replaced"></a>

Continuation is useful when the customer wants to build on earlier migration activity. If the earlier target-store result should no longer be used, performing a new migration may be more suitable.

#### Performing a new migration when configuration adjustment is enough <a href="#performing-a-new-migration-when-configuration-adjustment-is-enough" id="performing-a-new-migration-when-configuration-adjustment-is-enough"></a>

A new migration may be unnecessary when the customer only needs to continue with revised settings. If the earlier result is still useful, continuing with a new configuration may provide a more focused path.

#### Ignoring later source-store changes <a href="#ignoring-later-source-store-changes" id="ignoring-later-source-store-changes"></a>

If the source store remains active, new records may appear after earlier migration activity. Customers should consider whether those records need to be included before launch or before the target store is used for business operations.

#### Treating the selected option as a substitute for validation <a href="#treating-the-selected-option-as-a-substitute-for-validation" id="treating-the-selected-option-as-a-substitute-for-validation"></a>

The selected option does not replace validation. Customers still need to confirm that the target store contains the expected data and supports the intended business outcome.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Additional Migration Options help customers decide what to do after migration activity has already taken place under the purchased service license. Continuing with the last used configuration supports efficiency when the previous setup is still suitable. Continuing with a new configuration supports flexibility when settings need adjustment. Performing a new migration supports a fresh target-store result when the earlier migrated result should be replaced.

The best choice depends on the customer’s goal, source-store changes, configuration needs, Entity Points capacity for newly migrated counted records, service responsibility, and validation expectations. If the right option is unclear, Live Chat can help review whether the next step should be continuation, configuration adjustment, a new migration, Add-ons, Custom Service review, or expert-handled execution.

### FAQs <a href="#faqs" id="faqs"></a>

**When do Additional Migration Options become available?**

Additional Migration Options become relevant after migration activity has already been performed under the purchased migration service license. Availability depends on migration history and service availability for the same migration path.

**What is the difference between continuing with the last used configuration and continuing with a new configuration?**

Continuing with the last used configuration uses the previous settings. Continuing with a new configuration allows the customer to review or adjust settings before another execution.

**When should a customer perform a new migration?**

A customer should perform a new migration when the goal is to create a fresh migration result for the same migration path rather than continue from the earlier migrated result.

**Do Additional Migration Options consume Entity Points?**

New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time. Counted records already recorded through the service license do not consume Entity Points again when migrated again.

**Does performing a new migration consume Entity Points again for already recorded records?**

No. Counted records already recorded through the service license do not consume Entity Points again when migrated again, including when a new migration is performed.

**Can customers perform these options manually?**

Yes. Customers on any service model can access and manually perform available migration actions if they choose.

**Who performs these options under Managed Service or Custom Service with Expert Handle?**

Next-Cart performs migration actions based on the customer’s request and agreed service scope. The customer can still perform available actions manually if they choose.

**What should customers check after using an additional migration option?**

Customers should verify that the target store contains the expected data, reflects the intended configuration or migration result, and is suitable for the next business step.
