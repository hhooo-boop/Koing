# التحقق من نشر صدى العراق 3.6

بعد رفع ملفات الإصدار إلى جذر مستودع GitHub المرتبط بـ Railway:

1. افتح Deployments وتأكد أن أحدث Commit دخل مرحلة البناء.
2. يجب أن ينفذ Railway `npm run build` دون الحاجة إلى `scripts/validate-release.js` أو ملفات الاختبار المتداخلة.
3. بعد نجاح النشر افتح `/api/release` على نطاق الخدمة. تحقق من `version: "3.6"` و`deploymentConsistent: true`.
4. إذا ظهر الخطأ نفسه رغم رفع `package.json` و`railway.json` الجديدين، افحص Build Command المخصص في إعدادات Railway؛ فقد يتجاوز `railway.json` ويستدعي الأمر القديم مباشرة.
