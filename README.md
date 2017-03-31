# Resume

A web Resume developed with Vue.js.
Demo: [http://cv.donggu.me](http://cv.donggu.me)

## Quick deploy
Directly copy files in `/dist` to your sever, and modify json file `resume-zh-CN.json` and `resume-En.json` in `/dist/static` to make it your own resume.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run all tests
npm test
```
## file inventory
- `/static/resume-zh-CN.json`  
  The Chinese version of your resume data.

- `/static/resume-En.json`  
  The English version of your resume data.

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
