# Ummulqura
[[عربي]](readme.ar.md)

Alusus library for converting dates to and from Hijri using the algorithm of Ummulqura Calendar.

## Adding to the Project
You can add it to the project using the following statements:
```
import "Srl/Console";
import "Apm";
Apm.importFile("Alusus/Ummulqura", "Hijri.alusus");
```

## Example

```
import "Srl/Console";
import "Apm";
Apm.importFile("Alusus/Ummulqura", "Hijri.alusus");

use Srl;

// a function to test the conversion from Gregorian to Hijri.
func testGregorianToHijri {
    // define a variable to hold a date in Gregorian format.
    def data: Hijri.Date = Hijri.convertToHijri(2021, 11, 1);
    Console.print("%d-%d-%d\n", data.year, data.month, data.day); // should print 1443-3-26
}
testGregorianToHijri();

// a function to test the conversion from Hijri to Gregorian.
func testHijriToGregorian {
    // define a variable to hold a date in Hijri format.
    def data: Hijri.Date = Hijri.convertToGregorian(1443, 3, 26);
    Console.print("%d-%d-%d\n", data.year, data.month, data.day); // should print 2021-11-1
}
testHijriToGregorian();
```

## Functions and Types

### Type

```
class Date {
    def year: int;
    def month: int;
    def day: int;
    def monthLen: int;
}
```

This type represent the date, whether in Gregorian or Hijri.

`year` the number of the year.

`month` the number of the month, starting from 1.

`day` the number of the day, starting from 1.

`monthLen` the number of days in the month referred to by `month`.

### convertToHijri

```
func convertToHijri(year:int, month:int, day:int): Date;
```

This functions convert a date from Gregorian format to Hijri format.

`year` the number of the year.

`month` the number of the month, starting from 1.

`day` the number of the day, starting from 1.

Returns the date in Hijri format.

### convertToGregorian

```
func convertToGregorian(year:int, month:int, day:int): Date;
```

This functions convert a date from Hijri format to Gregorian format.

`year` the number of the year.

`month` the number of the month, starting from 1.

`day` the number of the day, starting from 1.

Returns the date in Gregorian format.
