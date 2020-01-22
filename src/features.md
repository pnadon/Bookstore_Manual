# Features

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
