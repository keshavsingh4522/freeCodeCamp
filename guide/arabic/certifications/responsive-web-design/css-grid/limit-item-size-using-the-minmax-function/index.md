---
title: Limit Item Size Using the minmax Function ##
localeTitle: الحد الأقصى لحجم العنصر باستخدام الدالة minmax ##
---
إن استخدام الدالة _minmax_ بالاقتران مع وظيفة _التكرار_ هو بالضبط ما يصفه هذا التحدي ، ولكن هذا لم يكن واضحًا في حد ذاته بالنسبة لي في البداية. تتمثل طريقة تمرير هذا التحدي في إزالة قيمة **الحد الأقصى للعرض** داخل دالة _التكرار_ ، ثم إضافة الدالة _minmax_ بدلاً من قيمة _تكرار_ **أقصى عرض** .

في ما يلي **مثال** على ما يبدو مثل استخدام طريقة ما _قبل_ _وبعد_ :

### قبل

 `    grid-template-columns: repeat(3, 1fr); 
` 

### بعد

 `    grid-template-columns: repeat(3, minmax(50px, 2fr)); 
` 


### مصادر

[شبكة مطوري موزيلا](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax)