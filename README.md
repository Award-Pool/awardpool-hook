# awardpool-hook
Award Pool Verification JavaScript

When you create an action with a webhook, we will automatically append UID (?APuid=value) to any link provided.
This UID valueneeds to be temporarily stored on the users arrival.
The format of the URL on the purchase completion page must be formatted as follows using the ?APuid=value, as well as adding the javascript on the page.
There’s a number of different ways that this javascript can execute - the default will be on page load.

The code is a JavaScript script that interacts with a webhook belonging to an Award Pool service. The script is responsible for completing an action and grants points to a user when it is executed.

It has two main functions, apHook() and apTimer(), and one additional function APScroll()

The apHook() function is the main function that handles the GET request to the Award Pool webhook API. It first checks that the APuid value, which is passed in the URL query string, is not empty or null. If it is, the function constructs the full URL for the GET request by including the APuid and version(or 'live' if version is not passed) in the URL. Then it uses the Fetch API to make the GET request to the award pool API and returns the response as JSON.

The returned JSON is then logged to the console including the data, completed status and the status of the request. The function also logs a message to the console to indicate if the request was posted or not.

The apTimer() function sets a timer before executing the apHook() function, using setTimeout(). The APScroll() function is used to execute the apHook() when a user scrolls to a part of the page with a div id of 'apHook'. It gets the position of the div, checks whether the element is in the viewport, and runs the apHook function if it is and logs a message to the console.

The comments also contain instructions on how to enable or disable certain functions by removing slashes on specific lines.
