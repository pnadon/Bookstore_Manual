# Getting to know the Bookstore App



If some of the content in this manual is unclear, please contact [Philippe Nadon](https://nadon.io) at **phil@nadon.io**.

# Overview

`The Bookstore App` is designed to facilitate the ordering process for customers who wish to have custom text embroidered on their clothing.
To do so, the app allows one to navigate between pages, each of which offers a singular `category` of customization. Upon completing an order to their satisfaction a customer may review their order, and then the user of the app may submit the application. Upon submission, the user also has the ability to export the order summary to PDF, or begin a new order. The app also allows one to load previous order based on their order number, which easily allows the ability to correct or resume previous orders.

## Features

All of the app's features are listed below:
- Cross-platform usage as a Desktop App (experience is identical on both Mac and PC).
- The `Welcome` page asks for the user's name, email and phone number for storage of contact information.
- `New Order`, `Next`, `Prev`, and `Submit Order` all automatically submit the current order information to Google Sheets.
- `Load Order` allows one to load any order listed in `Google Sheets`.
- The `App Settings` section of the `Google Sheet` allows one to adjust prices and SKUs per customization area.
- The `Completed Orders` section of the `Google Sheet` allows one to view all orders than have been submitted(ie. not incomplete), and has a separate column displaying the order number of the order, which is directly related to the order's row in the `Orders` Section.
- The `Orders` section of the `Google Sheet` displays all orders, completed or otherwise. It is a protected range by default, which displays a warning if one attempts to modify it.
- The app uses a `JSON Store` to automatically save and load data submitted within the input fields and dropdown menus as a form of "auto-save" while using the app.
- The app forces the user to fill out information per page (contact info on the `Welcome` page, "yes/no" to whether they would like customizations per customization page).
- The app displays a price counter at the bottom, which updates in realtime as the user enters information
- Each customization page displays a sample image which shows an example of customized text in that area (such as a picture of the left sleeve of a hoodie with custom text, for the `Left Arm` page).
- The app allows the user to load a folder containing images with specific filenames, which will populate all the images in the app with the corresponding image in the folder (allows one to update the images in the app).
- Every customization option in the app shows the associated cost within the dropdown, which is automatically pulled from the `Google Sheet`.
- The order number being edited is displayed in the header at the top.
- Every customization option offers a text box as an input method, for flexibility.
- The `Summary` page shows all inputted information, as well as the SKU and price (if applicable). The inputted information is also grouped relative to their category (contact information, customization, etc.).
- The app allows the user to export the order as a PDF, for ease of sharing information.
- After submitting an order, the app allows one to easily reload the app and begin a fresh order.
- Due to almost all information being stored in a `Google Sheet`, this app can easily be used on multiple devices simultaneously and offers seamless syncing of information. *WARNING: DO NOT ATTEMPT TO EDIT THE SAME ORDER AT THE SAME TIME*
- The app does not allow one to edit the `Hood` page of a crewneck.
- The app is styled using the `University of Alberta` theme :)

## Typical Usage

A customer walks into the bookstore, and requests that he get a green hoodie with some customized text for his graduation. The user of the app (typically a staff member or bookstore manager) prompts the customer to describe what he wants as the user fills out the information on his `Windows` laptop. To start with, the user shows the customer the app, which is currently at the `Welcome` page. The `Welcome` page shows the user two options: Make a new order, or load a previous order (if the customer wishes to edit a previously incomplete or incorrect order). If the user wishes to make a new order, the user requests that the customer fill out his information in the input fields. Having done so, the customer (or user) then presses the `New Order` button and proceeds to the next page. From here, the customer goes through every option until he arrives at the `Summary` page, where he reviews his choices. Having changed his mind on what he wants on the front of the shirt, the user uses the navigation buttons to navigate back to that option, and then adjust his input. Once he has done so and returned to the `Summary` page, he make finalize his order by pressing the `Submit Order` button. Once he has done so, the user has set up an integration with `MailChimp`, where upon submitting an order an email is automatically sent out thanking the user and giving them a summary of what they ordered and how the cost was broken down (using the integration with the `Google Sheet`, where the input info and prices are all stored).

# Customization

## Images

The images used in the app are loaded automatically at startup. The does this by searching for the images in the folder you have specified, if any. The files must be named in a specific manner for the app to detect them correctly. If the folder is moved or deleted the app will not be able to find the images, and a default `error image` will be placed instead. To ensure that the app reliably loads the images every launch, make sure not to move the folder where the images are stored.

To change the folder where the app looks for the images, click the button at the top-left which says `Load Images` and select the desired folder where the images are stored.

## Prices

To modify the prices associated with each customizable section, open the `Google Sheet` which is linked to the app. At the bottom, you can see 3 sections labelled `Completed Orders`, `Orders`, and `App Settings`. Click `App Settings` and you should see two columns; one with a `Settings` header and another with a `Value` header. The cells in the `Value` column are the values associated with the thing in the `Settings` column. For example, if you wish to modify the price for the front of an article of clothing, you would modify the cell immediately to the right of the cell under `Settings` that contains `Front Price`. This change should take effect once the app reloads.

*WARNING: PRICES CAN ONLY BE NUMBERS, DO NOT ADD SYMBOLS OR LETTERS*

## SKUs

See the `Prices` section, as SKUs are modified in the same way as the prices. SKUs can contain any letter or number, and most symbols.

# Managing Orders

## Creating a New Order

A new order can be created by filling out the information on the `Welcome` page, and then pressing `New Order`. The app will then send request that the `Google Sheet` appends a new row to the `Orders` section, and then fill in the contact information provided, as well as the date the order was first created.

## Loading a Previous Order

A previous order can be loaded by going to the `Welcome` page, and entering the number corresponding to the row/order number that the user wishes to load into the input field that says `Enter order #`. Afterwards, press the `Load Order` button and within a few seconds you should see the app transition to the next page, with all of the information in that row populated within the app's inputs.

## Finalizing / Submitting an Order

An order can be finalized by pressing the `Submit Order` button in the `Summary` page. The app will send the order's information to `Google Sheets`, as well as enter the date the order was completed as well as a `yes` in the `Completed` column to signify that the order has been completed.

## Deleting an Order

The app does not offer any functionality for deleting an order. The reason is that there is little to no reason to delete an order (as `Google Sheets` does not really offer a realistic limit on entries), however the functionality is still there within `Google Sheets`. To delete a row or values in a cell, simply select the rows, right-click and select delete. 

*WARNING: IF YOU WANT TO REUSE ORDER NUMBERS, MAKE SURE TO DELETE THE ROWS THEMSELVES, OTHERWISE IF YOU SIMPLY WISH TO REMOVE INFORMATION BUT NOT REUSE THE ROWS, THEN ONLY DELETE THE CONTENT WITHIN THE ROWS*

*WARNING: DO NOT DELETE ORDER #2, IT HOLDS THE FUNCTION FOR POPULATING THE ROW / ORDER NUMBERS, WHICH ALLOWS YOU TO TRACE ORDERS IN THE COMPLETED ORDER SECTION BACK TO THE ORDERS SECTION*

# Viewing and Sharing Order Information

## The Summary Page

The `Summary` page allows you to review all the customizations entered during the order, as well as the SKU and price associated with them, and the text entered. *It is important that you review the Summary page to ensure that the information was entered correctly*. The information is sorted in the order you would normally enter the information, and grouped in categories for easier viewing. If a customization was not entered, instead of a SKU, price and text you will see `N/A`.

## Export to PDF

See `The Summary Page` for information provided in the PDF, it is essentially identical aside from the format. The `Export to PDF` option is found in the `Thank You` page, which is loaded after a user has pressed `Submit Order` in the `Summary` page. The `Export to PDF` option opens a dialog where you can save the summary in PDF form on your computer. The PDF option is useful for printing or otherwise sending to others to see.

## Viewing Completed Orders

Completed orders can be view on the `Google Sheet` under the section `Completed Orders`, it is not recommended to load the order in the app to view it, as it offers an easy way to modify the data (which is not ideal for a completed order). Only load an order if you wish to modify it.

## Making Custom Google Sheet "Sheets", Functions

`Google Sheets`, much like `Microsoft Excel`, allows you to input functions which can modify or filter the data in a spreadsheet in an easy manner. For example, one could create a new section, and then filter in orders which have been completed in the past 7 days. Please see [this link](https://support.google.com/docs/table/25273?hl=en) on a full list of functions available for `Google Sheets`.

*WARNING: DO NOT MODIFY THE DATA IN THE ORDERS SECTION. INSTEAD, CREATE A NEW SECTION AND PERFORM YOUR OPERATIONS THERE, SO THAT THE ORIGINAL DATA IS UNTOUCHED!*

## Integrating 3rd party services with Google Sheets

`Google Sheets` can easily be connected to 3rd party services so that you may automate more of your business. Both [Zapier](https://zapier.com/) and [Automate](https://automate.io/) are a good place to start.

# Bugs, Concerns

## Known Bugs

### Bug 1
**Problem:** Clicking buttons too quickly after entering information or sending/receiving information from `Google Sheets` (such as loading an order) will cause the app to either buffer your input, do nothing (in which case you may press the button again after waiting a few seconds), or result in an error

**Solution:** Be patient with the app. Depending on your internet connection some requests to `Google Sheets` may take up to a few seconds, try not to spam buttons or otherwise "put strain" on the app. If you experience strange behaviour, verify the correctness of the input on `Google Sheets`, and try again / change the info on `Google Sheets`.

### Bug 2
**Problem:** Entering `n/a` exactly into the input field will register as the user not wanting that option, but might still add up the price for that section. This is because the app registers "n/a" as a section that the user did not enter.
**Solution:** If a rather unique customer wishes to have `n/a` on a portion of their clothing, please make them put it in quotations or something.

### Bug 3
**Problem:** The app is fixed to a specific `Google Sheet` and account, and cannot be changed.
**Solution:** While the ability to change to a different `Google Sheet` or account makes sense, we were unable to make time to implement that change. If you wish to change some of the credentials associated with the app, please contact [Philippe Nadon](https://nadon.io) at **phil@nadon.io**.

### Bug 4
**Problem:** The app is supposed to be cross-platform, but i can't connect to `Google Sheets` on my `Mac`!
**Solution:** While the app is fully functional on `MacOS`, the way the app looks for external files is different, and so we would need to implement a different way of reading in the token and credentials on a `Mac`. This is similar to the previous bug, where due to time constraints this was not implemented.

## Concerns

You can contact [Philippe Nadon](https://nadon.io) at **phil@nadon.io** for any questions or concerns.