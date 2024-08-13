# Docker


Docker experiment for Software Enginnering Lab Course @ SUT.

اعضای تیم:
- همراز عرفاتی ۹۹۱۰۹۷۹۹
- امیرحسین براتی ۹۹۱۰۱۳۰۸
- امیرحسین عابدی ۹۹۱۰۵۵۹۴

## استقرار پروژه

با استفاده از 
`docker-compose.yml` 
و
`Dockerfile`
میتوانیم پروژه را برای استقرار روی یک سیستم با استفاده از داکر آماده کنیم. در ابتدا قبل از اینکه استقرار را انجام دهیم باید دیتابیس مربوط به پروژه را به 
`PostgreSQL`
تغییر دهیم. به این منظور در تنظیمات جنگو تغییرات زیر را اعمال می‌کنیم:

![image](./images/1-1.png)

با این تنظیمات اکنون 
`Django`
به جای استفاده از دیتابیس دیفالت، از طریق پورت 
5432
سعی می‌کند به دیتابیس جدید که از جنس 
`PosgreSQL`
است متصل شود.

برای اینکه استقرار پروژه را به پایان برسانیم، باید یک 
`Dockerfile`
مربوط به آن ایجاد کنیم. این فایل در کنار
`root`
جنگو قرار میگیرید و به صورت زیر خواهد بود:

![image](./images/1-3.png)

در این داکرفایل سعی می‌کنیم تا یک محیط پایتونی مناسب برای خود ایجاد کنیم. برای 
`image`
این قسمت از رجیستری آروان استفاده کردیم. پس از کپی کردن فایل 
`requirements.txt`
پروژه خودمان، پکیج‌های موردنیاز را نصب می‌کنیم و سپس سایر محتویات را به پوشه 
‍`/app`
این کانتینر کپی می‌کنیم. 

برای اینکه پروژه به صورت صحیح کار کند، باید یک کانتینر هم برای 
`PostgreSQL`
ایجاد کنیم که اینکار را در فایل 
`docker-compose.yml`
انجام می‌دهیم:

![image](./images/1-2.png)

## ارسال درخواست به وب سرور


## تعامل با داکر

### نمایش imageها و containerها
![image](./images/3-1.png)

![iamge](./images/3-2.png)

### اجرای دستور در container
دستور زیر یک کاربر ادمین برای برنامه ایجاد می‌کند که دسترسی ورود به صفحه ادمین را دارد.

![image](./images/3-3.png)

## پرسش‌ها

#### وظایف زیر را توضیح دهید:

<div dir="rtl">

<b>
ارسال درخواست به وب سرور:
</b>

در این بخش، با کمک برنامه‌ی postman اقدام به ارسال درخواست به برنامه کردیم تا هم کاربر جدید بسازیم، هم بعد از آن برای این کاربر ساخته شده یادداشت بسازیم. البته در این میان نیاز به لاگین کردن هم بود که خود postman در ادامه‌ی آن کوکی را ست کرد که باعث شد کاربر لاگین بماند. مراحل خواسته شده در صورت سوال به صورت زیر است:

ساخت کاربر


![IMG_20240813_231353_338](https://github.com/user-attachments/assets/7609b90d-4076-4f61-b3b7-1d1f97cff1c8)

ساخت متن اول



![IMG_20240813_231355_748](https://github.com/user-attachments/assets/f989e360-62a8-4624-bdbf-21902a744844)

ساخت متن دوم


![IMG_20240813_231356_947](https://github.com/user-attachments/assets/4a36f6ea-67e6-4f74-841c-86e86c72da55)

گرفتن متن‌های ساخته شده:

![IMG_20240813_231359_482](https://github.com/user-attachments/assets/27d0b9d8-1ad6-43e6-a8b0-4cdeb3f5d051)



****

<b>
تعامل با داکر:
</b>

****

<b>
پرسش‌ها:
</b>

وظایف زیر را توضیح دهید:

۱. image
- image

    داکر ایمیج 
    فایلی است که برای اجرای کد در کانتینر داکر استفاده می شود.
    docker image
    ها
    به عنوان مجموعه‌ای از دستورالعمل‌ها برای ساخت یک کانتینر داکر، مانند یک الگو، عمل می‌کنند.
    docker image
    ها
    همچنین به عنوان نقطه شروع هنگام استفاده از Docker عمل می کنند.
    یک 
    image
    با یک
    snapshot
    در محیط های ماشین مجازی قابل مقایسه است.

    یک
    docker image 
    یک الگوی readOnly است که حاوی مجموعه‌ای از دستورالعمل‌ها برای ایجاد کانتینری است که می‌تواند روی پلتفرم داکر اجرا شود. این یک راه راحت برای بسته بندی برنامه ها و محیط های سرور از پیش پیکربندی شده ارائه می دهد که می توانید از آنها برای استفاده خصوصی خود استفاده کنید یا به صورت عمومی با سایر کاربران Docker به اشتراک بگذارید.

- dockerfile

    فایل Dockerfile یک فایل متنی است که شامل تمام دستوراتی است که کاربر می تواند در
    command line
    برای جمع آوری یک
    image 
    فراخوانی کند.
    Dockerfile از DSL (Domain Specific Language) استفاده می کند و حاوی دستورالعمل هایی برای تولید یک Docker image است. Dockerfile فرآیندهایی را برای تولید سریع یک image تعریف می کند.


- container

    کانتینر یک واحد استاندارد نرم افزار است که کد و تمام وابستگی های آن را بسته بندی می کند تا برنامه به سرعت و با اطمینان از یک محیط محاسباتی به محیط دیگر اجرا شود. یک docker container image یک package نرم افزاری سبک وزن، مستقل و قابل اجرا است که شامل همه چیزهایی است که برای اجرای یک برنامه لازم است: کد، زمان اجرا، ابزارهای سیستم، کتابخانه های سیستم و تنظیمات.

</div>

#### کاربرد kubernetes:

کوبرنتیز یک روش کارآمد برای اجرای سیستم های multi-tenant است. چه بخواهید چندین برنامه و محیط را مستقر کنید، یا نیاز به جداسازی منابع توسط تیم داشته باشید، ویژگی‌های Kubernetes مانند فضاهای نام و کنترل دسترسی مبتنی بر نقش (RBAC) می‌توانند برای تقسیم خوشه‌ها به برش‌های منطقی برای هر یک از مستاجران شما استفاده شوند.

#### رابطه‌ی kubernetes با داکر:

داکر برای بسته بندی برنامه ها در کانتینرها استفاده می شود، در حالی که Kubernetes برای هماهنگی و مدیریت آن کانتینرها در تولید استفاده می شود.

