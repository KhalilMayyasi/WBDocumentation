
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
      #. Templates can be managed from:
      
      .. code-block:: text
      
         ‘Store Management > Settings > E-Mail and SMS Notifications’

.. list-table::
   :widths: 5 10 5
   :header-rows: 1

   * - Event (when)
     - Terms (conditions)
     - Action (what is done)
   * - Changing order status
     - For orders with any delivery, 
       
       payment and order status
     - Send notification
   * - Ordering
     - For orders with any delivery, 
       
       payment, and order status
     - Reserve product
   * - Changing order status
     - Order Status is ‘Cancelled’
     - Remove from reserve
   * - Changing order status
     - Order status from ‘Active’ to ‘Failed’
     - Remove from reserve
   * - When payment fails
     - Any
     - Remove from reserve