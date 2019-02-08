# Time

> SET_CLOCK_TIME - 0x47C3B5848C3E45D8 0x26F6AF14

void SET_CLOCK_TIME(int hour, int minute, int second)

```
SET_CLOCK_TIME(12, 34, 56);
```

> PAUSE_CLOCK - 0x4055E40BD2DBEC1D 0xB02D6124

void PAUSE_CLOCK(BOOL toggle)



> ADVANCE_CLOCK_TIME_TO - 0xC8CA9670B9D83B3B 0x57B8DA7C

void ADVANCE_CLOCK_TIME_TO(int hour, int minute, int second)



> ADD_TO_CLOCK_TIME - 0xD716F30D8C8980E2 0xCC40D20D

void ADD_TO_CLOCK_TIME(int hours, int minutes, int seconds)



> GET_CLOCK_HOURS - 0x25223CA6B4D20B7F 0x7EF8316F

int GET_CLOCK_HOURS()

```
Gets the current ingame hour, expressed without zeros. (09:34 will be represented as 9)
```

> GET_CLOCK_MINUTES - 0x13D2B8ADD79640F2 0x94AAC486

int GET_CLOCK_MINUTES()

```
Gets the current ingame clock minute.
```

> GET_CLOCK_SECONDS - 0x494E97C2EF27C470 0x099C927E

int GET_CLOCK_SECONDS()

```
Gets the current ingame clock second. Note that ingame clock seconds change really fast since a day in GTA is only 48 minutes in real life.
```

> SET_CLOCK_DATE - 0xB096419DF0D06CE7 0x96891C94

void SET_CLOCK_DATE(int day, int month, int year)



> GET_CLOCK_DAY_OF_WEEK - 0xD972E4BD7AEB235F 0x84E4A289

int GET_CLOCK_DAY_OF_WEEK()

```
Gets the current day of the week.

0: Sunday
1: Monday
2: Tuesday
3: Wednesday
4: Thursday
5: Friday
6: Saturday
```

> GET_CLOCK_DAY_OF_MONTH - 0x3D10BC92A4DB1D35 0xC7A5ACB7

int GET_CLOCK_DAY_OF_MONTH()



> GET_CLOCK_MONTH - 0xBBC72712E80257A1 0x3C48A3D5

int GET_CLOCK_MONTH()



> GET_CLOCK_YEAR - 0x961777E64BDAF717 0xB8BECF15

int GET_CLOCK_YEAR()



> GET_MILLISECONDS_PER_GAME_MINUTE - 0x2F8B4D1C595B11DB 0x3B74095C

int GET_MILLISECONDS_PER_GAME_MINUTE()



> GET_POSIX_TIME - 0xDA488F299A5B164E 0xE15A5281

void GET_POSIX_TIME(int* year, int* month, int* day, int* hour, int* minute, int* second)

```
Gets system time as year, month, day, hour, minute and second.

Example usage:

	int year;
	int month;
	int day;
	int hour;
	int minute;
	int second;

	TIME::GET_POSIX_TIME(&amp;year, &amp;month, &amp;day, &amp;hour, &amp;minute, &amp;second);

```

> _GET_LOCAL_TIME_GMT - 0x8117E09A19EEF4D3 

void _GET_LOCAL_TIME_GMT(int* year, int* month, int* day, int* hour, int* minute, int* second)

```
console hash: 0xC589CD7D = GET_UTC_TIME
gets current UTC time 
```

> GET_LOCAL_TIME - 0x50C7A99057A69748 0x124BCFA2

void GET_LOCAL_TIME(int* year, int* month, int* day, int* hour, int* minute, int* second)

```
Gets local system time as year, month, day, hour, minute and second.

Example usage:

int year;
int month;
int day;
int hour;
int minute;
int second;
or use std::tm struct

TIME::GET_LOCAL_TIME(&amp;year, &amp;month, &amp;day, &amp;hour, &amp;minute, &amp;second);

```

