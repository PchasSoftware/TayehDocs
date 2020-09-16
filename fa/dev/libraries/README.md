# کتابخانه ی tayeh_client (نسخه: 1.0.0-alpha):
اجرای تایه کلاینت در جاوا اسکریپت و تایپ اسکریپت
-   استفاده ی آسان
-   سازگار
-   جامع
##  ![introduction](https://img.icons8.com/nolan/40/training.png)مقدمه :
 ما در سایت تایه این امکان را به کاربران میدهیم که از اطلاعات خود استفاده کنند و تجارت خود را به صورت آنلاین توسعه دهند.
 حالا میخواهیم یک امکان ویژه به برنامه نویسان در این زمینه بدهیم تا از API ما استفاده کنند و دیگر نیازی به توسعه سمت سرور و ایجاد جدول های داده نداشته باشند.
 در نهایت، ما یک قدم فراتر گذاشتیم و یک کتابخانه ی API برای سمت کلاینت ایجاد کردیم تا کارهای شما را به حداقل رسانده و برای شما زمان بخریم.
;) به طور خلاصه، ما همه چیز را ساده تر کرده ایم. اینطور فکر نمیکنید؟ 
حالا این کتابخانه کجاست و چگونه باید از آن استفاده کرد؟ به شما خواهیم گفت.
شروع کنیم...
## ![start](https://img.icons8.com/nolan/40/start.png) شروع کار:
قبل از اینکه شروع به نصب کنید، باید کارهایی را انجام دهید.
به وبسایت تایه بروید و بعد از طی کردن مراحلی که در آنجا توضیح داده شده، `API_KEY` و `API_SECRET` را به عنوان نام کاربری و رمز عبور خود دریافت کنید.
حالا با داشتن این اطلاعات میتوانیم نصب را شروع کنیم...
### نصب و استفاده:
این مجموعه را از طریق `npm` یا `yarn` نصب کنید.
ما نام آن را tayeh_client گذاشته ایم:
```
npm install tayeh_client
# or
yarn add tayeh_client
```
کتابخانه را در پروژه خود اضافه کنید:
```
const TayehClient = require('tayeh-client');
// or
import TayehClient from 'tayeh-client';
```
سپس یک نمونه از آن ایجاد کنید: (مقادیری که از سایت دریافت کرده اید اینجا به کار می آید.)
```
const  tayeh  =  new  TayehClient({API_KEY: 'API_KEY', API_SECRET: 'API_SECRET'});
```
بعد از ایجاد یک نمونه در پروژه و ارسال مقادیر ورودی، یک API_ACCESS اختصاصی به شکل توکن برای شما تولید میشود که در درخواست های داخلی کتابخانه مورد استفاده قرار میگیرد.
## ![speaker](https://img.icons8.com/nolan/40/speaker.png) درخواست ها:
درخواست های API کتابخانه در حال حاضر در کلاس های Shop و User و Media دسته بندی شده اند.
در این پرونده، ما راهنمایی های کاملی را برای استفاده از توابع این کلا سها در اختیار شما قرار میدهیم. حتماً در ابتدا این راهنما را مطالعه کنید.
 سپس کافی است تا تابع معادل با درخواست خود را از نمونه ی ایجاد شده صدا بزنید تا به نتیجه ی مورد نظر دست یابید.
 برای مثال:

    //Get a shop with an ID 
    tayeh.getShop(2).then((data) =>  {
    //you have data. use it
    })
در اینجا شروع به ارائه ی دستورالعمل میکنیم...
### فروشگاه:
عنوان تابع|آرگومان های ورودی|پیشفرض ها|توضیحات|نمونه ی خروجی
|---------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------
| getShop |(shop_id:  number)||
| createShop |(params:  NewShop)||
| updateShop |(params:  UpdateShop)||
||||
| getShopPage |(page_number:  number, params?: { text?:  string; creator_id?:  number })||
||||
| getShopProducts |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| createShopProduct |(shop_id:  number, params:  NewProduct)||
| deleteShopProduct |(shop_id:  number, product_id:  number)||
| updateShopProduct |(shop_id:  number, params:  UpdateProduct)||
||||
| getShopTransactions |(shop_id:  number)||
| findShopTransactions |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| getProductTransactions |(shop_id:  number, product_id:  number)||
| deleteShopTransaction |(shop_id:  number, transaction_id:  number)||
| createShopTransaction |(shop_id:  number, params:  NewTransaction)||
| updateShopTransaction |(shop_id:  number, params:  UpdateTransaction)||
||||
| getShopInvoices |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| getShopInvoice |(shop_id:  number, invoice_id:  number)||
| deleteShopInvoice |(shop_id:  number, invoice_id:  number)||
| createShopInvoice |(shop_id:  number, params:  NewInvoice)||
| updateShopInvoice |(shop_id:  number, params:  UpdateInvoice)||
||||
| getShopSeries |(shop_id:  number, params?: { page?:  number; per_page?: number; type?:  string; page_unit?:  string; })||
||||
| getShopTotal |(shop_id:  number, params?: { page?:  number; per_page?: number; product_id?:  number; })||
||||
| getShopRevenue |(shop_id:  number, params?: { unit?:  string; product_id?:  number; start?:  number; end?:  number; })||
||||
| getShopCustomers |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| getShopCustomer |(shop_id:  number, customer_id:  number)||
| deleteShopCustomer |(shop_id:  number, customer_id:  number)||
| createShopCustomer |(shop_id:  number, params:  NewCustomer)||
| updateShopCustomer |(shop_id:  number, params:  UpdateCustomer)||
||||
| getShopUsers |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| getShopUser |(shop_id:  number, user_id:  number)||
| deleteShopUser |(shop_id:  number, user_id:  number)||
| createShopUser |(shop_id:  number, params:  NewUser)||
| updateShopUser |(shop_id:  number, params:  UpdateUser)||
||||
| getShopAddresses |(shop_id:  number, params?: { page?:  number; per_page?: number; search?:  string })||
| deleteShopAddress |(shop_id:  number, address_id:  number)||
| createShopAddress |(shop_id:  number, params:  NewAddress)||
| updateShopAddress |(shop_id:  number, params:  UpdateAddress)||
### کاربر:
عنوان تابع|آرگومان های ورودی|پیشفرض ها|توضیحات|نمونه ی خروجی
|---------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------
| getUserMe |()||
| getShopPrimary |()||
| createShopPrimary |(shop_id:  number)||
| getUserShops |(params?:  Pagination)||
| updateShop |(params?:  { page?:  number; per_page?: number; })||
### رسانه:
عنوان تابع|آرگومان های ورودی|پیشفرض ها|توضیحات|نمونه ی خروجی
|---------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------
| getMedia |(media_id:  number)||
| createMedia |(params:  NewMedia)||
## ![contribution](https://img.icons8.com/cotton/40/crowdfunding.png) مشارکت ها:
مشارکت های شما به گرمی پذیرفته میشوند. لطفاً اگر به مشکلی برخورد کردید یا از نظر شما جایی نیاز به بهبود بود، یک issue .در [گیت هاب تایه کلاینت](https://github.com/aref00/tayeh/issues) ارسال کنید
## پشتیبانی
هر نوع سوال یا انتقاد و پیشنهادی دارید میتوانید با تیم پشتیبانی ما مطرح کنید؛ مطمئناً در اولین فرصت پاسخ داده خواهد شد 
## پایان
در انتها امیدوارم تکنولوژی جدید ما بتواند بیشترین کمک را به شما بکند و شما نیز از انتخاب و استفاده ی تایه راضی باشید و لذت ببرید.
با تشکر از حضور و حمایتتان
