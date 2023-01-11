# awardpool-hook
Award Pool Verification JavaSCript

The script serves to make a GET request to the Award Pool API and retrieve some data, using an unique identifier passed in the URL query string (APuid) and an optional version parameter.

The script defines two main functions: apHook() and apTimer(). apHook() is the function that handles the GET request to the API, by first checking whether the APuid value is not empty and not null. If so, it constructs the full URL for the GET request, by including the APuid and version (or 'live', if version is not passed) in the URL, and then uses the Fetch API to make the request. The function logs the posted APuid and version to the console. The function also uses the .then() method to handle the response. The function logs the data, the completed status and status of the request.

apTimer() sets a timer in seconds before executing the apHook() function, using setTimeout(). APScroll() function is used to execute the apHook() when a user scrolls to a part of the page with a div id of 'apHook'. It gets the position of the div and checks whether the element is in the viewport and runs the apHook function if it is and logs a message to the console
