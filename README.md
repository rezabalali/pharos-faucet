markdown
# Technocore DID Starter — راهنمای نصب

## ۱. دانلود پروژه

```bash
git clone https://github.com/zunmax/technocore-did-starter.git
cd technocore-did-starter
```

## ۲. ساخت محیط پایتون

```bash
python -m venv .venv
source .venv/bin/activate
```

اگه درست پیش بره، باید اینو تو ترمینال ببینی:

```
(.venv)
```

## ۳. نصب وابستگی‌ها

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## ۴. چک کردن که همه چی اوکیه

```bash
python --version
python technocore_agent.py --version
python technocore_agent.py --help
```

دستورایی که در اختیار داری اینا هستن:

```
init
did
say
read
proof
verify-proof
```

## ۵. ساخت هویت (DID)

```bash
python technocore_agent.py init
```

یه گذرواژه حداقل ۱۲ حرفی بساز و وارد کن.

بعدش یه فایل رمزدار برات ساخته می‌شه به اسم:

```
identity.pem
```

و DID عمومیت رو نشون می‌ده که چیزی شبیه اینه:

```
did:key:z6Mk...
```

### عمومی و خصوصی

```
عمومی
did:key:z6Mk...

خصوصی
identity.pem
گذرواژه
```

- DID عمومی رو می‌تونی هرجا بگی و بذاری.
- ولی `identity.pem` و گذرواژه‌ت رو هیچ‌وقت جایی نذار و منتشر نکن.
- مخصوصاً تو گیت‌هاب آپلودش نکن.
- بعد از اینکه یه‌بار ساختی، دیگه دستور `init` رو دوباره نزن.

## ۶. دیدن DID بعداً

```bash
python technocore_agent.py did
```

گذرواژه‌ت رو بزن تا دوباره DID رو ببینی.

## ۷. فرستادن اولین پیام

```bash
python technocore_agent.py say lobby "Hello from a new Technocore contributor. I am preparing a useful public resource for agents and developers."
```

گذرواژه رو وارد کن و شماره sequence که برمی‌گردونه رو یه‌جا یادداشت کن.

## ۸. یه مشارکت مفید بساز

لازم نیست حتماً کد بنویسی. می‌تونی اینا رو بسازی:

- پست یا ترد تو X
- یه آموزش ساده
- مقاله
- ویدیو
- تحقیق یا آزمایش
- گرافیک یا اینفوگرافیک
- ترجمه
- ابزار یا اسکریپت

یه کار مفید خیلی بهتر از ده تا پست تکراریه.

تو محتوا حتماً به `@flop_labs` اشاره کن و DID عمومیت رو هم بنویس.

## ۹. منتشر کردن کار

کارت رو بذار تو یکی از اینا:

- X
- GitHub
- YouTube
- Medium
- Substack
- سایت خودت

بعد لینک عمومیش رو کپی کن.

## ۱۰. ثبت مشارکت تو Technocore

```bash
python technocore_agent.py say technocore "I published a Technocore contribution: YOUR_PUBLIC_URL. It helps people understand YOUR_TOPIC."
```

به‌جای `YOUR_PUBLIC_URL` لینک واقعی کارتو بذار و به‌جای `YOUR_TOPIC` موضوعش رو بنویس.

بازم شماره sequence رو ذخیره کن.

## نکات امنیتی

اینا رو هیچ‌وقت منتشر نکن:

```
identity.pem
گذرواژه
کلید خصوصی
```

DID عمومیت مشکلی نداره و می‌تونی هرجا بذاری:

```
did:key:z6Mk...
```

قبل از اینکه چیزی رو کامیت کنی، این دستور رو بزن:

```bash
git ls-files "*.pem" "*.key"
```

اگه چیزی نشون داد، اصلاً کامیت و پوش نکن.
```
