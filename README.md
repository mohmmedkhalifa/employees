# نظام إدارة حضور الموظفين / Employee Attendance Management System

نظام ويب عصري لإدارة حضور وانصراف الموظفين باستخدام Vue.js و Firebase.

A modern web-based employee attendance management system using Vue.js and Firebase.

## ✨ المميزات / Features

### للأدمن / For Admin:
- 🔐 تسجيل دخول آمن باستخدام Firebase Authentication
- 👤 إعداد حساب الأدمن عند التسجيل لأول مرة
- ➕ إضافة موظفين جدد
- 🔍 البحث عن الموظفين
- 📊 عرض سجلات الحضور والانصراف
- ⏰ تسجيل الحضور والانصراف الشخصي
- 📅 عرض التاريخ والوقت بالعربية

### للموظفين / For Employees:
- 📱 صفحة خاصة لكل موظف بدون الحاجة لتسجيل دخول
- ✅ تسجيل الحضور
- 🚪 تسجيل الانصراف
- 📋 عرض آخر السجلات

## 🚀 التثبيت والإعداد / Installation & Setup

### 1. استنساخ المستودع / Clone Repository

```bash
git clone https://github.com/mohmmedkhalifa/employees.git
cd employees
```

### 2. إعداد Firebase

#### أ) إنشاء مشروع Firebase:
1. اذهب إلى [Firebase Console](https://console.firebase.google.com/)
2. أنشئ مشروع جديد
3. فعّل Firebase Authentication (Email/Password)
4. أنشئ قاعدة بيانات Cloud Firestore

#### ب) الحصول على بيانات الاتصال:
1. في Firebase Console، اذهب إلى Project Settings
2. في قسم "Your apps"، اختر Web app (</>)
3. سجل التطبيق واحصل على `firebaseConfig`

#### ج) تكوين ملف Firebase:
1. انسخ ملف `firebase-config.example.js` إلى `firebase-config.js`:
```bash
cp firebase-config.example.js firebase-config.js
```

2. افتح `firebase-config.js` وأضف بياناتك:
```javascript
export const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### 3. إعداد Firebase Security Rules

في Firebase Console:
1. اذهب إلى Firestore Database → Rules
2. انسخ محتوى ملف `firestore.rules` والصقه في قواعد Firestore
3. انشر القواعد

### 4. إنشاء حساب الأدمن

1. في Firebase Console → Authentication
2. أضف مستخدم جديد يدوياً بالبريد الإلكتروني وكلمة المرور
3. احفظ البريد الإلكتروني وكلمة المرور للاستخدام

### 5. تشغيل المشروع محلياً

بما أن المشروع يستخدم ES6 modules، تحتاج إلى خادم ويب محلي:

```bash
# باستخدام Python
python -m http.server 8000

# أو باستخدام Node.js (npx http-server)
npx http-server -p 8000

# أو باستخدام PHP
php -S localhost:8000
```

ثم افتح المتصفح على: `http://localhost:8000`

## 📱 الاستخدام / Usage

### للأدمن:

1. **التسجيل لأول مرة:**
   - افتح `index.html`
   - سجل دخول بالبريد الإلكتروني وكلمة المرور
   - أدخل اسمك عند المطالبة

2. **إضافة موظف:**
   - اضغط على قسم "إضافة موظف جديد"
   - أدخل اسم الموظف والمنصب
   - اضغط "إضافة"
   - انسخ رابط الموظف وشاركه معه

3. **عرض سجلات الحضور:**
   - اضغط على اسم الموظف في القائمة
   - ستظهر جميع سجلات الحضور والانصراف

### للموظفين:

1. افتح الرابط الخاص بك (المشارك من الأدمن)
2. سجل حضورك أو انصرافك
3. شاهد آخر سجلاتك

## 🌐 النشر على GitHub Pages

### الطريقة 1: النشر اليدوي

1. في إعدادات المستودع على GitHub
2. اذهب إلى Settings → Pages
3. اختر Source: Deploy from a branch
4. اختر Branch: main / (root)
5. احفظ

موقعك سيكون متاحاً على:
`https://mohmmedkhalifa.github.io/employees/`

### الطريقة 2: باستخدام GitHub Actions (اختياري)

يمكنك إنشاء workflow للنشر التلقائي، لكن المشروع الحالي لا يحتاج لعملية build.

## 📁 هيكل المشروع / Project Structure

```
employees/
├── index.html              # صفحة لوحة تحكم الأدمن
├── employee.html           # صفحة الموظف
├── styles.css              # ملف الأنماط
├── firebase-config.js      # تكوين Firebase (غير مضاف للـ git)
├── firebase-config.example.js  # مثال لتكوين Firebase
├── firestore.rules         # قواعد أمان Firestore
├── .gitignore             # الملفات المستثناة من Git
└── README.md              # هذا الملف
```

## 🔒 الأمان / Security

### Firebase Security Rules:
- الأدمن فقط يمكنه رؤية جميع البيانات
- الموظفون يمكنهم رؤية وتسجيل بياناتهم الخاصة فقط
- لا يمكن للموظفين رؤية أو تعديل بيانات موظفين آخرين

### ملاحظات أمنية مهمة:
- ⚠️ **لا تشارك ملف `firebase-config.js`** - هذا الملف مضاف إلى `.gitignore`
- 🔐 استخدم كلمات مرور قوية لحساب الأدمن
- 🛡️ راجع Firebase Security Rules بانتظام

## 🎨 التصميم / Design

- ✅ تصميم عصري وبسيط
- ✅ دعم كامل للغة العربية (RTL)
- ✅ متجاوب مع جميع الأجهزة (Desktop, Tablet, Mobile)
- ✅ ألوان جذابة وواجهة سهلة الاستخدام
- ✅ تنسيق التاريخ والوقت بالعربية

## 🛠️ التقنيات المستخدمة / Technologies Used

- **Vue.js 3** - إطار عمل JavaScript
- **Firebase Authentication** - المصادقة وإدارة المستخدمين
- **Cloud Firestore** - قاعدة البيانات
- **CSS3** - التنسيق والتصميم
- **ES6 Modules** - نظام الوحدات

## 📞 الدعم / Support

للمشاكل والاقتراحات، يرجى فتح issue في المستودع.

## 📄 الترخيص / License

هذا المشروع مفتوح المصدر ومتاح للاستخدام الحر.

---

**ملاحظة:** تأكد من عدم مشاركة بيانات Firebase الخاصة بك مع أي شخص!

**Note:** Make sure not to share your Firebase credentials with anyone!