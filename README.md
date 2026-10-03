# middleware-app-practice

## 概要

COACHTECH 教材 Tutorial 10-2「ミドルウェア ハンズオン演習」で作成した成果物です。

カスタムミドルウェアを使い、ユーザー権限に応じて管理者専用ページへのアクセスを制御するWebアプリケーションです。

## 使用技術

- PHP 8.x
- Laravel 10.x
- カスタムミドルウェア
- Laravel Fortify（認証）
- MySQL (Docker, Laravel Sail)

## 学んだこと

- ミドルウェアがRequest と Responseの間で処理を介在させる仕組み
- sail artisan make:middlewareコマンドによるカスタムミドルウェアの生成方法
- app/Http/Kernel.php の $middlewareAliasesにミドルウェアを登録し、admin という名前で呼び出せるようにする設定
- routes/web.php で　->middleware('admin') を付与して特定のルートを保護する方法

## 動作確認

- sail up -d で環境の起動
- sail artisan migrate --seed でデータベースの初期化とテストデータの投入を実行
- ブラウザで http://localhost にアクセス
- 管理者ユーザーでログインし、 /admin にアクセスすると管理者専用ページが表示されることを確認
- ログアウト後、一般ユーザーでログインし、 /admin にアクセスすると 403 Forbidden エラーが表示されることを確認
