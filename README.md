# Cromag - Advanced Date and Time, No Monkeys

[![Build Status](https://secure.travis-ci.org/JerrySievert/cromagjs.png)](http://travis-ci.org/JerrySievert/cromagjs)

## In a Nutshell

- Drop in replacement for `Date`
- Adds tons of functionality
- Works in Node.js and in the browser
- 19 static methods, 69 instance methods
- No monkeys

## Using in the browser

    <script src="cromag.min.js"></script>
    <script>
      var now = new Cromag();
      console.log(now.toString());
    </script>

## Using in Node.js

    $ npm install cromag
    
    var Cromag = require('cromag');
    
    var now = new Cromag();
    console.log(now.toString());

# API

## Constructor

Creates a `Cromag` instance which allows you to work with dates and times.

    new Cromag()
    new Cromag(milliseconds)
    new Cromag(dateString)
    new Cromag(year, month, day [, hour, minute, second, millisecond ])

**milliseconds** - `Number` representing the number of milliseconds since `1 January 1970 00:00:00 UTC`

**dateString** - `String` value representing a date

**year** - `Number` representing the year

**month** - `Number` representing the month, `0` for `January` through `11` for `December`

**day** - `Number` representing the day of the month `1-31`

**hour** - `Number` representing the hour of the day `0-23`

**minute** - `Number` representing the minute of the hour `0-59`

**second** - `Number` representing the second of the minute `0-59`

**millisecond** - `Number` representing the millisecond `0-999`

## Static Methods

### now

Returns the number of `milliseconds` of the current time.  Equivalent to `+new Cromag()` or `new Cromag().valueOf()`

    Cromag.now()

### parse

Returns the number of `milliseconds` of the time passed as `dateString`.

    Cromag.parse(dateString)
    Cromag.parse(dateString, format)

**dateString** - `String` value representing a date

**format** - `String` representing a date format

### UTC

Returns the number of `milliseconds` representing universal time for the parameters provided.  These parameters are the same as the long form of the `constructor`.

    Cromag.UTC(year, month, day)
    Cromag.UTC(year, month, day, hour)
    Cromag.UTC(year, month, day, hour, minute)
    Cromag.UTC(year, month, day, hour, minute, second)
    Cromag.UTC(year, month, day, hour, minute, second, millisecond)

**year** - `Number` representing the year

**month** - `Number` representing the month, `0` for `January` through `11` for `December`

**day** - `Number` representing the day of the month `1-31`

**hour** - `Number` representing the hour of the day `0-23`

**minute** - `Number` representing the minute of the hour `0-59`

**second** - `Number` representing the second of the minute `0-59`

**millisecond** - `Number` representing the millisecond `0-999`

### today

Returns a new instance of `Cromag` set to `00:00:00` local time of the current day.

    Cromag.today()

### tomorrow

Returns a new instance of `Cromag` set to `00:00:00` local time of the next day.

    Cromag.tomorrow()

### yesterday

Returns a new instance of `Cromag` set to `00:00:00` local time of the previous day.

    Cromag.yesterday()

### validateDay

Returns `boolean` as to whether the date passed is valid.

    Cromag.validateDay(day, year, month)

**day** - `Number` representing the day of the month, `1-31`

**year** - `Number` representing the year

**month** - `Number` representing the month, `0-11`

### validateYear

Returns `boolean` as to whether the year passed is valid

    Cromag.validateYear(year)

**year** - `Number` representing the year

### validateMonth

Returns `boolean` as to whether the month passed is valid

    Cromag.validateMonth(month)

**month** - `Number` representing the month, `1-31`

### validateHour

Returns `boolean` as to whether the hour passed is valid

    Cromag.validateHour(hour)

**hour** - `Number` representing the hour, `0-23`

### validateMinute

Returns `boolean` as to whether the minute passed is valid

    Cromag.validateMinute(minute)

**minute** - `Number` representing the minute, `0-59`

### validateSecond

Returns `boolean` as to whether the second passed is valid

    Cromag.validateSecond(second)

**second** - `Number` representing the second, `0-59`

### validateMillisecond

Returns `boolean` as to whether the millisecond passed is valid

    Cromag.validateMillisecond(millisecond)

**millisecond** - `Number` representing the millisecond, `0-999`

### compare

Returns `-1` if `date1` is less than `date2`, `0` if they are the same, or `1` if `date1` is more recent than `date2`.

    Cromag.compare(date1, date2)

**date1** - `Cromag` first date/time to compare

**date2** - `Cromag` second date/time to compare

### equals

Returns `boolean` as to whether `date1` is equal to `date2`.

    Cromag.equals(date1, date2)

**date1** - `Cromag` first date/time to compare

**date2** - `Cromag` second date/time to compare

### getDayNumberFromName

Returns the `Number` representing the day passed in, `0-7`

    Cromag.getDayNumberFromName(name)

**name** - `String` day as 2 characters, 3 characters, or full day, `su/sun/sunday`

### getMonthNumberFromName

Returns the `Number` representing the month passed in, `0-11`

    Cromag.getMonthNumberFromName(name)

**name** - `String` day as 3 characters or full month, `jan/january`

### isLeapYear

Returns `boolean` as to whether the year passed is a leap year

    Cromag.isLeapYear(year)

**year** - `Number` year to check

### getDaysInMonth

Returns the `Number` of days in the month passed, `1-31`

    Cromag.getDaysInMonth(monthNumber)

**monthNumber** - `Number` of the month to check, `0-11`

## Instance Methods

### add

Adds and subtracts (in case of negative values) `time`

    d.add(offsets)

**offsets** - `Object` containing a mix of `milliseconds`, `seconds`, `minutes`, `hours`, `days`, `weeks`, `months`, and `years`

## addDays

Adds and subtracts the `Number` of days

    d.addDays(days)

**days** - `Number` of days

### addHours

Adds and subtracts the `Number` of hours

    d.addHours(hours)

**hours** - `Number` of hours

### addMilliseconds

Adds and subtracts the `Number` of milliseconds

    d.addMilliseconds(milliseconds)

**milliseconds** - `Number` of milliseconds

### addMinutes

Adds and subtracts the `Number` of minutes

    d.addMinutes(minutes)

**minutes** - `Number` of minutes

### addMonths

Adds and subtracts the `Number` of months

    d.addMonths(months)

**months** - `Number` of months

### addSeconds

Adds and subtracts the `Number` of seconds

    d.addMSeconds(seconds)

**seconds** - `Number` of seconds

### addYears

Adds and subtracts the `Number` of years

    d.addYears(years)

**years** - `Number` of years

### between

Returns `boolean` as to whether the date is between `date1` and `date2`

    d.between(date1, date2)

**date1** - `Cromag` first date/time to compare
**date2** - `Cromag` seconds date/time to compare

### clearTime

Sets the time to `00:00:00` in the current locale

    d.clearTime()

### clone

Returns a `Cromag` object set to the same date/time

    d.clone()

### compare

Returns `-1` if `date` is less than date/time, `0` if they are the same, or `1` if `date` is more recent

    d.compare(date)

**date** - `Cromag` date to compare to

### equals

Returns `boolean` as to whether the `date` passed is equal to the date/time

    d.equals(date)

**date** - `Cromag` date to compare to

### getDate

Returns the `Number` day of the month, `1-31`

    d.getDate()

### getDay

Returns the `Number` day of the week, `0-6`

    d.getDay()

### getDaysBetween

Returns the `Number` of days between the `date` passed and this instance

    d.getDaysBetween(date)

**date** - `Cromag` date to compare to

### getFullYear

Returns the `Number` full year, 4 digits

    d.getFullYear()

### getHours

Returns the `Number` of the hour, `0-23`

    d.getHours()

### getHoursBetween

Returns the `Number` of hours between the `date` passed and this instance

    d.getHoursBetween(date)

**date** - `Cromag` date to compare to

### getMilliseconds

Returns the `Number` of the milliseconds, `0-999`

    d.getMilliseconds()

### getMinutes

Returns the `Number` of the minutes, `0-59`

    d.getMinutes()

### getMinutesBetween

Returns the `Number` of minutes between the `date` passed and this instance

    d.getMinutesBetween(date)

**date** - `Cromag` date to compare to

### getMonth

Returns the `Number` of the month, `0-11`

    d.getMonth()

### getMonthAbbr

Returns the `String` representation of the abbreviated version of the month, `Jan-Dec`

    d.getMonthAbbr()

### getMonthName

Returns the `String` representation of the month, `January-December`

    d.getMonthName()

### getOrdinalNumber

Returns the `Number` of the year, `1-366`

    d.getOrdinalNumber()

### getSeconds

Returns the `Number` of the second, `0-59`

    d.getSeconds()

### getSecondsBetween

Returns the `Number` of seconds between the `date` passed and this instance

    d.getSecondsBetween(date)

**date** - `Cromag` date to compare to

### getTime

Returns the `Number` value of the milliseconds since the `epoch`, similar to `valueOf()`

    d.getTime()

### getTimezoneOffset

Returns the `Number` of minutes of the time-zone offset for the current locale

    d.getTimezoneOffset()

### getUTCDate

Returns the `Number` day of the month, universal time

    d.getUTCDate()

### getUTCDay

Returns the `Number` day of the week, universal time

    d.getUTCDay()

### getUTCFullYear

Returns the `Number` full year, universal time

    d.getUTCFullYear()

### getUTCHours

Returns the `Number` of the hour, universal time

    d.getUTCHours()

### getUTCMilliseconds

Returns the `Number` of the milliseconds, universal time

    d.getUTCMilliseconds()

### getUTCMinutes

Returns the `Number` of the minutes, universal time

    d.getUTCMinutes()

### getUTCMonth

Returns the `Number` of the month, universal time

    d.getUTCMonth()

### getUTCOffset

Returns a `String` representation of the UTC Offset

    d.getUTCOffset()

### getUTCSeconds

Returns the `Number` of the second, universal time

    d.getUTCSeconds()

### isAfter

Returns the `boolean` value of whether the date/time is after `date`

    d.isAfter(date)

**date** - `Cromag` representing a date/time

## isBefore

Returns the `boolean` value of whether the date/time is before `date`

    d.isBefore(date)

**date** - `Cromag` representing a date/time

### setDate

Sets the day of the month, `1-31`

    d.setDate(day)

**day** - `Number` representing the day of the month, `1-31`

### setFullYear

Sets the year

    d.setFullYear(year)

**year** - `Number` representing the year

### setHours

Sets the hour of the day, `0-23`

    d.setHours(hour)

**hour** - `Number` representing the hour of the day, `0-23`

### setMilliseconds

Sets the number of milliseconds

    d.setMilliseconds(milliseconds)

**milliseconds** - `Number` representing the number of milliseconds, `0-999`

### setMinutes

Sets the minutes of the hour, `0-59`

    d.setMinutes(minute)

**minute** - `Number` representing the minute of the hour, `0-59`

### setMonth

Sets the month of the year, `0-11`

    d.setMonth(month)

**month** - `Number` representing the month of the year, `0-11`

### setSeconds

Sets the seconds of the hour, `0-59`

    d.setSeconds(seconds)

**seconds** - `Number` representing the seconds of the hour, `0-59`

### setTime

Sets the date and time to the number of milliseconds since the `epoch`

    d.setTime(time)

**time** - `Number` representing the number of seconds since the `epoch`

### setTimeToNow

Sets the date/time to the current value

    d.setTimeToNow()

### setUTCDate

Sets the day of the month, `1-31`, universal time

    d.setUTCDate(day)

**day** - `Number` representing the day of the month, `1-31`

### setUTCFullYear

Sets the year, universal time

    d.setUTCFullYear(year)

**year** - `Number` representing the year

### setUTCHours

Sets the hour of the day, `0-23`, universal time

    d.setUTCHours(hour)

**hour** - `Number` representing the hour of the day, `0-23`

### setUTCMilliseconds

Sets the number of milliseconds, universal time

    d.setUTCMilliseconds(milliseconds)

**milliseconds** - `Number` representing the number of milliseconds, `0-999`

### setUTCMinutes

Sets the minutes of the hour, `0-59`, universal time

    d.setUTCMinutes(minute)

**minute** - `Number` representing the minute of the hour, `0-59`

### setUTCMonth

Sets the month of the year, `0-11`, universal time

    d.setUTCMonth(month)

**month** - `Number` representing the month of the year, `0-11`

### setUTCSeconds

Sets the seconds of the hour, `0-59`, universal time

    d.setUTCSeconds(seconds)

**seconds** - `Number` representing the seconds of the hour, `0-59`

### toCLFString

Returns a `String` representation of this in an Apache CLF format

    d.toCLFString()

### toDateString

Returns the `date` portion of the date/time as a `String`

    d.toDateString()

### toDBString

Returns a `String` representation of this in a `YYYY-MM-DD HH24:MI:SS` format

    d.toDBString()

### toFormat

Returns a `String` representation of this formatted with the format passed

    d.toFormat(format)

**format** - `String` representing the format, including `MM`, `DD`, `YYYY`, `YY`, `MI`, `SS`, `HH`, `HH24`

### toISOString

Returns the date/time in ISO 8601 Extended Format as a `String`

    d.toISOString()

### toJSON

Returns the `JSON` string representation of the date/time as a `String`

    d.toJSON()

### toLocaleDateString

Returns the `String` representation of the `date` in the current locale

    d.toLocaleDateString()

### toLocaleString

Returns the `String` representation of the `date` and `time` in the current locale

    d.toLocaleString()

### toLocaleTimeString

Returns the `String` representation of the `time` in the current locale

    d.toLocaleTimeString()

### toString

Returns the `String` representation of the `date` and `time` in the current locale

    d.toString()

### toTimeString

Returns the `String` representation of the `time` in the current locale

    d.toTimeString()

### toUTCString

Returns the `String` representation of the `date` and `time` in universal time

    d.toUTCString()

### valueOf

Returns the `Number` of milliseconds since the `epoch`

    d.valueOf()

### toYMD

Returns a `String` representation of `year`, `month`, and `day` with `value` as the separator

    d.toYMD(value)

**value** - `String` representing a separator
