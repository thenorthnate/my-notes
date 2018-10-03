# Web Programming Notes

## Vue
To set up a new Vue project (using Flask as your backend), follow these [steps](https://testdriven.io/developing-a-single-page-app-with-flask-and-vuejs):
1. `npm install -g vue-cli@2.9.3`
2. `vue init webpack client`
3. Vue build: `Runtime + Compiler`
4. Install vue-router?: `Yes`
5. Use ESLint to lint your code?: `Yes`
6. Pick an ESLint preset: `Airbnb`
7. Set up unit tests: `No`
8. Setup e2e tests with Nightwatch: `No`
9. Should we run npm install for you after the project has been created: `Yes, use NPM`

You may want to install these common libraries:
- Bulma
- Axios (`npm install axios@0.18.0 --save`)
- Echarts
- Echarts Stat
- Font Awesome

To import these libraries, include the import statement at the top of the main.js
file as shown below:
```javascript
// The Vue build version to load with the `import` command
// (runtime-only or standalone) has been set in webpack.base.conf with an alias.
import { library } from '@fortawesome/fontawesome-svg-core';
import {
  faCheck,
  faUpload,
  faDatabase,
  faPlus,
  faMinus,
  faArrowCircleUp,
  faCog,
  faFile,
  faFileExcel,
  faAngleRight,
  faAngleDown,
} from '@fortawesome/free-solid-svg-icons';
import { FontAwesomeIcon, FontAwesomeLayers } from '@fortawesome/vue-fontawesome';
import 'bulma/css/bulma.css';
import Vue from 'vue';
import App from './App';
import router from './router';

library.add(faCheck);
library.add(faUpload);
library.add(faDatabase);
library.add(faPlus);
library.add(faMinus);
library.add(faArrowCircleUp);
library.add(faCog);
library.add(faFile);
library.add(faFileExcel);
library.add(faAngleRight);
library.add(faAngleDown);
Vue.component('font-awesome-icon', FontAwesomeIcon);
Vue.component('font-awesome-layers', FontAwesomeLayers);

Vue.config.productionTip = false;

/* eslint-disable no-new */
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>',
});
```

You will want to edit the src/router/index.js file to incorporate your routes,
and change the mode to history mode by including `mode: 'history',` after the
routes definitions.

You will also want to remove the photo from the main.vue source. To run the application,
simply navigate to the "client" folder and run `npm run dev`. 
