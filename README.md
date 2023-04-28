# fnd-to-mcd-materials

Components and how they modify the mule event

- Set variable : new variable
- Logger : no modifications
- HTTP Request : By default, replaces attributes and payload with the HTTP Response (headers and body)
- Batch Job : After its initialization, payload is overridden, no changes from batch job are visible outside.
- Flow Reference: uses same mule event
- Set payload : Modifies only payload
- Choice : no changes
- Scatter-gather: replaces payload with the collection of mule messages from all routes, variables are kept
- DB Select: replaces mule message (attr / payload)
- Most of File operations: replace mule message
- For each : Keeps the original mule message, and retains changes for variables
- Parallel For each : Keeps in the payload the results from transformations for every element of the collection, and retains changes for variables
