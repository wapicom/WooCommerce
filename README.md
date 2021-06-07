# WooCommerce Plugin
WooCommerce plugin - a plugin that allows to transfer orders from your WooCommerce store to the WAPI system.
Download plugin: [wapiou.zip](https://github.com/wapicom/WooCommerce/files/6610049/wapiou.zip)

#### Steps for integration WooCommerce store and WAPI system

1. Install the plugin. The plugin can be installed in the WooCommerce admin panel in the **Plugins >> Add New** section (the screenshot also shows how the section will look when the WAPI plugin is already installed):
picture
2. After installing the plugin, the WAPI tab will appear in the **WooCommerce >> Settings**:
picture
picture
3. In the WAPI tab, you need to enter the data for integration - API X-CLIENT ID and API HMAC key. For test orders, the WAPI support team will give you test API X-CLIENT ID and API HMAC key. Also for test orders check the **Test Environment** box. To check that the test orders have been successfully transferred to the WAPI system, the WAPI support team will give a login and password for the WAPI test system, where it will be possible to check whether the orders have arrived.

When real orders will start, the **Test Environment** checkbox must be unchecked, and production values must be inserted into the API X-CLIENT ID and API HMAC key fields (also given by the WAPI support team after successfull test orders).

You can specify any **Your Company/Project name** field (usually the name of the store).

picture

4. The **WooCommerce >> Settings >> Shipping** section specifies the shipping zones and the shipping method to each of the zones. To add a new zone, you need to click on **Add shipping zone** button:
picture

To edit an existing zone, click on the **Edit button** near the zone:
picture

The **Shipping Zone editing** window looks like this:
picture

Here you need to specify the countries, orders for which will be fulfilled through WAPI, and select the **WAPI Shipping Method** (move the Enabled slider).

The Shipping Method can be edited. If you click on the name of the Shipping method, the following fields will open:
picture

So, for the countries, orders for which will be fulfilled through WAPI, the WAPI Shipping Method is selected. Now the system will assign orders to these countries via WAPI.

5. This is how the purchase will look from the buyer's side when the buyer chooses the country for which orders are fulfilled through WAPI:
picture

6. The order will be passed to the WAPI side after the order status changes to "processing" or the payment is made through one of the payment plugins.

The order looks like this. In the screenshot, the Status field is marked, which can be changed manually. Other fields can be edited too:

picture

7. On the right side of the order page, the history of actions with the order is displayed, as well as errors that occur during order processing. Errors related to passing an order to WAPI will be displayed here. If an error occurs, you can send us a screenshot of this panel:
picture

Also in the right section it is possible to resend the order, for example, after making edits to the order (editing the zip code, for example):
picture

8. When the order is successfully sent, in the right section there will be information about the track number and the history of changing the order statuses:
picture

9. The plugin updates information about the status of packages that are currently being delivered on a scheduled basis.

10. When the order is delivered, the plugin will change the order status to "Completed".


Important: virtual products for test requests must be "Demo Product-1" and "Demo Product-2". Also it is important to indicate in the request the country of delivery "ES" or "IT".

The SKU of products in WooCommerce must match the SKU of products in our system. At the test stage SKU: Demo Product-1 and Demo Product-2, at the production stage SKU in WooCommerce must match those that you sent us in the master data.

It is also important to test the cases with variable products and bundles, because this can be done by different plugins, and our plugin may not recognize them.

When the integration is set up, and the products have arrived at the warehouse, the client is given a login and password to access the WAPI system so that he can view information on the stock of products in warehouses.
