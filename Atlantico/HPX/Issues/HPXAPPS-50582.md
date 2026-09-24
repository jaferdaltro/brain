https://hp-jira.external.hp.com/browse/HPXAPPS-52592
## Device Mgmt-Device Details Progressive Loading (Data Fetching Coordination)

### Acceptance Criteria
- Documentation
- Skelenton display time is explicitly considered
- Loading Dependencies
- Technical review completed with the engineering team

### Description
- Should the parent container orchestrate all data fetches (cascade pattern)?
- Or should sections fetch their own data (parallel pattern)?
- Which approach minimizes skeleton display time?

### PERGUNTAS
- Na primeira vez em que o loading funcionar pegaremos o load que é um preview.
- Loading do device list
- com o device id pegamos o device status, poderia ter o fetch do tracking card 
- Use device data - use coordinator device data, 
	- context devices ( ele quis me mostrar o context devices)
	- existe um lugar que é feito o fetch dos dados
		- useCoordinator device data - investigar 
	
- A sequencia de loading


https://hp-jira.external.hp.com/browse/HPXAPPS-51567