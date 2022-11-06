## [Гайд по работе со сборкой](/GUIDE.md) 📕

## Краткая инструкция по работе
Для начала работы у вас должент быть установлен **Node.js** 14 версии

### Основные команды для работы
- Установка - `npm i`
- Запуск локального сервера - `npm start`
- Сборка проекта, минификация скриптов <br>
и оптимизация изображений перед деплоем на прод - `npm run build`
- Запуск тестирования на соответствия кодгайдам - `npm test`
- Создание webp изображений в директории source - `npm run webp`

### Вся разработка ведётся в директории `source`
### Итоговый код попадает в директорию `build`

Деплой проекта
1) npm install --save-dev gulp-gh-pages

2) задача в галпе 
const path = require('path');
const ghPages = require('gulp-gh-pages');

gulp.task('deploy', function() {
  return gulp.src('./build/**/*')
    .pipe(ghPages());
});

3) в консоли выполняем команду gulp deploy
при успешном деплое в консоли видим сообщения
λ gulp deploy
[15:26:00] Using gulpfile D:\Github\designlab1\gulpfile.js
[15:26:00] Starting 'deploy'...
[15:27:01] [gh-pages] Cloning repo
[15:27:01] [gh-pages] Create branch `gh-pages` and checkout
[15:27:03] [gh-pages] Copying files to repository
[15:27:04] [gh-pages] Adding 351 files.
[15:27:04] [gh-pages] Committing "Update 2022-09-20T12:26:00.648Z"
[15:27:05] [gh-pages] Pushing to remote.
[15:27:10] Finished 'deploy' after 1.17 min

4) после этого в комитах появляется новая ветка gh-pages и просит сделать пулреквест

5) идем в settings => pages => branch gh-pages - выбираем папку /root => сохраняем

6) появляется ссылка на сайт, копируем ее в настройках в About, сохраняем
