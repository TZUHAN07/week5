# week5
要求⼆：建立資料庫和資料表
>CREATE TABLE member(id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(255) NOT NULL ,username VARCHAR(255) NOT NULL ,password VARCHAR(255) NOT NULL ,follower_count INT UNSIGNED NOT NULL DEFAULT 0, time DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP);
>![image](https://user-images.githubusercontent.com/111477348/196713725-b11d322a-66ed-44ab-8665-d6125ee5c0f6.png)

要求三：SQL CRUD
● 使⽤ INSERT 指令新增⼀筆資料到 member 資料表中，這筆資料的 username 和
password 欄位必須是 test。接著繼續新增⾄少 4 筆隨意的資料。
>INSERT INTO member(id,name,username,password,follower_count,time) VALUES (1,"Tom","test","test",37, '2022-10-19 00:40:35');
![image](https://user-images.githubusercontent.com/111477348/196717182-f67e1bf3-cabe-4d39-9f9a-ab6b1ea5ac83.png)
>INSERT INTO member(id,name,username,password,follower_count,time) VALUES (2,"Mick","mick02","1234",27,'2022-10-19 01:20:25');
>INSERT INTO member(id,name,username,password,follower_count,time) VALUES (3,"Eric","eric03","2468",75,'2022-10-19 07:50:05');
>INSERT INTO member(id,name,username,password,follower_count,time) VALUES (4,"Mandy","mandy04","1357",63,'2022-10-19 09:20:45');
>INSERT INTO member(id,name,username,password,follower_count,time) VALUES (5,"Zoe","zoe05","6789",13,'2022-10-19 10:07:27');

● 使⽤ SELECT 指令取得所有在 member 資料表中的會員資料。
>SELECT * FROM member;
>![image](https://user-images.githubusercontent.com/111477348/196717766-4758d5c7-fe56-4826-87f0-e54c985c235d.png)

● 使⽤ SELECT 指令取得所有在 member 資料表中的會員資料，並按照 time 欄位，由
近到遠排序。
-因一開始的隨機資料的時間為順序的時間，所以再新增兩列資料去做測試。
>INSERT INTO member(name,username,password,follower_count,time) VALUES ("Leo","leo06","3333",56,'2022-10-19 03:05:27');
>INSERT INTO member(name,username,password, time) VALUES ("Sam","sam07","5555",'2022-10-19 08:13:16');
>![image](https://user-images.githubusercontent.com/111477348/196724588-cb6130a1-c984-4931-8a25-42d2e9b10763.png)

>SELECT * FROM member ORDER BY time;
>![image](https://user-images.githubusercontent.com/111477348/196724737-2f1d3998-26a1-4812-ae8d-d96371dd6e48.png)

● 使⽤ SELECT 指令取得 member 資料表中第 2 ~ 4 共三筆資料，並按照 time 欄位，
由近到遠排序。( 並非編號 2、3、4 的資料，⽽是排序後的第 2 ~ 4 筆資料 )
>SELECT * FROM member ORDER BY time LIMIT 1,3;
>![image](https://user-images.githubusercontent.com/111477348/196724882-db88b3ed-cd1d-410b-bc06-9362956dac7f.png)

● 使⽤ SELECT 指令取得欄位 username 是 test 的會員資料。
> SELECT * FROM member WHERE username = 'test';
>![image](https://user-images.githubusercontent.com/111477348/196724950-0483dffd-dd36-40c8-afa3-b35501d20911.png)

● 使⽤ SELECT 指令取得欄位 username 是 test、且欄位 password 也是 test 的資料。
>SELECT * FROM member WHERE username = 'test' and password ='test';
>![image](https://user-images.githubusercontent.com/111477348/196725258-2e6fd2a6-a260-464a-a05c-936e5927d7fa.png)

● 使⽤ UPDATE 指令更新欄位 username 是 test 的會員資料，將資料中的 name 欄位改
成 test2。
>UPDATE member SET name=’ test2’ WHERE username=’ test’;
>![image](https://user-images.githubusercontent.com/111477348/196725372-5ff32b2a-f08d-4f8f-b4ba-092ed4bdc27a.png)

要求四：SQL Aggregate Functions
● 取得 member 資料表中，總共有幾筆資料 ( 幾位會員 )。
>SELECT COUNT(id) FROM member;
>![image](https://user-images.githubusercontent.com/111477348/196725564-0ff1f2ac-aa1d-4d76-a350-fe317a2f106f.png)

● 取得 member 資料表中，所有會員 follower_count 欄位的總和。
>SELECT SUM(follower_count) FROM member;
>![image](https://user-images.githubusercontent.com/111477348/196725652-c55ed03f-5e1e-4fe0-9be7-e2d27b07f9bc.png)

● 取得 member 資料表中，所有會員 follower_count 欄位的平均數。
>SELECT AVG(follower_count) FROM member;
>![image](https://user-images.githubusercontent.com/111477348/196725726-2e677c79-cb12-452c-90a9-9caf58bf3845.png)


