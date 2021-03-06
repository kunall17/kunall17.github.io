---
layout: page
title: GSOC '17
sidebar_link: true
---


# Google summer of code '17: Report

### Introduction

I worked on the react native framework, to enhance the cross platform group chat application for the orgranization **Zulip**.

I have been contributing to Zulip since my [last GSOC](./gsoc16) and it has been a great experience so far, thanks to the Zulip Organization for selecting me again.

In this course of 3 months I have done a lot of changes, implemented new features, fixed many crutial bugs, worked on not only RN but also on several other things.

### Some quick links

* [Repository link](https://github.com/zulip/zulip-mobile)
* [Pull request's](https://github.com/zulip/zulip-mobile/pulls?utf8=%E2%9C%93&q=author%3Akunall17%20)
* [More about Zulip](https://zulipchat.com/)

### Contribution

###### _(List of main features worked on)_

* [Push notifications for android & ios](#push-notifications-for-android--ios)
* [Implemented prettier (code formatting)](#implemented-prettier-code-formatting))
* [Hooked up detox E2E & the prettier formatting check](#hooked-up-detox-e2e-&-the-prettier-formatting-check)
* [Markdown parser (converts markdown to html for messages)](#markdown-parser-(converts-markdown-to-html-for-messages))
* [Several changes in the settings screen](#several-changes-in-the-settings-screen)
* [Use parser to locally echo the message sent](#use-parser-to-locally-echo-the-message-sent)
* [Implemented the outbox functionallity](#implemented-the-outbox-functionallity)
* [Message auto saved as drafts](#implemented-the-outbox-functionallity)
* [Full screen markdown editor](#implemented-the-outbox-functionallity)
* [Pleothera of other fixes](#pleothera-of-other-fixes)
* [Message auto saved as drafts](#message-auto-saved-as-drafts)
* [Implemented muting of topics/streams](#implemented-muting-of-topics-streams)


###### _(Details on the above listed)_


##### Push notifications for android & ios

Used the wix/react-native-notifications for the ios & android notifications

###### Android

Inital implementation was 

![](https://user-images.githubusercontent.com/12700799/27065186-66ef3f04-5019-11e7-9e01-53487d28a0bf.png)

Then 

![](https://user-images.githubusercontent.com/12700799/27505924-160f7982-58ca-11e7-84bf-df54271ebfe0.png)


[Grouped notifications into one and show the notifications as a list](https://github.com/zulip/zulip-mobile/pull/734)  
[Initial implementation of android GCM push notifications](https://github.com/zulip/zulip-mobile/pull/637)  
[Don't show message's count if only 1 message in the android notifications](https://github.com/zulip/zulip-mobile/pull/802)  
[Use big view styles for 1 conversation](https://github.com/zulip/zulip-mobile/pull/755)  


###### iOS

[Implementation of ios push notifications](https://github.com/zulip/zulip-mobile/pull/746)  
[Added log statment and enabled background modes for ios notifications](https://github.com/zulip/zulip-mobile/pull/1054)  


##### End to end integration test's using appium & detox

Initially I implemented appium, but the test's were flaky even after good writeup (even after getting it reviewed by experienced people)
Hence we decided to move on to detox which is a newer library built specifically for react native and its not flaky


[Add integration testing using appium for the iOS](https://github.com/zulip/zulip-mobile/pull/602)  
[Replace appium with detox](https://github.com/zulip/zulip-mobile/pull/825)  


##### Rework on the compose box design

Added a topic field to the compose box, by this now its possible to write a new topic in the stream narrow

[Hide mode changer as there is only one compose option: compose text](https://github.com/zulip/zulip-mobile/pull/694)  
[Hide other icons in the ComposeOptions](https://github.com/zulip/zulip-mobile/pull/689)  

[New compose box design](https://github.com/zulip/zulip-mobile/pull/561)  

Similary, implemented this for the private narrow as well
Unfortunetly this PR didn't got through as we decided it's not the best UX to send messages to other people without narrowing to their conversation.

[New compose box design for private messages](https://github.com/zulip/zulip-mobile/pull/678)  

[Display topic input only in stream narrow](https://github.com/zulip/zulip-mobile/pull/945)  


##### Menu for the long press of message

This added to show menu on long press of a message and have features like reply, narrow etc.

[Show action sheet on long press of header](https://github.com/zulip/zulip-mobile/pull/801)  

##### Editing message made possible

This added an imperative feature of editing a sent message, and was long due for the project.

[Implemented editing message](https://github.com/zulip/zulip-mobile/pull/402)

##### Implemented prettier (code formatting)

One of most important part of my contribution, was this.
Prettier added a code styling guide and increased the code readibility of the project.


[Renable prettier and fix all issues related to it](https://github.com/zulip/zulip-mobile/pull/859)  was a massive PR to fix all the non-formatted code, and now the code styling of the project is much better

[Implement prettier for the project](https://github.com/zulip/zulip-mobile/pull/850)  


##### Hooked up detox E2E & the prettier formatting check

This took a lot of time to use the UI testing checking automically in the travis CI
Now the CI does a release build from scratch and use the generated file to run a end to end test, runs without any flakiness

Currently there aren't many test running as we need a dev server for the main screen testing

Prettier check test's if the code in the branch is formatted according the prettier specified format

[Added detox smoke test's in the travis CI](https://github.com/zulip/zulip-mobile/pull/915)  
[Use prettier-check to check if all files are formatted with prettier](https://github.com/zulip/zulip-mobile/pull/910)  


##### Markdown parser (converts markdown to html for messages)

This converts the markdown to the html which now helps locally echoing the sent message and previewing the written markdown in the Full Screen Editor.

[Implement markdown parser to convert markdown to html](https://github.com/zulip/zulip-mobile/pull/949)  

##### Several changes in the settings screen


[Separate language to another screen in settings screen](https://github.com/zulip/zulip-mobile/pull/944)  
[Add online notification switch to settings](https://github.com/zulip/zulip-mobile/pull/828)  
[Add a setting for enabling offline push notifications](https://github.com/zulip/zulip-mobile/pull/748)  
[Fetch updates for notification and display settings](https://github.com/zulip/zulip-mobile/pull/754)  

##### Use parser to locally echo the message sent

Uses parser to convert 

##### Implemented the outbox functionallity

[Implement reducers and actions for outbox and use it in ComposeBox](https://github.com/zulip/zulip-mobile/pull/977)  
[Use result of post request for sending message](https://github.com/zulip/zulip-mobile/pull/1079)  
[Fix outbox bugs](https://github.com/zulip/zulip-mobile/pull/1041)  
[Implement action sheet for outbox messages](https://github.com/zulip/zulip-mobile/pull/1022)  
[Use outbox messages to render messages to the chat screen](https://github.com/zulip/zulip-mobile/pull/1014)  

##### Message auto saved as drafts

[Implement drafts screen](https://github.com/zulip/zulip-mobile/pull/1019)  

##### Full screen markdown editor

This is a full screen markdown editor which would be really helpful for writing long big formatted message 

**Glimpse of the editor**

![](https://user-images.githubusercontent.com/12700799/28812575-f42b21d4-76b2-11e7-9085-99b66223750f.gif)


[I also extracted this out in a library ](https://github.com/kunall17/react-native-markdown-editor)

[Full screen markdown editor](https://github.com/zulip/zulip-mobile/pull/882)  

##### Implemented muting of topics/streams

This added an option to mute/unmute topics/streams

[Add API calls for muting/unmuting stream/topic](https://github.com/zulip/zulip-mobile/pull/574)  
[Added reducers for receiving updates on subscriptions and muted topics](https://github.com/zulip/zulip-mobile/pull/569)
[Implemented Muting/Unmuting of streams and topics](https://github.com/zulip/zulip-mobile/pull/415)  


##### Pleothera of other fixes


[Fix: Muted topics were being displayed in homeView](https://github.com/zulip/zulip-mobile/pull/410)  
[Fix: NoSuchMethodError for builder.addAction](https://github.com/zulip/zulip-mobile/pull/1088)  
[Fix eventQueueId in appReducers](https://github.com/zulip/zulip-mobile/pull/1076)  
[[WIP] Fix flow, jest unit test errors](https://github.com/zulip/zulip-mobile/pull/1068)  
[Fix chatReducers EVENT_NEW_MESSAGE incorrect implementation](https://github.com/zulip/zulip-mobile/pull/1066)  
[Fix for unauthorized access and push notification](https://github.com/zulip/zulip-mobile/pull/1051)  
[Fix re-rendering of AppContainer due to outbox](https://github.com/zulip/zulip-mobile/pull/1009)  
[Fix: Upgrade expo actionsheet due to BackAndroid being deprecated](https://github.com/zulip/zulip-mobile/pull/1005)  
[Fix android GCM push notifications](https://github.com/zulip/zulip-mobile/pull/1000)  
[Fix react-native-fetch-blob package crash](https://github.com/zulip/zulip-mobile/pull/999)  
[Fix master branch flow errors](https://github.com/zulip/zulip-mobile/pull/976)  
[Fetch realm_filters and its event updates](https://github.com/zulip/zulip-mobile/pull/956)  
[Handle back pressed in android](https://github.com/zulip/zulip-mobile/pull/898)  
[Fixes #934: Play zulip.mp3 on android push notification](https://github.com/zulip/zulip-mobile/pull/943)  
[Fix release build through command line errors](https://github.com/zulip/zulip-mobile/pull/940)  
[Fix unread selectors and fix eslint error](https://github.com/zulip/zulip-mobile/pull/928)  
[Fix: Downgrade photoview dependency to 1.2.0](https://github.com/zulip/zulip-mobile/pull/899)  
[Fix: navigation to dev auth screen](https://github.com/zulip/zulip-mobile/pull/873)  
[Fixes #683: Split users into users and presence](https://github.com/zulip/zulip-mobile/pull/750)  
[Fix: Receive twentyFourHourTime from the server on intital fetch](https://github.com/zulip/zulip-mobile/pull/747)  
[Fixes #633: Remove ActionSheetProvider from root in the chat.js](https://github.com/zulip/zulip-mobile/pull/634)  
[Fix: Renamed mute topic & streams](https://github.com/zulip/zulip-mobile/pull/631)  
[Use translated strings in message action sheet](https://github.com/zulip/zulip-mobile/pull/829)  