# iontone-chat

A drop-in chat widget for ionTone / HyperB agents. One script tag adds a floating chat icon and chat window to any web page.

## Usage

Add this line to your page, just before `</body>`:

```html
<script
  src="https://cdn.jsdelivr.net/gh/DrChoon/iontone-chat@1.1.0/chat_widget.min.js"
  data-code="WORKSPACE_ID|AGENT_ID"
></script>
```

`data-code` is your workspace ID and agent ID, separated by a pipe (`|`). Nothing else is needed: the script, styles and logo animation are all in the one file.

Pin a version (`@1.1.0`) rather than `@latest` or a branch name, so your page only changes when you choose to update.

## Optional attributes

| Attribute              | Description                                                                 |
| ---------------------- | --------------------------------------------------------------------------- |
| `data-theme-color`     | Hex colour for the header and accents, e.g. `#004BC0`.                      |
| `data-header-title`    | Text in the chat window header. Default: `Ask Us`.                          |
| `data-initial-message` | Greeting shown before the user types. Default: `Hi there! How can I help you today?` |
| `data-toggle-label`    | Text of the bubble next to the closed chat icon. Default: `Need AI help?`.  |
| `data-base-url`        | Agents API origin. Default: `https://chat.iontone.com`.                     |

```html
<script
  src="https://cdn.jsdelivr.net/gh/DrChoon/iontone-chat@1.1.0/chat_widget.min.js"
  data-code="WORKSPACE_ID|AGENT_ID"
  data-theme-color="#004BC0"
  data-header-title="Ask Us"
  data-initial-message="Hi there! How can I help you today?"
  data-toggle-label="Need AI help?"
></script>
```

## How it connects

The widget talks to the production service at `https://chat.iontone.com`, which needs no authentication. The widget sends no credentials and works on any website.

## License

Licensed under the [Apache License, Version 2.0](LICENSE). Copyright 2026 aZaaS Pte Ltd, Singapore. See [NOTICE](NOTICE).

The widget bundles third-party open-source components. Their licenses and notices are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), and a short copyright banner is kept at the top of `chat_widget.min.js`.

## Trademark notice

The ionTone name and the ionTone logo mark are trademarks of **aZaaS Pte Ltd, Singapore**. The Apache License 2.0 covers the code only and does not grant any right to use these marks. Do not use them to imply endorsement or affiliation, and do not use them in a derived product or fork without written permission from aZaaS Pte Ltd.
