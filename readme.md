SASS - это CSS-препроцессор
SASS-файлы имеют расширение .scss (обычно) или .sass (реже)
компилируется в CSS

NPM (Node Package Manager) -инструмент для установки пакетов через терминал
список пакетов и зависимостей хранится в файле package.json 

команда для установки пакета:
npm install (или npm i) package_name

установка на Ubuntu

curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - &&\
sudo apt-get install -y nodejs

для создания package.json 
npm init

для установки SASS 
npm i sass
он будет установлен в node_modules

при скачивании репы с гитхаба нужно запустить npm i для скачивания пакетов и зависимостей проекта

для компиляции SASS в CSS нужно создать в файле package.json
в разделе scripts 

"scripts": {
    "sass:build": "sass --no-source-map scss:www/css"
  },
  
  "scripts": {
    "sass:build": "sass каталог_с_SASS:каталог_для_CSS"
  },
  
  
команда для запуска скрипта 
npm run название скрипта

npm run sass:build

для автоматической компиляции нужно добавить еще один скрипт в package.json

"scripts": {
    "sass:build": "sass --no-source-map scss:www/css",
    "sass:watch": "sass --no-source-map --watch scss:www/css"
  },
  
  
установка Bootstrap 5
npm i bootstrap
создать файл bootstrap.scss в своем каталоге scss
импортировать в него основной файл из установленного бутстрапа
@import '../node_modules/bootstrap/scss/bootstrap.scss';

добавлять переменные нужно в него выше команды импорта бутстрапа!
посмотреть переменные которые можно переопределить можно в ффайле node_modules/bootstrap/scss/_variables.scss
переопределять их нужно в своем файле bootstrap.scss

подключение js бутстрапа
скопировать файл
node_modules/bootstrap/dist/js/bootstrap.bundle.min.js
и добавить его в свой каталог с js

---
установка font awesome
npm i @fortawesome/fontawesome-free
создаю новый scss файл fontawesome.scss
импортирую в него файлы

@import '../node_modules/@fortawesome/fontawesome-free/scss/fontawesome.scss';

@import '../node_modules/@fortawesome/fontawesome-free/scss/brands.scss';

@import '../node_modules/@fortawesome/fontawesome-free/scss/solid.scss';

также нужно скопировать веб шрифты 
fortawesome/fontawesome-free/webfonts и закинуть их в свой паблик каталог
---

установка Bootstrap Icons
npm i bootstrap-icons
создать в каталоге с scss файл bootstrap-icons.css и импортировать в него 
@import '../node_modules/bootstrap-icons/font/bootstrap-icons.scss';

скопировать каталог со шрифтами из node_modules\bootstrap-icons\font\fonts и закинуть её в свой каталог с css
