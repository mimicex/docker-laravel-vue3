# laravel 10 + vue3 + docker

# 建立 laravel 專案名稱為:test_laravel，可以改成你要的名稱
composer create-project --prefer-dist laravel/laravel test_laravel


cd test_laravel

# 安裝 vue3
npm install -D vue@next 
npm install -D @vue/compiler-sfc
npm install vue-loader@^16.2.0 --save-dev --legacy-peer-deps

# 安裝ui 環境
composer require laravel/ui

# 如果遇到 版本錯誤ERROR，基本上問題都是php版本問題，10對應的是 8.1 - 8.2
# 不清楚請先看官方說明支援的php版本
# https://laravel.com/docs/9.x/releases
( ! ) Fatal error: Composer detected issues in your platform: Your Composer dependencies require a PHP version ">= 8.1.0". You are running 8.0.22. 

# composer.json
{
    "config": {

        "platform-check": false
    }
}

composer dump


# 連線進去你的 images 下指令，會建立一份預設的vue3格式出來
php artisan ui vue


npm run dev