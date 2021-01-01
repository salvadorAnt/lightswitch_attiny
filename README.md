# lightswitch_attiny
Basic sketch for an Attiny85 circuit with SG90 servo and TSOP4838 IR Receiver used to turn on a light switch.
 * Uses ATTinycore (https://github.com/SpenceKonde/ATTinyCore) and its built-in Attiny_servo library
 * Uses IRMP (https://github.com/ukw100/IRMP) for Pin-change Interrupt-based IR receiving.
 
Notes
 - Attiny85 powered by 2xAA batteries
 - Servo powered by 4xAA batteries
 - Uses IRLZ44N low-side Mosfet to switch on servo power
 - Attiny85 sleeps (Power Down) after 5 secs of inactivity, and also switches off Mosfet gate; woken on Pin Change Interrupt (IR signal) and powers on Mosfet gate for Servo
 - In my limited tests with DMM on breadboard, getting this current draw:
  -- Attiny85 circuit: ~4.2 mA (Awake) and 235uA (asleep) 
  -- Servo: ~5mA (Idle) and 95uA (Mosfet off)
