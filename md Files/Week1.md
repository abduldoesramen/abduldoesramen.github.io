# Week 1

### Data Modelling

Aims of data modelling:

- Describe what **information** is contained in the database.
- Describe **relationshipos** between data items, e.g JOHN is enrolled in COMP3311.
- Describe **contstraints** on data, e.g student's can't enrol more than certain amount of courses.

Data modelling is a **design** process.

- Converts requirements into a data model.

Kinds of data models:

- **Logical**: abstract, for conceptual design, e.g. ER, UML.
- **Physical**: record-based, for implementation, e.g. relational, SQL.

Strategy: design using abstract model; map to physical model.
Requirements --> ER Model --> (Relational Model) --> SQL Schema [GOAL].

### Some Design Ideas

- Start simple, pick the most obvious things that are relevant to the requirements THEN refine.
- Identify objects and their properties, THEN relationships between objects.
- Most design involve kinds (classes) of people, e.g. customers, executives, branch managers, etc.
- Keywods in requirements suggest data/relationships.
- Don't confuse operations with relationships
  - (Operation: he **buys** a book; relationship (the result): the book is **owned** by him).
- Consider all _possible_ data, not just what is available (e.g. given only SAMPLE data).

```
GMail Data Model
================
Objects:
messages ... title, content, sender*, timestamp
users ... gmail-address, name, password, ...
labels (tags) ... owner, name, colour parent*
settings ... name, value, user*

Relationships:
sender ... messages - users
recipients ... messages - mail-address
has-label ... messages - labels
tag-hierarchy ... child-tag - parent-tag
settings ... user - setting

Constraints:
gmail-addresses are unique/distinct
users must have a password
every message has a timestamp
every message has a sender
message content should not be empty
```

### Quality of Design

No single "best" design for a given application.
Most important aspects of a design (data model):

- correctness (satisfies requirements accurately)
- completeness (all reqs covered, all assumptions explict)
- consistency (no contradictory statements)

Potential **inadequacies** in a design:

- Omits information that needs to be included
- Contains redundant information (-> inconsistency)
- Leads to an inefficient implementation
- Violates syntactic or semantic rules of data model

# ER Model

### Entity-Relationship Data Modelling

World is full of inter-related entities
ER has three major modelling constructs:

- **attribute**: data item describing a property of interest
- **entity**: collection of attributes describing object of interest
- **relationship**: association between entities (objects)

ER diagrams are a graphical _tool_ for data modelling.
An ER diagram consists of:

- A collection of **entity set** definitions
- A collection of **relationship** set definitions
- **Attributes** associated with entity and relationship sets
- **Connections** between entity and relationship sets.

ER diagram example: Rectangles = entites, Ovals = attributes, Diamonds = relationships.
