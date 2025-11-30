# vicare
home-assistant/core component in homeassistant/components/vicare

Ref
* https://developers.home-assistant.io/docs/core/entity/
* https://developers.home-assistant.io/docs/core/entity/sensor/
* https://github.com/openviess/PyViCare/?tab=readme-ov-file#testing
* https://developers.home-assistant.io/docs/creating_component_code_review/#1-external-requirements

# In Home Assistant

With [Advanced SSH & Web Terminal Update](https://github.com/hassio-addons/addon-ssh),

```bash
cd
cd homeassistant/custom_components
git clone -b core_issue_155695 https://github.com/tlinnet/vicare.git
# Possible clean previous deps
ls -la ~/.homeassistant/deps
ls -la ~/homeassistant/deps
# Restart HA
# Verify vicare Integration is marked with Red box
# Saying: Version 99.0.0 Custom integration that replaces a Core component
# Enable Debug logging. After restart, logs are found in Settings -> System -> Logs -> Download logs

```
