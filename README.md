# VFCashPython
مكتبة استلام مدفوعات تلقائى من فودافون كاش

قم بوضع ملف VFCash.py مع ملفاتك و قم باستدعائة ب :
```python

from VFCash import *

```

- طريق فحص عملية الدفع إذا اكتمل : 
```python

cash = VFCash("هنا معرفك")
response = cash.checkPayment("phone","amount","callback link","user id")

```
- قم بوضع معرفك فى الكود (احصل عليه من التطبيق) .
- رابط العودة او callback link: هو رابط يتم ارسال طلب اليه عن طريق POST فى هذه الحالة . و يستخدم للتأكد من أن عملية الدفع تمت بنجاح . يتم ارسال معه عدده مفاتيح عن طريق GET مثل key و status و extra .
- ويحتوي متغير response على مفتاحين status و message . تكون قيمة status هى success عند نجاح الطلب و عندها يرسل طلب ل callback و تكون قيمة status هى fail عند فشل الطلب و عندها لا يرسل طلب ل callback و تحتوي مفتاح message على سبب الفشل . او رسالة النجاح .
  
- تقدر تتحقق من العملية فى صفحة callback كما ذكرنا مسبقا فى مرحلة التحقق من عملية الدفع فى php .
