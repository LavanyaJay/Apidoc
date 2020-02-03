

This object represents a ticket. You can retrieve all tickets for an event and also a logged in user can create a ticket.

.. raw:: html

   <div class='cli'>
   http GET :5000/events/1/tickets
   </div>

The Ticket object
-----------------

.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - id
     - integer
     - Unique id representing the ticket
   * - eventId
     - integer
     - Unique id representing the event
   * - tktAuthor
     - string
     - Name of the ticket owner
   * - tktDesc
     - text
     - Detail description of the ticket
   * - tktPrice
     - Decimal (rounded off to 2 places after decimal point)
     - Price of the ticket
   * - tktRisk
     - % number
     - calculated by internal algorithm, denotes the risk factor associated with the 
       ticket
   * - userId
     - integer
     - Unique id representing the ticket owner 

.. code-block:: json

    {
        "id": 1,
        "eventId": 1,
        "tktAuthor": "Som",
        "tktDesc": "Discounted Price",
        "tktPrice": "300",
        "tktRisk": "15.00",
        "userId": 1,
        "createdAt": "2020-01-30T18:54:10.192Z",
        "updatedAt": "2020-01-31T08:53:34.064Z"
        
    }

Retrieve Tickets
----------------
Retrieve a list of all tickets associated with an event. 

.. raw:: html

   <div class='cli'>
   http GET :5000/events/1/tickets
   </div>

Arguments
^^^^^^^^^
.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - eventId :sup:`REQUIRED`
     - integer
     - Represents unique event id 

Returns
^^^^^^^
A list of tickets for an event:
 
.. code-block:: json

     
   [
    {
        "id": 1, 
        "eventId": 1,
        "tktAuthor": "Som",
        "tktDesc": "Discounted Price",
        "tktPrice": "300",
        "tktRisk": "15.00",
        "userId": 1,
        "createdAt": "2020-01-30T18:54:10.192Z",
        "updatedAt": "2020-01-31T08:53:34.064Z"
        
    },
    {
        "id": 2,
        "eventId": 1,
        "tktAuthor": "Tom",
        "tktDesc": "Ticket with free drinks",
        "tktPrice": "200",
        "tktRisk": "40.00",
        "userId": 2,
        "createdAt": "2020-01-30T18:54:10.192Z",
        "updatedAt": "2020-01-31T08:53:34.064Z"
        
    }
   ]
     
Retrieve Single ticket
----------------------
Retrieve a single ticket by ticket id.

.. raw:: html

   <div class='cli'>
   `http: GET :5000/events/1/tickets/1`
   </div>

Arguments
^^^^^^^^^
.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - eventId :sup:`REQUIRED`
     - integer
     - Represents unique event id 

   * - id :sup:`REQUIRED`
     - integer
     - Represents unique ticket id 

Returns
^^^^^^^
A single event
 
.. code-block:: json

    {
        "id": 1,
        "eventId": 1,
        "tktAuthor": "Som",
        "tktDesc": "Discounted Price",
        "tktPrice": "300",
        "tktRisk": "15.00",
        "userId": 1,
        "createdAt": "2020-01-30T18:54:10.192Z",
        "updatedAt": "2020-01-31T08:53:34.064Z"
        
    }

.. _createTicket:

Create Ticket
--------------
Create a new ticket for an event.

.. raw:: html

   <div class='cli'>
   <pre>
   http POST:5000/events/1/tickets
          tktDesc="Premier Pass"
          tktPrice="400"
          Authorisation:"Bearer &lt token &gt"        
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
   * - tktDesc :sup:`REQUIRED`
     - text
     - Detail description of the ticket
   * - tktPrice :sup:`REQUIRED`
     - DECIMAL, (rounded off to two places after decimal point)
     - Price of the ticket
  

Returns
^^^^^^^
.. code-block:: json

     {
        "id": 3 
        "eventId": 1,
        "tktAuthor": "User-3",
        "tktDesc": "Premier Pass",
        "tktPrice": "400",
        "tktRisk": "25.00",
        "userId": 3,
        "createdAt": "2020-01-31T18:54:10.192Z",
        "updatedAt": "2020-01-31T08:53:34.064Z"
        
    }

.. _updateTicket:

Update Ticket
--------------
Update a ticket by ticket owner.

.. raw:: html

   <div class='cli'>
   <pre>
   http PATCH:5000/events/1/tickets/3
              "tktDesc": "Premier Pass"
              "tktPrice":350"
              Authorisation:"Bearer &lt token &gt"        
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
   * - tktDesc :sup:`REQUIRED`
     - text
     - Detail description of the ticket
   * - tktPrice :sup:`REQUIRED`
     - DECIMAL, (rounded off to two places after decimal point)
     - Price of the ticket
  

Returns
^^^^^^^
.. code-block:: json

     {
        "id": 3,
        "eventId": 1,
        "tktAuthor": "User-3",
        "tktDesc": "Premier Pass",
        "tktPrice": "350",
        "tktRisk": "25.00",
        "userId": 3,
        "createdAt": "2020-01-31T18:54:10.192Z",
        "updatedAt": "2020-01-31T10:53:34.064Z"
        
    }

      