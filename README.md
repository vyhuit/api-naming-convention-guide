# api-naming-convention-guide
Naming conventions for API endpoints are important for creating clear, consistent, and maintainable APIs. While there is no strict standard, following common conventions can make your API more intuitive and easier to work with. Here are some common practices:

**1. Use Nouns for Resources:**

> Endpoint names should generally represent the resource being accessed. Use nouns to describe the resource rather than verbs.

~~~js
// Good
/users
/products

// Avoid
/getUsers
/retrieveAllProducts
~~~

**2. Use Plural Nouns or Singular Nouns:**

> Represent collections with plural nouns to indicate that the endpoint deals with **multiple instances of a resource**.

> If an endpoint represents **a singleton resource** (an instance of a resource), use a singular noun.

~~~js
// Good
/users // Return many
/product //Return one

// Avoid
/user // Return many
/products //Return one
~~~

**3. Hierarchy and Nesting:**

> Represent relationships between resources through hierarchy or nesting. Use slashes to indicate nested resources.

~~~js
// Good
/organizations/{org_id}/users
/products/{product_id}/reviews

// Avoid
/getOrganizationUsers
/productReviews
~~~


**4. Use HTTP Methods for Operations:**

> Use HTTP methods (GET, POST, PUT, DELETE, etc.) to represent operations on resources. The combination of the HTTP method and the endpoint path should convey the action.


~~~js
// Good
GET /users        // Retrieve all users
POST /users       // Create a new user
GET /users/{id}   // Retrieve a specific user
PUT /users/{id}   // Update a specific user
DELETE /users/{id}// Delete a specific user

// Avoid
/getAllUsers
/createNewUser
~~~


**5. Avoid Verbs:**

> Try to avoid using verbs in endpoint names. The HTTP method should already indicate the action.

~~~js
// Good
POST /users       // Create a new user
PUT /users/{id}   // Update a specific user

// Avoid
/createUser
/updateUser/{id}
~~~

**6. Use Consistent Naming Conventions:**

> Maintain consistency in naming across your API to make it more predictable.


~~~js
// Good
/users
/users/{id}
/users/{id}/posts

// Avoid
/user
/user_id/{id}
/user_posts
~~~

**7. Use Hyphens or Underscores? Choose one of them:**

> Choose either hyphens or underscores to separate words in your endpoint paths. Stick to your chosen convention consistently.

~~~js
// Good
/user-profiles
/product-reviews

// Avoid
/user_profiles
/productReviews
~~~

**8. Versioning:**

> Consider including API versioning in your endpoint paths to handle changes without breaking existing clients.

~~~js
// Good
/v1/users
/v2/products

// Avoid
/users?version=1
~~~


**9. Handle Errors Gracefully:**

> Design a consistent error-handling mechanism. Use appropriate HTTP status codes and provide informative error messages in the response body.


~~~js
// Good
404 Not Found
{
  "error": "User not found"
}

// Avoid
200 OK
{
  "error_code": 404,
  "error_message": "User not found"
}
~~~

**10. Security Considerations:**

> Implement proper authentication and authorization mechanisms. Use HTTPS to secure data transmission. Avoid exposing sensitive information in URLs.


~~~js
// Good
POST /login
GET /users/{id}

// Avoid
GET /get-user-by-token/{token}
~~~

**11. Documentation:**

> Provide comprehensive and up-to-date documentation for your API. Include details on endpoint usage, expected parameters, response formats, and examples.


~~~js
// Good
GET /users/{id}
Retrieves information about a specific user.

// Avoid
Endpoint not documented.
~~~