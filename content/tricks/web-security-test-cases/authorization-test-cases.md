---
title: Authorization Test Cases
description: "Unlock the secrets to effective authorization with essential test cases. Understand how to verify user permissions, enforce access controls, and ensure data protection for a secure application environment."
keywords: ["date input test cases", "manual testing", "date validation", "test cases for dates"]
type: docs
prev: docs/folder/
---

### About:

In the realm of application security, authorization plays a pivotal role in determining access controls. Two important concepts in this space are vertical and horizontal authorization, each serving unique purposes. Let's unpack what they mean:

###### Vertical Authorization:
- Defines what level of access different roles have.
- Often seen in hierarchies where authority escalates upwards.
- Examples include the distinction between admin, manager, and user roles.
- Ensures that higher-level roles have broader access to resources and functions.

###### Horizontal Authorization:
- Distinguishes access among users with the same level.
- Limits users to specific data or actions, even when in the same role.
- Commonly implemented in systems where users manage their own data, like in CRM applications.
- Ensures users can access only their own data or resources, preventing unauthorized access to peer data.

### Test cases:

###### 1. Try force browse the resources your user don't have access to.
###### 2. Attempt to access unauthorized URLs or API endpoints to ensure access is properly restricted.
###### 3. Verify if same authorization applied for all HTTP methods (e.g POST, PATCH, GET)
``` bash
    POST /account?id=<id> → PUT /account?id=<id>
```
###### 4. Try change request Content-Type header. Access controls may be inconsistently implemented across different content types.
``` bash
    POST /api/[…] Content-type: application/xml test → 
    POST /api/[…] Content-type: application/json {”user”:”test”}
```
###### 5. Try to change request file type (Rails app specificaly)
``` bash
    GET /user_data/2341 → GET/user_data/2341.json
```
###### 6. Verify if app still accepts numeric ID insdead of UUID
``` bash
    username=user1 → username=1234
    account_id=7541A92F-0101-4D1E-BBB0-EB5032FE1686 → account_id=5678 
    album_id=MyPictures → album_id=12
```
###### 7. Try replace single id to array of ids
``` bash
    {”id”: 19} → {”id”:[19]}
```

###### 8. Try add -1 so that SQL execute different value after authorization
``` bash
    POST /updateUser user_id=1338 → user_id=1338-1
```

###### 9. Try to remove part of the body to fail access control
``` bash
    POST /api/DeleteUser ...  
    
    {"org_name":"<org_name>", "user_id":"<user_id>"}  
    
    => 403

    To

    POST /api/DeleteUser ....  
    
    {"user_id":"<user_id>"}  
    
    => 200
```

###### 10. Verify that the API response does not expose excessive data.
- Try to see if response does contain any PII (email, date of birth, address) but it is not needed for the front-end

