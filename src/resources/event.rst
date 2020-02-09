
This object represents an event. You can retrieve all the ongoing events.

The TicketSwap server provides 2 events per page.

.. raw:: html

   <div class='cli'>
   http GET:5000/events?page=&ltpageno&gt
   </div>

The Event object
----------------

.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Attributes
     - Type
     - Description
   * - id
     - integer
     - Unique id for the event
   * - eName
     - string, max length = 255 
     - Name Of The Event
   * - eDesc
     - text
     - Detail description of the event
   * - eImg
     - url
     - Image for the event
   * - eStartDt
     - Date, (YYYY-MM-DD)
     - Start date of the event
   * - eEndDt
     - Date, (YYYY-MM-DD)
     - End date of the event

.. code-block:: json

    {
        "id": 1,
        "eName": "Fun Carnival",
        "eDesc": "The greatest carnival of the year",
        "eImg": "https://www.liberaldictionary.com/wp-content/uploads/2019/02/
                 carnival-2981.jpg",
        "eStartDt": "2020-01-01T00:00:00.000Z",
        "eEndDt": "2020-02-28T00:00:00.000Z"
   }

Retrieve Events
---------------
Retrieve a list all open events. This endpoint supports Offset-based pagination. When listing events you must pass the page number.

.. raw:: html

   <div class='cli'>
   http ':5000/events?page=3'
   </div>

Arguments
^^^^^^^^^

.. list-table:: 
   :widths: 15 25 60
   :header-rows: 1

   * - QueryParameter
     - Type
     - Description
   * - page
     - integer, default value =1
     - Indicates the page that needs to be returned.
       TicketSwap returns 2 events per page.

Returns
^^^^^^^
A list of ongoing events along with pagination details:
 
.. code-block:: json

     {
    "pageOfItems": [
        {
            "id": 1,
            "eName": "Fun Carnival",
            "eDesc": "The greatest carnival of the year",
            "eImg": "https://www.liberaldictionary.com/wp-content/uploads/2019/02/
                     carnival-2981.jpg",
            "eStartDt": "2020-01-01T00:00:00.000Z",
            "eEndDt": "2020-02-28T00:00:00.000Z",
            "createdAt": "2020-01-30T18:48:43.895Z",
            "updatedAt": "2020-01-30T18:48:43.895Z"
        },
        {
            "id": 2,
            "eName": "The Grand Opera",
            "eDesc": "Experience the magic, beginning of the year",
            "eImg": "https://media.tacdn.com/media/attractions-splice-
                     spp-674x446/07/69/50/2f.jpg",
            "eStartDt": "2020-01-15T00:00:00.000Z",
            "eEndDt": "2020-03-30T00:00:00.000Z",
            "createdAt": "2020-01-30T18:51:44.446Z",
            "updatedAt": "2020-01-30T18:51:44.446Z"
        }
    ],
    "pager": {
        "currentPage": 1,
        "endIndex": 1,
        "endPage": 3,
        "pageSize": 2,
        "pages": [
            1,
            2,
            3
        ],
        "startIndex": 0,
        "startPage": 1,
        "totalItems": 5,
        "totalPages": 3
    }
   }
  
Retrieve Single event
---------------------
Retrieve a single event by event id.

.. raw:: html

   <div class='cli'>
   http: GET:5000/events/4
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
     - Represents unique event id 

Returns
^^^^^^^
A single event
 
.. code-block:: json

    {
     "id": 4,
     "eName": "The Joker -movie",
     "eDesc": "Stunning performance and great reviews",
     "eImg": "https://www.liberaldictionary.com/wp-content/uploads/2019/02/
              carnival-2981.jpg",
     "eStartDt": "2020-02-15T00:00:00.000Z",
     "eEndDt": "2020-02-15T00:00:00.000Z",
     "createdAt": "2020-01-31T08:22:59.967Z",
     "updatedAt": "2020-01-31T08:22:59.967Z"
    }

.. _createEvent:

Create Event
------------
Create a new event.

.. raw:: html

   <div class='cli'>
   <pre>
   http POST:5000/events/
          eName="The great Opera"
          eDesc="The most awaited show of the season"
          eImg="http://image.url.com"
          eStartDt="20200201"
          eEndDt="20200228"
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
   * - eName :sup:`REQUIRED`
     - string, max length = 255
     - Name Of The Event
   * - eDesc :sup:`OPTIONAL`
     - text, 
     - Detail description of the event
   * - eImg :sup:`REQUIRED`
     - url
     - Image for the event
   * - eStartDt :sup:`REQUIRED`
     - Date, (YYYY-MM-DD)
     - Start date of the event
   * - eEndDt :sup:`REQUIRED`
     - Date, (YYYY-MM-DD)
     - End date of the event, which must be >= eStartDt

Returns
^^^^^^^
.. code-block:: json

    {
     
     "id": 6,
     "eDesc": "One of a kind show",
     "eName": "The Grand Rock Music Concert",
     "eImg": "https://www.liberaldictionary.com/wp-content/uploads/2019/02/
              carnival-2981.jpg",
     "eStartDt": "2020-02-14T23:00:00.000Z",
     "eEndDt": "2020-02-15T23:00:00.000Z",
     "createdAt": "2020-01-31T09:03:23.487Z",
     "updatedAt": "2020-01-31T09:03:23.487Z"

    }    