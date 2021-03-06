---
title: List Sort Method
localeTitle: قائمة طريقة الفرز
---
## قائمة طريقة الفرز

قوائم الثعبان لديها المدمج في `sort()` طريقة بتعديل القائمة في مكان و `sorted()` المدمج في وظيفة أن يبني قائمة مفروزة جديدة من iterable.

list.sort (مفتاح = ... ، عكس = \[صواب / خطأ\])

### المعلمات

هناك نوعان من المعلمات الاختيارية لهذه الطريقة _key_ - يجب أن تكون قيمة الإدخال للمعلمة الرئيسية دالة تأخذ وسيطة واحدة وتقوم بإرجاع قيمة تستخدم لإجراء المقارنات لفرز العناصر في القائمة _عكس = \[قيمة\]_ _value = True_ : يقوم بفرز العناصر الموجودة في القائمة بترتيب تنازلي _value = False_ : يقوم بفرز العناصر الموجودة في القائمة بترتيب تصاعدي. هذا يعتبر القيمة الافتراضية. يرجى ملاحظة أن طريقة `sort()` لا تعيد أي قيمة. يعدل القائمة الأصلية.

### مثال للاستخدام

```py
a = [4, 2, 5, 3, 1]
a.sort()
print a # prints [1, 2, 3, 4, 5]

b = ['free', 'code', 'camp']
b.sort()
print b # prints ['camp', 'code', 'free']
``` 

النظر في مثال مع المعلمة **العكسية**

```py
a = [4, 2, 5, 3, 1]

#Sorts the list in descending order
a.sort(reverse=True)

print a # prints [5, 4, 3, 2, 1]
``` 

إذا كنت تريد فرز القائمة بناءً على وظيفتك الخاصة ، فاستخدم المعلمة **الرئيسية** . في ما يلي مثال لفرز السلاسل في القائمة حسب الطول ، بترتيب تصاعدي

```py
a = ["hello", "hi", "hey"]

#The built-in len() function is given as an input to key parameter to sort the strings by length
a.sort(key = len)

print a # prints ['hi', 'hey', 'hello']
``` 

في ما يلي مثال آخر ، حيث تحتوي القائمة على مجموعات (الاسم والعمر). يوضح الاستخدام أدناه كيفية فرز القائمة حسب العمر ، بترتيب تصاعدي.

```py
#Consider the second element in the tuple for sorting
>>> def compareByAge(element):
...     return element[1]

b = [('Adam', 20), ('Rahman', 30), ('Rahul', 25)]

#Sort the list by age
b.sort(key = compareByAge)

#Output
print b # prints [('Adam', 20), ('Rahul', 25), ('Rahman', 30)]
``` 

### أساسيات الفرز

إن الفرز التصاعدي البسيط سهل للغاية - ما عليك سوى استدعاء الدالة sort (). تقوم بإرجاع قائمة تم فرزها:

```python
>>> sorted([5, 2, 3, 1, 4])
[1, 2, 3, 4, 5]
``` 

يمكنك أيضا استخدام طريقة list.sort () من القائمة. يقوم بتعديل القائمة في المكان (ويعود بلا لتفادي الخلط). عادة ما يكون أقل ملاءمة من sorted () - ولكن إذا لم تكن في حاجة إلى القائمة الأصلية ، فستكون أكثر كفاءة.

```python
>>> a = [5, 2, 3, 1, 4]
>>> a.sort()
>>> a
[1, 2, 3, 4, 5]
``` 

اختلاف آخر هو أن طريقة list.sort () محددة فقط للقوائم. في المقابل ، تقبل الدالة sorted () أي أمر ممكن.

```python
>>> sorted({1: 'D', 2: 'B', 3: 'B', 4: 'E', 5: 'A'})
[1, 2, 3, 4, 5]
``` 

#### تفاصيل التنفيذ

إذا أراد المرء معرفة التفاصيل المتعلقة بتنفيذ وظيفة الفرز ، فالخوارزمية ، وتعقيد الوقت ، إلخ ، تشير [هنا](http://svn.python.org/projects/python/trunk/Objects/listsort.txt) . باختصار ، تستخدم وظيفة الفرز خوارزمية TimSort ، والتي وفقًا لمطوّري Python ، هي: -

> دمج ، مستقر ، طبيعي ، مدمج ، يسمى متواضع timsort (مهلا ، أنا كسبت ذلك ). لديها أداء خارق على العديد أنواع المصفوفات مرتبة جزئيا (أقل من مقارنات Lg (N!) المطلوبة، و عدد قليل من N-1) ، ولكن بسرعة كما في السابق بايثون معاينة للغاية الهجين في المصفوفات العشوائية.

#### الفرز () المعلمات

بشكل افتراضي ، لا يتطلب sort () أي معلمات إضافية. ومع ذلك ، فإنه يحتوي على معلمتين اختياريتين:

*   عكسي - إذا كان صحيحًا ، فسيتم عكس القائمة التي تم فرزها (أو فرزها حسب ترتيب تنازلي)
*   وظيفة رئيسية تعمل كمفتاح للمقارنة بين الفرز

#### معلومات اكثر:

يمكن العثور على مزيد من المعلومات حول `sort()` [هنا](https://docs.python.org/3/library/functions.html#sorted)

يمكن العثور على مزيد من المعلومات حول sort () وفرزها () [هنا](https://docs.python.org/3.6/tutorial/datastructures.html)

يمكن العثور على مزيد من المعلومات حول sort () وفرزها () [هنا](https://docs.python.org/3.6/tutorial/datastructures.html) .