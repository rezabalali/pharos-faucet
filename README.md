```markdown
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

باید این را در ترمینال ببینید:

```
(.venv)
```

## ۳. نصب وابستگی‌ها

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## ۴. بررسی نصب

```bash
python --version
python technocore_agent.py --version
python technocore_agent.py --help
```

دستورات موجود:

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

یک گذرواژه حداقل ۱۲ کاراکتری وارد کنید.

فایل رمزگذاری‌شده ساخته می‌شود:

```
identity.pem
```

و DID عمومی شما نمایش داده می‌شود:

```
did:key:z6Mk...
```

### عمومی در برابر خصوصی

```
عمومی
did:key:z6Mk...

خصوصی
identity.pem
گذرواژه
```

- DID عمومی را می‌توانید به اشتراک بگذارید.
- فایل `identity.pem` و گذرواژه را هرگز منتشر نکنید.
- هرگز `identity.pem` را در گیت‌هاب آپلود نکنید.
- بعد از ساخت هویت، دوباره دستور `init` را اجرا نکنید.

## ۶. مشاهده DID بعداً

```bash
python technocore_agent.py did
```

گذرواژه را وارد کنید تا DID شما دوباره نمایش داده شود.

## ۷. ارسال اولین پیام

```bash
python technocore_agent.py say lobby "Hello from a new Technocore contributor. I am preparing a useful public resource for agents and developers."
```

گذرواژه را وارد کنید.

شماره sequence را ذخیره کنید.

## ۸. ساخت یک مشارکت مفید

مشارکت می‌تواند یکی از این موارد باشد:

- پست یا ترد در X
- آموزش
- مقاله
- ویدیو
- تحقیق
- آزمایش
- گرافیک
- ترجمه
- ابزار یا کد

یک مشارکت مفید بهتر از پست‌های تکراری است.

در محتوا به `@flop_labs` اشاره کنید و DID عمومی خود را بنویسید.

## ۹. انتشار کار

کار خود را در یکی از این جاها منتشر کنید:

- X
- GitHub
- YouTube
- Medium
- Substack
- وب‌سایت شخصی

آدرس عمومی را کپی کنید.

## ۱۰. ثبت مشارکت در Technocore

```bash
python technocore_agent.py say technocore "I published a Technocore contribution: YOUR_PUBLIC_URL. It helps people understand YOUR_TOPIC."
```

`YOUR_PUBLIC_URL` را با آدرس واقعی و `YOUR_TOPIC` را با موضوع جایگزین کنید.

شماره sequence را ذخیره کنید.

## امنیت

هرگز این موارد را منتشر نکنید:

```
identity.pem
گذرواژه
کلید خصوصی
```

DID عمومی قابل اشتراک‌گذاری است:

```
did:key:z6Mk...
```

قبل از کامیت، این دستور را بزنید:

```bash
git ls-files "*.pem" "*.key"
```

اگر فایلی نشان داد، آن را کامیت یا پوش نکنید.
```
