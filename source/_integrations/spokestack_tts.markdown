---
title: "Spokestack Text-to-Speech (TTS)"
description: "Spokestack TTS platform documentation"
ha_release: "0.38"
ha_category: Text-to-speech
ha_iot_class: "Cloud Push"
ha_codeowners:
  - '@spokestack'
  - '@will-rice'
  - '@space-pope'
ha_domain: spokestack_tts
---

[Spokestack](https://www.spokestack.io/) offers open-source libraries for adding a voice interface to _anything_. `spokestack_tts` is a text-to-speech platform to read text with natural-sounding custom voices. Usage of TTS with the default voice is free, but the API requires authentication.

If you already have an account, [log in](https://www.spokestack.io/login), otherwise you will need to [create](https://www.spokestack.io/create) one. The credentials can be found in your [account settings](https://www.spokestack.io/account/settings).

## Configuration

To get started, add the following lines to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
tts:
  - platform: spokestack_tts
    key_id: "YOUR_API_KEY"
    key_secret: "YOUR_API_SECRET"
```

{% configuration %}
key_id:
  description: Spokestack API key ID
  required: true
  type: string
  default: None

key_secret:
  description: Spokestack API secret key
  required: true
  type: string
  default: None

language:
  description: The language to use. We only support English right now, but we are expanding support
  required: false
  type: string
  default: "`en-US`"

voice:
  description: Voice used for synthesis. Only the default voice is available for now, but more are on the way.
  required: false
  type: string
  default: "`demo-male`"

mode:
  description: Synthesis mode. The supported modes are `text`, `ssml`, and `markdown`
  required: false
  type: string
  default: 'text'
{% endconfiguration %}

## Full configuration example

A full configuration sample including optional variables:

```yaml
# Example configuration.yaml entry
tts:
  - platform: spokestack_tts
    key_id: "YOUR_API_KEY"
    key_secret: "YOUR_API_SECRET"
    language: "en-US"
    voice: "demo-male"
    mode: text
```
