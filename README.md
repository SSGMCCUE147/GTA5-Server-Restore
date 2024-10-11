# GTA5-Server-Restore
instructions on how to restore your server after a database corruption 



here are the instructions on how to wipe and restore your QBCore FiveM GTA5 server after a database corruption

also here is a video to help you with a normal setup but also goes along with this. i just added a few steps to restore your server
https://www.youtube.com/watch?v=yTHj8XBNxgk&t=1058s

Step 1

Locate your server folder. Inside that folder make your way to the txData folder and open it. inside that folder you will see a folder called QBCoreFramework_xxxxxx.base. inside there you need to copy your resource folder and server.cfg to a safe location for later use to restore your server

Step 2

delete your server folder. you saved a copy of the files you need so dont worry

Step 3

Open your heidiSQL and delete your server from there and create a new one. do not open it just yet

Step 4

uninstall XAMPP and reninstall it https://www.apachefriends.org/  . you may have to delete the XAMPP folder in C drive in order to reinstall it

Step 5

Time to download your artifacts to build the server. go to this link to download

https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/

download the newest one. not the latest recomended. the one at the top of the list

Step 6

make a folder on your desktop and call it your server name. open that folder and make 2 folders called 'server' and 'server data' 
extract the server files to the 'server' folder

Step 7

start XAMPP and start up apache and MySQL then open heidiSQL and open your server

Step 8

go into the server folder and run the FXServer.exe
this will also open the TXAdmin website
follow the prompts on the website
1 pick your server name
2 pick your deployment type. Popular Template
3 select your Template. QBCore Framework
4 data location. go to your server folder and make a new folder called txData. you will now have 3 folders there called server server data and txData. open the txData folder and copy the path and put that path into the data location on the website and click save
5 click on Go to Recipe Deployer
6 scroll to the bottom and click on next
7 go to https://keymaster.fivem.net/ and sign in. once signed in click on new server
choose your display name
in the FXServer.exe file you ran opened a CMD prompt. open that and get your IP. in a box it will have http://localhost and under that will be your IP. type your IP into the website in Initial server IP address bar
for server type select other/home hosted
then click generate
copy your server key and go back to the txAdmin website and paste the key into the license key location and click Run Recipe

Step 9

once it is done deploying click next
1 it will open the sever config. at line 16 of that server config you will see the sv_licenseKey. you need to copy that key and then go to where you you made a copy of your resource folder and server.cfg. open the server.cfg file and go to line 22. that is your old key there. delete that and paste the new key that you copied
2 go back to the txAdmin website and then go to line 23 and you will see the 'set mysql_connection_sting' and the path. copy the path and go back to the server.cfg you have opend and go to line 29 and delete the old one and paste the new one and then save it

Step 10

click on save and run server
it will start the first boot of the server
once the first boot is done click on the restart to rerun it again. this sets up a few things that need to happen in order for the server to work

Step 11

once it finishes booting for the second time you will then shutdown the server
you will close the FXServer CMD prompt
you will close out of heidiSQL
you will then go to the XAMPP Control panal and stop MySQL FIRST then stop apache

Step 12

open up the new server folder and go to txData/QBCoreFramework_xxxxxx.base and delete the resouce folder and the server.cfg and the server.cfg.bak

then you will go to where you saved the resource folder and server.cfg and copy those to the txData/QBCoreFramework_xxxxxx.base folder

Step 13

you will then have to re run all of your SQL files for all the Scripts you have added before. just go into the resource folder and find your scripts and the SQL should be in there. so start up XAMPP and start apache and then MySQL then open up heidiSQL and then you can run your SQLs. depending on if you have had to drop a table to re run the SQL the first time you installed it will determine if you have to drop it or not. sometimes it will be the same or it will update the table and sometimes you need to drop a table to run the new SQL. please refer to the website you got the script from to detemine weather ot not you need to drop the table first or not. you could also check your README.MD file to assist you as well. Some times you will get a error when running the SQLs. ignore the errors. its due to running a SQL that tryies to update a table that already exists/has nothing to update in that table. this is 100% normal

Step 14

Once you have ran all of your SQLs you are ready to boot up your server. make your new player and then everything will be the way it was before your database was courupted

Step 15

GO HAVE SOME FUN!!!!!!!!!!!!!!!
