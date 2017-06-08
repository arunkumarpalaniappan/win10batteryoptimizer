## Battery Optimizer

An easy-to-use Python library for maintaing the optimal battery life for windows 10.

[https://pypi.python.org/pypi?:action=display&name=win10batteryoptimizer&version=0.1.1](https://pypi.python.org/pypi?:action=display&name=win10batteryoptimizer&version=0.1.1)


## Installation

```
pip install win10batteryoptimizer
```

## Requirements

### Installation of pywin32
```
pypiwin32
setuptools
time
win10toast
```

## Example

```
import time
from win10batteryoptimizer import Notifier
notifier = Notifier()
    battery_percent = notifier.get_battery_level()
    battery_line_status = notifier.get_battery_line()
    while ((int)(battery_percent>80) and (int)(battery_line_status)):
        notifier.create_plug_out_toast()
        time.sleep(600)
    while ((int)(battery_percent<40) and (int)(battery_line_status)==0):
        notifier.create_plug_in_toast()
        time.sleep(600)
    while ((int)(battery_percent)>39 and (int)(battery_percent)<81):
        time.sleep(600)
```