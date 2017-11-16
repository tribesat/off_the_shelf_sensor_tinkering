# 13Nov2017

## Light and Temp sensesing

These sensors are connected to an arudino uno with a logic shifter

TSL2561 I2C address (adr floating): 0x39

* Works at this address alone
* does not work when VEML 6070 and TMP102 also in circuit

TMP102 I2C address (adr low): 0x48

* Everything with this works as expected

VEML 6070 (no adr change possible): 0x39 AND 0x38

* You need two I2C address to read from this, this is weird but it's the way it is
* Works with TMP102 and TSL2561 in circuit
* I2C conflict with the TSL, this one seems to win

TSL2561 I2C (adr low): 0x29

* I went low to get past the I2C conflict 
* High would change it to 0x49, I didn't do this because I'm scared of confilicts with the TMP102
* Now works with full circuit

## MPU9250

This sensor has been giving me problems, right now it is connected to a 8Mhz, 3.3V arduino pro mini. I did this to get rid of the logic shifter as a variable, and because the code I'm trying to use was developed on this system

I2C scanner shows 0x0C and 0x68

* We expect two I2C address from the baord because the accelerometer/gyro and magnetometer are independent (sorta)

Upload "MPU9250BasicAHRS_I2C" sketch to board, following result:

```
MPU9250 I AM 0x71 I should be 0x71
MPU9250 is online...
BHW::ii = 0
BHW::ii = 1
BHW::ii = 2
BHW::ii = 3
BHW::ii = 4
BHW::ii = 5
BHW::ii = 6
BHW::ii = 7
BHW::ii = 8
BHW::ii = 9
BHW::ii = 10
BHW::ii = 11
BHW::ii = 12
BHW::ii = 13
BHW::ii = 14
BHW::ii = 15
BHW::ii = 16
BHW::ii = 17
BHW::ii = 18
BHW::ii = 19
BHW::ii = 20
BHW::ii = 21
BHW::ii = 22
BHW::ii = 23
BHW::ii = 24
BHW::ii = 25
BHW::ii = 26
BHW::ii = 27
BHW::ii = 28
BHW::ii = 29
BHW::ii = 30
BHW::ii = 31
BHW::ii = 32
BHW::ii = 33
BHW::ii = 34
BHW::ii = 35
BHW::ii = 36
BHW::ii = 37
BHW::ii = 38
BHW::ii = 39
BHW::ii = 40
BHW::ii = 41
BHW::ii = 42
BHW::ii = 43
BHW::ii = 44
BHW::ii = 45
BHW::ii = 46
BHW::ii = 47
BHW::ii = 48
BHW::ii = 49
BHW::ii = 50
BHW::ii = 51
BHW::ii = 52
BHW::ii = 53
BHW::ii = 54
BHW::ii = 55
BHW::ii = 56
BHW::ii = 57
BHW::ii = 58
BHW::ii = 59
BHW::ii = 60
BHW::ii = 61
BHW::ii = 62
BHW::ii = 63
BHW::ii = 64
BHW::ii = 65
BHW::ii = 66
BHW::ii = 67
BHW::ii = 68
BHW::ii = 69
BHW::ii = 70
BHW::ii = 71
BHW::ii = 72
BHW::ii = 73
BHW::ii = 74
BHW::ii = 75
BHW::ii = 76
BHW::ii = 77
BHW::ii = 78
BHW::ii = 79
BHW::ii = 80
BHW::ii = 81
BHW::ii = 82
BHW::ii = 83
BHW::ii = 84
BHW::ii = 85
BHW::ii = 86
BHW::ii = 87
BHW::ii = 88
BHW::ii = 89
BHW::ii = 90
BHW::ii = 91
BHW::ii = 92
BHW::ii = 93
BHW::ii = 94
BHW::ii = 95
BHW::ii = 96
BHW::ii = 97
BHW::ii = 98
BHW::ii = 99
BHW::ii = 100
BHW::ii = 101
BHW::ii = 102
BHW::ii = 103
BHW::ii = 104
BHW::ii = 105
BHW::ii = 106
BHW::ii = 107
BHW::ii = 108
BHW::ii = 109
BHW::ii = 110
BHW::ii = 111
BHW::ii = 112
BHW::ii = 113
BHW::ii = 114
BHW::ii = 115
BHW::ii = 116
BHW::ii = 117
BHW::ii = 118
BHW::ii = 119
BHW::ii = 120
BHW::ii = 121
BHW::ii = 122
BHW::ii = 123
BHW::ii = 124
BHW::ii = 125
BHW::ii = 126
BHW::ii = 127
BHW::ii = 128
BHW::ii = 129
BHW::ii = 130
BHW::ii = 131
BHW::ii = 132
BHW::ii = 133
BHW::ii = 134
BHW::ii = 135
BHW::ii = 136
BHW::ii = 137
BHW::ii = 138
BHW::ii = 139
BHW::ii = 140
BHW::ii = 141
BHW::ii = 142
BHW::ii = 143
BHW::ii = 144
BHW::ii = 145
BHW::ii = 146
BHW::ii = 147
BHW::ii = 148
BHW::ii = 149
BHW::ii = 150
BHW::ii = 151
BHW::ii = 152
BHW::ii = 153
BHW::ii = 154
BHW::ii = 155
BHW::ii = 156
BHW::ii = 157
BHW::ii = 158
BHW::ii = 159
BHW::ii = 160
BHW::ii = 161
BHW::ii = 162
BHW::ii = 163
BHW::ii = 164
BHW::ii = 165
BHW::ii = 166
BHW::ii = 167
BHW::ii = 168
BHW::ii = 169
BHW::ii = 170
BHW::ii = 171
BHW::ii = 172
BHW::ii = 173
BHW::ii = 174
BHW::ii = 175
BHW::ii = 176
BHW::ii = 177
BHW::ii = 178
BHW::ii = 179
BHW::ii = 180
BHW::ii = 181
BHW::ii = 182
BHW::ii = 183
BHW::ii = 184
BHW::ii = 185
BHW::ii = 186
BHW::ii = 187
BHW::ii = 188
BHW::ii = 189
BHW::ii = 190
BHW::ii = 191
BHW::ii = 192
BHW::ii = 193
BHW::ii = 194
BHW::ii = 195
BHW::ii = 196
BHW::ii = 197
BHW::ii = 198
BHW::ii = 199
x-axis self test: acceleration trim within : 2.0% of factory value
y-axis self test: acceleration trim within : -0.1% of factory value
z-axis self test: acceleration trim within : 2.7% of factory value
x-axis self test: gyration trim within : -5.0% of factory value
y-axis self test: gyration trim within : -1.0% of factory value
z-axis self test: gyration trim within : 0.3% of factory value
MPU9250 initialized for active data mode....
AK8963 I AM 0xFF I should be 0x48
Communication failed, abort!
```

