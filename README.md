# iontone-chat

A drop-in chat widget for ionTone / HyperB agents. One script tag adds a floating chat icon and chat window to any web page.

## Usage

Add this line to your page, just before `</body>`:

```html
<script
  src="https://cdn.jsdelivr.net/gh/azaas/iontone-chat@1.2.1/chat_widget.min.js"
  data-code="WORKSPACE_ID|AGENT_ID"
></script>
```

`data-code` is your workspace ID and agent ID, separated by a pipe (`|`). (For a Web Chat channel use `data-channel` instead, see below.) Nothing else is needed: the script, styles and logo animation are all in the one file.

Pin a version (`@1.2.1`) rather than `@latest` or a branch name, so your page only changes when you choose to update.

## Optional attributes

| Attribute              | Description                                                                 |
| ---------------------- | --------------------------------------------------------------------------- |
| `data-theme-color`     | Hex colour for the header and accents, e.g. `#004BC0`.                      |
| `data-header-title`    | Text in the chat window header. Default: `Ask Us`.                          |
| `data-initial-message` | Greeting shown before the user types. Default: `Hi there! How can I help you today?` |
| `data-toggle-label`    | Text of the bubble next to the closed chat icon. Default: `Need AI help?`.  |
| `data-base-url`        | Agents API origin. Default: `https://chat.iontone.com`.                     |
| `data-channel`         | Web Chat channel public key (replaces `data-code`; see Web Chat mode).      |
| `data-webchat-url`     | Flow builder address for Web Chat mode.                                     |

```html
<script
  src="https://cdn.jsdelivr.net/gh/azaas/iontone-chat@1.2.1/chat_widget.min.js"
  data-code="WORKSPACE_ID|AGENT_ID"
  data-theme-color="#004BC0"
  data-header-title="Ask Us"
  data-initial-message="Hi there! How can I help you today?"
  data-toggle-label="Need AI help?"
></script>
```

## Web Chat mode

To put a Web Chat channel of your organisation's ionTone flow builder on your site (a flow, rather than an agent, answers the visitor), use `data-channel` instead of `data-code`:

```html
<script
  src="https://cdn.jsdelivr.net/gh/azaas/iontone-chat@1.2.1/chat_widget.min.js"
  data-channel="CHANNEL_PUBLIC_KEY"
  data-webchat-url="https://FLOW_BUILDER_ADDRESS/BASE_PATH"
></script>
```

| Attribute            | Description                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------- |
| `data-channel`       | The channel's public key, shown in ionTone under Operations, Messaging, Web Chat. Not a secret. |
| `data-webchat-url`   | Where the flow builder is served, including its base path. Default: the page's own origin.  |

Everything else is optional: the channel's own settings (title, greeting, launcher label, colour, side) are used unless you set `data-header-title`, `data-initial-message`, `data-toggle-label` or `data-theme-color`, which win.

Add your site's address (for example `https://www.example.com`) to the channel's **allowed origins** in ionTone; the widget is not shown on a page the channel does not allow. Visitors need no sign-in. Replies and anything your team write from Messaging appear live in the window, and a returning visitor sees their earlier conversation.

## How it connects

In agent mode (`data-code`) the widget talks to the production service at `https://chat.iontone.com`, which needs no authentication. The widget sends no credentials and works on any website.

In Web Chat mode (`data-channel`) it talks only to the flow builder address you give in `data-webchat-url`. It sends no cookies; a visitor's session is a token the widget keeps in the browser's `localStorage` (the session id and token only, never the messages), and the channel's allowed-origins list decides which sites may use it.

## License

Licensed under the [Apache License, Version 2.0](LICENSE). Copyright 2026 aZaaS Pte Ltd, Singapore. See [NOTICE](NOTICE).

The widget bundles third-party open-source components. Their licenses and notices are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), and a short copyright banner is kept at the top of `chat_widget.min.js`.

## Trademark notice

The ionTone name and the ionTone logo mark are trademarks of **aZaaS Pte Ltd, Singapore**. The Apache License 2.0 covers the code only and does not grant any right to use these marks. Do not use them to imply endorsement or affiliation, and do not use them in a derived product or fork without written permission from aZaaS Pte Ltd.
