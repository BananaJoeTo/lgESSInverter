# lgess Binding

Please be adviced that this oh binding is still experimental!

![alt text][paperUIControl]
![alt text][paperUIConfiguration]
![alt text][paperUIConfigurationProperties]
![alt text][paperUIConfiguration1]
![alt text][paperUIConfiguration2]

## Supported Things

## Discovery

Not implemented right now!

## Binding Configuration

## Thing Configuration
```
Thing lginverter:D010KE1N211:YOUR_NAME "YOUR_NAME" @ "WHATEVER" [
    serial="YOUR_SERIAL",
    ip="YOUR_IP",
    password="YOUR_PASSWORD",
    version="V1",
    useCommonInformation=true,
    commonRefreshInternalInSeconds=10,
    useSystemInformation=true,
    systemRefreshInternalInSeconds=60,
    useBatteryInformation=false,
    batteryRefreshInternalInSeconds=30,
    useHomeInformation=true,
    homeRefreshInternalInSeconds=10,
    useNetworkInformation=true,
    networkRefreshInternalInSeconds=120
]
```
## Channels

Please have a look into `channel-group-type-[battery | common | home | network | systeminfo].xml` under `/src/main/resources/ESH-INF`

```
Number:Energy               [YOUR_PREFIX]_generation_today
                            "Energy generation today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#generationToday"}

Number:Energy               [YOUR_PREFIX]_generation_month
                            "Energy generation this month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#generationMonth"}


Number:ElectricCurrent      [YOUR_PREFIX]_pv_string_carport_ampere
                            "Current PV carport ampere [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString1Amperage"}

Number:Power                [YOUR_PREFIX]_pv_string_carport_power
                            "Current PV carport power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString1Power"}

Number:ElectricPotential    [YOUR_PREFIX]_pv_string_carport_voltage
                            "Current PV carport volt [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString1Voltage"}

Number:ElectricCurrent      [YOUR_PREFIX]_pv_string_house_ampere
                            "Current PV house ampere [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString2Amperage"}

Number:Power                [YOUR_PREFIX]_pv_string_house_power
                            "Current PV house power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString2Power"}

Number:ElectricPotential    [YOUR_PREFIX]_pv_string_house_voltage
                            "Current PV house volt [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvString2Voltage"}

Number:Power                [YOUR_PREFIX]_grid_active_power
                            "Grid active power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridActivePower"}

Number:ElectricCurrent      [YOUR_PREFIX]_grid_aphase
                            "Grid A-Phase [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridAPhase"}

Number:Energy               [YOUR_PREFIX]_grid_feedin_today
                            "Grid feed-in today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridFeedInToday"}

Number:Energy               [YOUR_PREFIX]_grid_consumption_today
                            "Grid consumption today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridConsumptionToday"}

Number:Energy               [YOUR_PREFIX]_grid_feedin_month
                            "Grid feed-in month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridFeedInMonth"}

Number:Energy               [YOUR_PREFIX]_grid_consumption_month
                            "Grid consumption month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#gridConsumptionMonth"}

Number:Power                [YOUR_PREFIX]_consumption_power
                            "Consumption power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#consumptionPower"}

Number:Energy               [YOUR_PREFIX]_consumption_today
                            "Consumption today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#consumptionToday"}

Number:Energy               [YOUR_PREFIX]_consumption_month
                            "Consumption month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#consumptionMonth"}

Number:Energy               [YOUR_PREFIX]_pv_consumption_today
                            "PV consumption today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvConsumptionToday"}

Number:Energy               [YOUR_PREFIX]_pv_consumption_month
                            "PV consumption month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#pvConsumptionMonth"}
Number:Dimensionless        [YOUR_PREFIX]_self_consumption_today
                            "Self consumption today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#selfConsumptionToday"}
Number:Mass                 [YOUR_PREFIX]_co2_reduction_month
                            "CO2 reduction month [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:common#co2ReductionMonth"}
Number:Power                [YOUR_PREFIX]_pms_ac_power_output
                            "PMS AC power output [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:systeminfo#pmsACPowerOutput"}
Number:Power                [YOUR_PREFIX]_statistic_pcs_pv_total_power
                            "STAT PCS PV total power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statPcsPVTotalPower"}
Number:Power                [YOUR_PREFIX]_statistic_ac_power_output
                            "STAT AC power output [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statACPowerOutput"}
Number:Power                [YOUR_PREFIX]_statistic_load_power
                            "STAT load power [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statLoadPower"}
Number:Dimensionless        [YOUR_PREFIX]_statistic_self_consumption_today
                            "STAT self consumption today [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statSelfConsumptionToday"}
Number:Energy               [YOUR_PREFIX]_statistic_pv_generation
                            "STAT PV generation [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statPVGeneration"}
Number:Energy               [YOUR_PREFIX]_statistic_grid_feed_in
                            "STAT grid feed-in [%.2f %unit%]"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#statGridFeedIn"}
Switch                      [YOUR_PREFIX]_is_direct_consumption
                            "Is direct consumption"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#isDirectConsumption"}
Switch                      [YOUR_PREFIX]_is_grid_feedin
                            "Is grid feed-in"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#isGridFeedIn"}
Switch                      [YOUR_PREFIX]_is_grid_consumption
                            "Is grid consumption"
                            {channel="lginverter:D010KE1N211:[YOUR_NAME]:home#isGridConsumption"}
```

## InfluxDB persistence




influxdb.persist
```
Strategies {
    everyMinute : "0 * * * * ?"
    everyFiveMinutes : "0 0/5 * * * ?"
    everyHour   : "0 0 * * * ?"
    everyDay    : "0 0 0 * * ?"
    default = everyChange
}

Items {
[YOUR_NAME]_generation_today, [YOUR_NAME]_generation_month,[YOUR_NAME]_pv_string_carport_ampere,[YOUR_NAME]_pv_string_carport_power,[YOUR_NAME]_pv_string_carport_voltage,[YOUR_NAME]_pv_string_house_ampere,[YOUR_NAME]_pv_string_house_power,[YOUR_NAME]_pv_string_house_voltage,[YOUR_NAME]_grid_active_power,[YOUR_NAME]_grid_aphase,[YOUR_NAME]_grid_feedin_today,[YOUR_NAME]_grid_consumption_today,[YOUR_NAME]_grid_feedin_month,[YOUR_NAME]_grid_consumption_month,[YOUR_NAME]_consumption_power,[YOUR_NAME]_consumption_today,[YOUR_NAME]_consumption_month,[YOUR_NAME]_pv_consumption_today,[YOUR_NAME]_pv_consumption_month,[YOUR_NAME]_self_consumption_today,[YOUR_NAME]_co2_reduction_month,[YOUR_NAME]_pms_ac_power_output,[YOUR_NAME]_statistic_pcs_pv_total_power,[YOUR_NAME]_statistic_ac_power_output,[YOUR_NAME]_statistic_load_power,[YOUR_NAME]_statistic_self_consumption_today,[YOUR_NAME]_statistic_pv_generation,[YOUR_NAME]_statistic_grid_feed_in,[YOUR_NAME]_is_direct_consumption,[YOUR_NAME]_is_grid_feedin,[YOUR_NAME]_is_grid_consumption : strategy = everyChange, everyFiveMinutes, everyHour
}
```

![alt text][grafana]

[grafana]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/grafana.png "Grafana"
[paperUIControl]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/paperUIControl.png "PaperUI #Control"
[paperUIConfiguration]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/paperUIConfiguration_0.png "PaperUI #Configuration"
[paperUIConfiguration1]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/paperUIConfiguration_1.png "PaperUI #Configuration"
[paperUIConfiguration2]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/paperUIConfiguration_2.png "PaperUI #Configuration"
[paperUIConfigurationProperties]: https://github.com/amocoma/lgESSInverter/blob/master/ressources/paperUIConfigurationProperties.png "PaperUI #Configuration"

