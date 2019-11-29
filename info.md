配置方法如下：
```
switch:
  - platform: phicomm_dc1_switch
    name: dc1_1
    ip: 192.168.2.90
    ports: {'1':'dc1_1_s1','2':'dc1_1_s2','3':'dc1_1_s3'}

sensor:
  - platform: template
    sensors:
      dc1_1_v:
        friendly_name: 当前电压
        value_template: "{{ states.switch.dc1_1.attributes.v }}"
        unit_of_measurement: V
      dc1_1_p:
        friendly_name: 当前功率
        value_template: "{{ states.switch.dc1_1.attributes.p }}"
        unit_of_measurement: W


group:
  dc1_1:
    name: 排插1
    view: false
    entities:
      - sensor.dc1_1_v
      - sensor.dc1_1_p
      - switch.dc1_1
      - switch.dc1_1_s1
      - switch.dc1_1_s2
      - switch.dc1_1_s3

homeassistant:        
  customize:
    switch.dc1_1:
      friendly_name: 电源开关
    switch.dc1_1_s1:
      friendly_name: 插口1
    switch.dc1_1_s2:
      friendly_name: 插口2
    switch.dc1_1_s3:
      friendly_name: 插口3
```
更多教程：http://1t.click/avAU | 电报  群：http://1t.click/avAX
电报频道：http://1t.click/avBs | Twitter ：http://1t.click/avBg
Facebook：http://1t.click/avBn |
