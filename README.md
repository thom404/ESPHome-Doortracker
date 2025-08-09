# ToFDoorEntryTracker

A ESPHome project designed to count people passing through a doorway using two Time-of-Flight (ToF) sensors mounted on top of a door frame.

## Python virtual enviroment

### Create virtual enviroment

```bash
python3 -m venv .venv
```

### Activate virtual enviroment

```bash
source .venv/bin/activate
```

---

## ESPHome CLI sheet

### Update/install esp home

```bash
pip3 install esphome -U
```

### Compile & install/update firmware

```bash
esphome run thomas-room-door-tof.yaml
```

### Or alternatively run these commands individually

#### Compile firmware

```bash
esphome compile thomas-room-door-tof.yaml
```

#### install firmware

#### First install of firmware

on first install you have to manual flash the binary file in *PATH* ``.esphome\build\exampleProject\.pioenvs\exampleProject\firmware.bin`` to the esp device

#### compile firmware

```bash
esphome compile thomas-room-door-tof.yaml
```

#### upload firmware

```bash
esphome upload thomas-room-door-tof.yaml
```

---

## secret management

configure secrets in `secrets.yaml` file and bind the properties to the ``thomas-room-door-tof.yaml`` file

To Bind to the root secrets file you can add another secrets.yaml in the device folder and paste this into the file:

```yaml
<<: !include ../secrets.yaml
```

### Configure secret in `secrets.yaml` file

```yaml
secretProperty: "mysecret"
```

### Use secret in `xiaomi_bslamp2` file

```yaml
property: !secret secretProperty
```
