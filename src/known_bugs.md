# Known Bugs

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