# Edge Case: GET /stats when no students exist

* One edge case I considered is what happens when there are no students in the database. Normally, calculating the average would cause a division-by-zero error, while min() and max() would fail because there are no marks.

* To handle this, the endpoint checks whether the student list is empty before doing any calculations. If it is empty, it returns count, average, min, and max as 0 with a 200 status code. This keeps the response predictable and avoids runtime errors.