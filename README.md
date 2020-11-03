# VisuelKo
Just some folow up system

I need to read data from a Siemens PLC (Simatic S7, CPU: Win LCRTX F EC)


*** CODE I use***
import snap7.client as c
from snap7.util import *
from snap7.snap7types import *
import tkinter

plc = c.Client()
plc.connect('10.44.23.11', 0, 1)

reading = plc.read_area(0x84, 751, 22, 2)

print(reading)
print("test")



Error code:
b'CLI : function refused by CPU (Unknown error)'
Traceback (most recent call last):
  File "C:/Users/72215431/PycharmProjects/SiemensVisuel/SiementVisuel.py", line 9, in <module>
    reading = plc.read_area(0x83, 751, 22, 2)
  File "C:\Users\72215431\PycharmProjects\SiemensVisuel\venv\lib\site-packages\snap7\client.py", line 262, in read_area
    check_error(result, context="client")
  File "C:\Users\72215431\PycharmProjects\SiemensVisuel\venv\lib\site-packages\snap7\common.py", line 65, in check_error
    raise Snap7Exception(error)
snap7.snap7exceptions.Snap7Exception: b'CLI : function refused by CPU (Unknown error)'
