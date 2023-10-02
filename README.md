# AlarmClockWithGUI
import tkinter as tk
import time
import winsound

def set_alarm():
    alarm_time = entry.get()
    while True:
        current_time = time.strftime("%H:%M:%S")
        if current_time == alarm_time:
            play_alarm()
            break

def play_alarm():
    for _ in range(5):  # Play the alarm sound 5 times
        winsound.Beep(1000, 1000)  # Beep at 1000 Hz for 1 second
        time.sleep(1)

# Create the main window
root = tk.Tk()
root.title("Alarm Clock")

# Create a label
label = tk.Label(root, text="Enter alarm time (HH:MM:SS):")
label.pack()
# Create an entry field
entry = tk.Entry(root)
entry.pack()

# Create a button to set the alarm
set_button = tk.Button(root, text="Set Alarm", command=set_alarm)
set_button.pack()

# Run the main loop
root.mainloop()
