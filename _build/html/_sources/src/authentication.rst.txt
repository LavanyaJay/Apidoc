.. _authentication:

********************************
Authentication and Authorisation
********************************

.. contents:: :local:

Bearer Authentication
---------------------

The TicketSwap API requires userid and password for Authentication, followed by JWT Bearer token to authorise requests.
  
Developers must send this token in the authorisation header when making requests to protected resources.

.. raw:: html

   <div class='cli'>
   <pre> Authorisation: Bearer &lt token &gt </pre>
   </div>

 
How does JWT get generated
--------------------------

Certain endpoints for specific resources require users to sign. All verified login users will be issued a JWT, which in turn must be provided to access these endpoints.

.. raw:: html

   <div class='cli'>
   <pre>
   request
    .post(`${baseUrl}/events`)
    .set('Authorisation', `Bearer &lt token &gt`)
   </pre>
   </div>

The following resource endpoints require JWT Authentication:

* :ref:`createEvent`
* :ref:`createTicket`
* :ref:`Update Ticket <updateTicket>`

