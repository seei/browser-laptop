# Global





* * *

### setState(appState) 

Dispatches an event to the main process to replace the app state
This is called from the main process on startup before anything else

**Parameters**

**appState**: `object`, Initial app state object (not yet converted to ImmutableJS)



### newWindow(frameOpts, browserOpts, restoredState, cb) 

Dispatches an event to the main process to create a new window.

**Parameters**

**frameOpts**: `Object`, Options for the first frame in the window.

**browserOpts**: `Object`, Options for the browser.

**restoredState**: `Object`, State for the window to restore.

**cb**: `function`, Callback to call after the window is loaded, will only work if called from the main process.



### addSite(siteDetail, tag, originalSiteDetail, destinationIsParent) 

Adds a site to the site list

**Parameters**

**siteDetail**: `Object`, Properties of the site in question, can also be an array of siteDetail

**tag**: `string`, A tag to associate with the site. e.g. bookmarks.

**originalSiteDetail**: `string`, If specified, the original site detail to edit / overwrite.

**destinationIsParent**: `boolean`, Whether or not the destinationDetail should be considered the new parent.
  The details of the old entries will be modified if this is set, otherwise only the tag will be added.



### clearSitesWithoutTags() 

Clears all sites without tags



### removeSite(siteDetail, tag) 

Removes a site from the site list

**Parameters**

**siteDetail**: `Object`, Properties of the site in question

**tag**: `string`, A tag to associate with the site. e.g. bookmarks.



### moveSite(sourceDetail, destinationDetail, prepend, destinationIsParent) 

Dispatches a message to move a site locations.

**Parameters**

**sourceDetail**: `string`, the location, partitionNumber, etc of the source moved site

**destinationDetail**: `string`, the location, partitionNumber, etc of the destination moved site

**prepend**: `boolean`, Whether or not to prepend to the destinationLocation
  If false, the destinationDetail is considered a sibling.

**destinationIsParent**: `boolean`, Whether or not the destinationDetail should be considered the new parent.



### mergeDownloadDetail(downloadId, downloadDetail) 

Dispatches a message to add/edit download details
If set, also indicates that add/edit is shown

**Parameters**

**downloadId**: `string`, A unique ID for the download

**downloadDetail**: `Object`, Properties for the download



### clearCompletedDownloads() 

Dispatches a message to clear all completed downloads



### setDefaultWindowSize(size) 

Sets the default window size

**Parameters**

**size**: `Array`, [width, height]



### setResourceETag(resourceName, etag) 

Sets the etag value for a downloaded data file.
This is used for keeping track of when to re-download adblock and tracking
protection data.

**Parameters**

**resourceName**: `string`, 'adblock' or 'trackingProtection'

**etag**: `string`, The etag of the reosurce from the http response



### setResourceLastCheck(resourceName, lastCheck) 

Sets the lastCheck date.getTime() value for the data file

**Parameters**

**resourceName**: `string`, 'adblock', 'trackingProtection', or 'httpsEverywhere'

**lastCheck**: `number`, The last check date of the reosurce from the http response



### setResourceEnabled(resourceName, enabled) 

Sets whether the resource is enabled or not.

**Parameters**

**resourceName**: `string`, 'adblock', 'trackingProtection', or 'httpsEverywhere'

**enabled**: `boolean`, true if the resource is enabled.



### setUpdateLastCheck() 

Sets the update.lastCheckTimestamp to the current
epoch timestamp (milliseconds)



### setUpdateStatus(status, verbose, metadata) 

Sets the update status

**Parameters**

**status**: `string`, update status from js/constants/updateStatus.js.

**verbose**: `boolean`, Whether to show UI for all the update steps.

**metadata**: `object`, Metadata from the pdate server, with info like release notes.



### savePassword(passwordDetail) 

Saves login credentials

**Parameters**

**passwordDetail**: `Object`, login details



### deletePassword(passwordDetail) 

Deletes login credentials

**Parameters**

**passwordDetail**: `Object`, login details



### clearPasswords() 

Deletes all saved login credentials



### changeSetting(key, value) 

Changes an application level setting

**Parameters**

**key**: `string`, The key name for the setting

**value**: `string`, The value of the setting



### changeSiteSetting(hostPattern, key, value, temp) 

Change a hostPattern's config

**Parameters**

**hostPattern**: `string`, The host pattern to update the config for

**key**: `string`, The config key to update

**value**: `string | number`, The value to update to

**temp**: `boolean`, Whether to change temporary or persistent
  settings. defaults to false (persistent).



### showMessageBox(detail) 

Shows a message box in the notification bar

**Parameters**

**detail**: `Object`, Shows a message box in the notification bar



### hideMessageBox(message) 

Hides a message box in the notification bar

**Parameters**

**message**: `string`, Hides a message box in the notification bar



### addWord(word, learn) 

Adds a word to the dictionary

**Parameters**

**word**: `string`, The word to add

**learn**: `boolean`, true if the word should be learned, false if ignored



### setDictionary(locale) 

Adds a word to the dictionary

**Parameters**

**locale**: `string`, The locale to set for the dictionary




* * *










