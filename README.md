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
# Possible clean previous pip installation with Advanced SSH & Web Terminal. Disable “Protected mode” to allow container access
docker exec -it homeassistant bash
python3 -m site
python3 -c "import importlib; print(importlib.util.find_spec('PyViCare'))"
pip list | grep -i PyViCare
pip uninstall PyViCare
exit
# Restart HA
# Verify vicare Integration is marked with Red box
# Saying: Version 99.0.0 Custom integration that replaces a Core component
# Enable Debug logging. After restart, logs are found in Settings -> System -> Logs -> Download logs
```

This is a very usefull mapping
```
heating.power.consumption.summary.heating.currentDay : getPowerSummaryConsumptionHeatingCurrentDay : energy_summary_consumption_heating_currentday
heating.power.consumption.summary.heating.currentMonth : getPowerSummaryConsumptionHeatingCurrentMonth : energy_summary_consumption_heating_currentmonth
heating.power.consumption.summary.heating.currentYear : getPowerSummaryConsumptionHeatingCurrentYear : energy_summary_consumption_heating_currentyear
heating.power.consumption.summary.heating.lastSevenDays : getPowerSummaryConsumptionHeatingLastSevenDays : energy_summary_consumption_heating_lastsevendays

heating.power.consumption.summary.dhw.currentDay : getPowerSummaryConsumptionDomesticHotWaterCurrentDay : energy_dhw_summary_consumption_heating_currentday
heating.power.consumption.summary.dhw.currentMonth : getPowerSummaryConsumptionDomesticHotWaterCurrentMonth : energy_dhw_summary_consumption_heating_currentmonth
heating.power.consumption.summary.dhw.currentYear : getPowerSummaryConsumptionDomesticHotWaterCurrentYear : energy_dhw_summary_consumption_heating_currentyear
heating.power.consumption.summary.dhw.lastSevenDays : getPowerSummaryConsumptionDomesticHotWaterLastSevenDays : energy_summary_dhw_consumption_heating_lastsevendays

heating.power.consumption.heating.year[0] : getPowerConsumptionHeatingThisYear : energy_consumption_heating_this_year
heating.power.consumption.dhw.year[0] : getPowerConsumptionDomesticHotWaterThisYear : energy_consumption_dhw_this_year

heating.power.consumption.total.day[0] : getPowerConsumptionToday : power consumption today
heating.power.consumption.total.month[0] : getPowerConsumptionThisMonth : power consumption this month
heating.power.consumption.total.year[0] : getPowerConsumptionThisYear : power consumption this year
```