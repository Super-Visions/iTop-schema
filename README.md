# iTop DataModel XSD

[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat-square)](https://github.com/rudnerbjoern/iTop-schema/issues)

This project provides an **XSD schema** to validate `datamodel.xxx.xml` files used in the [iTop CMDB software](https://www.combodo.com/itop).

The goal is to catch **syntax errors** and **inconsistencies** in your iTop data models *before* importing them into iTop.

## Current Status

- Supported iTop design versions:
  - [Version 3.2](https://www.itophub.io/wiki/page?id=latest:customization:xml_reference#version_32)
- The project is in an **early stage**:
  - The XSD is still **incomplete**.
  - Many **errors and gaps** are expected.
  - More advanced validations (e.g. for attribute types and relations) are not yet implemented.

## How to Help

**Contributions are very welcome!**

- If you have experience with iTop data models or XSD, please help us improve this schema.
- Issues, suggestions, and pull requests are highly appreciated.
- Testing with real-world `datamodel.xml` files is extremely helpful.

## Usage

You can either:

  1. Download the latest `itop_design.xsd` file.
  2. Validate your `datamodel.xml` with your preferred XML validator.

or if you have a directly link it into your datamodel like this:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<itop_design version="3.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/rudnerbjoern/iTop-schema/refs/heads/main/3.2/itop_design.xsd">
```

WARNING: when using the `xml-model` declaration the datamodel will not be processed by the iTop installer!

```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://raw.githubusercontent.com/rudnerbjoern/iTop-schema/refs/heads/main/itop_design.xsd"?>
<itop_design xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="3.2">
```

or use a tool like `xmllint`:

```bash
xmllint --noout --schema https://raw.githubusercontent.com/rudnerbjoern/iTop-schema/refs/heads/main/3.2/itop_design.xsd datamodel.xml
```

## Contributors

Thanks to everyone who has contributed to this project!

Special thanks to:

- [@Hipska](https://github.com/Hipska) — for valuable additions, corrections, and improvements to the XSD.
