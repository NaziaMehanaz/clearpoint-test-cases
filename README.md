# clearpoint-test-cases
Pre Requisite:

Docker Installed, PostMan Client Installed and Git Hub account 

Environment Variables set for Host and Port

Test case summary:

Create an Item and make sure it is created and can be retrieved via uuid and via list all items.

Scope:

1. Item creation happy path (201) / failure scenarios (409, 400)
2. List all items (200) 
3. List Item via uuid (200) / (404)


How did we assert item is created successfully?

1. Checked response 201
2. Asserted response body contains a uuid 
3. Called get item by uuid using that uuid and make sure it returns 200

How did we assert only one item was added?

1. Count all items at the start of test 
2. Count all items at the end of test to make sure count is 1 greater than initial count

What failure scenarios we tested:

1. Item creation bad request (400) where we called POST without item description 
2. Item creation conflict (409) by posting the request with same item description as used at the time of successful creation of item api call
3. Fetch item by a random (possibly invalid uuid) and get not found 404

Execute the tests:
Right Click on the Collection and Click run collection and click Run Click_item_create_testcases
