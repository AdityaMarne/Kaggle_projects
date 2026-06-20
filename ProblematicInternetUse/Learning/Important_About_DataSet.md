Two elements of this study are being used for this competition: physical activity data (wrist-worn accelerometer data, fitness assessments and questionnaires) and internet usage behavior data.

A **wrist-worn accelerometer dataset** contains motion data collected from an accelerometer sensor worn on the wrist (often in a smartwatch, fitness band, or research device like ActiGraph devices).

### Core data it usually contains

#### 1. Raw acceleration signals (main part)

Usually measured along **3 axes**:

* **X-axis** → side-to-side wrist movement
* **Y-axis** → up-down wrist movement
* **Z-axis** → forward-backward movement

Values are often in **g (gravity units)** or **m/s²**.

Example:

| Timestamp | X    | Y     | Z    |
| --------- | ---- | ----- | ---- |
| 10:00:01  | 0.12 | -0.45 | 1.02 |
| 10:00:02  | 0.18 | -0.39 | 0.98 |

---

#### 2. Timestamp / Time series

Each reading has:

* Date
* Time
* Sampling frequency (for example 30 Hz, 50 Hz, 100 Hz)

**50 Hz** means 50 measurements per second.

---

#### 3. Derived features (sometimes precomputed)

Researchers often add features like:

* Mean acceleration
* Standard deviation
* Signal magnitude:

SMA = |x| + |y| + |z|

* Vector magnitude:

VM = \sqrt{x^2+y^2+z^2}

* Step counts
* Energy expenditure estimates
* Activity counts

The goal of this competition is to predict from this data a participant's Severity Impairment Index (sii), a standard measure of problematic internet use.

The competition data is compiled into two sources, parquet files containing the accelerometer (actigraphy) series and csv files containing the remaining tabular data.


Lux Measurements
Lux, or ambient light, is measured by ActiGraph’s ActiSleep, ActiSleep+, ActiTrainer, GT3X+, and our new wireless wGT3X+ and wActiSleep+ devices. Ambient light may affect subject sleeping habits and thus is a useful tool in analyzing circadian rhythms and sleeping patterns. Lux data is stored once per epoch. For GT3X+/ActiSleep+/wGT3X+/wActiSleep+ devices, Lux data is stored once per second. When converting a GT3X+ raw file into an accumulated *.agd format with epoch lengths greater than one second, the lux values for that epoch are averaged. 

The ActiTrainer, GT3X+, and wGT3X+ devices are capped at a maximum value of 2500; the ActiSleep, ActiSleep+, and wActiSleep+ are capped at 6000:

The wGT3X-BT device is capped at a maximum lux value of 5000 and the wActiSleep-BT is capped at 6500. The new GT9X Link device does not have a lux sensor.

An estimate of industry accepted lux values is shown below:

Lux Level                          Interpretation Comparison
1                                   Twilight
5                                   Minimal Street Lighting
10                                  Sunset
50                                  Family Living Room
80                                  Hallway 
100                                 Very Dark Overcast Day 
320 - 500                           Office Lighting 
400                                 Sunrise/Sunset 
1,000                               Overcast Day 
10,000-25,000                       Full Daylight 
32,000-130,000                      Direct Sunlight
