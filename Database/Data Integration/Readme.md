# Data Integraation Pattern

A data integration pattern is a standardized method for integrating data. Data integration involves moving, transforming, and consolidating data in all its forms. A data integration pattern helps standardize the overall process, synchronizing the data to provide usable and accessible data.

There are five primary data integration patterns.

## Migration

Migration is the movement of data from a lone source to a destination system at a specific point in time. Data from a source system is filtered using criteria based on the scope of the migration. The data is then transformed to a standard format before it is copied to a destination system. The final state of the replicated data will be inspected to ensure the integrity of the migration.

Migration is agnostic to the tools, systems, and applications that it interacts with. Migration ensures that the total amount of data collected stays intact despite changing components of the migrating organization’s IT landscape. Migration is designed to handle large volumes of data and to process many records simultaneously.

## Broadcast

Broadcast is the movement of data from a lone source to several destination systems continuously. This data integration pattern is transactional in that the logic executes only for the data that has updated since the previous time it moved.

Broadcast ensures that an event in the source system is provided to multiple destination systems automatically – without human intervention – in real-time. Depending on the importance of systems knowing that the event occurred, broadcast can be triggered by the event itself or as scheduled. Broadcast is designed to process data as a quickly as possible.

## Bi-directional Synchronization

Bi-directional synchronization is the union of two datasets from two different systems to perform as one while still existing separately. Bi-directional sync ensures that both systems have a consistent, real-time view of the data in both systems. This is valuable to organizations who need to use different applications from different suites simultaneously.

## Correlation

Correlation is the bi-directional sync performed at the intersection of datasets from two different systems. This pattern does bi-directional sync only with the data that is relevant to both systems. Because irrelevant data is not synchronized, data integration is simpler and more efficient.

## Aggregation

Aggregation merges data from multiple systems into one system, providing a centralized view of real-time data from various systems. Aggregation can retrieve, merge, and transform data from multiple sources as needed without requiring an additional combined system.

SnapLogic is the go-to for integration solutions. Learn why data pipeline patterns — pre-built, reusable integration pipelines that can be configured through a step-by-step wizard — are SnapLogic’s best kept secret.
