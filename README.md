# hyprcat

hyprcat is a project for managing a catalog of data products using Hydra and RDF principles.

## `ex.ttl`

`ex.ttl` provides an example of a data product described using the DPROD vocabulary and Hydra for its API interactions. It showcases how to define data products, their inputs/outputs, lifecycle status, and related operations. The file now includes an additional example data product (`:anotherDataProduct`) to demonstrate more variety, and data products are explicitly linked to their lifecycle status using the `dprod:hasLifecycleStatus` property.

## DPROD Vocabulary (`dprod.ttl`)

A basic RDFS/OWL vocabulary for describing data products, named DPROD, has been defined in the `dprod.ttl` file. This vocabulary provides initial definitions for the classes and properties used to describe data products within the hyprcat project. It has been expanded to include more metadata for the ontology itself (like version information, creator, and modification dates) and has more refined comments. Key definitions include:

*   `dprod:DataProduct`: Represents a data product.
*   `dprod:DataProductLifecycleStatus`: Represents the lifecycle status of a data product.
*   `dprod:inputDataset`: Property to link a data product to its input dataset(s).
*   `dprod:outputDataset`: Property to link a data product to its output dataset(s).
*   `dprod:hasLifecycleStatus`: Property to link a data product to its lifecycle status.

This vocabulary is expected to evolve as the project progresses.

## SHACL Shapes for Validation (`shapes.ttl`)

The `shapes.ttl` file contains SHACL (Shapes Constraint Language) shapes designed to validate the RDF data describing data products, such as the examples found in `ex.ttl`. These shapes help ensure that the data conforms to the expected structure and types as defined by the DPROD vocabulary.

Currently, the shapes for `dprod:DataProduct` instances check for:
*   The presence of exactly one `dct:title` which must be a string.
*   The existence of at least one `dprod:outputDataset`, which must be an IRI pointing to a `dcat:Dataset`.
*   An optional `dprod:hasLifecycleStatus` (at most one), which must be an IRI pointing to a `dprod:DataProductLifecycleStatus` instance.

**Conceptual Usage Note:** These shapes can be used with a SHACL validating processor to check the conformance of RDF data defining data products. For example, you could use a command-line tool or a library like PySHACL to validate your data against these shapes.

## Key Technologies

The key technologies used in this project include:

*   **RDF (Resource Description Framework):** A standard model for data interchange on the Web.
*   **Turtle (Terse RDF Triple Language):** A syntax and file format for expressing data in the RDF data model.
*   **Hydra:** A lightweight vocabulary to create hypermedia-driven Web APIs.
*   **DPROD vocabulary:** A domain-specific vocabulary (defined in `dprod.ttl`) for describing data products, including classes like `dprod:DataProduct` and properties like `dprod:inputDataset` and `dprod:hasLifecycleStatus`.
*   **SHACL (Shapes Constraint Language):** A language for validating RDF graphs against a set of conditions (defined in `shapes.ttl`).