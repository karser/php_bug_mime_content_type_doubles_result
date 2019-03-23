Starting from php 7.3.2 function mime_content_type doubles the result for xlsx files created in LibreOffice (6.0.7.3). While php 7.3.1 works correctly.


```
docker build --no-cache --build-arg PHP_VER=7.3.2 .

Step 5/5 : RUN php -r "var_dump(mime_content_type('/test.xlsx'));"
 ---> Running in 71f6655ae0ed
string(130) "application/vnd.openxmlformats-officedocument.spreadsheetml.sheetapplication/vnd.openxmlformats-officedocument.spreadsheetml.sheet"


docker build --no-cache --build-arg PHP_VER=7.3.1 .

Step 5/5 : RUN php -r "var_dump(mime_content_type('/test.xlsx'));"
 ---> Running in 27e744a45920
string(65) "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet"
```
