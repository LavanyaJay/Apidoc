

This object represents a user. The user has to sign in to create events and tickets.

.. raw:: html

   <div class='cli'>
   http GET :5000/user/1
   </div>

The User object
---------------

.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - id
     - integer
     - Unique id representing the user
   * - email
     - url
     - Email address of the user
   * - userName
     - string
     - Name of the user
   * - password
     - string
     - Password for the user
   
   

.. code-block:: json

    {
    "id": 3,
    "email": "User-3@abc.com",
    "userName": "User-3",
    "password": "$2b$10$G8kI9cUooIAOTZtwYp1fNeXF4E.sqtBsnFbyHKPbryFuRdDtOZOIS",
    "createdAt": "2020-02-01T06:21:10.172Z",
    "updatedAt": "2020-02-01T06:21:10.172Z"
    
}
   
Retrieve User
-------------
Retrieve a user by user id.

.. raw:: html

   <div class='cli'>
    http GET :5000/user/1
   </div>

Arguments
^^^^^^^^^
.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - id :sup:`REQUIRED`
     - integer
     - Represents unique user id 

Returns
^^^^^^^
A single user
 
.. code-block:: json

    {
    "id": 1,
    "email": "som@abc.com",
    "userName": "Som",
    "password": "$2b$10$G8kI9cUooIAOTZtwYp1fNeXF4E.sqtBsnFbyHKPbryFuRdDtOZOIS",
    "createdAt": "2020-01-30T06:21:10.172Z",
    "updatedAt": "2020-01-30T06:21:10.172Z"
   }

Create User
-----------
Create a new user.

.. raw:: html

   <div class='cli'>
   <pre>
     http POST :5000/user
               email="User-3@abc.com"
               username="User-3"
               password="test123"        
   </pre>      
   </div>

Arguments
^^^^^^^^^
.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - email :sup:`REQUIRED`
     - url
     - The email represents the unique user identification
   * - username :sup:`REQUIRED`
     - string (max of 255 characters)
     - Name of the user
   * - password :sup:`REQUIRED`
     - string, (max of 10 characters)
     - Password for the user verification  

Returns
^^^^^^^
.. code-block:: json

   {
    "id": 3,
    "email": "User-3@abc.com",
    "userName": "User-3",
    "password": "$2b$10$G8kI9cUooIAOTZtwYp1fNeXF4E.sqtBsnFbyHKPbryFuRdDtOZOIS",
    "createdAt": "2020-02-01T06:21:10.172Z",
    "updatedAt": "2020-02-01T06:21:10.172Z"
   }


















