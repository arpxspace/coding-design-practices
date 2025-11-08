Dont abuse DRY just for the sake of 'typing less' code and making it look pretty. At the end of the day we want to achieve QWAN.

DRY aims to reduce redundancy and **centralise** some logic that can be reused in many places
- If multiple parts of your codebase need to enforce the same rule—like calculating a tax rate, validating an email format, or applying a discount—DRY makes sense. Centralizing that logic in one place ensures consistency and makes updates easier. For example, don’t write the same tax formula in ten different spots; put it in a single function.
- Repeated hardcoded values (e.g., magic numbers like 3.14159 or strings like "https://api.example.com") are a maintenance nightmare. DRY them up into a single source of truth, like a constants file or config module, so changes propagate automatically.


