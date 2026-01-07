# دليل الإعداد السريع / Quick Setup Guide

## 🚀 خطوات الإعداد السريعة

### 1️⃣ إعداد Firebase (5 دقائق)

1. **إنشاء مشروع Firebase:**
   - زر [Firebase Console](https://console.firebase.google.com/)
   - اضغط "Add project"
   - اتبع الخطوات

2. **تفعيل Authentication:**
   - من القائمة الجانبية: Build → Authentication
   - اضغط "Get started"
   - اختر "Email/Password" وفعّله
   - احفظ

3. **إنشاء Firestore Database:**
   - من القائمة الجانبية: Build → Firestore Database
   - اضغط "Create database"
   - اختر "Start in production mode"
   - اختر المنطقة (مثلاً: `eur3` لأوروبا)

4. **الحصول على بيانات الاتصال:**
   - اذهب إلى Project Settings (⚙️)
   - في قسم "Your apps"، اضغط على أيقونة الويب `</>`
   - أدخل اسم التطبيق (مثلاً: "Employee Attendance")
   - **لا** تختر Firebase Hosting
   - انسخ كود `firebaseConfig`

5. **إعداد Security Rules:**
   - ارجع إلى Firestore Database
   - اضغط على تبويب "Rules"
   - احذف المحتوى الموجود
   - انسخ محتوى ملف `firestore.rules` من المشروع
   - اضغط "Publish"

### 2️⃣ إعداد المشروع (دقيقة واحدة)

1. **نسخ ملف التكوين:**
```bash
cp firebase-config.example.js firebase-config.js
```

2. **إضافة بيانات Firebase:**
افتح `firebase-config.js` وعدّل البيانات:
```javascript
export const firebaseConfig = {
  apiKey: "AIza...",  // من Firebase Console
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc..."
};
```

### 3️⃣ إنشاء حساب الأدمن (دقيقة واحدة)

1. في Firebase Console → Authentication
2. اضغط "Add user"
3. أدخل:
   - Email: `admin@example.com` (أو أي بريد)
   - Password: كلمة مرور قوية
4. احفظ البيانات للاستخدام

### 4️⃣ تشغيل المشروع محلياً

اختر طريقة واحدة:

**Python:**
```bash
python -m http.server 8000
```

**Node.js:**
```bash
npx http-server -p 8000
```

**PHP:**
```bash
php -S localhost:8000
```

افتح المتصفح: `http://localhost:8000`

### 5️⃣ أول استخدام

1. افتح `http://localhost:8000`
2. سجل دخول ببيانات الأدمن
3. أدخل اسمك (سيُحفظ في قاعدة البيانات)
4. أضف موظفاً جديداً
5. انسخ رابط الموظف وشاركه

---

## ✅ جاهز للاستخدام!

الآن يمكنك:
- ✅ إضافة موظفين
- ✅ البحث عن الموظفين
- ✅ تسجيل حضورك
- ✅ مشاركة روابط الموظفين

---

## 🌐 النشر على GitHub Pages

### الخطوات:

1. **رفع الملفات إلى GitHub:**
```bash
git add .
git commit -m "Add employee attendance system"
git push origin main
```

2. **تفعيل GitHub Pages:**
   - اذهب إلى Settings في المستودع
   - اذهب إلى Pages
   - Source: Deploy from a branch
   - Branch: main, folder: / (root)
   - Save

3. **انتظر دقيقة واحدة**، ثم زر:
   `https://[username].github.io/[repo-name]/`

مثال:
`https://mohmmedkhalifa.github.io/employees/`

---

## ⚠️ تنبيهات مهمة

1. **لا تشارك ملف `firebase-config.js`** - مضاف للـ `.gitignore`
2. **احفظ بيانات الأدمن** في مكان آمن
3. **راجع Security Rules** بانتظام
4. **استخدم HTTPS** دائماً في الإنتاج

---

## 🆘 مشاكل شائعة وحلولها

### المشكلة: "CORS error" أو "Module not found"
**الحل:** استخدم خادم ويب محلي، لا تفتح الملف مباشرة

### المشكلة: "Permission denied" في Firestore
**الحل:** تأكد من نشر Security Rules الصحيحة

### المشكلة: لا يظهر الموظفون
**الحل:** تحقق من أن `isAdmin` مضبوط صحيحاً في الـ Firestore

### المشكلة: الرابط لا يعمل على الموظف
**الحل:** تأكد من أن ID الموظف موجود في URL

---

## 📞 المساعدة

للمزيد من المساعدة، راجع [README.md](README.md) أو افتح issue في المستودع.

---

**وقت الإعداد الكلي: أقل من 10 دقائق! ⚡**
