<h2> برنامج لاستخراج أسماء الرواة من الإسناد </h2>

برنامج بسيط مصمم بلغة بايثون وواجهة رسومية من مكتبة Tkinter

وظيفة البرنامج عزل أسماء الرواة عن في صيغ التحديث كـ حدثني عن قال...
والهدف من ذلك تشجير الإسناد من خلال موقع 
<h3>
 <a href="https://app.mindmup.com/">mindmup</a>
</h3>

<h2>طريقة الاستخدام</h2>


<h4>
● انسخ الإسناد من المكتبة الشاملة وضعه في البرنامج من خلال زر اللصق
</h4>

<img src="images/1.png">

<h4>
● انسخ النص الخارج من خلال زر النسخ، ثم الصقه بctrl v في عنصر اسم المصنف في موقع mindmup
</h4>

<img src="images/2.png">

<h4>
● تجربة عملية في استخدامه لتشجير بعض طرق حديث لا نكاح إلا بولي
</h4>
 
<img src="images/3.png">

<h2>ملاحظات</h2>

<h4>
● يجب وجود فاصلة (،) بعد اسم كل راو حتى يستطيع البرنامج فصل الرواة على الأسطر
</h4>

<h4>
● الكود في نسخة الواجهة غير الرسومية قد يعمل بشكل أفضل بسبب مشاكل في مكتبة Tkinter مع اللغة العربية، وبالإمكان استخدام البرنامج من خلال الموقع في الأسفل

</h4>

<h4><a href="https://ahmadakrabawe.github.io/isnadsite/">isnadsite</a></h4>

الكود المصدري:
```
x="""
 مُحَمَّدُ بْنُ بَشَّارٍ ، حَدَّثَنَا ابْنُ مَهْدِيٍّ ، حَدَّثَنَا سُفْيَانُ ، عَنْ أَبِي إِسْحَاقَ ، عَنْ أَبِي بُرْدَةَ ، عَنِ النَّبِيِّ
"""


char = ["َ", "ُ", "ِ", "ُ", "ْ","ٌ","ٍ", "ّ",":"]
for i in char:
  x = x.replace(i , "")

char2 = ["،"]
for i in char2:
  x = x.replace(i , "\n")

words = x.split(" ")
for word in words:
  if word in ["عن","حدثنا","أخبرنا","أن","أنه","يخبر","قال","أخبرني","قالا","يحدث","يخبر","سمع","نا","ثنا","أنا","أنبأنا","أنبأني","سمعت","نبأنا","نبأني","أنبا","نبا","قالوا","جميعا","حدثني","قالت"]:
    x = x.replace(word, "")

lines = x.split("\n")
lines = [line.strip() for line in lines]
lines_with_tabs = [("\t" * index) + line for index, line in enumerate(lines, start=0)]

x = "\n".join(lines_with_tabs)

print(x.strip())
```
