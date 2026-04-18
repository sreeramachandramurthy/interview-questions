# MongoDB

## Basics

1. What is MongoDB?

    MongoDB is a NoSQL, document-oriented database that stores data in flexible, JSON-like documents (BSON). It emphasizes horizontal scalability, rich querying via documents, high availability via replica sets, and flexible schema design.

2. What is BSON? How is it different from JSON?

    BSON (Binary JSON) is MongoDB’s binary representation of JSON-like documents. It supports additional data types (e.g., Date, Binary, ObjectId) and is designed for efficient encoding/decoding and traversal. Unlike JSON, BSON includes length prefixes and type information which enables faster parsing and storage with richer types.

3. What is a collection and what is a document in MongoDB?

    A document is the basic unit of data in MongoDB — a set of key-value pairs (like a JSON object). A collection is a group of documents (similar to a table in RDBMS). Collections are schema-flexible (documents in the same collection can have different fields).

4. What is an ObjectId? What is its structure?

    ObjectId is the default unique identifier type for _id fields in MongoDB. It’s a 12-byte value: 4-byte timestamp, 5-byte random value, and 3-byte incrementing counter. It encodes creation time and is generally unique.

## CRUD & Querying

1. How do you insert documents? Explain `insertOne` and `insertMany`.

    `insertOne(doc)` inserts a single document; `insertMany([doc1, doc2])` inserts multiple documents atomically per batch (but not across multiple batches). Both return write results and may throw on duplicate _id depending on write concern.

2. How to query documents — explain `find()` and `findOne()`?

    `find(query, projection)` returns a cursor for multiple documents matching the query. `findOne(query, projection)` returns a single matching document or null. Both support filters using MongoDB’s rich query operators.

3. Explain update operations: `updateOne`, `updateMany`, and `replaceOne`.

    `updateOne(filter, updateDoc)` updates first matched document using update operators (e.g., $set). `updateMany` applies to all matches. `replaceOne` replaces the entire document (except _id) with a new document.

4. How does upsert work?
Expected answer: When upsert: true is supplied in an update operation, MongoDB will insert a new document if no document matches the filter; otherwise it updates the matched document.

How to delete documents? (deleteOne, deleteMany)
Expected answer: deleteOne(filter) removes the first matched document; deleteMany(filter) removes all matching documents. Operations return counts of deleted documents.

Explain projection in queries.
Expected answer: Projection limits which fields are returned in query results. Use { field: 1 } to include or { field: 0 } to exclude. _id is included by default unless explicitly excluded.

How do you paginate results in MongoDB?
Expected answer: Use cursor methods: skip() and limit() for basic pagination. Better for large datasets is using range queries or sort on an indexed field and bookmarking the last seen value (cursor-based pagination) to avoid skip-related performance issues.

What is the difference between count(), countDocuments() and estimatedDocumentCount()?
Expected answer: estimatedDocumentCount() uses collection metadata for a fast estimate (may be stale). countDocuments() performs a query to count matching documents accurately. Legacy count() has ambiguous behavior and is deprecated for some uses.