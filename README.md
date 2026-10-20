# security-app-practice

## 概要

COACHTECH 教材 Tutorial 10-6「Webセキュリティ ハンズオン」で作成した成果物です。
CSRF保護とXSS対策を実装し、フォームの送信と入力内容の安全な表示を確認しました。

## 使用技術

- PHP 8.x
- Laravel 10.x
- CSRF 保護（`@csrf`）、XSS 対策（Blade の自動エスケープ）
- Docker
- Laravel Sail

## 学んだこと

- CSRF 攻撃の仕組みと @csrf ディレクティブ・CSRF トークンによる防御
- XSS 攻撃の仕組みと Blade の自動エスケープ（{{ }} と {!! !!} の違い）
- ユーザーの入力値を画面に表示する際に、HTMLエスケープが重要であること

## 動作確認

動作確認URL: http://localhost/contact

- お問い合わせフォームが表示される
- フォームに入力して送信できる
- 送信完了画面で入力内容が正しく表示される
- @csrfを削除して送信すると419 Page Expiredエラーになる（CSRF保護の確認）
- メッセージ欄に<script>alert('XSS')</script>を入力しても実行されない（XSS対策の確認）
