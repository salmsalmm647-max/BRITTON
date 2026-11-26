BRITTON — ملفات المتجر ولوحة التحكم

مهم: هذه ملفات واجهة وربط أولي بقاعدة Appwrite. لا تصبح قاعدة البيانات فعالة قبل إنشاء مشروع Appwrite وضبط المعرّفات والصلاحيات.

1) ارفع كل الملفات إلى جذر مستودع GitHub Pages.
2) افتح https://cloud.appwrite.io وأنشئ مشروعًا باسم BRITTON.
3) من Project Settings انسخ Project ID وضعه في appwrite-config.js بدل PUT_YOUR_PROJECT_ID_HERE.
4) أضف Web Platform داخل Appwrite واكتب نطاق موقع GitHub Pages، مثل:
   https://USERNAME.github.io
   أو نطاق المستودع إن كان المشروع منشورًا في مسار فرعي.
5) أنشئ Database ID مطابقًا لـ britton_db.
6) أنشئ Collections بهذه المعرفات والحقول (كلها String ما لم يذكر غير ذلك):
   products: name (string, required), category (string), description (string), imageUrl (string), price (integer/double).
   categories: name (string, required), imageUrl (string).
   orders: customerName (string), phone (string), city (string), district (string), nationalAddress (string), address (string), items (string), total (double), status (string), createdAt (string).
   اجعل Document Security مفعّلًا عند الحاجة، واضبط صلاحيات القراءة العامة للمنتجات والأقسام، وإنشاء الطلبات للزوار. اجعل إدارة المنتجات والأقسام والطلبات للمستخدمين المسجلين فقط.
7) أنشئ حساب مسؤول من Appwrite Auth ثم سجل دخوله من admin.html.
8) في appwrite-config.js ضع Database ID وCollection IDs إذا اخترت معرفات مختلفة.
9) افتح المتجر من index.html ولوحة الإدارة من admin.html.

ملاحظات مهمة:
- صور المنتجات في هذه النسخة تُضاف عبر رابط صورة مباشر؛ لم يتم تضمين رفع الملفات إلى Storage بعد.
- لا تضع API Key أو أي سر في ملفات JavaScript العامة.
- نموذج الطلب ينشئ سجلًا وفاتورة برقم الطلب، لكن لا يوجد ربط شركة شحن أو إرسال بريد/واتساب تلقائي في هذه النسخة.
- عدد الزوار، إعدادات المتجر، تغيير الشعار/الخلفية، ومساعد الذكاء الاصطناعي تحتاج خدمات/وظائف إضافية ولم تُفعّل هنا.
- اختبر الموقع وقواعد الصلاحيات قبل استقبال طلبات فعلية.
