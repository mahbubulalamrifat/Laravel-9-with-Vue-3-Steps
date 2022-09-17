# Laravel-9-with-Vue-3-Steps
1. composer create-project laravel/laravel projectName
2. npm install vue@next vue-loader@next
3. npm install
4. npm install @vitejs/plugin.vue

5. go to vite.config and add (import vue from '@vitejs/plugin-vue') and then add [ vue() ] in plugins array..
vite.config should look like this 
////// vite.config ////////
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import vue from '@vitejs/plugin-vue'

export default defineConfig({
    plugins: [
        vue(),
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
});



////// vite.config ////////

6. go to resource/js/app.js and add this 
import { createApp } from 'vue';

import app from './Project/app.vue'  ----> this will be your demo file where your vue will be written

createApp(app).mount('#app');

7. go to your welcome.blade.php to mount vue and add

<div id="app"></div>

@vite('resources/js/app.js')
