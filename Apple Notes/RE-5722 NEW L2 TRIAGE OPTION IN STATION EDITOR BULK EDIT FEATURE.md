---
apple-notes-id: 2ED208CD-4F3B-4B5D-921B-E35CFDADB8C8
---
<a href="https://github.pie.apple.com/reliability/recon-ui/tree/auto-l2-triage" rel="noopener" class="external-link" target="_blank"><u>auto-l2-triage</u></a>

**Problem Statement**
As of now, since we currently do not support L2 Triage selection in the Station Editor UI, we also do not have an option to select L2 Triage in the Bulk Edit functionality which exists on the Station Editor sidebar, we need to add this as part of the Auto L2 Triage epic.

**Proposed Technical Implementation**
- Add a new option for L2 Triage below the L1 Triage one
- Bind the L2 Triage selection to the L1 Triage one, only allow to select the L2 from the L1
- Keep the L2 Triage select disabled and with a placeholder "Select L1 first" if no L1 was selected
- Increment the Bulk Edit feature with the L2 Triage values
- Make sure the feature is working as expected now for L2 Triage values also

**Definition of Done**
This ticket should be considered completed when the L2 Triage Bulk Edit option in the Station Editor UI is created and the functionality is working as expected.


![[Pasted Graphic 32.png]]

### Prerequisite:
1. A valid project should exist
2. Few Stations should be created on Stations page (Say PARAMETRIC)
3. User should have uploaded station files from Upload Station CSV page

### Steps:
1. Navigate to Setup > Stations
2. Select prerequisite station "PARAMETRIC"
3. Now select "All Builds" option from Build dropdown
4. Select few results check boxes for doing bulk edit
5. Click on Bulk edit icon and expand Bulk edit section
6. Now observe

### Expected Result
1. L2 Triage option should be displayed below L1 Triage
2. Placeholder text "Select L1 first" should be displayed in L2 Triage field
3. L2 Triage field should be disabled till the user selects L1 Triage
4. The correct value of L2 triage should be displayed as per the L1 Triage selection
5. User should not be able to select more than 1 value from L2 triage
6. Selected results should be updated on clicking Apply button
7. If L1 Triage is not having any L2 Triage value then user should not be able to select/add any random L2 Triage value
8. Newly created L2 value should be displayed on L2 Triage filter
9. Clear field? checkbox should be displayed infront of L2 Triage field
10. The selected value should be cleared on selecting the Clear field checkbox
11. The field should get blank if user deselects the Clear field checkbox
12. L2 Triage value should be removed when user click on Clear All button

ResultsRow.reindex 


![[Pasted Graphic 11 1.png]]


![[Pasted Graphic 1 16.png]]

this.args.changes.station_column_default_l2_triage_id