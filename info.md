配置方法如下：
```
switch:
  - platform: phicomm_dc1
    name: dc1_shufang
    hidden: true
    ip: 192.168.0.111
    ports: {'1':'dc1_shufang_s1','2':'dc1_shufang_s2','3':'dc1_shufang_s3'}
  - platform: phicomm_dc1
    name: dc1_huayuan
    hidden: true
    ip: 192.168.0.112
    ports: {'1':'dc1_huayuan_s1','2':'dc1_huayuan_s2','3':'dc1_huayuan_s3'}
  - platform: phicomm_dc1
    name: dc1_chufang
    hidden: true
    ip: 192.168.0.113
    ports: {'1':'dc1_chufang_s1','2':'dc1_chufang_s2','3':'dc1_chufang_s3'}

sensor:
  - platform: template
    sensors:
      dc1_shufang_v:
        friendly_name: 当前电压
        value_template: "{{ states.switch.dc1_shufang.attributes.v }}"
        unit_of_measurement: V
      dc1_shufang_p:
        friendly_name: 当前功率
        value_template: "{{ states.switch.dc1_shufang.attributes.p }}"
        unit_of_measurement: W

  - platform: template
    sensors:
      dc1_huayuan_v:
        friendly_name: 当前电压
        value_template: "{{ states.switch.dc1_huayuan.attributes.v }}"
        unit_of_measurement: V
      dc1_huayuan_p:
        friendly_name: 当前功率
        value_template: "{{ states.switch.dc1_huayuan.attributes.p }}"
        unit_of_measurement: W

  - platform: template
    sensors:
      dc1_chufang_v:
        friendly_name: 当前电压
        value_template: "{{ states.switch.dc1_chufang.attributes.v }}"
        unit_of_measurement: V
      dc1_chufang_p:
        friendly_name: 当前功率
        value_template: "{{ states.switch.dc1_chufang.attributes.p }}"
        unit_of_measurement: W


group:
  dc1_shufang:
    name: 书房DC1排插
    view: false
    entities:
      - sensor.dc1_shufang_v
      - sensor.dc1_shufang_p
      - sensor.dc1_shufang_totale
      - switch.dc1_shufang
      - switch.dc1_shufang_s1
      - switch.dc1_shufang_s2
      - switch.dc1_shufang_s3
  dc1_huayuan:
    name: 花园DC1排插
    view: false
    entities:
      - sensor.dc1_huayuan_v
      - sensor.dc1_huayuan_p
      - sensor.dc1_huayuan_totale
      - switch.dc1_huayuan
      - switch.dc1_huayuan_s1
      - switch.dc1_huayuan_s2
      - switch.dc1_huayuan_s3
  dc1_chufang:
    name: 厨房DC1排插
    view: false
    entities:
      - sensor.dc1_chufang_v
      - sensor.dc1_chufang_p
      - sensor.dc1_chufang_totale
      - switch.dc1_chufang
      - switch.dc1_chufang_s1
      - switch.dc1_chufang_s2
      - switch.dc1_chufang_s3

homeassistant:        
  customize:
    switch.dc1_shufang:
      friendly_name: 由你定
    switch.dc1_shufang_s1:
      friendly_name: 由你定
    switch.dc1_shufang_s2:
      friendly_name: 由你定
    switch.dc1_shufang_s3:
      friendly_name: 由你定
    switch.dc1_huayuan:
      friendly_name: 由你定
    switch.dc1_huayuan_s1:
      friendly_name: 由你定
    switch.dc1_huayuan_s2:
      friendly_name: 由你定
    switch.dc1_huayuan_s3:
      friendly_name: 由你定
    switch.dc1_chufang:
      friendly_name: 由你定
    switch.dc1_chufang_s1:
      friendly_name: 由你定
    switch.dc1_chufang_s2:
      friendly_name: 由你定
    switch.dc1_chufang_s3:
      friendly_name: 由你定
```
更多教程：http://1t.click/avAU | 电报  群：http://1t.click/avAX |
电报频道：http://1t.click/avBs | Twitter ：http://1t.click/avBg |
Facebook：http://1t.click/avBn |
