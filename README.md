# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without checking if it's actually a number. This can lead to unexpected behavior or crashes if a non-numeric ID is provided.

## Bug

The `bug.js` file contains the faulty code.  It attempts to find a user based on the provided ID, but it doesn't handle the case where the ID is not a valid number.  This can result in errors like `NaN` being used in comparisons, or even exceptions if the parsing fails completely.

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It includes error handling to check if the `userId` is a valid number before attempting to parse it and use it in a database lookup. This prevents crashes and provides a more graceful user experience.