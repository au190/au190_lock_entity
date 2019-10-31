# Lovelace custom card for lock entity

This Lovelace custom card avoid toggling entities by mistake in lovelace.
This will display a normal toggle with a lock symbol in front of it.
Clicking the lock will make it go away and enable the toggle to be manouvered for five seconds.
https://github.com/au190/


#### Installation
The easiest way to install it is through [HACS (Home Assistant Community Store)](https://custom-components.github.io/hacs/),
search for <i>au190_lock_entity</i> and select it from Plugins.<br />
If you are not using HACS, you may download it form github and put it into $homeassistant_config_dir/www/community/.<br />

#### Lovelace UI configuration
If a list of users is supplied, only those users can disable the lock:
Note that this is not to be considered propper security. The lock can easily be circumvented.

```
resources:
  - type: js
    url: /local/custom_ui/au190_lock_entity/au190_lock_entity.js

---

cards:
  - entities:
      - entity: input_boolean.bedroomlamp
        secondary_info: last-changed
      - entity: input_boolean.bedroombiglamp
        secondary_info: last-changed
        type: 'custom:au190-lock-entity'
      - entity: input_boolean.bedroomtv
        secondary_info: last-changed
        type: 'custom:au190-lock-entity'
    show_header_toggle: false
    title: Bed Room
    type: entities
type: vertical-stack

```

Lovelace UI:<br />
<img src='https://raw.githubusercontent.com/au190/au190_lock_entity/master/1.png'/>



Updated HACS ready
Original: https://github.com/thomasloven/lovelace-toggle-lock-entity-row


