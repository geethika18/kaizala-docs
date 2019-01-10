[](../README.md) > [KASClient](../modules/kasclient.md) > [Form](../modules/kasclient.form.md)

# Module: Form

## Index


### Creation

* [initFormAsync](kasclient.form.md#initformasync)
* [submitFormRequestV2](kasclient.form.md#submitformrequestv2)
* [submitFormRequestWithoutDismiss](kasclient.form.md#submitformrequestwithoutdismiss)
* [updateForm](kasclient.form.md#updateform)


### Response

* [getFormAsync](kasclient.form.md#getformasync)
* [getFormStatusAsync](kasclient.form.md#getformstatusasync)
* [getMyFormResponsesAsync](kasclient.form.md#getmyformresponsesasync)
* [sumbitFormResponse](kasclient.form.md#sumbitformresponse)
* [sumbitFormResponseWithoutDismiss](kasclient.form.md#sumbitformresponsewithoutdismiss)


### Summary

* [addCommentOnForm](kasclient.form.md#addcommentonform)
* [closeForm](kasclient.form.md#closeform)
* [copyFormAndForward](kasclient.form.md#copyformandforward)
* [getActionInstanceLocalDataCacheAsync](kasclient.form.md#getactioninstancelocaldatacacheasync)
* [getActionPackageLocalDataCacheAsync](kasclient.form.md#getactionpackagelocaldatacacheasync)
* [getFormReactionAsync](kasclient.form.md#getformreactionasync)
* [getFormSummaryAsync](kasclient.form.md#getformsummaryasync)
* [getFormURLAsync](kasclient.form.md#getformurlasync)
* [getFormUserCapabilitiesAsync](kasclient.form.md#getformusercapabilitiesasync)
* [isSubscribed](kasclient.form.md#issubscribed)
* [likeForm](kasclient.form.md#likeform)
* [sendRemindersToRespond](kasclient.form.md#sendreminderstorespond)
* [shareFormURL](kasclient.form.md#shareformurl)
* [showAllReactions](kasclient.form.md#showallreactions)
* [updateActionInstanceLocalDataCacheAsync](kasclient.form.md#updateactioninstancelocaldatacacheasync)
* [updateActionPackageLocalDataCacheAsync](kasclient.form.md#updateactionpackagelocaldatacacheasync)
* [updateFormPropertiesAsync](kasclient.form.md#updateformpropertiesasync)




---

## Creation

<a id="initformasync"></a>

###  initFormAsync

▸ **initFormAsync**(callback: *`function`*): `void`


Initializes and returns an empty form object based on the default form file present in the package


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASForm} form can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="submitformrequestv2"></a>

###  submitFormRequestV2

▸ **submitFormRequestV2**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldDismiss?: *`boolean`*, shouldSendToSubscribers?: *`boolean`*): `void`


Submits the newly created form as a request. This results a new conversation card


**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) | - |  \- |
| `Default value` shouldDismiss | `boolean` | false |
| `Default value` shouldSendToSubscribers | `boolean` | true |

**Returns:** `void`

___




<a id="submitformrequestwithoutdismiss"></a>

###  submitFormRequestWithoutDismiss

▸ **submitFormRequestWithoutDismiss**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldInflate: *`boolean`*): `void`


Submits the newly created form as a request. This results a new conversation card


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) |  \- |
| shouldInflate | `boolean` |

**Returns:** `void`

___




<a id="updateform"></a>

###  updateForm

▸ **updateForm**(fields: *`string`*, shouldInflate: *`boolean`*, callback: *`function`*): `void`


use for making changes in form fields like title, description and settings.


**Parameters:**

| Name | Type |
| ------ | ------ |
| fields | `string` |
| shouldInflate | `boolean` |
| callback | `function` |

**Returns:** `void`

___





## Response

<a id="getformasync"></a>

###  getFormAsync

▸ **getFormAsync**(callback: *`function`*): `void`


Gets the form object associated with the conversation card


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASForm} form can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getformstatusasync"></a>

###  getFormStatusAsync

▸ **getFormStatusAsync**(callback: *`function`*): `void`


Gets the status of the form associated with the conversation card


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {boolean} isActive true if the form is not yet expired*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getmyformresponsesasync"></a>

###  getMyFormResponsesAsync

▸ **getMyFormResponsesAsync**(callback: *`function`*): `void`


Gets all the responses of the current user against the form


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormResponse\[\]} responses can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="sumbitformresponse"></a>

###  sumbitFormResponse

▸ **sumbitFormResponse**(questionToAnswerMap: *`JSON`*, responseId: *`string`*, isEdit: *`boolean`*, showInChatCanvas: *`boolean`*, isAnonymous: *`boolean`*): `void`


Submits a new response against the form associated with the conversation card This will dismiss the current screen


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| questionToAnswerMap | `JSON` |  question id to answer mapping |
| responseId | `string` |  to be filled if the current response is an edit/update to a previous one |
| isEdit | `boolean` |  denotes if the current response is an edit/update to a previous one |
| showInChatCanvas | `boolean` |  denotes if a separate chat card needs to be created for this response or not |
| isAnonymous | `boolean` |  denotes if the response should be registered as anonymous or not |

**Returns:** `void`

___




<a id="sumbitformresponsewithoutdismiss"></a>

###  sumbitFormResponseWithoutDismiss

▸ **sumbitFormResponseWithoutDismiss**(questionToAnswerMap: *`JSON`*, responseId: *`string`*, isEdit: *`boolean`*, showInChatCanvas: *`boolean`*, isAnonymous: *`boolean`*): `void`


Submits a new response against the form associated with the conversation card This won't dismiss the current screen


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| questionToAnswerMap | `JSON` |  question id to answer mapping |
| responseId | `string` |  to be filled if the current response is an edit/update to a previous one |
| isEdit | `boolean` |  denotes if the current response is an edit/update to a previous one |
| showInChatCanvas | `boolean` |  denotes if a separate chat card needs to be created for this response or not |
| isAnonymous | `boolean` |  denotes if the response should be registered as anonymous or not |

**Returns:** `void`

___





## Summary

<a id="addcommentonform"></a>

###  addCommentOnForm

▸ **addCommentOnForm**(comment: *`string`*): `void`


Requests to add a comment to a form


**Parameters:**

| Name | Type |
| ------ | ------ |
| comment | `string` |

**Returns:** `void`

___




<a id="closeform"></a>

###  closeForm

▸ **closeForm**(): `void`


Closes the form associated with the card, no responses will be allowed further


**Returns:** `void`

___




<a id="copyformandforward"></a>

###  copyFormAndForward

▸ **copyFormAndForward**(): `void`


Launches the conversation picker to forward a copy of the existing form as a new conversation card


**Returns:** `void`

___




<a id="getactioninstancelocaldatacacheasync"></a>

###  getActionInstanceLocalDataCacheAsync

▸ **getActionInstanceLocalDataCacheAsync**(callback: *`function`*): `void`


Retrieves the ActionInstance Properties from the local data cache if any exists These properties are stored at an action instance level. So the local data saved for the particular action instance will be returned by this API.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   *   *   @param {KASActionProperties} actionProperties ActionInstance/Form Properties*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___




<a id="getactionpackagelocaldatacacheasync"></a>

###  getActionPackageLocalDataCacheAsync

▸ **getActionPackageLocalDataCacheAsync**(callback: *`function`*): `void`


Retrieves the Action Package Properties from the local data cache if any exists These properties are saved at the action package level. So all action instances created from this action package will receive the same data.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   *   *   @param {KASActionPackageProperties} actionPackageProperties Action Package Properties*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___




<a id="getformreactionasync"></a>

###  getFormReactionAsync

▸ **getFormReactionAsync**(callback: *`function`*): `void`


Gets the consolidated reaction (likes and comments) of the conversation card associated with the form


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormReaction} reaction can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getformsummaryasync"></a>

###  getFormSummaryAsync

▸ **getFormSummaryAsync**(mostUpdatedCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*, notifyCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*): `void`


Gets flat responses by all the users, and processed summary from all the responses associated with the form. It requires two callbacks:


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| mostUpdatedCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to immediately get the most updated summary from local database. It has below parameters:*   @param {KASFormFlatSummary} flatSummary can be null in case of error*   @param {KASFormProcessedSummary} processedSummary can be null in case of error*   @param {string} error message in case of error, null otherwise |
| notifyCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to get notified with the latest summary fetched from server. It has below parameters:*   @param {KASFormFlatSummary} flatSummary can be null in case of error*   @param {KASFormProcessedSummary} processedSummary can be null in case of error*   @param {string} error message in case of error, null otherwise<br><br>This is useful when the network is flaky/disconnected, so that summary can immediately be shown with the present data we have, but with an option to refresh it later on arrival of latest data from server! None of the callbacks are mandatory, so if 1st is nil, this method can be used to always fetch summary from server, and if 2nd is nil, this can be used to always fetch summary from local database! |

**Returns:** `void`

___




<a id="getformurlasync"></a>

###  getFormURLAsync

▸ **getFormURLAsync**(callback: *`function`*): `void`


Gets the file url from server containing flat responses associated with the form


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} url can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getformusercapabilitiesasync"></a>

###  getFormUserCapabilitiesAsync

▸ **getFormUserCapabilitiesAsync**(callback: *`function`*): `void`


Gets form permissions


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormUserCapabilities} permissions |

**Returns:** `void`

___




<a id="issubscribed"></a>

###  isSubscribed

▸ **isSubscribed**(callback: *`function`*): `void`


Gets whether the current user is subscriber or not


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {boolean} isSubscribed true if current user subscriber |

**Returns:** `void`

___




<a id="likeform"></a>

###  likeForm

▸ **likeForm**(): `void`


Requests to add a like count to a form, the count may decrease if the current user has already liked the form


**Returns:** `void`

___




<a id="sendreminderstorespond"></a>

###  sendRemindersToRespond

▸ **sendRemindersToRespond**(): `void`


Sends a reminder (a new conversation card) against the existing card


**Returns:** `void`

___




<a id="shareformurl"></a>

###  shareFormURL

▸ **shareFormURL**(url: *`string`*): `void`


Launches native share screen for the form url


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| url | `string` |  to be shared |

**Returns:** `void`

___




<a id="showallreactions"></a>

###  showAllReactions

▸ **showAllReactions**(showComments?: *`boolean`*): `void`


Shows all the reaction screen (likes and comments) against the form


**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` showComments | `boolean` | true |

**Returns:** `void`

___




<a id="updateactioninstancelocaldatacacheasync"></a>

###  updateActionInstanceLocalDataCacheAsync

▸ **updateActionInstanceLocalDataCacheAsync**(actionProperties: *[KASActionProperties](../classes/kasclient.kasactionproperties.md)*, callback: *`function`*): `void`


Updates/saves the given ActionInstance Properties to the local data cache These properties are stored at an action instance level. So each action instance can save some local data in the cache and it will only be accessible by that particular instance
*__warning__*: This API doesn't work as expected in case of historical messages.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionProperties | [KASActionProperties](../classes/kasclient.kasactionproperties.md) |  ActionInstance/Form Properties to be updated/saved |
| callback | `function` |  with below parameters:*   *   *   @param {boolean} success indicates if the update is successful or not*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___




<a id="updateactionpackagelocaldatacacheasync"></a>

###  updateActionPackageLocalDataCacheAsync

▸ **updateActionPackageLocalDataCacheAsync**(actionPackageProperties: *[KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md)*, callback: *`function`*): `void`


Updates/saves the given Action Package Properties to the local data cache These properties are saved at the action package level. So the data is shared among all action instances created from this action package.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionPackageProperties | [KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md) |  Action Package Properties to be updated/saved |
| callback | `function` |  with below parameters:*   *   *   @param {boolean} success indicates if the update is successful or not*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___




<a id="updateformpropertiesasync"></a>

###  updateFormPropertiesAsync

▸ **updateFormPropertiesAsync**(propertyUpdates: *[KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[]*, notifyUsers: *`string`[]*, notificationMessage: *`string`*, callback: *`function`*): `void`


Post a request to update the properties associated with the form


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| propertyUpdates | [KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[] |  an array of all update infos that are needed to be performed, update infos can be created using KASFormPropertyUpdateFactory |
| notifyUsers | `string`[] |  send push notifications to these user ids regarding this update |
| notificationMessage | `string` |  push notification message |
| callback | `function` |  with below parameters:*   @param {boolean} success indicates if the update is successful or not |

**Returns:** `void`

___





