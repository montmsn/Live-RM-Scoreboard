# Live Football Score

A live football scoreboard overlay for streamers (Kick, Twitch, YouTube) that follows Real Madrid matches and shows them on stream through OBS or Streamlabs.

- A floating glass capsule at the top of the screen with both clubs' logos, the score and the match clock.
- Goals open the capsule with an animation, the scorer's name, the minute and confetti in the scoring team's colours.
- Yellow and red cards, half-time, second half, added time and full time are announced automatically.
- The scorer list opens at every 10th minute (10', 20', 30' …).
- When there is no match today it shows the next fixture with the kick-off time in your local time zone.

Data comes from ESPN's public scoreboard JSON: free, no API key. Polls every 15 seconds while a match is live. ESPN usually runs a minute or two behind the broadcast.

## Use it in OBS

1. Download `overlay.html`.
2. In OBS add a **Browser** source, tick **Local file** and pick `overlay.html`.
3. Set width **1920** and height **1080**. The background is transparent.

Streamlabs: Add Source → Browser Source → Local File.

## Options

Add them to the address (untick *Local file* and use a `file:///…/overlay.html?…` URL):

| Option | What it does |
|---|---|
| `?demo=1` | Plays a scripted sample match |
| `?scale=1.2` | Bigger or smaller (e.g. `0.8`, `1.2`) |
| `?pos=bottom` | Moves the scoreboard to the bottom |
| `?team=86` | ESPN team id to follow (86 = Real Madrid) |
| `?debug=1` | Shows a status log of every request |

Combine with `&`, e.g. `?scale=1.2&pos=bottom`.

A Persian setup guide is below.

---

<div dir="rtl">

## آموزش فارسی

### این چیه؟
یه اسکوربورد زنده برای استریم (کیک، توییچ، یوتیوب) که بازی‌های رئال مادرید رو دنبال می‌کنه و نتیجه رو بالای صفحه‌ی استریمت نشون می‌ده. هیچ برنامه یا ثبت‌نامی لازم نداره، فقط یه فایله.

### قدم ۱: دانلود فایل
1. فایل `overlay.html` رو دانلود کن.
2. یه پوشه‌ی ثابت بساز (مثلا `C:\Kick`) و فایل رو اونجا بذار.
3. بعدا جابه‌جاش نکن، وگرنه OBS پیداش نمی‌کنه.

### قدم ۲: اضافه کردن به OBS
1. OBS رو باز کن.
2. پایین صفحه، توی کادر **Sources** روی **+** بزن.
3. **Browser** رو انتخاب کن، یه اسم بهش بده (مثلا «اسکوربورد») و OK بزن.
4. تیک **Local file** رو بزن، روی **Browse** کلیک کن و `overlay.html` رو انتخاب کن.
5. **Width** رو `1920` و **Height** رو `1080` بذار.
6. OK بزن. تمام! اسکوربورد بالای صفحه ظاهر می‌شه و بقیه‌ی صفحه شفافه.

> توی **Streamlabs** هم همینه: Add Source ← Browser Source ← Local File.

### قدم ۳: امتحانش کن (حالت دمو)
قبل از بازی واقعی ببین درست کار می‌کنه:
1. روی سورس دوبار کلیک کن تا تنظیماتش باز بشه.
2. تیک **Local file** رو بردار.
3. توی کادر **URL** آدرس فایل رو با `?demo=1` بنویس، مثلا:
   `file:///C:/Kick/overlay.html?demo=1`
4. OK بزن. یه بازی نمایشی رئال و بارسا پخش می‌شه با گل، کارت و پایان بازی.
5. بعد از امتحان، `?demo=1` رو پاک کن تا دوباره نتیجه‌ی واقعی نشون بده.

### خودش چی کار می‌کنه؟
- بازی امروز رئال رو خودش پیدا می‌کنه (لالیگا، لیگ قهرمانان، کوپا دل‌ری و…).
- وقتی بازی زنده‌ست، هر ۱۵ ثانیه نتیجه رو به‌روز می‌کنه.
- گل رو با انیمیشن، اسم گلزن، دقیقه و کاغذرنگی نشون می‌ده.
- کارت زرد و قرمز، پایان نیمه، نیمه‌ی دوم، وقت اضافه و پایان بازی رو خودکار اعلام می‌کنه.
- هر ۱۰ دقیقه (۱۰، ۲۰، ۳۰…) لیست گلزن‌ها رو باز می‌کنه.
- اگه امروز بازی نباشه، بازی بعدی رو با ساعتش به وقت کامپیوتر خودت نشون می‌ده.
- نتیجه از ESPN میاد و معمولا یکی دو دقیقه از پخش تلویزیونی عقب‌تره. این طبیعیه.

### تنظیمات اختیاری
مثل حالت دمو، تیک Local file رو بردار و این‌ها رو آخر آدرس اضافه کن:

| تنظیم | کارش |
|---|---|
| `?demo=1` | بازی نمایشی برای امتحان |
| `?scale=1.2` | بزرگ‌تر یا کوچیک‌ترش می‌کنه (مثلا `0.8` یا `1.2`) |
| `?pos=bottom` | اسکوربورد رو پایین صفحه می‌بره |
| `?team=86` | تیمی که دنبال می‌کنه (۸۶ یعنی رئال مادرید) |
| `?debug=1` | پایین صفحه نشون می‌ده داره چی کار می‌کنه |

برای چند تنظیم با هم از `&` استفاده کن، مثلا:
`file:///C:/Kick/overlay.html?scale=1.2&pos=bottom`

### مشکل داری؟
- **هیچی نشون نمی‌ده:** مطمئن شو اینترنت وصله و آدرس فایل درسته (اسلش‌ها `/` باشن نه `\`).
- **نتیجه به‌روز نمی‌شه:** روی سورس راست‌کلیک کن، Properties رو باز کن و **Refresh cache of current page** رو بزن.
- **خیلی بزرگ یا کوچیکه:** از `?scale=` استفاده کن.
- **هنوز درست نشد:** آدرس رو با `?debug=1` باز کن و متن پایین صفحه رو بفرست.

</div>
