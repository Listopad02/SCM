# Release digital-office.mirea
Для релиза необходимо создать коммит, добавить ему тэг который должен быть инкрементально больше предыдущего тэга в формате [d-v0.0.x].

Если делать коммит через стандартное решение от VS Code: 
- Добавляем файлы в коммит;
- Пишем описание коммита;
- **Фиксируем**;
- Добавляем тэг ( это можно сделать с помощью [ctrl+shift+p] и ищем [Git: Create Tag]. Пишем имя тэга и описание. Для получения последнего тэга можно использовать команду [git describe --tags]);
- Пушим вместе с тэгом ( [ctrl+shift+p] и ищем [Git: Push (Follow Tags)] );
- Ждем примерно 3 минуты;
- Готово :)

# Поддомены

[iacmon.ru](https://iacmon.ru) - старая версия сайта, но не бесполезная. Там много сверстанных страниц, которые мы планируем плавно переносить на новую версию. стэк: обычный html, css, js, php. Под капотом есть битрикс но юзается только для авторизации.

[new.iacmon.ru](https://new.iacmon.ru) - новая версия сайта на реакте с блэкджеком и конструкторами. Новая система с возможностью конфигурации страниц по причудам пользователей. Имеется много задач по доработке компонентов.

[admin.iacmon.ru](https://admin.iacmon.ru) - админская часть для новой версии, написана на yii2. Есть много задач по доработке интерфейса.

[donm.mirea.ru](https://donm.mirea.ru) - Департамент Москвы, тоже на реакте, можно сказать ветка новой версии.

[admdonm.mirea.ru](https://admdonm.mirea.ru) - админка для Департамента

# Небольшое введение

В рамках проекта разрабатываются различные компоненты. В текущий момент они не структурированы. 
Преймуществами системы являются конструкторы, которые позволяют пользователям собирать свои страницы, формы и тп. 
Страницы системы собираются из конфигов в формате json. Конфиги страниц должны храниться в админской части сайта, 
но в текущий момент они храняться на фронтовой части в файлах [src/resources/pageConfigBeta.js] (Конфиг страниц), 
[src/resources/formConfig.js] (Конфиг форм). За сборку страниц отвечает компонент 
[src/PComponents/Report/Report.js] (Страницы), [src/PComponents/Renderer/Renderer.js] (Форм).
У каждого из компонентов на одном с ним уровне есть перечень используемых компонентов, он содержится в файле [componentsObject.js].

# Компоненты

src/components

src/componentsBeta

## Требования к компонентам

**Если компонент будет использоваться в конструкторе, то он должен соответствовать данным требованиям.**

### uid
<строка> Уникальный идентификатор компонента. Поле заполняется автоматически средствами бэка. Используется для получения данных с бэка.

### component
<строка> Тип компонента

### withApiData 
<булево> Будут ли запрашиваться данные с бэка

### options
<объект> Поле опций для компнента.

### data
<объект, строка> Поле для данных.

### styles
<строка> Поле стилей для обертки каждого компонента. Заполняется строкой. Требуется обработчик, который сможет преобразовывать стили в виде объекта в строку соответствующую styled.

### children
<массив> Поле принимающее массив объектов представляющих из себя объект компонента.

### loader
<булево> Добавлять ли лоадер к компоненту. (по умолчанию true).

# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

