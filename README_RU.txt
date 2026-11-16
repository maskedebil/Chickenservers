ChickenStrike2Servers — Cloudflare Worker + статическая HTML-страница

ВАЖНО
Этот архив — стартовый серверный проект, а не готовый сетевой мод для Chicken Strike.
Он умеет создавать комнаты на 24 часа, проверять код комнаты и ретранслировать сообщения через WebSocket.
Чтобы игроки действительно играли вместе в Chicken Strike, сетевой клиент игры должен подключаться к /ws/КОД и отправлять/получать игровые сообщения. Сам по себе этот сайт не меняет игру.

СОСТАВ
- wrangler.jsonc — конфигурация Cloudflare Worker, Assets и Durable Object
- src/index.js — Worker и класс Durable Object Room
- game/index.html — веб-страница управления комнатами
- package.json — команды проекта

ПУБЛИКАЦИЯ ЧЕРЕЗ CLOUDFLARE WORKERS BUILDS (GitHub)
1. Распакуйте архив и загрузите ВСЕ файлы и папки в корень GitHub-репозитория.
   В корне должны быть wrangler.jsonc, package.json, папки src и game.
2. В Cloudflare создайте/откройте Worker, подключённый к этому GitHub-репозиторию.
3. Root directory: /
4. Build command: npm install
5. Deploy command: npm run deploy
6. После первого успешного развёртывания откройте выданный адрес *.workers.dev.

НЕ используйте настройки Cloudflare Pages для этого проекта: он использует Worker и Durable Objects.
Если Cloudflare спросит разрешить создание/изменение ресурсов Durable Objects, подтвердите это для своего проекта.

ПРОВЕРКА
Откройте https://ВАШ-ДОМЕН/api/health — ожидается {"ok":true,...}
На главной странице нажмите «Создать комнату».
