<div dir="rtl">

# 🎵👻 GhostBeats

بوت ديسكورد بيشغّل موسيقى من يوتيوب بأوامر **عربية وإنجليزية** — بدون أي تعقيد. كل نسخة بوت بتنربط بروم صوتي، وبتقدر تشغّل تلات بوتات بثلاث رومات بنفس الوقت من واجهة واحدة.

---

## ✨ المميزات

- **أوامر عربية وإنجليزية** بدون رمز بادئ — اكتب `شغّل` أو `play` عادي بالشات.
- **أوامر Slash** كمان (`/play`, `/download` ...) لو بتفضّلها.
- **تشغيل، إيقاف، تخطّي، قائمة انتظار، تكرار، تقديم** — كل اللي بتحتاجه.
- **تحميل أي أغنية mp3** — اكتب `حمل` أو `mp3` والبوت بيرفعلك الملف بالشات.
- **ذكاء اصطناعي اختياري** — فعّله وكلّم البوت عادي (يحتاج مفتاح API).
- **واجهة تحكّم بسيطة** — تحط التوكنات، تكبس تشغيل، وخلص.
- **بيجهّز حاله لحاله** — أول تشغيل بينزّل مكوّن يوتيوب المطلوب تلقائياً (بدون أي خطوة منك).
- **سجل ذكي** — بيقلك بالضبط شو صاير ولو صار خطأ بيشرحه بالعربي.

---

## 🚀 التشغيل (٣ خطوات)

### ١. جهّز البوت على ديسكورد
1. روح على [Discord Developer Portal](https://discord.com/developers/applications) ← **New Application**.
2. من تبويب **Bot** ← **Reset Token** ← انسخ التوكن (هاد سر البوت — لا تشاركه مع حدا).
3. من تبويب **Bot** فعّل الخيارات الثلاثة تحت **Privileged Gateway Intents** (خصوصاً **Message Content Intent**).
4. ادعُ البوت لسيرفرك بهالرابط (بدّل `APP_ID` بالـ Application ID تبعك):

</div>

```
https://discord.com/api/oauth2/authorize?client_id=APP_ID&permissions=3180608&scope=bot%20applications.commands
```

<div dir="rtl">

> **مهم:** صلاحية `3180608` بتشمل رفع الملفات وإضافة التفاعلات — لازمة عشان أمر التحميل والميزات تشتغل. لو عندك بوتات قديمة، أعد دعوتها بنفس الرابط.

### ٢. شغّل البرنامج
- افتح **GhostBeats.exe** (دبل-كليك).
- **Server ID:** انسخه من ديسكورد (فعّل Developer Mode ← كليك يمين على السيرفر ← Copy Server ID).
- لكل بوت: حط الـ **Token** والـ **Channel ID** (الروم الصوتي اللي بدك البوت يدخله).
- اكبس **💾 حفظ** ثم **▶️ تشغيل**.

### ٣. استمتع
بروم الصوت، اكتب بالشات:

| الأمر | البديل | الوظيفة |
|------|--------|---------|
| `شغّل <اسم أو رابط>` | `play` | يشغّل أغنية |
| `وقف` | `stop` | يوقف ويطلع |
| `تخطّى` | `skip` | الأغنية الجاية |
| `وقف مؤقت` | `pause` | إيقاف مؤقت |
| `كمّل` | `resume` | متابعة |
| `كرّر` | `loop` | تكرار |
| `قائمة` | `queue` | قائمة الانتظار |
| `حمّل <اسم>` | `mp3` | يرفعلك الأغنية mp3 |
| `أوامر` | `help` | كل الأوامر |

</div>

---

<div dir="rtl">

## 🍪 لو طلع خطأ «Sign in» عند التشغيل أو التحميل

أحياناً يوتيوب بيطلب إثبات إنك مش بوت. الحل سهل:

1. بواجهة GhostBeats، خانة **«كوكيز يوتيوب»** ← اختر متصفحك (لازم تكون مسجّل دخول يوتيوب فيه).
2. **حفظ** ← **تشغيل**.

لو المتصفح Chrome أو Edge وما زبط (بيمنعوا قراءة الكوكيز)، في حل أثبت — **ملف كوكيز**:

1. بفايرفوكس، ركّب إضافة **cookies.txt** ([من هون](https://addons.mozilla.org/firefox/addon/cookies-txt/)).
2. افتح **نافذة خاصة** (Ctrl+Shift+P) ← سجّل دخول يوتيوب.
3. وإنت على يوتيوب، اكبس أيقونة الإضافة ← **Current Site → Download**.
4. **سكّر النافذة الخاصة** (هيك الكوكيز بتضل صالحة شهور).
5. بواجهة GhostBeats، خانة **«ملف كوكيز»** ← **اختيار…** ← اختر الملف ← **حفظ** ← **تشغيل**.

> 🔒 **تحذير أمني:** ملف الكوكيز = جلسة دخول حسابك. خليه على جهازك بس، **ولا تشاركه ولا توزّعه** مع البوت أبداً.

---

## 🧩 مكوّن يوتيوب (Deno) — تلقائي

يوتيوب الحديث بيحتاج محرّك JavaScript صغير اسمه **Deno** لفك تشفير الروابط. **ما عليك تعمل شي** — أول تشغيل، البرنامج بينزّله تلقائياً بالخلفية وبيحطه جنبه (مرة وحدة، بيحتاج إنترنت). بتشوف بالسجل:

```
⬇️ أول تشغيل: عم نزّل Deno (محرّك يوتيوب) تلقائياً...
✓ Deno انضاف جنب البرنامج — يوتيوب صار بكامل قوته.
```

لو فشل التنزيل التلقائي (نت ضعيف مثلاً)، نزّله يدوياً: من [صفحة Deno](https://github.com/denoland/deno/releases/latest) نزّل `deno-x86_64-pc-windows-msvc.zip`، فك الضغط، وحط `deno.exe` جنب `GhostBeats.exe`.

---

## 📜 قراءة السجل

أول سطر بالسجل بيقلك حالة كل شي:

```
🧩 Deno/Node: موجود ✓ | حزمة ejs: موجودة ✓ | كوكيز يوتيوب: ملف cookies.txt
```

ثلاث علامات ✓ معناها كل شي تمام. لو في ✗، السطر نفسه بيقلك شو ينقص وكيف تحلّه.

---

## 🛡️ تنبيهات ويندوز

- **SmartScreen** («Windows protected your PC»): اكبس **More info → Run anyway**. بيطلع لأن البرنامج مش موقّع رسمياً (مش فيروس).
- **مكافح الفيروسات:** أحياناً بيشتبه ببرامج PyInstaller. لو بدك تطمّن، افحص الملف على [VirusTotal](https://www.virustotal.com).

---

## ❓ مشاكل شائعة

| المشكلة | الحل |
|---------|------|
| البوت ما بيدخل الروم | تأكد من Channel ID، وإنه البوت معزوم بصلاحية `3180608` |
| «Sign in» مكرر | اضبط الكوكيز (فوق) |
| الموسيقى بتتقطّع | نت ضعيف أو السيرفر بعيد — جرّب روم تاني |
| الأوامر ما بتنشتغل | فعّل **Message Content Intent** بالـ Developer Portal |

---

<div align="center">

صُنع بـ ❤️ من **Bug_Hunter**

</div>

</div>

---

<div align="ltr">

# 🎵👻 GhostBeats

A Discord bot that plays YouTube music with **Arabic and English** commands — zero hassle. Each bot instance connects to one voice channel, and you can run three bots in three channels at once from a single control panel.

---

## ✨ Features

- **Arabic & English commands** with no prefix — just type `play` or `شغّل` in chat.
- **Slash commands** too (`/play`, `/download` ...) if you prefer.
- **Play, stop, skip, queue, loop, seek** — everything you need.
- **Download any song as mp3** — type `mp3` or `download` and the bot uploads the file.
- **Optional AI chat** — enable it and talk to the bot (needs an API key).
- **Simple control panel** — paste your tokens, hit start, done.
- **Self-provisioning** — on first run it auto-downloads the required YouTube component (no steps from you).
- **Smart log** — tells you exactly what's happening, and explains errors clearly.

---

## 🚀 Setup (3 steps)

### 1. Create the bot on Discord
1. Go to the [Discord Developer Portal](https://discord.com/developers/applications) → **New Application**.
2. Under **Bot** → **Reset Token** → copy the token (this is your bot's secret — never share it).
3. Under **Bot**, enable all three **Privileged Gateway Intents** (especially **Message Content Intent**).
4. Invite the bot with this link (replace `APP_ID` with your Application ID):

</div>

```
https://discord.com/api/oauth2/authorize?client_id=APP_ID&permissions=3180608&scope=bot%20applications.commands
```

<div align="ltr">

> **Important:** The `3180608` permission includes file uploads and reactions — required for the download command and other features. If you have older bots, re-invite them with this same link.

### 2. Run the app
- Open **GhostBeats.exe** (double-click).
- **Server ID:** copy it from Discord (enable Developer Mode → right-click your server → Copy Server ID).
- For each bot: enter the **Token** and **Channel ID** (the voice channel it should join).
- Hit **💾 Save** then **▶️ Start**.

### 3. Enjoy
In the voice channel, type in chat:

| Command | Alias | Function |
|---------|-------|----------|
| `play <name or link>` | `شغّل` | Plays a song |
| `stop` | `وقف` | Stops and leaves |
| `skip` | `تخطّى` | Next song |
| `pause` | `وقف مؤقت` | Pause |
| `resume` | `كمّل` | Resume |
| `loop` | `كرّر` | Loop |
| `queue` | `قائمة` | Show queue |
| `download <name>` | `mp3` | Uploads the song as mp3 |
| `help` | `أوامر` | All commands |

</div>

---

<div align="ltr">

## 🍪 If you get a "Sign in" error on play or download

Sometimes YouTube asks to confirm you're not a bot. Easy fix:

1. In the GhostBeats panel, the **"YouTube cookies"** field → pick your browser (you must be logged into YouTube there).
2. **Save** → **Start**.

If your browser is Chrome or Edge and it doesn't work (they block cookie reads), there's a more reliable way — a **cookies file**:

1. In Firefox, install the **cookies.txt** add-on ([here](https://addons.mozilla.org/firefox/addon/cookies-txt/)).
2. Open a **Private window** (Ctrl+Shift+P) → sign in to YouTube.
3. While on YouTube, click the add-on icon → **Current Site → Download**.
4. **Close the private window** (this keeps the cookies valid for months).
5. In the GhostBeats panel, the **"Cookies file"** field → **Browse…** → pick the file → **Save** → **Start**.

> 🔒 **Security warning:** A cookies file = your account login session. Keep it on your device only, and **never share or distribute it** with the bot.

---

## 🧩 YouTube component (Deno) — automatic

Modern YouTube needs a small JavaScript engine called **Deno** to decode links. **You don't need to do anything** — on first run, the app auto-downloads it in the background and places it next to itself (once, needs internet). You'll see in the log:

```
⬇️ First run: downloading Deno (YouTube engine) automatically...
✓ Deno added next to the app — YouTube is now at full power.
```

If the auto-download fails (weak connection, etc.), grab it manually: from the [Deno releases page](https://github.com/denoland/deno/releases/latest) download `deno-x86_64-pc-windows-msvc.zip`, unzip it, and put `deno.exe` next to `GhostBeats.exe`.

---

## 📜 Reading the log

The first log line tells you the status of everything:

```
🧩 Deno/Node: found ✓ | ejs package: found ✓ | YouTube cookies: cookies.txt file
```

Three ✓ marks means all good. If there's a ✗, the line itself tells you what's missing and how to fix it.

---

## 🛡️ Windows warnings

- **SmartScreen** ("Windows protected your PC"): click **More info → Run anyway**. It appears because the app isn't officially signed (not a virus).
- **Antivirus:** sometimes flags PyInstaller apps. To be safe, scan the file on [VirusTotal](https://www.virustotal.com).

---

## ❓ Common issues

| Problem | Fix |
|---------|-----|
| Bot won't join the channel | Check the Channel ID, and that the bot was invited with permission `3180608` |
| Repeated "Sign in" | Set up cookies (above) |
| Music keeps cutting out | Weak connection or distant server — try another channel |
| Commands don't work | Enable **Message Content Intent** in the Developer Portal |

---

<div align="center">

Made with ❤️ by **Bug_Hunter**

</div>

</div>
