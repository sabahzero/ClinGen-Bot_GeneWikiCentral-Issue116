# ClinGen Bot for Automation, Gene Wiki Central Issue #116
This Github repository is a complete workflow tackling </br>
SuLab > GeneWikiCentral > Issues: https://github.com/SuLab/GeneWikiCentral/issues/116 </br>
from start to finish (including debugging) </br>
![Gene Wiki Central Issue #116](https://github.com/sabahzero/ClinGen-Bot_GeneWikiCentral-Issue116/blob/master/README-images/GeneWikiCentral-Issue116.png)

The operating, weekly scheduled bot can be viewed in the [Su Lab repository](https://github.com/SuLab): </br>
Uploaded in SuLab > scheduled_bots > clingen: https://github.com/SuLab/scheduled-bots/tree/master/scheduled_bots </br>  

with up-to-date console output viewable via Jenkins: </br>
http://jenkins.sulab.org/job/clingen/ </br> </br>

## About
This automated bot retrieves gene-disease validity data from [ClinGen](https://search.clinicalgenome.org/kb/gene-validity) and integrates it into [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page) as 'genetic association' statements for both gene and disease item pages on a weekly basis. </br></br>
Example gene A2ML1: </br>
https://www.wikidata.org/wiki/Q18051234
![Genetic Association for A2ML1](https://github.com/sabahzero/ClinGen-Bot_GeneWikiCentral-Issue116/blob/master/README-images/Genetic-Association.png)
In this example, we see the last commit by the bot was on October 1, 2019 for this gene-disease association under the gene (A2ML1) item page.

## Validated checks of this bot 
- Classification: A write only occurs for reports in which the gene-disease assocation is "Definitive", or confirmed.
- Symmetry: For every relevant write by gene, identified by the [HGNC ID](https://www.genenames.org/) with an item page on Wikidata, there is a corresponding Wikidata item page for the associated disease (by [MONDO ID](https://www.ebi.ac.uk/ols/ontologies/mondo)) that is also written.
- Missing or multiple QIDs: A write does not occur if there is (a) not a QID available for a gene on Wikidata for that gene-disease association (b) not a QID available for a disease on Wikidata for that gene-disease association, or (c) multiple QIDs for a gene or disease on Wikidata for that gene-disease association. This can be observed in the output file (.csv).
- Updates: A reference is updated if beyond 180 days since the previous write.

## Checks of this bot to be validated
- Removal of entries no longer part of database, or with an adjusted Classification status.

### Contributions and Acknowledgements 
Python script contributions, in order: [Sabah Ul-Hasan](https://github.com/sabahzero), [Andra Waagmeester](https://github.com/andrawaag), [Andrew Su](https://github.com/andrewsu), [Ginger Tsueng](https://github.com/gtsueng) </br>
Support: The Scripps Research Institute, National Institute of Health, ClinGen, Wikidata, Github, Jenkins, Jupyter Notebook, Python
