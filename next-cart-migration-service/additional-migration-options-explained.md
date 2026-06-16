# Additional Migration Options Explained

After a migration is performed with a purchased migration path, the customer may need to continue using the same path. The source store may keep receiving new orders, customers, products, or content while the target store is being prepared. The customer may also decide that the earlier migrated result should be refreshed with a new migration setup.

Next-Cart supports these needs as part of the complete migration experience. The available actions depend on the customer’s migration history for the purchased migration path, but the purpose is straightforward: help the customer continue migration activity when the target store needs newer data, a revised configuration, or a fresh migration result.

### What Can Be Done After a Migration Has Already Been Performed <a href="#what-can-be-done-after-a-migration-has-already-been-performed" id="what-can-be-done-after-a-migration-has-already-been-performed"></a>

After performing a migration using the purchased migration path, customers can access the license again and continue the migration process with the same migration path. Depending on the migration history, they may be able to choose one of three actions:

| Action                                                  | What it is for                                                                 | Typical customer goal                                                                                       |
| ------------------------------------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | Continue migration activity using the previous migration configuration         | Add newer source data to the target store without rebuilding the configuration from the beginning           |
| Continue the Migration with a new configuration         | Continue migration activity after reviewing or changing configuration settings | Add newer source data while adjusting selected entities, mapping choices, Add-ons, or configuration details |
| Perform a new migration                                 | Run a new migration for the same migration path                                | Replace the earlier migrated result with a fresh migration setup or changed migration scope                 |

For a first-time migration with the purchased migration path, customers follow the normal migration flow: set up platform connections, configure migration with the available migration options and any purchased Add-ons, then execute migration. The continuation and new-migration actions become relevant only after migration activity has already taken place.

### Continue the Migration with the Last Used Configuration <a href="#continue-the-migration-with-the-last-used-configuration" id="continue-the-migration-with-the-last-used-configuration"></a>

Continue the Migration with the last used configuration is useful when the previous migration setup is still correct, and the customer wants to continue migration activity without repeating configuration work.

This action is usually appropriate when the source store has continued operating after an earlier migration, and the target store needs newer records before launch or before another review round. The customer’s main concern is not redesigning the migration setup; it is keeping the migrated target data closer to the latest source-store state.

A customer might use this action when:

* the earlier migration configuration already produced the expected result;
* the source store has received newer orders, customers, products, or content after the earlier migration;
* the customer wants to preserve the previous configuration choices;
* the target store needs a later data update before launch or final verification.

This action is not a substitute for reviewing the target store. After continuing the migration, the customer should verify that the expected newer records are present and that existing migrated data still behaves as intended.

### Continue the Migration with a New Configuration <a href="#continue-the-migration-with-a-new-configuration" id="continue-the-migration-with-a-new-configuration"></a>

Continue the Migration with a new configuration is useful when the customer wants to continue migration activity, but adjust the setup before execution.

This action is different from continuing with the last used configuration because the customer intentionally reviews or changes migration settings. The customer may need to update selected entities, revise mapping decisions, apply or adjust Add-ons, or change configuration details before continuing.

A customer might use this action when:

* the earlier configuration needs adjustment before another migration run;
* the Demo Migration or validation review revealed mapping details that should be changed;
* the customer has purchased or adjusted Add-ons that affect the next migration run;
* the target store preparation changed after the previous migration;
* the customer wants to continue migration activity without treating the project as a fully fresh migration.

This action is useful when the goal is still to continue from previous migration activity, but the next run should not blindly reuse the previous setup.

### Perform a New Migration <a href="#perform-a-new-migration" id="perform-a-new-migration"></a>

Perform a new migration is useful when the customer wants to run a fresh migration for the same migration path instead of continuing from the earlier migrated result.

This action should be considered when the previously migrated target data needs to be replaced due to a new migration setup or a changed migration scope. It is not simply another way to add newer source records. It can change the target result more substantially because the migration is being performed again according to the new setup.

A customer might use this action when:

* the earlier migrated result should no longer be used as the working target-store result;
* the migration configuration or scope has changed enough that continuing is not appropriate;
* the customer wants to rebuild the target data based on a new migration setup;
* the target store used for earlier testing should be refreshed before a more serious migration review;
* the customer needs a cleaner result after earlier setup, mapping, or target-store decisions changed.

Before performing a new migration, the customer should understand that the earlier migrated target result may be replaced according to the new migration setup. The correct choice depends on whether the business goal is to update the previous result or create a new one.

### How Service Models Affect Who Performs These Actions <a href="#how-service-models-affect-who-performs-these-actions" id="how-service-models-affect-who-performs-these-actions"></a>

Customers of any service model can access and perform available migration actions manually if they choose. The service model determines who is primarily responsible for performing migration actions and what level of Next-Cart involvement is included.

| Service model                        | Who performs migration actions                                                                                                                                           | Customer responsibility                                       |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------- |
| Standard Service                     | The customer performs migration actions.                                                                                                                                 | The customer verifies the final result and migration outcome. |
| Custom Service without Expert Handle | The customer performs migration actions.                                                                                                                                 | The customer verifies the final result and migration outcome. |
| Managed Service                      | Next-Cart performs migration actions based on the customer’s request. The customer can still perform available actions manually if they choose.                          | The customer verifies the final result and migration outcome. |
| Custom Service with Expert Handle    | Next-Cart performs migration actions based on the customer’s request and agreed service scope. The customer can still perform available actions manually if they choose. | The customer verifies the final result and migration outcome. |

With any service model, the customer remains responsible for final result verification and migration outcome. Expert handling can reduce execution burden, but it does not remove the need for customer-side review of business accuracy, storefront readiness, and launch suitability.

### How These Actions Affect Entity Points <a href="#how-these-actions-affect-entity-points" id="how-these-actions-affect-entity-points"></a>

New data entities consume the corresponding Entity Points when they are migrated. Data entities that have already been recorded through the migration service license do not consume Entity Points again when migrated again, even if the customer performs a new migration that replaces the previous migration result.

This distinction matters because the customer’s action choice does not automatically determine Entity Points consumption. The relevant question is whether the migration includes new data entities or already recorded entities.

For example, if newer orders were created after the earlier migration and are migrated for the first time, those orders can consume Entity Points. If an already recorded order is migrated again as part of a new migration, that already recorded entity does not consume Entity Points again.

### How to Choose the Right Action <a href="#how-to-choose-the-right-action" id="how-to-choose-the-right-action"></a>

The right action depends on the customer’s goal after the earlier migration.

| Customer goal                                                                | Better action to consider                                                                                                         |
| ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Keep the previous configuration and add newer source data                    | Continue the Migration with the last used configuration                                                                           |
| Add newer source data but adjust configuration first                         | Continue the Migration with a new configuration                                                                                   |
| Replace the earlier migrated target result with a fresh migration setup      | Perform a new migration                                                                                                           |
| Review a target store closer to launch after the source store kept operating | Continue the Migration with the last used configuration or with a new configuration, depending on whether settings need to change |
| Correct a migration setup that no longer reflects the desired target result  | Perform a new migration                                                                                                           |

The safest decision is the one that matches the desired target-store outcome. If the previous migration result is still useful, continuing the migration is usually the more relevant direction. If the previous result should be replaced, performing a new migration is usually the clearer choice.

### What to Validate After the Action <a href="#what-to-validate-after-the-action" id="what-to-validate-after-the-action"></a>

After continuing the migration or performing a new migration, validation should focus on the specific goal of the selected action.

If the customer continued the migration, validation should confirm that the expected newer records were added and that the previously migrated data remains usable. Important checks may include newer orders, newer customers, updated products, new content, and any data affected by changed configuration choices.

If the customer performed a new migration, validation should confirm that the target store reflects the newly selected migration scope and configuration. The customer should also confirm that outdated or unwanted results from the earlier migration are not being relied on for launch decisions.

In both cases, validation should include business-sensitive samples, not only total record counts. The customer should review whether the migrated data is accurate, usable, and suitable for the next business step.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Continuing migration activity and performing a new migration support different customer goals after an initial migration has already been performed. Continuing the migration helps keep the target store aligned with later source-store activity, either with the last used configuration or with a revised configuration. Performing a new migration is more appropriate when the previous migrated result should be replaced by a fresh migration setup.

The right choice should be based on the desired target-store outcome, the configuration changes needed, the customer’s service model, and the validation work required after execution. Customers should treat these actions as part of responsible migration planning rather than as last-minute fixes before launch.

### FAQs <a href="#faqs" id="faqs"></a>

**Can I continue migration activity after completing a migration?**

Yes. After performing a migration with the purchased migration service license, customers can access the license again and continue working with the same migration path when available. They may be able to continue with the last used configuration, continue with a new configuration, or perform a new migration.

**What is the difference between continuing the migration and performing a new migration?**

Continuing the migration is used when the customer wants to keep working from previous migration activity, usually to add newer source data or adjust configuration before another run. Performing a new migration is used when the earlier migrated target result should be replaced by a fresh migration setup.

**Can customers perform these actions manually under any service model?**

Yes. Customers of any service model can access and perform available migration actions manually if they choose. Standard Service customers and Custom Service customers without Expert Handle perform migration actions themselves. Managed Service customers and Custom Service customers with Expert Handle can ask Next-Cart experts to perform migration actions based on the customer’s request and agreed scope.

**Do already migrated entities consume Entity Points again?**

No. New data entities consume the corresponding Entity Points when they are migrated. Data entities that have already been recorded through the migration service license do not consume Entity Points again when migrated again, even if the customer performs a new migration that replaces the previous migration result.

**What should be checked after continuing the migration?**

The customer should verify that the expected newer records were added and that previously migrated data still behaves correctly. Validation should focus on business-sensitive samples such as newer orders, newer customers, updated products, new content, and any data affected by configuration changes.

**What should be checked after performing a new migration?**

The customer should confirm that the target store reflects the new migration setup and selected scope. The customer should also verify that the result is suitable for the next business step and that outdated assumptions from the earlier migrated result are not used for launch decisions.
