---
title: Date input test cases
description: "A comprehensive list of the top 10 test cases for testing date input fields manually. Improve your testing strategies with these essential examples."
keywords: ["date input test cases", "manual testing", "date validation", "test cases for dates"]
type: docs
prev: docs/folder/
---

##### 1. Valid Date Format  
   Input a valid date in the expected format (e.g., `YYYY-MM-DD`) and verify it is accepted.

##### 2. Invalid Date Format
   Input an incorrectly formatted date (e.g., `DD-MM-YYYY`) and verify it is rejected.

##### 3. Out-of-Range Date  
   Test with dates outside the acceptable range (e.g., `1900-01-01` or `2100-12-31`).

##### 4. Leap Year Date  
   Test with leap year dates (e.g., `2024-02-29`) to ensure they are handled correctly.

##### 5. Non-Leap Year Date
   Input an invalid leap year date (e.g., `2023-02-29`) and verify it is rejected.

##### 6. Empty Input
   Submit the form with an empty date field to verify appropriate error handling.

##### 7. Boundary Values
   Input the earliest and latest acceptable dates (e.g., `2000-01-01` and `2099-12-31`).

##### 8. Invalid Characters  
   Test with non-numeric characters (e.g., `abcd-ef-gh`) and verify they are rejected.

##### 9. Partial Input
   Enter incomplete dates (e.g., `2024-02` or `2024`) and ensure appropriate errors.

##### 10. If date has "From" and "To" dates swap them around
   The system automatically swaps the dates, setting the earlier date as "From" and the later date as "To."
    