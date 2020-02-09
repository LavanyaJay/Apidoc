
Introduction
============

The TicketSwap API is a REST API. The API has resource-oriented URLs, accepts request bodies with :attr:`~"Content-Type": "application/json"`, and returns JSON-encoded responses, and uses standard HTTP response codes, authentication, and verbs.


This is TicketSwap API v.1.0.


.. raw:: html

   <div class='cli'>
   Base URL
   <pre>http://localhost:5000</pre>
   </div>


Data:    /usr/local/var/lib/elasticsearch/elasticsearch_hic/
Logs:    /usr/local/var/log/elasticsearch/elasticsearch_hic.log
Plugins: /usr/local/var/elasticsearch/plugins/
Config:  /usr/local/etc/elasticsearch/

To have launchd start elastic/tap/elasticsearch-full now and restart at login:
  brew services start elastic/tap/elasticsearch-full
Or, if you don't want/need a background service you can just run:
  elasticsearch

