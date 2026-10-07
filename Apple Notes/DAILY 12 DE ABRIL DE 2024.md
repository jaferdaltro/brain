---
apple-notes-id: 0DA921D2-FAA5-42A1-BD07-1714D6852BD3
---
- RE-5674
- RE-5670 - Re-design edit station (https://compass.scv.apple.com/jira/browse/RE-5670)
	- BRANCH: RE-5670-qa-criteria



 const isChangedName = changedAttributes?.name\[1\].trim().length > 1;

    let success;

    if (isChangedName) { success = await this.args.saveStation(station) }