# jamboree
Jamboree is a Systems Biology web app designed to support genome-scale metabolic network reconstruction. It's called Jamboree because that's what the metabolic modelling community calls the meetings where we all get together to curate networks. In practice, especially in the beginning when working practices were still being defined, this involved swapping lots of spreadsheets. We've always needed a better platform that allows records (molecular species, reactions and compartments) to be edited collaboratively in near-realtime.

The reconstruction process involves the discovery of missing information, its curation by biochemistry experts, and integration of curated information into the network. The goal of Jamboree is to allow curators to curate. Jamboree includes to discover missing information and incorporates changes into the network as they are made.

# Design
The Systems Biology community uses a data standard called SBML to represent genome-scale metabolic models. Essentially the app consists of a front end written in Angular JS, a Flask-based middle layer and a backend built around the SBML library libSBML. Conventionally one might use a more standard database backend (we trialled plenty - Neo4j, RethinkDB) but ended up using an in-memory datastore principally because libSBML works with most SBML files which, it has to be said, are not always assembled following best practices. The libSBML team have done an awesome job that isn't easy to replicate, so we didn't.

# Deployment
Due to the way university research is funded it can be difficult to support web app hosting costs once the money runs out. The idea here is that the reconstruction leaders are responsible for installing and hosting the web app on their own web (ideally Cloud) server. So if you're planning to coordinate a new reconstruction you would set up the app on your server and then invite collaborators to join your team. To keep installation simple the entire app runs out of a Docker container.

