# TTS-Mimic Home Assistant integration
Mimic1 integration for Home assistant.


I love the ap voice for Mycroft (miss the sound of the Ubuntu podcast as well)
So i thought i'd try my hand a creating an integration to use Mimic1 as a Text To Speech integration for Home Assistant

For this to work you need to have Home assistant and Mimic running on the same machine.

To get Mimic either build mimic using instructions @ https://github.com/MycroftAI/mimic1
or
curl https://forslund.github.io/mycroft-desktop-repo/mycroft-desktop.gpg.key | sudo apt-key add - 2> /dev/null && echo "deb http://forslund.github.io/mycroft-desktop-repo bionic main" | sudo tee /etc/apt/sources.list.d/mycroft-desktop.list
apt-get update
apt-get install mimic

Copy the Mimic folder (with the files inside it) to your custom_component config folder in Home Assisant.
Mimic\
      tts.py
      manifest.json
      __init__.py

then in your configuration.yaml add the following lines.

```
tts:
   - platform: mimic
     target: ap
```

If you already have an entry to tts: then just add
```
   - platform: mimic
     target: ap
```

restart Home Assistant

Target is the voice to use, as i have not looked at how to pass a custom item from the config file yet.
