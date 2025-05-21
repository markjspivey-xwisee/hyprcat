# hyprcat

hyprcat is a project for managing a catalog of data products using Hydra and RDF principles.

## `ex.ttl`

`ex.ttl` provides an example of a data product described using the DPROD vocabulary and Hydra for its API interactions. It showcases how to define data products, their inputs/outputs, lifecycle status, and related operations.

## DPROD Vocabulary (`dprod.ttl`)

A basic RDFS/OWL vocabulary for describing data products, named DPROD, has been defined in the `dprod.ttl` file. This vocabulary provides initial definitions for the classes and properties used to describe data products within the hyprcat project. Key definitions include:

*   `dprod:DataProduct`: Represents a data product.
*   `dprod:DataProductLifecycleStatus`: Represents the lifecycle status of a data product.
*   `dprod:inputDataset`: Property to link a data product to its input dataset(s).
*   `dprod:outputDataset`: Property to link a data product to its output dataset(s).

This vocabulary is expected to evolve as the project progresses.

## Key Technologies

The key technologies used in this project include:

*   **RDF (Resource Description Framework):** A standard model for data interchange on the Web.
*   **Turtle (Terse RDF Triple Language):** A syntax and file format for expressing data in the RDF data model.
*   **Hydra:** A lightweight vocabulary to create hypermedia-driven Web APIs.
*   **DPROD vocabulary:** A domain-specific vocabulary (defined in `dprod.ttl`) for describing data products, including classes like `dprod:DataProduct` and properties like `dprod:inputDataset`.