Introduction
----
This repository contains the scripts and data which was used to create the Crónica particular de San Fernando edition. The copyright of the
images prevents them from being shared openly.

This repository can be used to rebuild some of the edition data (excluding images) or the data can be built later using
the editoria admin tools. The critical edition data can only be rebuild using the estoria-admin tools.


Requirements
----
nodejs


Additional requirements for building the data
----
To run the scripts that build the data lxml must installed either globally or in a python virtual environment.
Alternatively if you are also installing editoria-admin the virtual evinroment set up in that process can be used.

Installation
----

Clone the repository into a directory which is not used for serving the files (e.g. your home directory). Once build
the files will be moved to the location from which it will be served. In the example below the repository was cloned as
**cpsf-digital**.

The repository has a submodule which must also be initialised as follows.

```bash
git submodule init
git submodule update
```

Navigate to the edition directory and install the node modules.
```bash
cd cpsf-digital/edition
npm install
```

Optional: Build the data that can be built here:

navigate the the script directory and run the relevant scripts
```bash
cd src/assets/scripts
python make_paginated_json.py
python add_html_to_paginated_json.py
python make_chapter_index_json.py
python make_reader.py
python make_critical_chapter_verse_json.py
python make_verse_page_index_json.py
python make_translation.py
python make_cpsf_critical.py
```

build the webpack package

```bash
npm run build
```

to test locally you can run

```bash
npm start
```

To serve the files in production the contents of the edition/dist directory needs to be copied to the location that
will server the edition.

For the estoria-admin tools to work properly the collation directory in this repository must be sym linked to the data
directory in the location serving the edition.
