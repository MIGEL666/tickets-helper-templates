# Privacy Policy — Tickets Helper

**Last updated:** August 2026

## Summary

Tickets Helper is a browser extension that helps support agents quickly find and fill in a ready-made reply template based on the text of a customer request. **The extension does not collect, store, or transmit any personal data to the developer or any third party.** All processing happens locally, on the user's own device.

## What data the extension processes, and where it goes

| Data | What happens to it |
|---|---|
| Text pasted into the "Request" field | Processed entirely in the browser (locally) to detect a matching template and to extract values (e.g. ID, email, card number, deposit amount) for substitution into that template. **Never sent anywhere.** Cleared when the popup closes; nothing is logged or retained beyond the current session. |
| Template library | Stored locally in the browser's extension storage (`chrome.storage.local`), on the user's own device only. Not synced to a Google account, not accessible to other extensions or websites. |
| User preference (e.g. the "Header" toggle) | Stored locally the same way, purely to remember the user's UI preference between sessions. |
| Clipboard | The extension writes the finished reply text to the system clipboard only when the user clicks "Copy." No clipboard content is read, stored, or transmitted. |

## Network access

The extension makes **one type of network request**: once per day at most, it checks a single static file (a plain list of reply templates) hosted at a URL controlled by the developer, to keep the template library up to date. This request:
- sends no personal data, request text, or identifying information — it is a plain file download;
- does not execute any remote code — only text/JSON data is read and displayed;
- fails silently if there is no network connection; the extension continues working with its last cached copy.

No other network requests are made. The extension does not use analytics, tracking pixels, advertising SDKs, or any third-party telemetry service.

## Data retention and deletion

All data described above lives only in the user's local browser storage. Removing the extension, or clearing its data via the browser's extension settings, deletes everything immediately. The developer has no server-side copy of any user's data, because none is ever transmitted.

## Contact

Questions about this policy can be directed to the extension's developer/administrator within the organization that distributed it.

---

# Політика приватності — Tickets Helper (українською)

**Востаннє оновлено:** серпень 2026

## Коротко

Tickets Helper — розширення браузера, яке допомагає операторам підтримки швидко підібрати й заповнити готовий шаблон відповіді за текстом запиту клієнта. **Розширення не збирає, не зберігає й не передає жодних персональних даних розробнику чи будь-якій третій стороні.** Уся обробка відбувається локально, на пристрої користувача.

## Які дані обробляються і що з ними відбувається

| Дані | Що з ними відбувається |
|---|---|
| Текст, вставлений у поле "Запит" | Обробляється повністю в браузері (локально) для підбору шаблону та витягування значень (ID, email, номер картки, сума депозиту тощо) для підстановки. **Ніколи нікуди не надсилається.** Очищується при закритті попапу, нічого не логується й не зберігається довше поточної сесії. |
| Бібліотека шаблонів | Зберігається локально у сховищі розширення (`chrome.storage.local`), лише на пристрої користувача. Не синхронізується через Google-акаунт, недоступна іншим розширенням чи сайтам. |
| Налаштування користувача (напр. перемикач "Шапка") | Зберігається так само локально, лише щоб запам'ятати вибір інтерфейсу між сесіями. |
| Буфер обміну | Розширення записує готовий текст відповіді в буфер обміну лише за натисканням кнопки "Скопіювати". Вміст буфера ніколи не зчитується, не зберігається і не передається. |

## Мережевий доступ

Розширення робить **лише один тип мережевого запиту**: не частіше ніж раз на добу перевіряє один статичний файл (звичайний список шаблонів відповідей), розміщений за посиланням, яке контролює розробник, — щоб підтримувати бібліотеку шаблонів актуальною. Цей запит:
- не передає жодних персональних даних, тексту запитів чи ідентифікуючої інформації — це просте завантаження файлу;
- не виконує жодного віддаленого коду — читаються й відображаються лише текстові/JSON-дані;
- мовчки завершується невдало за відсутності мережі; розширення продовжує працювати з останньою збереженою копією.

Жодних інших мережевих запитів не робиться. Розширення не використовує аналітику, пікселі відстеження, рекламні SDK чи будь-які сторонні сервіси телеметрії.

## Зберігання та видалення даних

Усі описані вище дані існують лише в локальному сховищі браузера користувача. Видалення розширення чи очищення його даних через налаштування браузера миттєво видаляє все. Розробник не має серверної копії жодних даних користувача, оскільки вони ніколи нікуди не передаються.

## Контакти

Питання щодо цієї політики можна направляти адміністратору розширення у вашій організації.
