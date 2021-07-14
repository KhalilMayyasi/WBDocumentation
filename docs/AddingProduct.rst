
Adding a Product
================================

To add a product:

#. Access  the “Store Management” menu
#. Click on the “Products” menu
#. Click on “Add Product” next to the ‘Search & Filter Bar’
#. Add the following information:

   * Product name
   * Product image
   * Price 
   * Discount price

      * Activated if “Sale” checkbox is selected
      
   * Assign to Product Category
   * Main Category

      * Appears if product belongs to more than one category
      * Used as a form of navigation on websites to tell end users how they reached their current page
      * The first category the product was added to is the default main category
   * Product description
   * Select inventory item

      * Each new product will be  added to the Inventory Library (Store Management > geideaPOS > Inventory Library) which creates a barcode for the new product
      * The use case might be different if the product has more than one variation (Check :ref:`Creating Variations`)
   * Add product variation

      * If one is not added, the first version is treated as the first variation

To assign quantity to a product, check :ref:`Assign Product to Inventory Item and Managing Quantity`


Creating Variations
-------------------------------

Use variations to provide end users with different options for certain products (e.g. Size, Color, etc.).

To add variations for a product named ‘Long Tee’ and the variations are based on size:

#. Add a new product OR click on an existing product’s image (i.e. Long Tee)
#. Click on “Add Option” under “Product Variations”
#. Add the following information:

   * Variation Name:

      * In this example, the variation names would be ‘Small’ and ‘Medium’

   * The inventory item the variation links to:

      * The first variation has a default link to the current product (i.e. Long Tee)

         * Name the variation (e.g. Small)
      
      * The second variation links to a ‘New’ product in the inventory

         * Name the variation (e.g. Medium)
      
      * This creates a new inventory item under the same product as “Product Name (Variation Name)’ so for a shirt named ‘Long Tee’, the new variations would be “Long Tee (Small) and “Long Tee (Medium)”
   
   * Price of variation
   * Discount price of variation


Assign Product to Inventory Item and Managing Quantity
-----------------------------------------------------------------

Once a product/variation of a product has been created, a barcode is generated and the product/variation is linked to the inventory. This product can be accessed from:

   .. code-block:: text

      ‘Store Management > geideaPOS > Inventory Library’


   .. image:: ./productToInventory1.png
      :width: 700
      :alt: Alternative text

   .. image:: ./productToInventory3.png
      :width: 700
      :alt: Alternative text

   To add inventory (product quantity) for the first variation:

   #. Click on ‘New > Receipt’
   #. Add the following information:

      * Warehouse
      * Item
      * Quantity
      * Cost per unit

   To add inventory for the second variation is a bit different:

   #. Click on the second variation (In the above example, it would be “Long Sleeve Tee (small)”
   #. At the top right, click ‘New > Receipt’
   #. Add the following information:

      * Warehouse
      * Item
      * Quantity
      * Cost per unit

   .. image:: ./productToInventory4.png
      :width: 500
      :alt: Alternative text


Bulk Import & Rules (English and Arabic)
-------------------------------------------------

To add products via bulk import, add the Google Spreadsheet in the correct format in the following location:


   .. code-block:: text

      *Settings > Integrations & Data Sharing > Data Import > Google Spreadsheet*

A sample sheet can be found here as well.
Import items without variations, items with variations or both of them at the same time.

Bulk Import: Rules for Categories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. If this field is left empty, the item will be left as uncategorized.
#. If you type a new category name, then a new category will be created and the item will be assigned.
#. If an item has a category and a subcategory, please use the forward slash [Category/Subcategory] OR [e.g. Mens/Shoes]
#. If you want to  assign an item to more than one category, please type it with a comma: [Category 1, Category 2] OR [e.g. Mens/Shoes, Fall Collection]
#. Point 2 and 3 apply to the Product category:ar_SA in a right-to-left orientation. [ترحيب / أساور] → In this case, ترحيب is the main category and أساور is the subcategory.

Bulk Import: Rules for Variations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. **Items without variations:**


   * each string means one product will be imported
   * *variation name:en* and *variation name:ar_SA* should be empty


#. **Items with variations:**


   #. the string for the product (e.g T-Shirt)


      #. is not imported
      #. should contain *Product name:en*, *Product description; en*, *Product image link*, *Product category*, *Product description:en* and *Product name:ar_SA*
      #. should **NOT** contain:


         #. Variation name:en 
         #. Variation name:ar_SA
         #. Quantity 
         #. Price
         #. Discount price
         #. Cost per unit 
         #. Tax 
         #. Barcode


   #. the string for each variation of the product (e.g. Small, Medium, Large)


      #. is imported
      #. should **NOT** contain *Product name:en*, *Product description; en*, *Product image link*, *Product category*, *Product description:en* and *Product name:ar_SA*
      #. should contain


         #. Variation name:en 
         #. Variation name:ar_SA
         #. Quantity 
         #. Price
         #. Discount price
         #. Cost per unit 
         #. Tax 
         #. Barcode

Use the following as examples:

   * (`English Bulk Import Sample Sheet <https://docs.google.com/spreadsheets/d/1eTcs-3bGBH-0psDC5eZsnlt_ln6ykYVXPPc5740UAzc/edit?usp=sharing>`_)
   * (`Arabic Bulk Import Sample Sheet <https://docs.google.com/spreadsheets/d/1Cgk48UjQOMp_P0RcDl8TLIhSj9Hqh2XAScrzrdbSoV4/edit?usp=sharing>`_)

Bulk Import: Rules for Empty Fields and Barcodes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. If Product image link is empty, the item will be added without an image
#. If Cost per unit, Price, Discount price and Tax are empty – these fields will not be added
#. The Quantity field


   #. If a number is added, then a receipt transaction to the default warehouse will be created.
   #. If not, the inventory item will be created with an out of stock state.


#. A barcode is strongly requested! If there are  no existing barcodes for items to bulk import, then we suggest autofill in a Google Sheet (e.g. 000000000001, 000000000002).
#. If there is already an existing barcode in the online database and the user tries to import an item with the same barcode, then the existing item will be replaced with the data from the Google Sheet. **The best way is to bulk import to a new or empty store**, then adding products one at a time.