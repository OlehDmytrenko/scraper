# Програмний модуль ig_scu_pi.pl | Вступ

**Програмний модуль ig_scu_pi.pl – "Завантаження повних текстів документів, що опубліковані вибраними користувачами мережі Instagram"**, який написаний мовою програмування `Perl 5` [v5.28.1](https://perldoc.perl.org/5.28.1/perl5281delta), призначений для завантаження повних текстів веб-документів, що опубліковані вибраними користувачами мережі`Instagram`, що розміщаються на веб-сайті [picuki.com](https://www.picuki.com/), а також перетворення скачаної інформації до внутрішнього системного вигляду. 

### Зміст
- [Позначення та найменування програмного модуля](#name)
- [Програмне забезпечення, необхідне для функціонування програмного модуля](#software)
- [Функціональне призначення](#function)
- [Опис логічної структури](#structure)
- [Використовувані технічні засоби](#hardware)
- [Виклик та завантаження](#run)

<a name="name"></a>
<h2>Позначення та найменування програмного модуля</h2>

Програмний модуль має позначення **"ig_scu_pi.pl"**.

Повне найменування програмного модуля – **"Завантаження повних текстів документів, що опубліковані вибраними користувачами мережі Instagram"**.

<a name="software"></a>
<h2>Програмне забезпечення, необхідне для функціонування програмного модуля</h2>

Для функціонування програмного модуля, написаного мовою програмування `Perl 5` ([v5.28.1](https://perldoc.perl.org/5.28.1/perl5281delta)), необхідне наступне програмне забезпечення та пакети:

- `Docker` [v20.10](https://docs.docker.com/engine/release-notes/#version-2010)
- `Kubernetes` [v1.22.4](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.4)
- `utf8 for Perl` [v5.28.1](https://perldoc.perl.org/5.28.1/utf8) (Perl pragma to enable/disable UTF-8 (or UTF-EBCDIC) in source code)
- `LWP for Perl` [v5.28.1](https://perldoc.perl.org/5.28.1/perl5281delta) (The World-Wide Web library for Perl)
- `HTTP for Perl` [v5.28.1](https://perldoc.perl.org/5.28.1/perl5281delta) (HTTP Handlers)

<a name="function"></a>
<h2>Функціональне призначення</h2>

Програмний модуль **"ig_scu_pi.pl"** призначений для завантаження повних текстів веб-документів, що опубліковані вибраними користувачами мережі `Instagram`, що розміщаються на веб-сайті [picuki.com](https://www.picuki.com/), а також перетворення завантаженої інформації до внутрішнього системного вигляду. 

<a name="structure"></a>
<h2>Опис логічної структури</h2>

Програмний модуль складається з частин:
-	Завантаження конфігуратора – переліку каналів відеохостінгу `Instagram` із локального диску сервера
-	Завантаження масивів даних, що відповідають заданому набору аккаунтів користувачів і розміщуються на веб-сайті [picuki.com](https://www.picuki.com/) за адресами вигляду https://www.picuki.com/profile/«Ідентифікатор_каналу»
-	Попередньої обробки даних, що відповідають заданому набору аккаунтів користувачів і витягу окремих полів
-	Контролю вмісту поля «посилання» на дублювання
-	Обробки завантажених повідомлень, формування переліку вихідних полів
-	Виводу документів у робочі файли на сервері
-	Заповнення журналів роботи програмного модуля
-	Виклику програмного модуля перетворення даних із внутрішнього системного формату до формату `XML`

Програмний модуль **"ig_scu_pi.pl"** завантажує масиви даних, що відповідають заданому набору аккаунтів користувачів і розміщуються на веб-сайтах [Instagram](https://www.instagram.com/) і [picuki.com](https://www.picuki.com/), виокремлює контент з цих  масивів, забирає посилання, якщо посилання ще не використовувалось раніше, продовжує обробку даних повідомлення, перетворює ці дані до внутрішнього системного формату, викликає програмний модуль перетворення даних із внутрішнього системного формату до формату `XML`.

<a name="hardware"></a>
<h2>Використовувані технічні засоби</h2>

Програмний модуль експлуатується на сервері (або у хмарі серверів) під управлінням операційної системи типу `Linux` (64 разряди). В основі управління всіх сервісів є система оркестрації `Kubernetes`, де всі контейнери працюють з використанням `Docker`.

<a name="run"></a>
<h2>Виклик та завантаження</h2>

Завантаження програмного модуля забезпечується введенням в командному рядку (або виказанням у таблиці `crontab`)  повного імені завантажувального модуля без додаткових параметрів. Дані, отримані в результаті застосування цього модуля перетворюються до формату `XML` за допомогою окремого модулю `convert-obr1.pl`.
