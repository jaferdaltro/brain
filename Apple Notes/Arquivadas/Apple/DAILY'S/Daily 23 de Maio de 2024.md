---
apple-notes-id: F1A20328-1C28-44A1-AD5A-8655C26AF7B5
---
Orion posição 1

> I'm following Diego with Rails upgrade
> we are looking to reproduce the bug reported by QA related to Insight error

- **5670** foi concluído
- Acompanhar o Diego no Rails upgrade


### Problema com o Insight
**Queries:**
**REL:**
PfaQuery.create_insight_queries(Project.find_by_name('Insightdemo_22may'), { start_date: '2023/05/22', end_date: '2023/10/18', integrity_check: true, stations: Project.find_by_name('Insightdemo_22may').stations.where(name: \['REL'\]), units: Project.find_by_name('Insightdemo_22may').units }). 

**REL-COSMETIC:**
PfaQuery.create_insight_queries(Project.find_by_name('Insightdemo_22may'), { start_date: '2023/05/22', end_date: '2023/10/18', integrity_check: true, stations: Project.find_by_name('Insightdemo_22may').stations.where(name: \['REL-COSMETIC'\]), units: Project.find_by_name('Insightdemo_22may').units })