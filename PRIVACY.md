# Privacy Policy — Tickets Helper

**Last updated:** November 2026

## Summary

Tickets Helper is a browser extension that helps support agents quickly find and fill in a ready-made reply template based on the text of a customer request, and (optionally) open the related client card in the company's backoffice. **The extension does not send any personal data to the developer or to any third party.** The text of a request is processed locally, on the user's own device.

The only data that leaves the browser is described in the section "Client check in the backoffice" below. It happens only when the user explicitly clicks the "Process + open" button on the company's backoffice site, and it goes to the company's own backoffice system, never to the developer.

## What data the extension handles, and where it goes

| Data | What happens to it |
|---|---|
| Text pasted into the "Request" field (may contain a client ID, email, card number, deposit amount) | Processed entirely in the browser (locally) to detect a matching template and to extract values for substitution into that template. **Never sent to the developer or to any third party.** Cleared when the popup closes; nothing is logged or retained beyond the current session. The only value taken from it that is ever sent anywhere is the client ID, and only for the backoffice check described below. |
| Client ID | Used locally for template substitution. If the user clicks "Process + open" on the backoffice site, it is also sent to the company's backoffice API (`backofficewebadmin.betconstruct.com`) as part of a read-only lookup. It is never sent to the developer. |
| Backoffice session token | Read by the extension inside the backoffice page itself (from that page's own local storage) only at the moment of the client check, and used only for that single request to the backoffice API, exactly as the backoffice page does it. It is never passed to the extension popup, never stored, logged, or transmitted anywhere else. |
| Address (URL) of the active tab | Read when the popup is opened, only to determine whether the current tab is the company's backoffice (so the "Process + open" button is shown only there). Not stored or transmitted. The extension does not read or monitor other tabs or browsing activity. |
| Result of the client check | Only a minimal result (client found / not found / session expired) is returned to the popup and shown to the user. Client details from the backoffice response are not displayed, copied, or stored. |
| Template library | Stored locally in the browser's extension storage (`chrome.storage.local`), on the user's own device only. Not synced to a Google account, not accessible to other extensions or websites. |
| User preference (e.g. the "Header" toggle) | Stored locally the same way, purely to remember the user's UI preference between sessions. |
| Clipboard | The extension writes the finished reply text to the system clipboard only when the user clicks "Copy" (or when a template is selected and copied). No clipboard content is read, stored, or transmitted. |

## Network access

The extension makes **two types of network requests**:

1. **Template library update.** When the popup is opened, and at most once every 4 hours, the extension checks a single static file (a plain list of reply templates) hosted at a URL controlled by the developer (`raw.githubusercontent.com`), to keep the template library up to date. This request:
   - sends no personal data, request text, or identifying information — it is a plain file download;
   - does not execute any remote code — only text/JSON data is read and displayed;
   - fails silently if there is no network connection; the extension continues working with its last cached copy.

2. **Client check in the backoffice.** Only when the user clicks "Process + open" on the company's backoffice site, the extension sends one read-only (GET) request per click to the company's backoffice API to check whether the client ID from the request exists. The client ID is part of the request address, and the user's existing, already signed-in backoffice session is used for authorization. This request goes to the company's own backoffice system (the same system the user is working in), not to the developer. The extension only determines from the response whether the client exists; it does not read out, display, or store client details. It does not execute any remote code.

No other network requests are made. The extension does not use analytics, tracking pixels, advertising SDKs, or any third-party telemetry service.

## Permissions and why they are needed

| Permission | Purpose |
|---|---|
| `clipboardWrite` | To copy the prepared reply text to the clipboard when the user clicks "Copy". The clipboard is never read. |
| `storage` | To keep the template library and UI settings locally on the user's device (`chrome.storage.local`). |
| Host access to `raw.githubusercontent.com` | To download the static template list described above. |
| `activeTab` | To read the address of the active tab when the popup is opened, so the "Process + open" button is shown only on the company's backoffice, and to allow the function described below to run in that tab. |
| `scripting` | To run one fixed function (bundled in the extension; no remote code) in the active backoffice tab after the user clicks "Process + open", which performs the client check described above. |

## Data retention and deletion

All data stored by the extension lives only in the user's local browser storage. Nothing from the client check (client ID, token, response) is retained. Removing the extension, or clearing its data via the browser's extension settings, deletes everything immediately. The developer has no server-side copy of any user's data, because none is ever transmitted to the developer.

## Contact

Questions about this policy can be directed to the extension's developer/administrator within the organization that distributed it.

---

# Політика приватності — Tickets Helper (українською)

**Востаннє оновлено:** листопад 2026

## Коротко

Tickets Helper — розширення браузера, яке допомагає операторам підтримки швидко підібрати й заповнити готовий шаблон відповіді за текстом запиту клієнта та (за бажанням) відкрити відповідну картку клієнта в бекофісі компанії. **Розширення не надсилає жодних персональних даних розробнику чи будь-якій третій стороні.** Текст запиту обробляється локально, на пристрої користувача.

Єдині дані, які залишають браузер, описані в розділі «Перевірка клієнта в бекофісі» нижче. Це відбувається лише тоді, коли користувач сам натискає кнопку «Обробити + відкрити» на сайті бекофісу компанії, і дані йдуть до власної системи бекофісу компанії, а не до розробника.

## Які дані обробляються і що з ними відбувається

| Дані | Що з ними відбувається |
|---|---|
| Текст, вставлений у поле «Запит» (може містити ID клієнта, email, номер картки, суму депозиту) | Обробляється повністю в браузері (локально) для підбору шаблону та витягування значень для підстановки. **Ніколи не надсилається розробнику чи третім сторонам.** Очищується при закритті попапу, нічого не логується й не зберігається довше поточної сесії. Єдине значення з нього, яке взагалі кудись надсилається, — ID клієнта, і лише для перевірки в бекофісі, описаної нижче. |
| ID клієнта | Використовується локально для підстановки в шаблон. Якщо користувач натискає «Обробити + відкрити» на сайті бекофісу, ID також надсилається до API бекофісу компанії (`backofficewebadmin.betconstruct.com`) у вигляді запиту лише на читання. Розробнику він ніколи не надсилається. |
| Токен сесії бекофісу | Зчитується розширенням усередині самої сторінки бекофісу (з її власного локального сховища) лише в момент перевірки клієнта й використовується лише для цього одного запиту до API бекофісу — так само, як це робить сама сторінка бекофісу. Ніколи не передається в попап розширення, не зберігається, не логується й не надсилається в жодне інше місце. |
| Адреса (URL) активної вкладки | Зчитується при відкритті попапу, лише щоб визначити, чи поточна вкладка — бекофіс компанії (щоб кнопка «Обробити + відкрити» показувалась лише там). Не зберігається й не передається. Розширення не зчитує й не відстежує інші вкладки чи активність у браузері. |
| Результат перевірки клієнта | У попап повертається лише мінімальний результат (клієнта знайдено / не знайдено / сесію завершено) і показується користувачу. Дані клієнта з відповіді бекофісу не відображаються, не копіюються й не зберігаються. |
| Бібліотека шаблонів | Зберігається локально у сховищі розширення (`chrome.storage.local`), лише на пристрої користувача. Не синхронізується через Google-акаунт, недоступна іншим розширенням чи сайтам. |
| Налаштування користувача (напр. перемикач «Шапка») | Зберігається так само локально, лише щоб запам'ятати вибір інтерфейсу між сесіями. |
| Буфер обміну | Розширення записує готовий текст відповіді в буфер обміну лише за натисканням кнопки «Скопіювати» (або коли шаблон вибрано й скопійовано). Вміст буфера ніколи не зчитується, не зберігається і не передається. |

## Мережевий доступ

Розширення робить **два типи мережевих запитів**:

1. **Оновлення бібліотеки шаблонів.** Під час відкриття попапу, не частіше ніж раз на 4 години, розширення перевіряє один статичний файл (звичайний список шаблонів відповідей), розміщений за посиланням, яке контролює розробник (`raw.githubusercontent.com`), — щоб підтримувати бібліотеку шаблонів актуальною. Цей запит:
   - не передає жодних персональних даних, тексту запитів чи ідентифікуючої інформації — це просте завантаження файлу;
   - не виконує жодного віддаленого коду — читаються й відображаються лише текстові/JSON-дані;
   - мовчки завершується невдало за відсутності мережі; розширення продовжує працювати з останньою збереженою копією.

2. **Перевірка клієнта в бекофісі.** Лише коли користувач натискає «Обробити + відкрити» на сайті бекофісу компанії, розширення надсилає один запит лише на читання (GET) за кожен клік до API бекофісу компанії, щоб перевірити, чи існує клієнт із ID із запиту. ID клієнта міститься в адресі запиту, а для авторизації використовується вже наявна авторизована сесія користувача в бекофісі. Цей запит іде до власної системи бекофісу компанії (тієї самої, у якій працює користувач), а не до розробника. Із відповіді розширення лише визначає, чи існує клієнт; воно не зчитує, не показує й не зберігає дані клієнта. Віддалений код не виконується.

Жодних інших мережевих запитів не робиться. Розширення не використовує аналітику, пікселі відстеження, рекламні SDK чи будь-які сторонні сервіси телеметрії.

## Дозволи та навіщо вони потрібні

| Дозвіл | Призначення |
|---|---|
| `clipboardWrite` | Щоб копіювати підготовлений текст відповіді в буфер обміну за натисканням «Скопіювати». Буфер ніколи не зчитується. |
| `storage` | Щоб зберігати бібліотеку шаблонів і налаштування інтерфейсу локально на пристрої користувача (`chrome.storage.local`). |
| Доступ до хоста `raw.githubusercontent.com` | Щоб завантажувати описаний вище статичний список шаблонів. |
| `activeTab` | Щоб при відкритті попапу прочитати адресу активної вкладки, аби кнопка «Обробити + відкрити» показувалась лише на бекофісі компанії, і щоб описана нижче функція могла виконатися в цій вкладці. |
| `scripting` | Щоб після натискання «Обробити + відкрити» виконати в активній вкладці бекофісу одну фіксовану функцію (вшита в розширення, без віддаленого коду), яка виконує описану вище перевірку клієнта. |

## Зберігання та видалення даних

Усі дані, які зберігає розширення, існують лише в локальному сховищі браузера користувача. Нічого з перевірки клієнта (ID клієнта, токен, відповідь) не зберігається. Видалення розширення чи очищення його даних через налаштування браузера миттєво видаляє все. Розробник не має серверної копії жодних даних користувача, оскільки вони ніколи не передаються розробнику.

## Контакти

Питання щодо цієї політики можна направляти адміністратору розширення у вашій організації.
