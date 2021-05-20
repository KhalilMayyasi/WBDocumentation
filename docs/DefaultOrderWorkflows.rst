
Default Order Workflows
======================================

Geidea WB manages orders through the creation of workflows. These allow orders to move through a funnel. These are determined by the following 3 criteria:

#. *Events* (when a certain event takes place):

   #. Ordering
   #. Change of order status
   #. Successful payment
   #. Failed payment

#. *Terms* (apply conditions for the following variables):

   #. Delivery method
   #. Payment method
   #. Order status
   #. Final order status
   #. Payment status
   #. Delivery Status

#. *Action* (what WB should do):

   #. Reserve a product and start delivery
   #. Reserve product
   #. Remove from reserve
   #. Change order status
   #. Send notification

      #. If this option is selected, another field for ‘Template’
      #. Templates can be managed from::

   ‘Store Management > Settings > E-Mail and SMS Notifications’
