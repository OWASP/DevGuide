**

توسعه امن در استفاده های  تجاری [طراحی][sammd]، [پیاده‌سازی][sammi] و [اعتبار سنجی][sammv] از مدل تضمین  تکامل  نرم‌افزار OWASP یا [(SAMM)][samm] توصیف شده است.

همچنین برای توضیحی مناسب در مورد اینکه چرا افزودن امنیت به چرخه حیات توسعه نرم‌افزار مهم است، به [فرهنگ امنیت][culturewhy] مراجعه کنید.

  

#### پیش‌درآمد

  

بهترین مقدمه برای توسعه نرم‌افزار امن کاربردی، مقاله [تجزیه امنیت اپلیکیشن][sdlc] از OWASP است:

  

_یا چگونه کمتر نگران شدم و بر شانه‌های غول‌ها ایستادم._ - اسپایروس گاستراتوس، الی سعد

ظاهرا یک شعره :) 

  

بخش بزرگی از مطالب این بخش از پروژه [استانداردهای یکپارچه‌سازی][intstand] OWASP گرفته شده است.

  

#### مرور کلی

  

تقریباً تمام نرم‌افزارهای مدرن به شیوه‌ای تکرارشونده توسعه می‌یابند و از مرحله‌ای به مرحله دیگر عبور می‌کنند، مانند شناسایی نیازمندی‌های مشتری، پیاده‌سازی و تست. این مراحل به صورت چرخه‌ای در طول عمر اپلیکیشن تکرار می‌شوند. یک چرخه حیات توسعه نرم‌افزار (SDLC) مفهومی در زیر نشان داده شده است، در عمل ممکن است مراحل کمتر یا بیشتری بسته به فرآیندهای اتخاذ شده توسط سازمان وجود داشته باشد.

  

![چرخه حیات SDLC](https://github.com/alirezakkt/DevGuide/blob/main/docs/assets/images/sdlc_diag.png){ align=right width=180 }

  

با افزایش تعداد و پیچیدگی اکسپلویت‌ها علیه تقریباً هر اپلیکیشن یا سیستم تجاری، اکثر شرکت‌ها یک چرخه حیات توسعه نرم‌افزار امن (Secure SDLC) را اتخاذ کرده‌اند. SDLC امن هرگز نباید یک چرخه حیات جدا از چرخه حیات توسعه نرم‌افزار موجود باشد؛ بلکه باید همیشه همان چرخه حیات توسعه قبلی باشد اما با اقدامات امنیتی که در هر مرحله تعبیه شده است.

در غیر این صورت، ممکن است اقدامات امنیتی توسط تیم‌های توسعه پرمشغله کنار گذاشته شوند.
توجه داشته باشید که اگرچه Secure SDLC می‌تواند به صورت 'SSDLC' نوشته شود، اما تقریباً همیشه به صورت 'SDLC' نوشته می‌شود.

  

DevOps بسیاری از مراحل SDLC را یکپارچه و خودکار کرده و پایپ‌لاین‌های یکپارچه‌سازی مداوم (CI) و تحویل/استقرار مداوم (CD) را برای فراهم کردن بخش بزرگی از اتوماسیون SDLC پیاده‌سازی می‌کند.

DevOps و پایپ‌لاین‌ها با عواقب جدی در مقیاس بزرگ با موفقیت مورد اکسپلویت قرار گرفته‌اند و بنابراین، به روشی مشابه SDLC، بسیاری از اقدامات DevOps نیز امنیت را در خود جای داده‌اند. DevOps امن، یا DevSecOps، رویه‌های امنیتی را در فعالیت‌های DevOps تعبیه می‌کند تا در برابر حملات محافظت کرده و تست امنیت خودکار را برای SDLC فراهم کند.

  

نمونه‌هایی از چگونگی «پیاده سازی امنیت» در DevSecOps، فراهم کردن تست امنیت اپلیکیشن تعاملی، ایستا و پویا (IAST, SAST & DAST) و پیاده‌سازی امنیت زنجیره تأمین است، و فعالیت‌های امنیتی بسیار دیگری نیز وجود دارد که می‌توانند اعمال شوند. برای اطلاع از آخرین کنترل‌های امنیتی DevSecOps به [برگه تقلب امنیت CI/CD][cscicd] مراجعه کنید.

  

#### چرخه حیات توسعه امن

  

با مراجعه به چرخه توسعه [راهنمای امنیت اپلیکیشن][intstand] OWASP، چهار مرحله تکرارشونده در طول توسعه اپلیکیشن وجود دارد: نیازمندی‌ها، طراحی، پیاده‌سازی و راستی‌آزمایی. مراحل دیگر کمتر به صورت تکراری در چرخه توسعه انجام می‌شوند اما بخش به همان اندازه مهمی از SDLC را تشکیل می‌ده:
تحلیل شکاف (Gap Analysis)، معیارها (Metrics)، عملیات (Operation) و آموزش و فرهنگ‌سازی (Training & Culture Building).

  

تمام این مراحل SDLC باید فعالیت‌های امنیتی را در خود داشته باشند، به جای اینکه به عنوان فعالیت‌های جداگانه انجام شوند. اگر امنیت در این مراحل تعبیه شود، سربار آن بسیار کمتر شده و مقاومت تیم‌های توسعه در این مورد  کاهش می‌یابد.
هدف این است که SDLC امن به یک فرآیند آشنا مانند قبل تبدیل شود و تیم‌های توسعه مالکیت فعالیت‌های امنیتی در هر مرحله را بر عهده بگیرند.

  

ابزارها و منابع بسیاری از OWASP برای کمک به اعمال امنیت در SDLC وجود دارد.

  

* **نیازمندی‌ها (Requirements)**: این مرحله نیازمندی‌های عملکردی، غیرعملکردی و امنیتی اپلیکیشن را تعیین می‌کند.
* نیازمندی‌ها باید به صورت دوره‌ای بازبینی شده و از نظر کامل بودن و اعتبار بررسی شوند، و ارزش دارد که ابزارهای مختلف OWASP برای کمک به این امر در نظر گرفته شوند؛

    * [استاندارد راستی‌آزمایی امنیت اپلیکیشن (ASVS)][asvs] لیستی از نیازمندی‌ها برای توسعه امن را در اختیار توسعه‌دهندگان قرار می‌دهد،

    * پروژه [امنیت اپلیکیشن موبایل][masproject] یک استاندارد امنیتی برای اپلیکیشن‌های موبایل فراهم می‌کند

    * و [SecurityRAT][srat] به شناسایی مجموعه اولیه و پایه  نیازمندی‌های امنیتی کمک می‌کند.

  

* **طراحی (Design)**: طراحی امنیت در اپلیکیشن مهم است - هیچ وقت برای این کار دیر نیست اما هرچه زودتر انجام شود بهتر و آسان‌تر است.
* OWASP دو ابزار، [مدل‌سازی تهدید پایتونیک][pytm] و [اژدهای تهدید][tdtm]، برای مدل‌سازی تهدید به همراه بازی کردن امنیت با استفاده از [Cornucopia][cornucopia] فراهم می‌کند.

1

* **پیاده‌سازی (Implementation)**: پروژه [۱۰ کنترل پیشگیرانه برتر][proactive10] OWASP بیان می‌کند که آنها «مهم‌ترین کنترل‌ها و دسته‌های کنترلی هستند که هر توسعه‌دهنده‌ای باید مطلقاً، ۱۰۰٪ در هر پروژه‌ای بگنجاند» و این قطعاً توصیه خوبی است. پیاده‌سازی این کنترل‌ها می‌تواند درجه بالایی از اطمینان را فراهم کند که اپلیکیشن یا سیستم به طور منطقی امن خواهد بود. OWASP دو کتابخانه را فراهم می‌کند که می‌توانند در اپلیکیشن‌های وب گنجانده شوند، کتابخانه کنترل امنیتی [API امنیت سازمانی (ESAPI)][esapi-project] و [CSRFGuard][csrfguard] برای کاهش خطر حملات [جعل درخواست بین سایتی][cscsrf] (CSRF)، که به پیاده‌سازی این کنترل‌های پیشگیرانه کمک می‌کنند. علاوه بر این، [مجموعه برگه‌های تقلب][csproject] OWASP منبع ارزشمندی از اطلاعات و توصیه‌ها در مورد تمام جنبه‌های امنیت اپلیکیشن‌ها است.

  

* **راستی‌آزمایی (Verification)**: OWASP تعداد نسبتاً زیادی پروژه را فراهم می‌کند که به تست و راستی‌آزمایی کمک می‌کنند. این موضوع یک بخش در این راهنمای توسعه‌دهنده است و پروژه‌ها در انتهای این بخش لیست شده‌اند.

  

* **آموزش (Training)**: تیم‌های توسعه به طور مداوم به آموزش امنیت نیاز دارند. اگرچه آموزش بخشی از حلقه تکراری داخلی SDLC نیست، اما همچنان باید در چرخه حیات پروژه لحاظ شود. OWASP بسیاری از محیط‌ها و مواد آموزشی را فراهم می‌کند - لیست را در انتهای این بخش ببینید.

  

* **فرهنگ‌سازی (Culture Building)**: یک فرهنگ امنیتی خوب در یک سازمان تجاری به میزان زیادی به امن نگه داشتن اپلیکیشن‌ها و سیستم‌ها کمک خواهد کرد. فعالیت‌های زیادی وجود دارند که همگی با هم فرهنگ امنیت را ایجاد می‌کنند، پروژه [فرهنگ امنیت][culture] OWASP به جزئیات بیشتری در مورد این فعالیت‌ها می‌پردازد، و یک برنامه (Security Champion) خوب در کسب‌وکار، بنیادی برای یک وضعیت امنیتی خوب است.این راهنمای OWASP راهنمایی و مواد لازم را برای ایجاSecurity Champion در تیم‌های توسعه فراهم می‌کند .
* در حالت ایده‌آل، هر تیم باید یک قهرمان امنیت داشته باشد که علاقه خاصی به امنیت دارد و آموزش بیشتری دیده است، که این امر تیم را قادر می‌سازد تا امنیت را در کار خود تعبیه کند.

  

* **عملیات (Operations)**: [راهنمای DevSecOps][devsecops] OWASP توضیح می‌دهد که چگونه می‌توان یک پایپ‌لاین امن را به بهترین شکل پیاده‌سازی کرد، با استفاده از بهترین رویه‌ها و ابزارهای اتوماسیون برای کمک به «انتقال به چپ» (shift-left) مسائل امنیتی. برای اطلاعات بیشتر در مورد هر یک از موضوعات درون DevSecOps و به ویژه بخش‌های مربوط به عملیات، به راهنمای DevSecOps مراجعه کنید.

  

* **زنجیره تأمین (Supply chain)**: حملاتی که از زنجیره تأمین بهره‌برداری می‌کنند می‌توانند ویرانگر باشند و چندین مورد برجسته از محصولات که با موفقیت مورد اکسپلویت قرار گرفته‌اند، وجود داشته است. یک فهرست مواد نرم‌افزار (SBOM) اولین قدم برای جلوگیری از این حملات است و ارزش دارد که از استاندارد فهرست مواد (BOM) تمام پشته [CycloneDX][cyclone] OWASP برای [کاهش ریسک در زنجیره تأمین][cschain] استفاده شود.
* علاوه بر این، پروژه [Dependency-Track][deptrack] OWASP یک پلتفرم تحلیل مداوم SBOM است که می‌تواند با فراهم کردن کنترل بر SBOM، به جلوگیری از این اکسپلویت‌های زنجیره تأمین کمک کند.

  

* **وابستگی‌های شخص ثالث (Third party dependencies)**: پیگیری اینکه چه کتابخانه‌های شخص ثالثی در اپلیکیشن گنجانده شده‌اند، و چه آسیب‌پذیری‌هایی دارند، به راحتی قابل خودکارسازی است. بسیاری از مخازن عمومی مانند [github][github] و [gitlab][gitlab] این سرویس را به همراه برخی از طراحان تجاری ارائه می‌ده دهند. OWASP ابزار تحلیل ترکیب نرم‌افزار (SCA) [Dependency-Check][depcheck] را برای پیگیری کتابخانه‌های خارجی فراهم می‌کند.

  

* **تست امنیت اپلیکیشن (Application security testing)**: انواع مختلفی از تست‌های امنیتی وجود دارد که می‌توانند به صورت خودکار در زمان pull-request، merge یا به صورت شبانه اجرا شوند - یا در واقع به صورت دستی، اما وقتی خودکار باشند قدرتمندتر هستند. معمولاً تست امنیت ایستا اپلیکیشن (SAST) وجود دارد که کد را بدون اجرای آن تحلیل می‌کند، و تست امنیت پویای اپلیکیشن (DAST)، که ورودی را به اپلیکیشن در حال اجرا در یک sandbox یا محیط‌های ایزوله دیگر اعمال می‌کند. تست امنیت تعاملی اپلیکیشن (IAST) برای اجرای دستی و همچنین خودکار طراحی شده است، و بازخورد فوری در مورد تست‌ها هنگام اجرای آنها ارائه می‌دهد.

  

#### مطالعه بیشتر از OWASP

  

* [مجموعه برگه‌های تقلب][csproject]

* [برگه تقلب امنیت CI/CD][cscicd]

* [Cornucopia][cornucopia]

* استاندارد فهرست مواد (BOM) [CycloneDX][cyclone]

* [راهنمای DevSecOps][devsecops]

* [راهنمای قهرمانان امنیت][champions]

* [پروژه فرهنگ امنیت][culture]

* [۱۰ کنترل پیشگیرانه برتر][proactive10]

  

#### پروژه‌های راستی‌آزمایی OWASP

  

* [استاندارد راستی‌آزمایی امنیت اپلیکیشن (ASVS)][asvs]

* [پروژه Amass][amass]

* [Code Pulse][pulse]

* [Defect Dojo][defectdojo]

* [امنیت اپلیکیشن موبایل (MAS)][masproject]

* [Nettacker][net]

* [چارچوب تست تهاجمی وب (OWTF)][owtf]

* [راهنمای تست امنیت وب (WSTG)][wstg]

  

#### پروژه‌های آموزشی OWASP

  

* [پروژه امنیت API][apisec] (API Top 10)

* [Juice Shop][juice]

* [۱۰ مورد برتر موبایل][mobile10]

* [Security Shepherd][sec-shep]

* [Snakes And Ladders][snakes]

* [ده ریسک امنیتی برتر اپلیکیشن وب][top10]

* [WebGoat][webgoat]

  

#### منابع OWASP

  

* [کتابخانه CSRFGuard][csrfguard]

* [تحلیل ترکیب نرم‌افزار (SCA) Dependency-Check][depcheck]

* [پلتفرم تحلیل مداوم SBOM Dependency-Track][deptrack]

* [API امنیت سازمانی (ESAPI)][esapi-project]

* [راهنمای امنیت اپلیکیشن پروژه استانداردهای یکپارچه‌سازی][intstand]

* [امنیت اپلیکیشن موبایل (MAS)][mas]

* [مدل‌سازی تهدید پایتونیک][pytm]

* [اژدهای تهدید][tdtm]

* [SecurityRAT][srat] (ابزار خودکارسازی برای نیازمندی‌ها)

  

----

  

راهنمای توسعه‌دهنده OWASP یک تلاش اجتماعی است؛ اگر چیزی نیاز به تغییر دارد، لطفاً [یک ایشو (مسئله) ثبت کنید][issue0402] یا [در گیت‌هاب ویرایش کنید][edit0402].

  

[amass]: https://owasp.org/www-project-amass/

[apisec]: https://owasp.org/API-Security

[asvs]: https://owasp.org/www-project-application-security-verification-standard/

[champions]: https://owasp.org/www-project-security-champions-guidebook/

[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet

[cornucopia]: https://owasp.org/www-project-cornucopia/

[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet

[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet

[csproject]: https://owasp.org/www-project-cheat-sheets/

[csrfguard]: https://owasp.org/www-project-csrfguard/

[culture]: https://owasp.org/www-project-security-culture/

[culturewhy]: https://owasp.org/www-project-security-culture/stable/2-Why_Add_Security_In_Development_Teams/

[cyclone]: https://owasp.org/www-project-cyclonedx/

[depcheck]: https://owasp.org/www-project-dependency-check/

[deptrack]: https://dependencytrack.org/

[devsecops]: https://owasp.org/www-project-devsecops-guideline/

[defectdojo]: https://www.defectdojo.org/

[edit0402]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/02-secure-development.md

[esapi-project]: https://owasp.org/www-project-enterprise-security-api/

[github]: https://github.com/

[gitlab]: https://about.gitlab.com/

[issue0402]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/02-secure-development

[juice]: https://owasp.org/www-project-juice-shop/

[mas]: https://mas.owasp.org/

[masproject]: https://owasp.org/www-project-mobile-app-security/

[mobile10]: https://owasp.org/www-project-mobile-top-10/

[net]: https://owasp.org/www-project-nettacker/

[owtf]: https://owasp.org/www-project-owtf/

[proactive10]: https://owasp.org/www-project-proactive-controls/

[pulse]: https://owasp.org/www-project-code-pulse/

[pytm]: https://owasp.org/www-project-pytm/

[samm]: https://owaspsamm.org/about/

[sammd]: https://owaspsamm.org/model/design/

[sammi]: https://owaspsamm.org/model/implementation/

[sammv]: https://owaspsamm.org/model/verification/

[sdlc]: https://owasp.org/www-project-integration-standards/writeups/owasp_in_sdlc/

[sec-shep]: https://owasp.org/www-project-security-shepherd/

[snakes]: https://owasp.org/www-project-snakes-and-ladders/

[srat]: https://owasp.org/www-project-securityrat/

[tdtm]: https://owasp.org/www-project-threat-dragon/

[top10]: https://owasp.org/Top10/

[intstand]: https://owasp.org/www-project-integration-standards/

[webgoat]: https://owasp.org/www-project-webgoat/

[wstg]: https://owasp.org/www-project-web-security-testing-guide/

**
