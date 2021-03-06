# [Platforms](../) > Google Assistant

Learn more about Google Assistant specific features that can be used with the Jovo Framework.

* [Introduction to Google Assistant Specific Features](#introduction-to-google-assistant-specific-features)
* [Output](#output)
  * [Multiple Reprompts](#multiple-reprompts)
  * [Screen Surfaces](#screen-surfaces)


## Introduction to Google Assistant Specific Features

> Find an introduction to how Google Assistant works here: [Getting Started > Voice App Basics > Google Assistant](https://github.com/jovotech/jovo-framework-nodejs/tree/master/docs/01_getting-started/voice-app-basics.md/#google-assistant).

You can access the `googleAction` object like this:

```javascript
let google = app.googleAction();
```


## Output

Below are specific output elements that can be used for Google Actions. 

### Multiple Reprompts

Google Assistant allows to add multiple reprompts that are spoken out in order if there is no response by the user. Here is the official reference by Google: [Static Reprompts](https://developers.google.com/actions/assistant/reprompts#static_reprompts).

The reprompts can be added to the `ask` method by using an array.

```javascript
app.ask(speech, [reprompt1, reprompt2, goodbyeMessage]);
```

The first two messages are usually reprompt messages, the third one is used to say goodbye to the user.

### Screen Surfaces

Below are fetures that are specific for Google Actions with screen surfaces. Find the official refference by Google here: [Surface Capabilities](https://developers.google.com/actions/assistant/surface-capabilities).


#### Display Text

This will display an alternative text instead of the written speech output on your screen surface, e.g. the Google Assistant mobile phone app.

```javascript
app.googleAction().displayText(text);

// Example
let speech = 'Hello World!';
let text = 'Hello Phone!';
app.googleAction().displayText(text);
app.tell(speech);

// You can also add the tell directly to the Google Action object
app.googleAction().displayText(text)
    .tell(speech);
```

Here is the [official reference by Google](https://developers.google.com/actions/assistant/responses).

#### Google Assistant Cards

With Jovo, you can display cards on Google Assistant surfaces. 

You can find an example file here: [`indexGoogleAssistantCards.js`](https://github.com/jovotech/jovo-framework-nodejs/blob/master/examples/google_action_specific/indexGoogleAssistantCards.js).


### Suggestion Chips

Suggestion Chips provide the ability for your users to quickly answer a question by tapping on a button. Here is the official reference by Google: [Suggestion Chip](https://developers.google.com/actions/assistant/responses#suggestion-chip).

```javascript
app.googleAction().showSuggestionChips(['Chip1', 'Chip2', 'Chip3']);
```

Find an example here: [`indexGoogleAssistantCards.js`](https://github.com/jovotech/jovo-framework-nodejs/blob/master/examples/google_action_specific/indexGoogleAssistantCards.js).
