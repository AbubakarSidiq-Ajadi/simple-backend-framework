
Sentinel: Android Stealth Security App
=======================================

Sentinel is a powerful Android security tool designed for remote control and stealth monitoring. It operates without a user interface and can be controlled via SMS, Firebase, or ADB commands.

Features
--------
- Lock the device remotely (via SMS, Firebase, ADB)
- Track device location (GPS required)
- Ring phone at maximum volume
- Take pictures (front/back cameras)
- Record audio from microphone
- Factory reset the device (if admin enabled)

Control Methods
---------------
1. **SMS Commands**
   - Send an SMS from another phone to the device with commands like:
     - `LOCK`, `TRACK`, `SHUTDOWN`, `PICF`, `PICB`, `RECORD`, `WIPE`

2. **Firebase Cloud Messaging (FCM)**
   - Send a remote data message with a command key. Example JSON:
     ```json
     {
       "data": {
         "command": "LOCK"
       }
     }
     ```

3. **ADB Command Triggers**
   - Use ADB to simulate intents and test features directly.

Permissions Required
--------------------
- RECEIVE_SMS, SEND_SMS
- ACCESS_FINE_LOCATION
- CAMERA, RECORD_AUDIO
- BIND_DEVICE_ADMIN (must be granted manually)
- FOREGROUND_SERVICE
- READ/WRITE_EXTERNAL_STORAGE (with scoped storage fallback)

Setup
-----
1. Connect the app to Firebase and add `google-services.json`.
2. Compile and install the APK.
3. Enable Device Admin permissions.
4. Control the app via SMS or Firebase commands.

Important Notes
---------------
- No UI is provided; control is silent and stealthy.
- Fake shutdown is fully screen-blocking unless WAKE is triggered.
- Location, camera, and audio features must be granted permissions on install.

License
-------
This project is for educational and testing purposes only. Use responsibly.
