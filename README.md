# Station – Smoke/Air Quality Monitoring Simulator

A simple Python project that simulates a monitoring station which records readings (e.g. smoke or air-quality sensor values), validates them, and classifies them as **Safe** or triggers an **Alarm** based on defined thresholds.

## How It Works

The `station` class represents a single monitoring station with two thresholds:

- **`max_valid` (800):** Any reading above this is considered invalid/out of range and is **Rejected**.
- **`safe_smoke` (180):** Any valid reading above this triggers an **Alarm**; otherwise the reading is marked **Safe**.

Each reading passed to `run()` goes through this logic:

1. `check()` – validates whether the reading is within the acceptable range.
2. `act()` – if valid, decides whether the reading is safe or should raise an alarm.
3. `state()` – combines both checks to return the final status: `"Rejected"`, `"Alarm"`, or `"Safe"`.

## Features

- Stores a history of all readings (`self.readings`)
- Validates readings against a maximum allowed value
- Flags unsafe readings with an "Alarm" status
- Simple greeting method to identify the station

## Usage

```python
my_station = station("Remas' Station")
my_station.greet()               # Hi Remas' Station

my_station.add_readings(100)
my_station.add_readings(300)
my_station.add_readings(600)
my_station.add_readings(900)     # Above max_valid -> will be Rejected

my_station.run()                 # Prints each reading with its status
```

## Example Output

```
Hi Remas' Station
[100]
[100, 300]
[100, 300, 600]
[100, 300, 600, 900]
100 Safe
300 Alarm
600 Alarm
900 Rejected
```

## Requirements

- Python 3.x (no external libraries required)

## Running the Project

```bash
python Python_project.py
```

## Possible Improvements

- Make `max_valid` and `safe_smoke` configurable via the constructor instead of being hardcoded.
- Add input validation for non-numeric readings.

## License

Add a license of your choice (e.g., MIT) here.
