# Archetypes

This repository is collecting archetype representing logical units in a dataset starting as small as quantities as union of a value and a unit to archetypes for chemicals, instruments and references finally to complete metadata standards for specific experiments.

It is meant as a starting point by providing an easy way to specify the data model used in existing template (experimental: NanoFASE, NANoReg, CHADA, in silico: MODA, QMRF). This will be used:
1) to compare these standards and prepare recommondation for metadata coverage and completeness.
2) to generate a system to prepare a data model from predefined archetypes and create customised templates
3) to add more advanced features for data management, semantic annotation and FAIR sharing
4) to guide the ontology development with respect to the needed terminology but also to build relationships between the terms for generating an ontology-driven pre-reasoning capacity for the datasets.

### Some hopefully easy steps for supporting this collection of achetypes:
1) Use examples of existing metadata files from your work (your own data capturing templates, MODA templates, or just material and methods from your papers)
2) Extract major information and group them in logical units - start from the defined units if existing (e.g. for MODA and CHADA)
3) If possible, translate these values and the structure into a yaml file - it is really a quite simple format (this is the first tutorial I found: https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started) and good editors exist checking the correctness of the format - please only use the simple features (no references or something like this).
4) Look at existing archetypes and reuse them whenever possible.
5) Stop at the level of detail from when on existing archetypes can be used - e.g. references don't have to be completely specified since we know what is needed to define them.
6) Transfer the collected data into an archetype specification - make a copy of your metadata file you created in 3) and replace the values with variable types.

    a) Basic variables like strings and numbers can directly be specified but please use the archetype "quantity" whenever you specifiy a value which has a unit.

    b) Subsections needing a lot of information should be placed in a separate file defining a new archetype - this should also be done if the structure can be reused starting from quantities as just a combination of value and unit.

    c) Reused archetypes are just given by their name and the corresponding yaml file should exist.

    d) The real values from your dataset can be kept as comments (starting with "#") to make it easier for others to understand what should be described in a field. 
7) If you see need to extend more basic archetypes, go ahead and add the needed fields.
8) If there is already an achetype for a specific logical unit and you disagree with its layout, define an alternative archetype in a new file (make the use case explicite, e.g. there is a file NumericalSolver-Atomistic-MD.yaml in the MODA directory and we expect many more alternative archetypes for specific simulation types) - everything here are just proposals and after we have more examples, we can then still try to harmonise.
9) When templates are created from the archetypes, it is not expected that everyone will fill in every field.

    a) This allows to have alternative fields in the archetype.

    b) The use case of the archetype will then determine what values are important - e.g. mass or volume can be specified for the amount of a chemical used (archetype chemical).

    c) Please decide how large the changes of an existing archetype have to be to fulfil your needs - based on this, use alternative archetype definitions (point 8) or add alternative fields in the existing archetype (this point 9)
10) We appriciate any form of help:

    a) Send us the structure of your data model separated in archetypes as hand drawings, spreadsheets or documents
 
    b) or create yaml files and send them to us with some description.

    c) or clone the repository, create a new branch and send us a pull request so that we can check and include the changes in the master branch.


### Open questions:
1) How do we treat general archetypes, which needs to then be replaced by more specific ones? For example: general reference --> paper (with specific fields like issue and page numbers not included in references like talks and posters)
2) Should we allow to mark mandatory information?
