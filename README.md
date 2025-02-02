# MongoDB $inc Operator Unexpected Behavior with Negative Value

This example demonstrates an uncommon error related to the use of the `$inc` operator in MongoDB when dealing with negative values and the absence of a pre-existing field. 

The `$inc` operator is typically used to increment a numeric field. However, when used with a negative value and the field is missing, it throws an error instead of creating the field and setting it to a negative value. This is different from how `$set` would handle the same situation. 

**Bug:** Incorrect usage of `$inc` operator to decrement a non-existing field.

**Solution:** Use `$inc` only if the field is guaranteed to exist or incorporate an additional operation, such as `$setOnInsert`, to handle cases where the field is missing.