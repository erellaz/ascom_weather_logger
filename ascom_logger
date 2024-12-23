import win32com.client      #needed to load COM objects
import time
import datetime
import csv

logfile=r"C:\Users\guill\Desktop\weatherlog.csv"
#_______________________________________________________________
# ASCOM chooser allows to choose your mount in a popup window.

#Use chooser
# x = win32com.client.Dispatch("ASCOM.Utilities.Chooser")
# x.DeviceType = 'ObservingConditions'
# driverName=x.Choose("PegasusAstro UPBv3")
# weather=win32com.client.Dispatch(driverName)
#_______________________________________________________________
##OR use directly one of those
#weather = win32com.client.Dispatch("ASCOM.PegasusAstroUPBv3.ObservingConditions")
#weather = win32com.client.Dispatch("ASCOM.OpenWeatherMap.ObservingConditions")
weather = win32com.client.Dispatch("ASCOM.OCH.ObservingConditions")
print("You have choosen the following driver:",weather)
#_______________________________________________________________
weather.Connected=True
print("Connected?",weather.Connected)
print("Description",weather.Description)
print("Temperature",weather.Temperature)
print("Humidity",weather.Humidity)
print("Dew Point",weather.DewPoint)

with open(logfile, "w", newline="", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Time", "Temperature", "Humidity","CloudCover","WindSpeed"])
    f.flush()
    while True:
        measurment_time=datetime.datetime.now().strftime('%Y_%m_%d_%H_%M_%S')
        writer.writerow([measurment_time,weather.Temperature,weather.Humidity,weather.DewPoint,weather.CloudCover,weather.WindSpeed])
        f.flush()
        time.sleep(10)
