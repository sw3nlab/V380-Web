# V380-Web
<details>
  <summary> <b>Web server for ip cameras V380. Russian and English interfaces are supported. </b> </summary> 

### The HTTP server allows you to
- perform all sorts of manipulations with the records on the sd card. Now you do not need to take it out of the camera every time;
- watch the video archive on sd online without removing the card;
- display camera information;
- launch services (RTSP, telnet, ftp, HTTP);
- restart and safely shut down the camera before turning off the power.  
### HTTP-сервер позволяет
- производить всевозможные манипуляции с записями на sd-карте. Теперь вынимать её из камеры каждый раз вам нет необходимости;
- смотреть видео-архив на sd онлайн, не вынимая карты;
- отображать сведения о камере;
- производить запуск служб (RTSP, telnet, ftp, HTTP);
- перезагружать и безопасно завершать работу камеры перед отключением питания.
### Таблица определения модели камеры V380
| Camera | Оборудование / Hwprefix | Модель / Hwname | Установщик / Installer |
| --- | --- | --- | --- |
| V380 | Любая камера<br>Any camera | установка вручную<br>manual setup | [httpd_V380_any_manual.zip](https://github.com/Arkady23/V380-Web/releases/download/Initial-installer/httpd_V380_any_manual.zip) |

Ваша базовая прошивка может быть самой последней. Вся установка происходит на sd-карту. Если после установки очистить или вынуть sd, то камера будет работать в обычном режиме, как работала до установки.
### Установка
1. Отформатировать sd-карту в FAT32 ([Вот эта программа](http://ridgecrop.co.uk/index.htm?guiformat.htm) подходит).
2. Записать в корень карты содержимое [архива](https://github.com/Arkady23/V380-Web/releases/download/Initial-installer/httpd_V380_any_manual.zip) в составе:
- ark-add-on
- bin
- quick_check.ini
- setup.sh
3. Вставить карту в камеру и включить её... ждать пару минут. Камера включется с запущенным сервером telnet. После чего нужно зайти через telnet по адресу камеры (логин root, пароль посмотреть в файле quick_check.ini).
4. Ввести команду через telnet:<br>
    /mnt/sdcard/setup.sh
5. Камера должна перезагрузится. После чего можно заходить с помощью обозревателя интернета на адрес камеры. 
### Installation
1. Format the sd card to FAT32 ([Here this program](http://ridgecrop.co.uk/index.htm?guiformat.htm) is suitable).
2. Write to the root of the sd-card the contents of [the archive](https://github.com/Arkady23/V380-Web/releases/download/Initial-installer/httpd_V380_any_manual.zip) as part of:
- ark-add-on
- bin
- quick_check.ini
- setup.sh
3. Insert the card into the camera and turn it on... wait a couple of minutes. The camera turns on with the telnet server running. After that, you need to log in via telnet to the camera address (login root, password look in the file quick_check.in).
4. Enter command via telnet:<br>
    /mnt/sdcard/setup.sh<br>
5. The camera should reboot. After that, you can use the Internet browser to access the address of the camera. 
### News
People complain that the Web does not work and send the software version. I can't tell anything by the version numbers. Still need the installation protocol setup.sh , It would be nice to copy your Linux. The main thing is that there should be a telnet. Using the example of my camera, I just showed what you can do yourself if there is a telnet. So, what doesn't work for anyone, figure it out, and if something new turns out, then I'll finish it so that others can use it. There are plans to make, as there will be time and mood, a script for Windows that will copy all the videos from the camera in the background.  


Жалуются, что Web не работает и присылают версию ПО. Ничего не могу сказать по номерам версий. Еще надо протокол установки setup.sh, Хорошо бы ваш Linux скопировать. Главное, чтобы был telnet. Я на примере своей камеры просто показал, что можно самому сделать, если есть telnet. Так, что у кого не работает, разбирайтесь, а если что-то выяснится новое, то я доделаю, чтобы и другие могли использовать. В планах сделать, как будет время и настроение, скрипт для Windows, который будет в фоновом режиме копировать все видео с камеры.
  
![Просмотр основных настроек](screenshots/image_2022_08_21T23_12_43_133Z.png?raw=true)

</details>


<details>
<summary> <b> MY CAM REVISION </b> </summary>


![](IMG_20241213_092028.jpg)

### UART RX
> [!CAUTION]
> Расположение контактов может различатся в зависимости от ревизии.
![](IMG_20241213_185230.jpg)


</details>

### 4g cam ANYKA AK3918EV300 BOOT LOG
![](IMG_20241213_095927.jpg)

[FULL Boot Log](https://raw.githubusercontent.com/sw3nlab/V380-Web/refs/heads/main/4g_cam_boot_log.txt) 

[SPI Dump](https://github.com/sw3nlab/V380-Web/blob/main/4g.bin)

[Клиент под Windows для просмотра 4G камер V380 с компьютера ](https://drive.google.com/file/d/1OxkICOR_1UwQNb8umTJXPohaOjRI6evo/view?usp=drivesdk)
>Китайские клиенты под Win настолько коряво написаны, что разных версиях клиентов разные ограничения на количество символов в пароле при авторизации. 
В приведенной выше версии пароль из 15 символов проходит норм.
![](screenshots/screenV380.png)
>WINE
```php
sudo apt-get update
sudo apt-get install wine
#sudo dpkg --add-architecture i386
#sudo apt-get install wine32:i386
WINEARCH=win32 WINEPREFIX=~/clean_win32 winecfg
wine V380.2.0.3.exe

#если возникает ошибка
#Wine: could not load kernel32.dll, status c0000135
#rm -rf ~/.wine ~/.wine.old
```
так же можно попробовать запустить .apk приложение в эмуляторе типа BlueStacks 
