# Firebase Firestore Transaction Inconsistency

This repository demonstrates an uncommon error in Firebase Firestore transactions related to stale data and optimistic locking.  When multiple clients concurrently update the same document, the transaction might retry using outdated data, causing inconsistencies. The solution focuses on improved error handling and proper data refreshing within the transaction to ensure data consistency.

## Bug Description
The provided `bug.js` demonstrates a scenario where a Firestore transaction updates a document's counter. If multiple users run this code simultaneously, race conditions might lead to incorrect counter values due to stale data in the retried transaction. 

## Solution
The solution in `bugSolution.js` implements more robust error handling and data refreshing. It checks for data updates before completing the transaction, ensuring data consistency and atomicity.