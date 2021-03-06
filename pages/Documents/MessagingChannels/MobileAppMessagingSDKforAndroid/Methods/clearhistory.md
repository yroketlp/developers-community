---
pagename: clearHistory
redirect_from:
  - android-clearhistory.html
Keywords:

categoryname: "Messaging Channels"
documentname: Mobile App Messaging SDK for Android
subfoldername: Methods

order: 250
permalink: mobile-app-messaging-sdk-for-android-methods-clearhistory.html

indicator: messaging
---

Clear all conversations from the device. This clears all conversations and messages from the device only and does not remove them from the server. If the account has history enabled and is used on a new device, all conversations will be loaded from the server.

The return value indicates whether the action was completed successfully or not:

- True - All conversations were cleared successfully.
- False - Conversations were not cleared since there is an open conversation.

*Note: The clearHistory API call will work only if there is currently no active conversation.*

`public static boolean clearHistory()`
