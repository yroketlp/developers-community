---
pagename: Bot Basics
redirect_from:
    - conversation-builder-conversation-builder-automations.html
    - conversation-builder-automations.html
    - conversation-builder-bots.html
Keywords:
sitesection: Documents
categoryname: "Conversational AI"
documentname: Conversation Builder
subfoldername: Bots
permalink: conversation-builder-bots-bot-basics.html
indicator: both
---

### Types of bots

There are two, general types of bots:

* **Custom bots**: A [custom bot](conversation-builder-bots-custom-bots.html) is one that you design to accomplish a specific business function, such as fetching a consumer's order status or creating an account for the consumer. You can create a custom bot from scratch, or you can start from a predefined, industry-specific template. Either method allows you to fully customize the bot to meet your needs.
* **Survey bots**: A [survey bot](conversation-builder-bots-survey-bots.html) lets you collect feedback from consumers at the end of a conversation with a custom bot or human agent. Use a survey bot to measure bot/agent and skill performance and to identify opportunities to improve on your quality targets.

### Create a bot

* For details on creating a custom bot, see [here](conversation-builder-bots-custom-bots.html).
* For details on creating a survey bot, see [here](conversation-builder-bots-survey-bots.html).

### Configure bot settings

{: .important}
Survey bots have a few, unique settings that custom bots don't have. For information on these settings, see [here](conversation-builder-bots-survey-bots.html#step-3---configure-the-bot-settings).

**To configure bot settings**
1. Open the bot, and click <img style="width:25px" src="img/ConvoBuilder/icon_ellipsisVertical.png"> (3-dot icon) in the upper-left corner, just to the right of the menu bar.
2. Select **Bot Settings**.
3. Click **More Settings** to display all the settings.
4. Configure the settings as needed, and click **Save**.

Bot settings include:
- **Name**: Enter a name that’s concise and clear. Make sure abbreviations can be understood, and consider adding a prefix or suffix to indicate the environment (Dev, Prod, etc.) or language (En, Sp, Fr, etc.) if applicable. When you import a bot, by default, a date and time stamp is appended to the bot name; consider removing this because dates quickly become obsolete. 

- **Description**: Enter a description that’s meaningful to you and others. Consider including language that identifies the bot's goal and key behaviors.

- **Bot Type**: Read-only. This is always Consumer Facing Bot.

- **Bot Language**: Read-only. This setting determines the language of the bot. It must be set to be the same language as that for the domain that's associated with the bot. Otherwise, errors occur during NLU processing. You specify the bot language when you create the bot, and it can’t be changed afterward.

- **Bot Template**: Read-only. To facilitate the rapid creation of bots, all bots are based on [templates](conversation-builder-templates-overview.html). The default template is Basic, which uses English and includes just a Welcome dialog. You select the template when you create the bot, and it can’t be changed afterward.

- **Bot Group**: Optionally select the [bot group](conversation-builder-bots-bot-groups.html) for the bot. A bot can be a member of exactly one group.

- **Bot ID**: Read-only. This is a unique identifier that’s generated by the system. In some scenarios (for example, when using some APIs), you need to reference the bot ID. Here’s where you can find it.

- **Conversation Builder Platform Version**: Read-only. This identifies the platform version of the bot. Typically, you don’t need this information, but here’s where you can find it if asked for it (for example, in a support scenario).

- **Entity**: You can use this option to associate _a domain_ with the bot. However, the [NLU Assist](conversation-builder-nlu-assist.html) tool provides you with help in associating domains with dialogs, so typically you don’t need to specify a domain here.

- **Bot Account**: If you logged into Conversation Builder directly (i.e., _not_ via single sign-on from LiveEngage) and you have access to multiple organizations within your LiveEngage account, you can use this setting to change the organization under which this bot exists. If you logged into Conversation Builder via single sign-on from LiveEngage, the organization you were using in LiveEngage is active and can't be changed, and nothing appears in this list.

- **Public**: When you want other users in your LiveEngage account to be able to view and edit the bot, click the slider to On. The default value is Off. 

- **Bot Environment**: If desired, select the set of [environment variables](conversation-builder-environment-variables.html) that you want to associate with the bot. Environment variables allow you to manage certain values and constants outside of the bot, and use of them when appropriate is considered a best practice.

- **Session Length**: Select the length of the bot session, that is, how long the context of a conversation is maintained after the conversation becomes idle. If this is unset, the default of one hour is used. Be aware that Conversation Builder maintains its own session, and LiveEngage maintains its own session. This setting only determines the length of the Conversation Builder session.

- **Log Transcripts**: If you don’t want to log transcripts of conversations held via the bot, click the slider to Off. The default value is On. Transcripts can provide insights for a variety purposes. For example, they can inform the bot flow and help with tuning. However, some cases might prohibit transcript logging for privacy or other reasons.

    If you turn this off, metadata on the conversation is still logged, but the content of the conversation isn’t. If you keep this on, you can access the logged transcripts in the Bot Analytics application: Select the bot and then access the **Transcripts** page.

- **Shorten URLs**: Enable this if you want to shorten the URLs sent in interactions, which can be desirable if you have lengthy web links. Disable this to keep URLs as they are. The default value is Disabled (Off). For more on URL shortening, see [here](conversation-builder-interactions-interaction-basics.html#url-shortening).

    If you enable this setting, the shortened domain might need to be whitelisted. For more on whitelisting, see [here](conversation-builder-interactions-interaction-basics.html#whitelisting).

    To support backwards compatibility, button interactions use URL shortening even though the new Shorten URLs setting is set initially to Off. To disable URL shortening for buttons, enable the setting, save the change, disable the setting, and then save the change again. From this point forward, button interactions will respect the value of the setting and work like all other interactions.

- **Default User-Friendly Response**: This is an *error* response that gets sent to the user. Because you can supply the response, you can customize it in terms of substance and language (Spanish, Italian, etc.). If you enter a value here, it's used in two circumstances.
    
    First, when the bot encounters errors or throws exceptions, many times a default error response of, "Not able to understand your question. Can you please re-phrase it?" is sent to the user. Since this message is the same as the built-in, default Fallback message, it might confuse the user. To send a different response when errors occur, enter a value here. It won't replace or affect the Fallback message or a Fallback dialog, as they serve different purposes. Fallback handles when the user's utterance doesn't match a pattern or intent. In contrast, this error response is sent when the bot encounters an error or throws an exception.
    
    Second, during a LivePerson agent escalation, if the [escalation fails](conversation-builder-integrations-liveperson-agent-escalation-integrations.html#handle-transfer-failures) four times, the escalation then stops, and a default failure response of, "Not able to transfer to Agent at this time. Please try later." is sent to the user. To send a different response, enter a value here.

    To enter a value, click the slider to activate it, enter the text in the field that appears, and save. There is no character limit.

### Import a bot
You can add an bot by importing a bot JSON file that was previously exported. This is useful when you need to make a copy of a bot (just export and then import back into the same environment), or you need to copy or move a bot from one environment to another.

{: .important}
Before you import a bot from a different environment (that is, from one region or hosting platform to another), check whether the bot uses domains for intents and entities. If it does, you’ll need to export those domains too and import them into the target environment _before_ importing the bot, keeping the domain names identical. If you don’t import the domains _first_, the associations inside the bot to the intents and entities will break during the bot import. If that happens, you’ll need to reassociate the intents and entities manually.

**To import a bot**
1. If you logged into Conversation Builder directly (i.e., _not_ via single sign-on from LiveEngage) and you have access to multiple organizations within your LiveEngage account, verify in the upper-right corner that the organization under which the bot should exist is displayed. If it isn’t displayed, select it from the **Org** Name dropdown list.

    <img class="fancyimage" style="width:200px" src="img/ConvoBuilder/org_selection.png">

2. In the dashboard that lists your bots, click **Import Bot** in the upper-right corner.
3. In the dialog box that appears, navigate to and select the JSON file, and click **Open**.
    The bot is imported and given a name that includes a date and time stamp.
4. Change the name of the bot and any other configuration as needed. For help, see [Configure bot settings](conversation-builder-bots-bot-basics.html#configure-bot-settings) above.

### Export a bot
Export of a bot creates a JSON file.

You might need to export a bot for a few reasons:

- You want to create a variation of the bot, so you plan to copy the bot by exporting it and then importing it back into the same environment.
- You want to move or copy a bot to another environment, so you plan to export it and import it into a different environment.
- You want an extra measure of back-up—above and beyond [saving versions](conversation-builder-versions-releases.html#save-a-version) of bots that you can restore—so you plan to archive the JSON file for safekeeping.

{: .important}
In case 2 above—-moving or copying a bot to a different environment (that is, from one region or hosting platform to another)—-check whether the bot uses domains for intents and entities. If it does, you’ll need to export those domains too and import them into the target environment _before_ importing the bot, keeping the domain names identical. If you don’t import the domains _first_, the associations inside the bot to the intents and entities will break during the bot import. If that happens, you’ll need to reassociate the intents and entities manually.

**To export a bot**
1. Open the bot, and click <img style="width:25px" src="img/ConvoBuilder/icon_ellipsisVertical.png"> (3-dot icon) in the upper-left corner, just to the right of the menu bar.
2. Select **Bot Settings**.
3. Click **More Settings**, and then click the **Export Bot** icon <img style="width:25px" src="img/ConvoBuilder/icon_export.png">.
4. Follow the browser prompts to access and save the JSON file to a location of your choice.

### Delete a bot
Deleting a bot is a non-recoverable action, so be certain about doing so before taking this action.

{: .important}
If you want to delete a bot that is deployed, first stop the bot, un-deploy it, and remove any enterprise integrations that are running. This helps to ensure there are no adverse effects.

**To delete a bot**
1. Open the bot, and click <img style="width:25px" src="img/ConvoBuilder/icon_ellipsisVertical.png"> (3-dot icon) in the upper-left corner, just to the right of the menu bar.
2. Select **Bot Settings**.
3. Click **More Settings**, and then click the **Delete Bot** icon <img style="width:25px" src="img/ConvoBuilder/icon_delete.png">.
4. In the confirmation dialog:
    1. If you want to delete all the logs and analytics data for the bot, select the checkbox.
    2. Click **Proceed**.