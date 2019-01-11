#   App APIs:

| **API** | Description | Request Parameter | Response Output |
| :---: | :---: | :---: | :--- |
| **getUsersDetailsAsync** | Gets users' details (name, pic, phone number, etc.) against their ids | userIds array of user ids | *JSON of user info* |
| **showContactPickerAsync** | Shows a native contact picker, and returns an array of all the selected users' detail | <ul><li>*title of Contact Picker*</li><li>*selectedMutableUser* - array of selected userIds</li><li>*selectedImmutableUser* - array of fixed selected userIds</li><li>*isSingleSelection* - single selection in Contact Picker</li></ul> | Array of all the selected users' details (*Array of JSON*) |
| **showImagePickerAsync** | Shows a native image picker, and returns the selected image path | | *Selected image location* |
| **showAttachmentPickerAsync** | Displays an attachment picker in the native layer | <ul><li>*supportedTypes* - array of supported attachment types for the picker</li><li>additional props to configure the picker</li></ul> | |
| **downloadAttachmentAsync** | Download the attachment specified | <ul><li>*attachment with a valid server path to download*</li><li>callback on download completion</li></ul> | |
| **cancelAttachmentDownloadAsync** | Cancel a download operation queued for an attachment | attachment | |
| **showPlacePickerAsync** | Shows a native place picker, and returns the selected place (lt, lg, n) | Selected location | Latitude/longitude |
| **showLocationOnMap** | Opens up native maps with given location | [KASLocation](KASLocation.md) type | |
| **showDurationPickerAsync** | Shows a native duration picker with day/hour/minute | Default duration to be shown on picker | |
| **isTalkBackEnabledAsync** | Gets whether talkback is enabled or not | | Boolean |
| **generateUUIDAsync** | Gets the new UUID | | Newly generated uuid |
| **getCurrentDeviceLocationAsync** | Gets the current device location | | |
| **getAppLocaleAsync** | Gets the current app locale -language in which the app is rendered, useful for localizing Action's strings | | Locale |
| **getConversationParticipantsCountAsync** | Gets all the participant-ids of the current conversation | | Count of participants |
| **getConversationNameAsync** | Gets the current conversation name | | Name of the conversation |
| **dismissCurrentScreen** | Dismiss the current screen (Creation, Response, or Summary) | | |
| **showProgressBar** | Shows a native full sreen progress bar with the given text | Text to display | |
| **hideProgressBar** | Hides the current progress bar, if any | | |
| **getCurrentUserIdAsync** | Gets the current user id who has opened the Action | | User ID |
| **showImageImmersiveView** | Shows Image in Immersive view | Array of images url | |
| **openAttachmentImmersiveView** | Open attachment in Immersive view | Attachment object | |
| **hasStorageAccessForAttachmentType** | checks whether app has read/write access to the storage | Attachment type | |
| **generateBase64ThumbnailAsync** | Generates Base64 thumbnail for an image | localPath for the imageAttachment whose thumbnail needs to be generated | |
| **getFontSizeMultiplierAsync** | Gets the font size multiplier for large text -	Current only required by iOS | | |
| **getLocalizedStringsAsync** | Gets the localized strings' dictionary based on current app locale | Strings must be provided inside the package with names like: strings_en.json, strings_hi.json, etc.	 | Strings JSON |
| **logToReport** | Logs an error for "Send report" | Attachment type | |
| **isCurrentUserO365SubscribedAsync** | Checks if the current user an O365 subscriber | | Boolean |
| **registerHardwareBackPressCallback** | Registers a callback to be executed on hardware back button press (for Android) | | |
| **initLocalizationStringsAsync** | Initializes the localization strings' map | Dictionary  - the strings' map | Success(Boolean) denotes the success/failure of the initialization |
| **getString** |	Returns a string from the localized strings' file |stringId	||
| **getConversationDetailsAsync** |	Gets all context for current conversation|| KASConversationDetails|

##  Get user info

```typescript
/**
  * Gets users' details (name, pic, phone number, etc.) against their ids
  * @param {string[]} userIds array of user ids
  * @param {Callback} callback with below parameters:
  * * * * @param {Dictionary<UserId: string, UserInfo: KASUser>} userIdToInfoMap (users' details against their ids) can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getUsersDetailsAsync(userIds: string[], callback: function(userIdToInfoMap: {}, error: string))
```

##  Show contact picker

```typescript
/**
  * Shows a native contact picker, and returns an array of all the selected users' details
  * @param {Callback} callback with below parameters:
  * * * * @param {KASUser[]} selectedUsers (array of user details) can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showContactPickerAsync(callback: function(users: KASUser[], error: string))
```

##  Show image picker

```typescript
/**
  * Shows a native image picker, and returns the selected image path
  * @param {Callback} callback with below parameters:
  * * * * @param {string} selectedImagePath can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showImagePickerAsync(callback: function(selectedImagePath: string, error: string))
```

##  Get current device location

```typescript
/**
  * Gets the current device location
  * @param {Callback} callback with below parameters:
  * * * * @param {string} location can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getCurrentDeviceLocationAsync(callback: function(location: string, error: string))
```

##  Place picker

```typescript
/**
  * Shows a native place picker, and returns the selected place (lt, lg, n)
  * @param {Callback} callback with below parameters:
  * * * * @param {KASLocation} selectedLocation can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showPlacePickerAsync(callback: (selectedLocation: KASLocation, error: string))
```

##  Show location on maps

```typescript
/**
  * Opens up native maps with a marker at selected location(KASLocation type)
  * @param {KASLocation} selectedLocation
  */
  function showLocationOnMap(selectedLocation: KASLocation)
```

##  Show error message (alert or toast)

```typescript
/**
  * Shows a native alert (for iOS) or a toast (for Android) with the message
  * @param {string} message
  */
  function showNativeErrorMessage(message: string)
```

##  Get current language used by the app

```typescript
/**
  * Gets the current app locale, the language in which the app is rendered, useful for localizing MiniApp's strings
  * @param {Callback} callback with below parameters:
  * * * * @param {string} locale can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getAppLocaleAsync(callback: function(locale: string, error: string))
```

##  Get the name of the current conversation

```typescript
/**
  * Gets the current conversation name
  * @param {Callback} callback with below parameters:
  * * * * @param {string} name can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getConversationNameAsync(callback: function(name: string, error: string))
```

##  Dismiss the currently opened Action's screen

```typescript
/**
  * Dismiss the current screen (Creation, Response, or Summary)
  */
  function dismissCurrentScreen()
```

##  Show native progress bar

```typescript
/**
  * Shows a native full sreen progress bar with the given text
  * @param {string} text
  */
  function showProgressBar(text: string)
```

##  Hide native progress bar

```typescript
/**
  * Hides the current progress bar, if any
  */
  function hideProgressBar()
```

##  Get current user id

```typescript
/**
  * Gets the current user id who has opened the MiniApp
  * @param {Callback} callback with below parameters:
  * * * * @param {string} userId can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getCurrentUserIdAsync(callback: function(userId: string, error: string))
```

##  Register for hardware back button press (Android)

```typescript
/**
  * Registers a callback to be executed on hardware back button press (for Android)
  * @param {Callback} callback to be executed
  */
  function registerHardwareBackPressCallback(callback: function())
```

##  Localization for Action

```typescript
/**
  * Gets the localized strings' dictionary based on current app locale.
  * Strings must be provided inside the package with names like: strings_en.json, strings_hi.json, etc.
  * @param {Callback} callback with below parameters:
  * * * * @param {JSON} strings can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getLocalizedStringsAsync(callback: (strings: JSON, error: string))
```

##  printf() for Action

```typescript
/**
  * Returns a string.
  * @param {string} string denotes the formatted string. Specifier should be mentioned like {0},{1},{2}.....
  * @param {string[]} args array of arguments.
  */
  function printf(main: string, ...args: any[]): string
```

##  show profile info of a user. 
##	Warning: once you start a new conversation either from dialog box or full screen profile view
##	by tapping on chat icon, all changes done in the current conversation are lost

```typescript
/**
  * shows a dialog box with user's profile info (isMiniProfile == true) 
  *	or a full screen view of the user's profile (isMiniProfile == false)
  * @param {string} user id of the user whose profile is to be shown
  * @param {boolean} whether to show a dialog box with user's profile info or a full screen profile.
  * @param {Callback} callback with below parameters:
  * * * * @param {JSON} whether successful or not, can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showUserProfileAsync(userId: string, isMiniProfile: boolean, callback: (success: boolean, error: string) => void)
```
##  starts one on one conversation with the user
##	would not work inside public groups

```typescript
/**
  * starts one on one conversation directly with the user
  * @param {string} user id of the user
  * @param {Callback} callback with below parameters:
  * * * * @param {boolean} whether successful or not, can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function startChatAsync(userId: string, callback: (success: boolean, error: string) => void)
```
##  Opens camera to scan bar codes

```typescript
/**
  * Opens camera to scan Bar codes
  * @param {Callback} callback with below parameters:
  * * * * @param {string} string returned after scanning the Bar code
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showBarcodeScannerAsync(callback: (barCodeInfo: string, error: string) => void): void;
```

##  Opens camera to scan QR codes

```typescript
/**
  * Opens camera to scan QR codes
  * @param {Callback} callback with below parameters:
  * * * * @param {string} string returned after scanning the QR code
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showQRcodeScannerAsync(callback: (qrCodeInfo: string, error: string) => void): void;
```

##  Download the base 64 map image for a given location

```typescript
/**
  * Download the map image for a given location using Google's "staticmap" API and converts it to base64 string.
  * @param {KASLocationStaticMapImageParams} object with below parameters:
  * * * * @param {number} latitude of the location. This is a mandatory field and if not provided API will get an error callback.
  * * * * @param {number} longitude of the location. This is a mandatory field and if not provided API will get an error callback.
  * * * * @param {number} width(sizeX) of the image in pixels. This field is optional and default width used is 360.
  * * * * @param {number} height(sizeY) of the image in pixels. This field is optional and default width used is 170.
  * * * * @param {string} markerColor of the location marker in the map (as in Google's "staticmap" API). For eg. red, blue etc. This field is optional and by default red color is used.
  * * * * @param {number} zoom value for the map (as in Google's "staticmap" API). This field is optional and default is up to Google's "staticmap" API.
  * * * * @param {string} language shown in the map (as in Google's "staticmap" API). For eg. en, hi etc. This field is optional and default is up to Google's "staticmap" API (usually en).
  * * * * @param {string} mapType as per Google's "staticmap" API. Possible values can be {roadmap, satellite, hybrid, terrain}. This field is optional and default is up to Google's "staticmap" API (usually "roadmap").
  * @param {Callback} callback with below parameters:
  * * * * @param {string} base64 string for the image of the map.
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getMapImageAsBase64Async(params: KASLocationStaticMapImageParams, callback: (attachmentString: string, error: string) => void): void;
```

##  get address information corresponding to a given location

```typescript
/**
  * fetches the address list for a given location using Google's "geocode" API and returns the first address's info. from the list. If there are no addresses present for the location, and errorcallabck is invoked.
  * @param {KASLocationAddressParams} object with below parameters:
  * * * * @param {number} latitude of the location. This is a mandatory field and if not provided API will get an error callback.
  * * * * @param {number} longitude of the location. This is a mandatory field and if not provided API will get an error callback.
  * * * * @param {string} language shown in the map (as in Google's "geocode" API). For eg. en, hi etc. This field is optional and default is en(English).
  * @param {Callback} callback with below parameters:
  * * * * @param {JSON} json object containing the address information. The json object is the first item of the "results" fetched from Google's geocode API. Please refer to Google's geocode API's documentation for more information.
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getLocationAddressAsync(params: KASLocationAddressParams, callback: (json: JSON, error: string) => void): void;
```

##  Gets all context for current conversation

```typescript
/**
  * Fetches all present conversation related context from iOS/android client. for example, source conversation id/ type, host conversation id/ type, conversation participants map
  * @param {Callback} callback with below parameters:
  * * * * @param {KASConversationDetails} conversation context object
  * * * * * * * * hostConversationId                 This is the group where current user is part of, as a result of which he received this action. For non hierarchical groups, this is same as source conv
  * * * * * * * * hostConversationTitle              Name/Title of the host group
  * * * * * * * * hostConversationType               Type of host conversation
  * * * * * * * * hostConversationParticipantsMap    Participants map in host conversation.
  * * * * * * * * sourceConversationId               Conversation where action is received. For non-hierarchical group, this is same as host conversation
  * * * * * * * * sourceConversationTitle            Name/Title of the source conversation. For non-hierarchical group, this is same as host conversation title
  * * * * * * * * sourceConversationType             Type of source conversation. For non-hierarchical group, this is same as host conversation type
  * * * * * * * * currentUserId                      Current user's id
  * * * * * * * * currentUserRoleInHostConversation  Current user's role in host conversation
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getConversationDetailsAsync(callback: (result: KASConversationDetails, error: string) => void): void;
```