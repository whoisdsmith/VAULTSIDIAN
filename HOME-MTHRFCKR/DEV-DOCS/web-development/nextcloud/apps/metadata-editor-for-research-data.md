---
tags:: apps
---
# Metadata Editor for Research Data 🔬
A Nextcloud app to annotate a research data folder with metadata

![](../Apps/files_metadataeditor/img/screenshot_editor.png)
## Features
- add metadata as a JSON file ( `metadata.json`) for a folder with scientific
  data from within the Nextcloud file browser
- enter and edit metadata through web-forms
- the metadata schema is specified as a [JSON Schema](https://json-schema.org),
  which can be used for validating the input data or creating a data model, e.g.
  in a database
- currently the schema is based on the metadata schema of the data publisher
  [PANGAEA](https://www.pangaea.de) with input fields for
  - 👨‍🔬👩‍🔬 authors
  - 🧪🔎 sampling/measurement events 
  - 🚢🛩 campaigns 
  - 🩸🧬 method information

To install the app, copy the folder into the `apps` subfolder of the Nextcloud
folder and activate the app in the admin interface.

## Development
The app is inspired by the [Nextcloud plain text
editor](https://github.com/nextcloud/files_texteditor) and registers
`fileActions` in the `files` app. The Javascript part of the app is based on the
[React](https://reactjs.org) components provided by
[JSONForms](https://jsonforms.io), which render the input forms based on the
JSON Schema.

Documentation on how to develop Nextcloud apps can be found in the [Nextcloud
developer
documentation](https://docs.nextcloud.com/server/latest/developer_manual)


### Developing React input forms
Before working on the Javascript part of the app, npm packages have to be installed with 
```
  npm install
```
The component for entering the data can be developed without a running Nextcloud
server using 
```
  npm start
```
and opening the development server at https://localhost:8080. To build a deployable Javascript bundle in `js/` use
```
  npm run dev
```
for a non-minified development version or
```
    npm run build
```
for a minified production build.
