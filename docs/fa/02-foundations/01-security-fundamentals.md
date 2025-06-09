**

**

  

اصول پایه ای  امنیت اپلیکیشن بر مفاهیم امنیتی بیان شده در این راهنمای بیان شده است و این در اصل یک راهنما برای توسعه دهندگان است.

  

 هدف این بخش، ارائه مقدمه‌ای بر اصول پایه و اولیه است که هر تیم توسعه‌ای باید با آن‌ها آشنا باشد.

  

#### مدل تضمین تکامل نرم‌افزار (Software Assurance Maturity Model)

  

مدل بلوغ تضمین نرم‌افزار ([SAMM](https://owaspsamm.org/about/)) زمینه‌ای برای دامنه امنیت نرم‌افزار و بنیان‌های یک رویه امنیتی خوب فراهم می‌کند:

  

[- [حاکمیت (Governance)]](https://owaspsamm.org/model/governance/)

[- [طراحی (Design)]](https://owaspsamm.org/model/design/)

[- [پیاده‌سازی (Implementation)]](- [Implementation](https://owaspsamm.org/model/implementation/))

[- [راستی‌آزمایی (Verification)]]()

- [عملیات (Operations)][sammo]

  

مدل SAMM این بنیان‌ امنیت نرم‌افزار را به عنوان عملکرد های تجاری (Business Functions) توصیف می‌کند که خود به روش های تجاری (Business Practices) تقسیم می‌شوند.

  

 مدل تضمین تکامل نرم‌افزار [([SAMM])](https://owaspsamm.org/about/) در سرتاسر این راهنمای توسعه‌ استفاده شده است؛ اکثر بخش‌های این راهنما حداقل به یکی از کارکردهای تجاری یا رویه‌های SAMM اشاره میکنه

  

#### سه‌گانه CIA

  

امنیت به زبان ساده، کنترل این است که چه کسی می‌تواند با اطلاعات شما تعامل داشته باشد، چه کاری می‌تواند با آن انجام دهد و چه زمانی می‌تواند با آن تعامل داشته باشد. این ویژگی‌های امنیت را می‌توان با استفاده از سه‌گانه CIA تعریف کرد.

  

CIA مخفف محرمانگی (Confidentiality)، یکپارچگی (Integrity) و دسترس‌پذیری (Availability) است و معمولاً به صورت یک مثلث که نمایانگر ارتباط قوی بین سه اصل آن است، به تصویر کشیده می‌شود. این سه‌گانه به عنوان پایه های  امنیت اپلیکیشن در نظر گرفته می‌شود و اغلب محرمانگی، یکپارچگی یا دسترس‌پذیری به عنوان ویژگی‌های اطلاعات یا فرآیندها در یک سیستم معین استفاده می‌شوند. سه‌گانه CIA را می‌توان با سه‌گانه AAA بسط داد:

  

 مجوزدهی (Authorization)، احراز هویت (Authentication) و حسابرسی (Auditing).

  

#### محرمانگی (Confidentiality)

  

محرمانگی، حفاظت از داده‌ها در برابر افشای غیرمجاز است؛ این مفهوم به معنای تضمین این است که فقط افرادی با مجوز صحیح می‌توانند به داده‌ها دسترسی داشته باشند و هم برای داده‌های ثابت (data at rest) و هم برای دیتا های در حال انتقال (data in transit) اعمال می‌شود.

  

 محرمانگی همچنین با مفهوم گسترده‌تر حریم خصوصی داده‌ها مرتبط است.

  

#### یکپارچگی (Integrity)

  

یکپارچگی به معنای محافظت از داده‌ها در برابر تغییرات غیرمجاز یا تضمین قابل اعتماد بودن داده‌ها است. این مفهوم شامل ایده پایداری داده ها  (داده‌ها به صورت تصادفی یا عمدی تغییر نکرده‌اند) و ایده یکپارچگی منبع (داده‌ها از یک منبع قانونی آمده یا توسط آن تغییر کرده‌اند) می‌باشد.

  

#### دسترس‌پذیری (Availability)

  

دسترس‌پذیری به معنای تضمین حضور اطلاعات یا منابع است. این مفهوم نه تنها به در دسترس بودن خود داده‌ها (مثلاً با استفاده از تکثیر داده‌ها) بلکه به محافظت از سرویس‌هایی که دسترسی به داده‌ها را فراهم می‌کنند (مثلاً با استفاده از توزیع بار یا load balancing) نیز متکی است.

  

#### سه‌گانه AAA

  

سه‌گانه CIA اغلب با احراز هویت (Authentication)، مجوزدهی (Authorization) و حسابرسی (Auditing) گسترش می‌یابد، زیرا این موارد ارتباط نزدیکی با مفاهیم CIA دارند. CIA وابستگی شدیدی به احراز هویت و مجوزدهی دارد؛ محرمانگی و یکپارچگی داده‌های حساس بدون آن‌ها قابل تضمین نیست. حسابرسی به این دلیل اضافه می‌شود که می‌تواند مکانیزمی برای اطمینان از اثبات هرگونه تعامل با سیستم فراهم کند.

  

#### احراز هویت (Authentication)

  

[احراز هویت](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet\)) به معنای صحت سنجی موجودیتی است که می‌خواهد با یک سیستم امن تعامل داشته باشد.

  

 به عنوان مثال، این موجودیت می‌تواند یک مکانیسم خودکار یا یک عامل انسانی باشد؛ در هر دو حالت، احراز هویت برای یک اپلیکیشن امن الزامی است.

  

#### مجوزدهی (Authorization)

  

[مجوزدهی](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet\)) به معنای مشخص کردن حقوق دسترسی به منابع امن (داده‌ها، سرویس‌ها، فایل‌ها، اپلیکیشن‌ها و غیره) است.

  

 این حقوق، سطوح دسترسی مربوط به منابعی  که در حال ایمن‌سازی هستند، توصیف می‌کنند. 

  

مجوزدهی معمولاً پس از احراز هویت موفق انجام می‌شود.

  

#### تعقیب و مراقبت (Auditing)

  

حسابرسی به معنای پیگیری رویدادهای سطح پیاده‌سازی و همچنین رویدادهای سطح دامنه (domain-level) است که در یک سیستم رخ می‌دهند.

  

 این امر به فراهم کردن مفهوم عدم انکار (non-repudiation) کمک می‌کند، به این معنی که تغییرات یا اقدامات انجام شده بر روی سیستم محافظت‌شده غیرقابل انکار هستند.

  

سامانه های تعقیب و مراقبت نه تنها می‌تواند اطلاعات فنی در مورد سیستم در حال اجرا را فراهم کند، بلکه اثباتی برای انجام اقدامات خاصی نیز ارائه می‌دهد. سوالات متداولی که تعقیب و مراقبت به آن‌ها پاسخ می‌دهد عبارتند از: «چه کسی، چه کاری را، چه زمانی و احتمالاً چگونه انجام داده است؟»

  

#### آسیب‌پذیری‌ها (Vulnerabilities)

  

NIST یک [آسیب‌پذیری](https://csrc.nist.gov/glossary/term/vulnerability) را اینگونه تعریف می‌کند: «ضعف در یک سیستم اطلاعاتی، جریان و سیاست های امنیتی سیستم در فرایند ها ، طبقه بندی های  داخلی یا پیاده‌سازی که می‌تواند توسط یک مهاجم مورد بهره‌برداری یا فعال‌سازی قرار گیرد.»

  

در هر اپلیکیشن بزرگی ضعف‌ها یا باگ‌های زیادی وجود دارد، اما اصطلاح آسیب‌پذیری عموماً برای آن دسته از ضعف‌ها یا باگ‌هایی به کار می‌رود که این خطر وجود دارد که یک مهاجم بتواند با سواستفاده از آن ها تهدید در راستای سیستم به وجود بیاورند.

  

آسیب‌پذیری‌های امنیتی شناخته‌شده عبارتند از:

  

- دزدیدن کلیک[(Clickjacking)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet\))

- حمله با اعتبارنامه‌های سرقت‌شده [(Credential Stuffing)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet\))

- نشت اطلاعات بین سایتی (Cross-site leaks)][csxsleaks]

- حملات نفی کردن سرویس[(Denial of Service)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet\)) (DoS)

- حملات [XSS مبتنی بر DOM](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet\)) شامل [DOM Clobbering](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/DOM_Clobbering_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/DOM_Clobbering_Prevention_Cheat_Sheet\))

- [(IDOR)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet\))

- [تزریق (Injection)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet\)) شامل [تزریق دستور سیستم‌عامل](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet\)) و [XXE][csxxe]

- [حملات تزریق مخصوص LDAP](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet\))

- [آلودگی پروتوتایپ  در جاوا اسکریپت (Prototype pollution)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet\))

- حملات [SSRF][csssrf]

- [تزریق SQL](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet\)) و استفاده از  [کوئری](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet\)) های پارامتری

- [تغییر ریدایرکت و فورواردهای اعتبارسنجی‌نشده](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet\))

- [حملات XSS][csxss] و [دور زدن فیلتر XSS][csxssevade]

  

#### HTTP و HTML

  

اگرچه HTTP و HTML به خودی خود از اصول بنیادین امنیت نیستند، اما اپلیکیشن‌های وب به ارتباطات HTTP و HTML متکی هستند. هم توسعه‌دهندگان اپلیکیشن و هم مهندسان امنیت باید درک خوبی از HTTP و زبان HTML به همراه کنترل‌های امنیتی مختلف آن‌ها داشته باشند.

  

اکثر تیم‌های توسعه اپلیکیشن با ارتباطات HTTP و استاندارد HTML آشنا هستند، اما در صورت لزوم به آموزش‌های[w3consortium] یا [W3 Schools][w3schools] مراجعه کنید. [مجموعه برگه‌های تقلب](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/%5D\(https://cheatsheetseries.owasp.org/\)) OWASP اطلاعات مورد نیاز برای تولید نرم‌افزار امن را در اختیار توسعه‌دهندگان اپلیکیشن‌های وب قرار می‌دهد:

  

- برگه تقلب [امنیت HTML5](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet\)) طیف گسترده‌ای از کنترل‌ها را، مطابق با [استاندارد زنده HTML][htmlliving] فعلی، توصیف می‌کند.

- برای CSS به برگه تقلب [(CSS)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet\)) مراجعه کنید.

- هدرهای HTTP باید امن باشند، برگه تقلب [هدرهای پاسخ امنیتی HTTP](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet\)) را ببینید.

- [امنیت انتقال اکید HTTP][csstrict] را قویاً مد نظر قرار دهید.

- اگر اپلیکیشن قابلیت آپلود فایل دارد، از برگه تقلب [آپلود فایل](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet\)) پیروی کنید.

- با استفاده از برگه تقلب [سیاست امنیت محتوا](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet\))، از وجود سیاست امنیت محتوا اطمینان حاصل کنید.

- از JWT برای یک اپلیکیشن جاوا استفاده می‌کنید؟ به برگه تقلب [توکن وب JSON](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet\)) مراجعه کنید.

- اشیاء را ذخیره یا ارسال می‌کنید؟ برگه تقلب [Deserialization (وارسیال‌سازی)](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet%5D\(https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet\)) را بررسی کنید.

  

#### منابع

  

- [[WHATWG] ](https://whatwg.org/)[استاندارد زنده HTML][htmlliving]

- OWASP [مجموعه برگه‌های تقلب](https://www.google.com/search?q=%5Bhttps://cheatsheetseries.owasp.org/%5D\(https://cheatsheetseries.owasp.org/\))

- OWASP [مدل بلوغ تضمین نرم‌افزار][samm] (SAMM)

  

---

  

راهنمای توسعه‌دهنده OWASP یک تلاش اجتماعی است؛ اگر چیزی نیاز به تغییر دارد، لطفاً [یک ایشو ثبت کنید][issue0401] یا [در گیت‌هاب ویرایش کنید][edit0401].

  

[csssrf]:  [https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet) [csstrict]: [https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet) [csxss]: [https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet) [csxsleaks]: [https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet) [csxssevade]: [https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet) [csxxe]: [https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet) [edit0401]: [https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/01-security-fundamentals.md](https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/01-security-fundamentals.md) [htmlliving]: [https://html.spec.whatwg.org/multipage/](https://html.spec.whatwg.org/multipage/) [issue0401]: [https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&amp;template=request.md&amp;title=Update:%2002-foundations/01-security-fundamentals](https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/01-security-fundamentals) [nistvuln]: [https://csrc.nist.gov/glossary/term/vulnerability](https://csrc.nist.gov/glossary/term/vulnerability) [samm]: [https://owaspsamm.org/about/](https://owaspsamm.org/about/) [sammd]: [https://owaspsamm.org/model/design/](https://owaspsamm.org/model/design/) [sammg]: [https://owaspsamm.org/model/governance/](https://owaspsamm.org/model/governance/) [sammi]: [https://owaspsamm.org/model/implementation/](https://owaspsamm.org/model/implementation/) [sammo]: [https://owaspsamm.org/model/operations/](https://owaspsamm.org/model/operations/) [sammv]: [https://owaspsamm.org/model/verification/](https://owaspsamm.org/model/verification/) [w3consortium]: [https://www.w3.org/](https://www.w3.org/) [w3schools]: [https://www.w3schools.com/html/](https://www.w3schools.com/html/) [whatwg]: [https://whatwg.org/](https://whatwg.org/)

  

**

  
  
**
