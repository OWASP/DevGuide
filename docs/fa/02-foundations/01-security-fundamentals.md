اصول پایه‌ای امنیت اپلیکیشن بر مفاهیم امنیتی بیان شده در این راهنما استوار است و این در اصل یک راهنما برای
توسعه‌دهندگان است.

هدف این بخش، ارائه مقدمه‌ای بر اصول پایه و اولیه است که هر تیم توسعه‌ای باید با آن‌ها آشنا باشد.

#### مدل تضمین تکامل نرم‌افزار (Software Assurance Maturity Model)

مدل بلوغ تضمین نرم‌افزار ([SAMM][samm]) زمینه‌ای برای دامنه امنیت نرم‌افزار و بنیان‌های یک رویه امنیتی خوب
فراهم می‌کند:

- [حاکمیت (Governance)][sammg]
- [طراحی (Design)][sammd]
- [پیاده‌سازی (Implementation)][sammi]
- [راستی‌آزمایی (Verification)][sammv]
- [عملیات (Operations)][sammo]

مدل SAMM این بنیان‌های امنیت نرم‌افزار را به عنوان عملکردهای تجاری (Business Functions) توصیف می‌کند که
خود به رویه‌های تجاری (Business Practices) تقسیم می‌شوند.

مدل تضمین تکامل نرم‌افزار ([SAMM][samm]) در سرتاسر این راهنمای توسعه استفاده شده است؛ اکثر بخش‌های این
راهنما حداقل به یکی از کارکردهای تجاری یا رویه‌های SAMM اشاره می‌کند.

#### سه‌گانه CIA

امنیت به زبان ساده، کنترل این است که چه کسی می‌تواند با اطلاعات شما تعامل داشته باشد، چه کاری می‌تواند
با آن انجام دهد و چه زمانی می‌تواند با آن تعامل داشته باشد. این ویژگی‌های امنیت را می‌توان با استفاده از
سه‌گانه CIA تعریف کرد.

CIA مخفف محرمانگی (Confidentiality)، یکپارچگی (Integrity) و دسترس‌پذیری (Availability) است و معمولاً
به صورت یک مثلث که نمایانگر ارتباط قوی بین سه اصل آن است، به تصویر کشیده می‌شود. این سه‌گانه به عنوان
پایه‌های امنیت اپلیکیشن در نظر گرفته می‌شود و اغلب محرمانگی، یکپارچگی یا دسترس‌پذیری به عنوان ویژگی‌های
اطلاعات یا فرآیندها در یک سیستم معین استفاده می‌شوند. سه‌گانه CIA را می‌توان با سه‌گانه AAA بسط داد:
مجوزدهی (Authorization)، احراز هویت (Authentication) و حسابرسی (Auditing).

#### محرمانگی (Confidentiality)

محرمانگی، حفاظت از داده‌ها در برابر افشای غیرمجاز است؛ این مفهوم به معنای تضمین این است که فقط افرادی
با مجوز صحیح می‌توانند به داده‌ها دسترسی داشته باشند و هم برای داده‌های ثابت (data at rest) و هم برای
داده‌های در حال انتقال (data in transit) اعمال می‌شود.

محرمانگی همچنین با مفهوم گسترده‌تر حریم خصوصی داده‌ها مرتبط است.

#### یکپارچگی (Integrity)

یکپارچگی به معنای محافظت از داده‌ها در برابر تغییرات غیرمجاز یا تضمین قابل اعتماد بودن داده‌ها است.
این مفهوم شامل ایده پایداری داده‌ها (داده‌ها به صورت تصادفی یا عمدی تغییر نکرده‌اند) و ایده یکپارچگی
منبع (داده‌ها از یک منبع قانونی آمده یا توسط آن تغییر کرده‌اند) می‌باشد.

#### دسترس‌پذیری (Availability)

دسترس‌پذیری به معنای تضمین حضور اطلاعات یا منابع است. این مفهوم نه تنها به در دسترس بودن خود داده‌ها
(مثلاً با استفاده از تکثیر داده‌ها) بلکه به محافظت از سرویس‌هایی که دسترسی به داده‌ها را فراهم می‌کنند
(مثلاً با استفاده از توزیع بار یا load balancing) نیز متکی است.

#### سه‌گانه AAA

سه‌گانه CIA اغلب با احراز هویت (Authentication)، مجوزدهی (Authorization) و حسابرسی (Auditing) گسترش
می‌یابد، زیرا این موارد ارتباط نزدیکی با مفاهیم CIA دارند. CIA وابستگی شدیدی به احراز هویت و مجوزدهی
دارد؛ محرمانگی و یکپارچگی داده‌های حساس بدون آن‌ها قابل تضمین نیست. حسابرسی به این دلیل اضافه می‌شود که
می‌تواند مکانیزمی برای اطمینان از اثبات هرگونه تعامل با سیستم فراهم کند.

#### احراز هویت (Authentication)

[احراز هویت](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) به معنای
صحت‌سنجی موجودیتی است که می‌خواهد با یک سیستم امن تعامل داشته باشد.

به عنوان مثال، این موجودیت می‌تواند یک مکانیسم خودکار یا یک عامل انسانی باشد؛ در هر دو حالت، احراز هویت
برای یک اپلیکیشن امن الزامی است.

#### مجوزدهی (Authorization)

[مجوزدهی](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) به معنای مشخص
کردن حقوق دسترسی به منابع امن (داده‌ها، سرویس‌ها، فایل‌ها، اپلیکیشن‌ها و غیره) است.

این حقوق، سطوح دسترسی مربوط به منابعی که در حال ایمن‌سازی هستند، توصیف می‌کنند.

مجوزدهی معمولاً پس از احراز هویت موفق انجام می‌شود.

#### تعقیب و مراقبت (Auditing)

حسابرسی به معنای پیگیری رویدادهای سطح پیاده‌سازی و همچنین رویدادهای سطح دامنه (domain-level) است که
در یک سیستم رخ می‌دهند.

این امر به فراهم کردن مفهوم عدم انکار (non-repudiation) کمک می‌کند، به این معنی که تغییرات یا اقدامات
انجام شده بر روی سیستم محافظت‌شده غیرقابل انکار هستند.

سامانه‌های تعقیب و مراقبت نه تنها می‌تواند اطلاعات فنی در مورد سیستم در حال اجرا را فراهم کند، بلکه
اثباتی برای انجام اقدامات خاصی نیز ارائه می‌دهد. سوالات متداولی که تعقیب و مراقبت به آن‌ها پاسخ می‌دهد
عبارتند از: «چه کسی، چه کاری را، چه زمانی و احتمالاً چگونه انجام داده است؟»

#### آسیب‌پذیری‌ها (Vulnerabilities)

NIST یک [آسیب‌پذیری][nistvuln] را اینگونه تعریف می‌کند: «ضعف در یک سیستم اطلاعاتی، رویه‌های امنیتی سیستم،
کنترل‌های داخلی یا پیاده‌سازی که می‌تواند توسط یک منبع تهدید مورد بهره‌برداری یا فعال‌سازی قرار گیرد.»

در هر اپلیکیشن بزرگی ضعف‌ها یا باگ‌های زیادی وجود دارد، اما اصطلاح آسیب‌پذیری عموماً برای آن دسته از
ضعف‌ها یا باگ‌هایی به کار می‌رود که این خطر وجود دارد که یک مهاجم بتواند با سواستفاده از آن‌ها یک تهدید
برای سیستم به وجود بیاورد.

آسیب‌پذیری‌های امنیتی شناخته‌شده عبارتند از:

- [دزدیدن کلیک (Clickjacking)](https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html)
- [حمله با اعتبارنامه‌های سرقت‌شده (Credential Stuffing)](https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html)
- [نشت اطلاعات بین سایتی (Cross-site leaks)][csxsleaks]
- [حملات نفی سرویس (Denial of Service)](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html) (DoS)
- حملات [XSS مبتنی بر DOM](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html) شامل [DOM Clobbering](https://cheatsheetseries.owasp.org/cheatsheets/DOM_Clobbering_Prevention_Cheat_Sheet.html)
- [IDOR](https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html)
- [تزریق (Injection)](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html) شامل [تزریق دستور سیستم‌عامل](https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet.html) و [XXE][csxxe]
- [حملات تزریق مخصوص LDAP](https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet.html)
- [آلودگی پروتوتایپ در جاوا اسکریپت (Prototype pollution)](https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet.html)
- حملات [SSRF][csssrf]
- [تزریق SQL](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) و استفاده از [کوئری](https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet.html) های پارامتری
- [تغییر ریدایرکت و فورواردهای اعتبارسنجی‌نشده](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html)
- حملات [XSS][csxss] و [دور زدن فیلتر XSS][csxssevade]

#### HTTP و HTML

اگرچه HTTP و HTML به خودی خود از اصول بنیادین امنیت نیستند، اما اپلیکیشن‌های وب به ارتباطات HTTP و HTML
متکی هستند. هم توسعه‌دهندگان اپلیکیشن و هم مهندسان امنیت باید درک خوبی از HTTP و زبان HTML به همراه
کنترل‌های امنیتی مختلف آن‌ها داشته باشند.

اکثر تیم‌های توسعه اپلیکیشن با ارتباطات HTTP و استاندارد HTML آشنا هستند، اما در صورت لزوم به
آموزش‌های [w3consortium] یا [W3 Schools][w3schools] مراجعه کنید. [مجموعه برگه‌های تقلب OWASP](https://cheatsheetseries.owasp.org/)
اطلاعات مورد نیاز برای تولید نرم‌افزار امن را در اختیار توسعه‌دهندگان اپلیکیشن‌های وب قرار می‌دهد:

- برگه تقلب [امنیت HTML5](https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet.html) طیف گسترده‌ای از کنترل‌ها را، مطابق با [استاندارد زنده HTML][htmlliving] فعلی، توصیف می‌کند.
- برای CSS به برگه تقلب [CSS](https://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet.html) مراجعه کنید.
- هدرهای HTTP باید امن باشند، برگه تقلب [هدرهای پاسخ امنیتی HTTP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet.html) را ببینید.
- [امنیت انتقال اکید HTTP][csstrict] را قویاً مد نظر قرار دهید.
- اگر اپلیکیشن قابلیت آپلود فایل دارد، از برگه تقلب [آپلود فایل](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html) پیروی کنید.
- با استفاده از برگه تقلب [سیاست امنیت محتوا](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)، از وجود سیاست امنیت محتوا اطمینان حاصل کنید.
- از JWT برای یک اپلیکیشن جاوا استفاده می‌کنید؟ به برگه تقلب [توکن وب JSON](https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet.html) مراجعه کنید.
- اشیاء را ذخیره یا ارسال می‌کنید؟ برگه تقلب [Deserialization (وارسیال‌سازی)](https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html) را بررسی کنید.

#### منابع

- [استاندارد زنده HTML][htmlliving] [WHATWG]
- OWASP [مجموعه برگه‌های تقلب](https://cheatsheetseries.owasp.org/)
- OWASP [مدل بلوغ تضمین نرم‌افزار][samm] (SAMM)

---

راهنمای توسعه‌دهنده OWASP یک تلاش اجتماعی است؛ اگر چیزی نیاز به تغییر دارد، لطفاً
[یک ایشو ثبت کنید][issue0401] یا [در گیت‌هاب ویرایش کنید][edit0401].

[csssrf]: https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html
[csstrict]: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html
[csxss]: https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
[csxsleaks]: https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet.html
[csxssevade]: https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet.html
[csxxe]: https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html
[edit0401]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/01-security-fundamentals.md
[htmlliving]: https://html.spec.whatwg.org/multipage/
[issue0401]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/01-security-fundamentals
[nistvuln]: https://csrc.nist.gov/glossary/term/vulnerability
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammg]: https://owaspsamm.org/model/governance/
[sammi]: https://owaspsamm.org/model/implementation/
[sammo]: https://owaspsamm.org/model/operations/
[sammv]: https://owaspsamm.org/model/verification/
[w3consortium]: https://www.w3.org/
[w3schools]: https://www.w3schools.com/html/
[whatwg]: <https://whatwg.org/>