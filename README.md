# jamboree
Jamboree is a Systems Biology web app designed to support genome-scale metabolic network reconstruction. Jamborees are what the metabolic modelling community calls the meetings where we all get together to curate networks. In practice these often involve swapping lots of spreadsheets. We've always needed a better system that allows molecular species, reactions and compartments to be edited collaboratively in near-realtime.

## Discover Curate Integrate
The reconstruction process involves the discovery of missing information, its curation by biochemistry experts, and integration of curated information into the network. The goal of Jamboree is to allow curators to curate. Jamboree includes tools to discover missing information and incorporates changes into the network as they are made.

# Design
Essentially the app consists of a front end written in Angular JS, a Flask-based middle layer and a backend built around the SBML library libSBML. Conventionally one might use a more standard database backend (we trialled plenty - Neo4j, RethinkDB) but ended up using an in-memory datastore principally because libSBML works with the most SBML file.

# Deployment
Shouldn't a web app be something you just point your browser at? Well, yes, usually, but due to the way university research is funded it can be difficult to support web app hosting costs once the money runs out. The idea here is that the reconstruction leaders are responsible for installing and hosting the web app on their own web (ideally Cloud) server. To keep installation simple the entire app runs out of a Docker container.
