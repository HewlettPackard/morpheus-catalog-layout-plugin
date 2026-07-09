# Morpheus Catalog Item Layout Plugin

This plugin provides additional layout selections for catalog items during creation and editing in the Morpheus UI. It adds a `Layout` field to the catalog item form, allowing users to choose how the content and form are arranged.

## 📑 Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Repository structure](#repository-structure)
- [Building the plugin](#building-the-plugin)
- [License](#license)
- [Installing](#installing)
- [Detailed Usage Step](#detailed-usage-step)

---

## Features

- Adds a `Layout` field to the catalog item creation/edit form
- Provides five layout options for arranging content and form:

| Layout | Description |
| ------------- | ------------- |
| Default | The content and form are split side-by-side, in a 1:1 ratio. |
| Stacked | The content is displayed above the form. The form is centered and narrower than the full width. |
| Centered Form Only | The form is centered and narrower than the full width. Intended for when there is no content. |
| Wide Form | The content and form are split side-by-side, in a 1:2 ratio. Intended for when the form labels are long and/or the content is short. |
| Narrow Form | The content and form are split side-by-side, in a 2:1 ratio. Intended for when the content is long and/or the form labels are short. |

---

## Requirements

| Component | Minimum Version |
|----------|----------------|
| Morpheus | 6.3.0  |

---

## Repository structure

- `src/main/groovy/com/morpheusdata/cataloglayout` - Source code for the plugin
  - `CatalogItemStandardLayoutPlugin.groovy` - Plugin entry point (`CatalogItemLayoutPlugin`), registers the layout providers
  - `WideFormCatalogLayoutProvider.groovy` - Implements the Wide Form layout
  - `NarrowFormCatalogLayoutProvider.groovy` - Implements the Narrow Form layout
  - `CenteredFormOnlyCatalogLayoutProvider.groovy` - Implements the Centered Form Only layout
  - `StackedCatalogLayoutProvider.groovy` - Implements the Stacked layout
- `src/main/resources/renderer/hbs` - Handlebars templates used to render each layout
- `src/assets` - Static assets (images and stylesheets) used by the plugin
- `src/test` - Test resources
- `build.gradle` and `gradle.properties` - Build configuration files and dependency versions

---

## Building the plugin

Run the following command to compile and package the plugin jar:

```bash
./gradlew shadowJar
```

The packaged jar will be written to `build/libs`.

To execute tests, use the following command:

```bash
./gradlew test
```

---

## License

Copyright 2024 Morpheus Data, LLC. Licensed under the [Apache License, Version 2.0](LICENSE).

---

## Installing

1. Download the latest `.jar` from the [Releases](https://github.com/HewlettPackard/morpheus-upcloud-plugin/releases) page, or [build it yourself](#building-the-plugin).
2. In Morpheus, navigate to **Administration → Integrations → Plugins**.
3. Click **Browse** and upload the `.jar` file.
4. The **catalog item layout selections** will appear after the plugin loads.

---

## Detailed Usage Step

Once the plugin is uploaded to the Morpheus UI, a `Layout` field should be visible when either creating or editing a catalog item. The field opens a drop-down with the layout options described in [Features](#features).

![](./src/assets/images/catalog-layout-sample.gif)
