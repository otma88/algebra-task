Postupak rješavanja:


1. Kreirao sam rute u web.php, auth middleware laravel ima već napravljen (nije potrebano raditi svoj) te sam te kreirane rute stavio u grupu auth
2. kreirao sam resursni kontroller za autore: php artisan make:controller AuthorController --resource
3. kreirao sam store methodu po uputama iz zadatka
4. kreiro sam custom middleware za provjeru tokena: php artisan make:middleware IsTokenValidated
5. u app/Http/Middleware folderu se nalazi taj IsTokenValidated.php
6. u handle methodi izvlačimo token iz headera i provjeravamo da li je token validan, ako nije redirectamo ga na početni page
7. treba i registrirati middleware u bootstrap/app.php i definirati napravljen middleware
8. feature test se kreira s naredbom: php artisan make:test AuthorsRouteTest
9. unutar tests/Feature/AuthorsRouteTest.php napisati metodu za provjeru status koda
10. pokretanje testa se izvršava ovon naredbom: php artisan test
