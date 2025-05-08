Digital Downloads with WooCommerce Plugin
Overview
The Digital Downloads with WooCommerce plugin provides functionality for managing and tracking digital downloads. It integrates seamlessly with WooCommerce, allowing you to leverage its e-commerce capabilities while extending them with custom download tracking and a user-friendly frontend interface.

Features
WooCommerce Integration: Automatically tracks downloads upon order completion.

Custom Download Logs: Records downloads in a dedicated database table.

User Dashboard: Provides a frontend interface for users to view their downloads.

Responsive Design: Displays downloads in a clean, responsive table.

Simple Installation: Easily install and activate the plugin with a few steps.

Installation
Download the Plugin:

Save the provided PHP code as digital-downloads-woocommerce.php.

Upload the Plugin:

Place the file inside a folder named digital-downloads-woocommerce in the /wp-content/plugins/ directory.

Activate the Plugin:

Navigate to the WordPress admin dashboard.

Go to Plugins > Installed Plugins.

Find "Digital Downloads with WooCommerce" and click Activate.

Set Up Products:

Create or edit WooCommerce products and mark them as "Downloadable."

Create a Downloads Page:

Add the [downloads_dashboard] shortcode to a new or existing page to display the user’s downloads.

Usage
Logging Downloads
When an order is marked as "Completed" in WooCommerce, the plugin records the user’s purchased downloadable products into a custom database table.

Displaying Downloads
Users can view their downloads by navigating to the page containing the [downloads_dashboard] shortcode.

The table includes:

Product Name

Order ID

Download Date

Shortcode
[downloads_dashboard]
Displays a table of the logged-in user’s download history.

Example
html
Copy
Edit
[downloads_dashboard]
Output
A table displaying:

Product Name

Order ID

Date of Download

Database Structure
Table: wp_digital_downloads
The plugin creates a custom table to track downloads:

Column	Type	Description
id	BIGINT(20)	Auto-incrementing unique ID for each download.
user_id	BIGINT(20)	ID of the user who made the purchase.
product_id	BIGINT(20)	ID of the purchased product.
order_id	BIGINT(20)	WooCommerce order ID.
download_date	DATETIME	Timestamp of the download record.

Hooks and Filters
Actions
woocommerce_order_status_completed
Triggered when an order is marked as "Completed." The plugin uses this hook to log download data into the custom table.

php
Copy
Edit
add_action('woocommerce_order_status_completed', 'ddw_log_download_on_order_complete');
Styling
The plugin includes built-in styles for the downloads table. You can customize the appearance further using CSS.

Default Styles
css
Copy
Edit
.ddw-downloads-table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
    font-size: 16px;
}
.ddw-downloads-table th,
.ddw-downloads-table td {
    border: 1px solid #ddd;
    padding: 10px;
    text-align: left;
}
.ddw-downloads-table th {
    background-color: #f4f4f4;
    font-weight: bold;
}
.ddw-downloads-table tr:nth-child(even) {
    background-color: #f9f9f9;
}
Future Enhancements
Email Notifications: Notify users when a download becomes available.

Link Expiry: Add expiration dates for download links.

Admin Dashboard: Create an admin interface to view and manage download logs.

Advanced Filters: Allow users to filter downloads by date or product.
