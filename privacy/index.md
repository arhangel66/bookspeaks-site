# BookSpeaks privacy policy

Effective date: 2 October 2026. This policy covers BookSpeaks 1.0 for iPhone.

## In short

BookSpeaks has no account, no advertising and no tracking. To see how the app is used and to fix crashes it uses Google's Firebase Analytics and Crashlytics, without the advertising ID. Reading and offline voices work on your iPhone, and your library and reading position are kept there. Our server is used for sending books to the app by e-mail, for voicing a book you order, for the online voices, for your credits and purchases, and for our own usage records, and it keeps as little as that needs.

## What is kept on your iPhone

Books you add from Files, AirDrop or «Open in», your library, bookmarks, reading and listening position, settings, downloaded voices and the count of your free offline hour. We do not receive them, except the text you send to be voiced: a book you order for server voicing, or the sentences an online voice reads (below).

## Server voicing

If you order a book to be voiced ahead of time on our server, paid in credits, the app sends that book's text (split into sentences, with the chosen voice and language) to our server. The server passes the text to a GPU machine rented from our GPU provider, Lium, and that machine turns it into audio. The GPU machine keeps the text only while it voices it and is removed when the job ends; the audio is deleted from it as soon as our server collects it. Our server deletes the audio when the app has downloaded it, and at most 48 hours after it was made; it keeps the job record with the text for 7 days after the job ends, then deletes it when it next handles a request. If our automatic check finds a sentence that was voiced badly, the server log keeps what the check heard for that sentence, as long as the logs (below). Books you do not order are never sent.

## Online voices

The online voices read over the internet and spend credits for every hour of listening. While one reads, the app sends each sentence to our server, which passes it through OpenRouter to the company whose model speaks that voice — Google (the Gemini voices) or xAI (the Grok voices Eve and Rex) — to turn it into speech, and streams the audio back. Our server does not keep the text or the audio: it records only the request, the day and the credits spent, and keeps that with your credit record (below). Offline voices and the Apple voice never send text anywhere.

## Purchases and credits

Purchases are made through Apple; we never see your card or Apple ID. To keep your credit balance, our server records, under the appTransactionID that the App Store gives your copy of the app: the App Store transaction ids of your purchases, the product and credits bought, the free credits granted, the credits held and spent for each voicing order and for online listening, and refunds Apple reports to us. This record is kept while your copy of the app may use its credits, until you ask us to delete it. Nightly copies of it are kept for 30 days, on the same server and, encrypted, in an off-site backup (see «Who processes data for us»).

## What our server receives and keeps

When you open the «add by mail» screen, listen with an online voice or download a Russian voice («Света» or «Дима»), the app registers with our server (Vultr, Warsaw, Poland). For mail, the server keeps:

- Device token. A random token issued to the app, kept in the iPhone keychain. The server stores only its hash, not the token. It is not the advertising ID or any Apple device ID. Kept until you ask us to delete it.

- Your personal BookSpeaks address (random letters @bookspeaks.app). Kept until you ask us to delete it. When you change the address, the old one is retired and never given to anyone else.

- Approved senders: the e-mail addresses you allow to send you books, and your rule for other senders (ask or reject). Kept until you remove them in the app or ask us to delete them.

- Mailed books. A book file sent to your address, with its title, author and cover, is kept until the app downloads it, and at most 7 days. The text and headers of the e-mail are not kept.

- Addresses of unknown senders. If someone not on your list mails you, their address is kept with the held book until you accept or decline it, or with the rejection note, at most 7 days.

- Short-lived security records: the number of mails per device and the IP address used to register, to stop abuse. They are deleted after 24 hours, when the server next handles mail or a registration.

The 7-day and 24-hour limits are enforced when the server next handles a request, so a record can outlive them by the time until that next request.

## Usage data

The app sends our own server short events about how it is used: first launch, a book imported (its format and whether by file or mail), listening started and listening time, voice samples played and the voice chosen, a voicing order shown and confirmed (hours, credits, wait), the purchase screen shown, and a failed purchase with Apple's error type. Our server adds purchases, refunds and voicing jobs (credits, audio hours, cost). Each event has its time, the App Store country and the app version. They never contain book text, titles, file names or anything you type; a book is marked by a random number made only for this, not the id used elsewhere. Events are linked to your appTransactionID, not to your name or e-mail; we do not use the advertising ID and do not ask to track you. We use them only to understand which features matter and to check purchases, not for tracking or advertising, and we do not share them. They are deleted after 13 months; only totals are kept. Backups can hold an event up to 31 days longer.

The app also uses Firebase Analytics, a Google service, to count how it is used. It sends Google events such as the first launch, sessions, screens opened, purchases (product and price) and the kinds of events listed above, with a random app-instance ID that Firebase makes for this copy of the app, the device model, iOS version, app version and language, and an approximate location (country, region, city) that Google derives from your IP address. These events never contain book text, titles, file names or anything you type, and they are not linked to your appTransactionID, your name or your e-mail. We have turned off the advertising ID, and Firebase data is not used for advertising or tracking. Google keeps this event data for 14 months; after that only totals remain. We cannot find your Firebase data by your e-mail or BookSpeaks address, so it is not deleted on request: it ages out after 14 months. The records our own server keeps — purchases, credits and voicing costs — stay as described above.

## Crash reports

If the app crashes, Firebase Crashlytics, a Google service, sends Google a crash report: where in the code the app stopped (the stack trace) and its state at that moment, the device model, iOS version, app version, the last app events before the crash, and a random installation ID made by Firebase. A crash report contains no book text and is not linked to your appTransactionID, your name or your e-mail. Google keeps crash reports and their installation IDs for 90 days, then deletes them.

## Server logs

Like any web server, ours writes logs. The web server's log holds the IP address, time and requested address of each request. Because the app sends an approved sender's e-mail address as part of the request address, logs can contain sender addresses, and the voicing log can contain what our check heard for a badly voiced sentence. Logs are used only to run and protect the service. They have no fixed time limit: older entries are deleted as the logs reach their size limit or are rotated (some copies after 5 weeks), or when the web server is reinstalled. We cannot delete single entries from them on request.

## Who processes data for us

- Cloudflare receives mail sent to @bookspeaks.app and passes it to our server (Email Routing and a Worker that stores nothing itself). Cloudflare keeps a record of each mail — sender, recipient, subject and delivery status — for 31 days.

- Our server host (Vultr), in Warsaw, Poland (EU).

- Backblaze (B2 storage, EU region) holds our encrypted nightly backup. It is a copy of the credit record, the usage events, any feedback you sent (with the e-mail you gave there) and the voicing costs, encrypted on our server before it leaves, so Backblaze sees only unreadable data. It holds no book text, audio, device tokens or mail addresses of the «add by mail» screen. Backups are kept for 30 days.

- Our GPU provider (Lium) runs the machines that voice a book you order; they see its text while voicing it.

- OpenRouter receives each sentence an online voice reads and passes it to the company whose model speaks that voice.

- Google (Gemini text-to-speech) and xAI (Grok voices) turn those sentences into speech.

- Apple processes purchases and tells our server about them and about refunds.

- Google (Firebase) receives the app's usage events and crash reports, as described in «Usage data» and «Crash reports», and processes them for us. It may process them outside the EU.

- Hugging Face serves voice files when you download a voice. It sees your IP address and the file requested, nothing about you or your books.

We do not sell or share your data, and we do not use it for advertising.

## Deleting your data

In the app you can remove an approved sender, change your address, decline a held book and discard a failed import. The app cannot yet delete everything the server keeps about your device. To delete it, write to [support@bookspeaks.app](mailto:support@bookspeaks.app) from any address and include your BookSpeaks address (Settings → mail). We delete the device record, the address, the sender list and any waiting books within 30 days. Ask in the same letter and we also delete your credit balance and purchase record within 30 days; unspent credits are lost. Nightly copies of the credit record age out within 31 days after that; server logs are not edited (see «Server logs»).

Deleting the app removes your books from the iPhone, but not the device token in the iPhone keychain: if you install BookSpeaks again, it reconnects to the same server record. Ask us to delete it as above.

## Children

BookSpeaks is not directed at children under 13 and we do not knowingly collect their data. If you believe a child has sent us data, write to us and we will delete it.

## Changes

If this policy changes, we will update this page and its effective date. New kinds of data will be described here before they ship.

## Contact

[support@bookspeaks.app](mailto:support@bookspeaks.app)

# Политика конфиденциальности BookSpeaks

Действует с 2 октября 2026 года. Относится к BookSpeaks 1.0 для iPhone.

## Коротко

В BookSpeaks нет учётной записи, рекламы и слежки. Чтобы видеть, как пользуются приложением, и исправлять сбои, оно использует Firebase Analytics и Crashlytics от Google, без рекламного идентификатора. Чтение и офлайн-голоса работают на iPhone, библиотека и место чтения хранятся на нём. Наш сервер нужен для отправки книг в приложение по почте, для озвучки заказанной книги, для онлайн-голосов, для ваших кредитов и покупок и для наших собственных записей об использовании и хранит лишь то, что для этого необходимо.

## Что хранится на iPhone

Книги, добавленные из «Файлов», через AirDrop или «Открыть в», библиотека, закладки, место чтения и прослушивания, настройки, скачанные голоса и счётчик бесплатного офлайн-часа. Мы их не получаем, кроме текста, который вы отдаёте на озвучку: книги, заказанной для озвучки на сервере, или предложений, которые читает онлайн-голос (ниже).

## Озвучка на сервере

Если вы заказываете озвучку книги заранее на нашем сервере за кредиты, приложение отправляет текст этой книги (по предложениям, с выбранным голосом и языком) на наш сервер. Сервер передаёт текст GPU-машине, арендованной у нашего поставщика вычислений Lium, и она превращает его в звук. GPU-машина держит текст только пока озвучивает его и удаляется после окончания заказа; звук стирается с неё, как только наш сервер его забрал. Наш сервер удаляет звук, когда приложение его скачало, и не позже чем через 48 часов после создания; запись заказа с текстом он хранит 7 дней после окончания заказа и удаляет её при следующем обращении к серверу. Если наша автоматическая проверка находит плохо озвученное предложение, журнал сервера хранит то, что проверка в нём расслышала, столько же, сколько сами журналы (ниже). Книги, которые вы не заказывали, никуда не отправляются.

## Онлайн-голоса

Онлайн-голоса читают через интернет и тратят кредиты за каждый час прослушивания. Пока такой голос читает, приложение отправляет каждое предложение на наш сервер, а он передаёт его через OpenRouter компании, чья модель озвучивает этот голос, — Google (голоса Gemini) или xAI (голоса Grok: Eve и Rex), — чтобы превратить в речь, и возвращает звук в приложение. Наш сервер не хранит ни текст, ни звук: он записывает только запрос, день и потраченные кредиты и хранит это вместе с записью о ваших кредитах (ниже). Офлайн-голоса и голос Apple никуда не отправляют текст.

## Покупки и кредиты

Покупки проходят через Apple; мы не видим вашу карту и Apple ID. Чтобы вести баланс кредитов, наш сервер хранит под appTransactionID, который App Store выдаёт вашей копии приложения: номера транзакций App Store ваших покупок, купленный продукт и кредиты, выданные бесплатные кредиты, кредиты, удержанные и потраченные на каждый заказ озвучки и на онлайн-прослушивание, и возвраты, о которых сообщает Apple. Эта запись хранится, пока ваша копия приложения может тратить кредиты, или до вашей просьбы удалить её. Ночные копии этой записи хранятся 30 дней на том же сервере и в зашифрованном виде во внешней резервной копии (см. «Кто обрабатывает данные для нас»).

## Что получает и хранит наш сервер

Когда вы открываете экран «добавить по почте», слушаете онлайн-голосом или скачиваете русский голос («Света» или «Дима»), приложение регистрируется на нашем сервере (Vultr, Варшава, Польша). Для почты сервер хранит:

- Токен устройства. Случайный токен, выданный приложению и хранящийся в связке ключей iPhone. Сервер хранит только его хеш, а не сам токен. Это не рекламный идентификатор и не идентификатор устройства Apple. Хранится, пока вы не попросите его удалить.

- Ваш личный адрес BookSpeaks (случайные буквы @bookspeaks.app). Хранится, пока вы не попросите его удалить. При смене адреса старый выводится из работы и никому больше не выдаётся.

- Разрешённые отправители: адреса, с которых вам можно присылать книги, и правило для остальных (спрашивать или отклонять). Хранятся, пока вы не удалите их в приложении или не попросите удалить нас.

- Присланные книги. Файл книги, пришедший на ваш адрес, с названием, автором и обложкой хранится, пока приложение его не скачает, но не дольше 7 дней. Текст и заголовки письма не сохраняются.

- Адреса незнакомых отправителей. Если вам пишет кто-то не из списка, его адрес хранится вместе с задержанной книгой, пока вы её не примете или не отклоните, или вместе с отметкой об отказе, не дольше 7 дней.

- Короткие записи для защиты: число писем на устройство и IP-адрес при регистрации, чтобы не допустить злоупотреблений. Они удаляются через 24 часа, когда сервер в следующий раз обрабатывает почту или регистрацию.

Сроки 7 дней и 24 часа проверяются, когда сервер в следующий раз обрабатывает запрос, поэтому запись может пролежать чуть дольше — до этого следующего запроса.

## Данные об использовании

Приложение отправляет нашему собственному серверу короткие события о том, как им пользуются: первый запуск, добавленная книга (формат и откуда — файл или почта), начало прослушивания и время прослушивания, прослушанные образцы голосов и выбранный голос, показанный и подтверждённый заказ озвучки (часы, кредиты, ожидание), показ экрана покупки и неудачная покупка с типом ошибки Apple. Сервер добавляет покупки, возвраты и заказы озвучки (кредиты, часы аудио, стоимость). У каждого события есть время, страна App Store и версия приложения. В них никогда нет текста, названий, имён файлов книг и ничего, что вы вводите; книга помечена случайным номером, созданным только для этого. События связаны с вашим appTransactionID, а не с именем или почтой; мы не используем рекламный идентификатор и не просим разрешения на отслеживание. Мы используем их только чтобы понимать, какие функции важны, и проверять покупки, — не для слежки и рекламы, и никому их не передаём. Они удаляются через 13 месяцев; остаются только итоговые цифры. Резервные копии могут хранить событие до 31 дня дольше.

Ещё приложение использует Firebase Analytics, сервис Google, чтобы считать, как им пользуются. Оно отправляет Google события: первый запуск, сеансы, открытые экраны, покупки (продукт и цена) и события того же рода, что перечислены выше, — со случайным идентификатором, который Firebase создаёт для этой копии приложения, моделью устройства, версией iOS, версией и языком приложения и примерным местоположением (страна, регион, город), которое Google определяет по IP-адресу. В этих событиях никогда нет текста, названий, имён файлов книг и ничего, что вы вводите, и они не связаны с вашим appTransactionID, именем или почтой. Рекламный идентификатор мы отключили, данные Firebase не используются для рекламы и слежки. Google хранит эти события 14 месяцев, после этого остаются только итоговые цифры. Найти ваши данные в Firebase по почте или адресу BookSpeaks мы не можем, поэтому по просьбе они не удаляются: они исчезают через 14 месяцев. Записи нашего собственного сервера — покупки, кредиты и стоимость озвучки — хранятся так, как описано выше.

## Отчёты о сбоях

Если приложение падает, Firebase Crashlytics, сервис Google, отправляет Google отчёт о сбое: место в коде, где приложение остановилось (трассировку стека), и его состояние в этот момент, модель устройства, версию iOS, версию приложения, последние события приложения перед сбоем и случайный идентификатор установки, созданный Firebase. В отчёте нет текста книг, и он не связан с вашим appTransactionID, именем или почтой. Google хранит отчёты о сбоях и их идентификаторы установки 90 дней, затем удаляет.

## Журналы сервера

Как любой веб-сервер, наш ведёт журналы. Журнал веб-сервера хранит IP-адрес, время и запрошенный адрес каждого запроса. Приложение передаёт адрес разрешённого отправителя в адресе запроса, поэтому в журналах могут оказаться адреса отправителей, а в журнале озвучки — то, что наша проверка расслышала в плохо озвученном предложении. Журналы нужны только для работы и защиты сервиса. Срока хранения по времени у них нет: старые записи удаляются, когда журнал достигает предельного размера или сменяется (часть копий — через 5 недель), или при переустановке веб-сервера. Удалить из них отдельные записи по просьбе мы не можем.

## Кто обрабатывает данные для нас

- Cloudflare принимает письма на @bookspeaks.app и передаёт их нашему серверу (Email Routing и Worker, который сам ничего не хранит). Cloudflare хранит запись о каждом письме — отправитель, получатель, тема и статус доставки — 31 день.

- Хостинг нашего сервера (Vultr), Варшава, Польша (ЕС).

- Backblaze (хранилище B2, регион ЕС) хранит нашу зашифрованную ночную резервную копию. В ней копия записи о кредитах, события об использовании, отправленные вами отзывы (с почтой, которую вы там указали) и стоимость озвучки; она шифруется на нашем сервере до отправки, поэтому Backblaze видит только нечитаемые данные. В ней нет текста книг, звука, токенов устройств и адресов почты с экрана «добавить по почте». Копии хранятся 30 дней.

- Наш поставщик GPU (Lium) даёт машины, которые озвучивают заказанную книгу; они видят её текст, пока озвучивают.

- OpenRouter получает каждое предложение, которое читает онлайн-голос, и передаёт его компании, чья модель озвучивает этот голос.

- Google (синтез речи Gemini) и xAI (голоса Grok) превращают эти предложения в речь.

- Apple проводит покупки и сообщает нашему серверу о них и о возвратах.

- Google (Firebase) получает события об использовании приложения и отчёты о сбоях, как сказано в разделах «Данные об использовании» и «Отчёты о сбоях», и обрабатывает их для нас. Он может обрабатывать их за пределами ЕС.

- Hugging Face отдаёт файлы голосов, когда вы скачиваете голос. Он видит ваш IP-адрес и запрошенный файл, но ничего о вас и ваших книгах.

Мы не продаём и не передаём ваши данные и не используем их для рекламы.

## Удаление данных

В приложении можно удалить разрешённого отправителя, сменить адрес, отклонить задержанную книгу и убрать неудавшийся импорт. Удалить всё, что сервер хранит о вашем устройстве, приложение пока не умеет. Для этого напишите на [support@bookspeaks.app](mailto:support@bookspeaks.app) с любого адреса и укажите свой адрес BookSpeaks (Настройки → почта). Мы удалим запись устройства, адрес, список отправителей и ждущие книги в течение 30 дней. Попросите в том же письме, и в течение 30 дней мы удалим и баланс кредитов с записью о покупках; неистраченные кредиты при этом пропадут. Ночные копии записи о кредитах исчезают после этого в течение 31 дня; журналы сервера не правятся (см. «Журналы сервера»).

Удаление приложения стирает книги с iPhone, но не токен устройства в связке ключей: после повторной установки BookSpeaks снова подключится к той же записи на сервере. Чтобы её удалить, напишите нам, как сказано выше.

## Дети

BookSpeaks не предназначен для детей младше 13 лет, и мы сознательно не собираем их данные. Если вы считаете, что ребёнок передал нам данные, напишите нам, и мы их удалим.

## Изменения

Если политика изменится, мы обновим эту страницу и дату вступления в силу. Новые виды данных мы опишем здесь до их выхода.

## Связь

[support@bookspeaks.app](mailto:support@bookspeaks.app)
