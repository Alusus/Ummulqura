# Ummulqura
[[English]](README.md)

<div dir=rtl>

مكتبة أسس للتحويل بين التاريخين الميلادي والهجري باستخدام خوارزمية تقويم أم القرى.

## إضافة المكتبة للمشروع

يمكن إضافتها للمشروع باستخدام الجمل التالية:

```
اشمل "مـتم/طـرفية"؛
اشمل "مـحا"؛
مـحا.اشمل_حزمة("Alusus/Ummulqura@0.1"، "هـجري.أسس")؛
```

<div dir=ltr>

```
import "Srl/Console";
import "Apm";
Apm.importPackage("Alusus/Ummulqura@0.1", "Hijri.alusus");
```

</div>

## مثال

```
اشمل "مـتم/طـرفية"؛
اشمل "مـحا"؛
مـحا.اشمل_حزمة("Alusus/Ummulqura@0.1"، "هـجري.أسس")؛

استخدم مـتم؛

// دالة لاختبار التحويل من التاريخ الميلادي إلى الهجري
دالة اختبر_من_ميلادي_إلى_هجري {
    // نقوم بتعريف متغير من نمط تاريخ
    // هذا المتغير سيحمل قيمة التحويل للتاريخ الميلادي
    عرف تاريخ: هـجري.تـاريخ = هـجري.حول_لهجري(2012,11,1)؛
    طـرفية.اطبع("%d-%d-%d\n", تاريخ.السنة, تاريخ.الشهر, تاريخ.اليوم)؛
}
اختبر_من_ميلادي_إلى_هجري()؛

// دالة لاختبار التحويل من التاريخ الهجري إلى الميلادي
دالة اختبر_من_هجري_إلى_ميلادي {
    // نقوم بتعريف متغير من نمط تاريخ
    // هذا المتغير سيحمل قيمة التحويل للتاريخ الهجري
    عرف تاريخ: هـجري.تـاريخ = هـجري.حول_لميلادي(1443,3,26)؛
    طـرفية.اطبع("%d-%d-%d\n", تاريخ.السنة, تاريخ.الشهر, تاريخ.اليوم)؛
}
اختبر_من_هجري_إلى_ميلادي()؛
```

<div dir=ltr>

```
import "Srl/Console";
import "Apm";
Apm.importPackage("Alusus/Ummulqura@0.1", "Hijri.alusus");

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

</div>

## الأصناف والدوال

### تـاريخ (Date)

```
صنف تـاريخ {
    عرف السنة: صـحيح؛
    عرف الشهر: صـحيح؛
    عرف اليوم: صـحيح؛
    عرف طول_الشهر: صـحيح؛
}
```

<div dir=ltr>

```
class Date {
    def year: int;
    def month: int;
    def day: int;
    def monthLen: int;
}
```

</div>

يمثل هذا النوع تاريخًا، سواء بالميلادي أو الهجري.

#### السنة (year)

```
عرف السنة: صـحيح؛
```

<div dir=ltr>

```
def year: int;
```

</div>

رقم السنة.

#### الشهر (month)

```
عرف الشهر: صـحيح؛
```

<div dir=ltr>

```
def month: int;
```

</div>

رقم الشهر، بدءاً من 1.

#### اليوم (day)

```
عرف اليوم: صـحيح؛
```

<div dir=ltr>

```
def day: int;
```

</div>

رقم اليوم، بدءاً من 1.

#### طول_الشهر (monthLen)

```
عرف طول_الشهر: صـحيح؛
```

<div dir=ltr>

```
def monthLen: int;
```

</div>

عدد أيام الشهر المشار له بـ`الشهر`.

### حول_لهجري (convertToHijri)

```
دالة حول_لهجري(سنة: صـحيح، شهر: صـحيح، يوم: صـحيح): تـاريخ؛
```

<div dir=ltr>

```
func convertToHijri(year:int, month:int, day:int): Date;
```

</div>

تقوم هذه الدالة بتحويل تاريخ ميلادي معطى إلى تاريخ هجري.

* `سنة` (`year`): رقم السنة.
* `شهر` (`month`): رقم الشهر، بدءاً من 1.
* `يوم` (`day`): رقم اليوم، بدءاً من 1.

تعيد هذه الدالة نفس التاريخ ولكن بالهجري.

### حول_لميلادي (convertToGregorian)

```
دالة حول_لميلادي(سنة: صـحيح، شهر: صـحيح، يوم: صـحيح): تـاريخ؛
```

<div dir=ltr>

```
func convertToGregorian(year:int, month:int, day:int): Date;
```

</div>

تقوم هذه الدالة بتحويل تاريخ هجري معطى إلى تاريخ ميلادي.

* `سنة` (`year`): رقم السنة.
* `شهر` (`month`): رقم الشهر، بدءاً من 1.
* `يوم` (`day`): رقم اليوم، بدءاً من 1.

تعيد هذه الدالة نفس التاريخ ولكن بالميلادي.

---

## الرخصة

هذا المشروع مرخص بموجب رخصة غنو العمومية الصغرى الإصدار 3.0 (LGPL-3.0). راجع ملفات `COPYING` و `COPYING.LESSER` للحصول على التفاصيل.

</div>
