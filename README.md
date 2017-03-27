# MMM-CustomNotifications

This is a module for [MagicMirror²](https://magicmirror.builders/) to send custom notifications when notification received by other modules.

## Installation

In your terminal, go to your MagicMirror's Module folder:

````
cd ~/MagicMirror/modules
````

Clone this repository:
````
git clone https://github.com/hebestreit/MMM-CustomNotifications.git
````

## Using the module

To use this module, add it to the modules array in the `config/config.js` file:
````javascript
modules: [
    {
        module: 'MMM-CustomNotifications',
        config: {
            notifications: [
                {
                    notification: "RFID_DATA", // received notification key and payload
                    payload: "daniel",
                    dispatch: [ // dispatch following notifications if notification above received
                        {
                            notification: "CURRENT_PROFILE",
                            payload: "daniel",
                        },
                        {
                            notification: "SHOW_ALERT",
                            payload: {
                                type: "notification",
                                title: "Welcome",
                                message: "Hi Daniel!"
                            },
                        }
                    ]
                }
            ]
        }
    }
]
````

## Configuration options

The following properties can be configured:

| Option                     | Description
| -------------------------- | -----------
| `notifications`            | Use this property to register notifications with their payload and dispatch custom notifications.<br><br> **Possible values:** `array` <br> **Default value:** `[]`
