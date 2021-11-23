# Контрольные задания
### Дисциплина “Безопасность операционных систем”
### Составил доцент Ю.Н.Переляев
### Выполнил: Хростовский Андрей Александрович
### Группа: 01351-ДБ

***

## Задание 1

### Создайте новый файл second, в котором бы трижды повторялась строка текста из файла first.

1. Создаем файл `first`:
	```bash
	khr@khr-MS-7A38:~$ touch first
	```
	
2. Записываем строку `text` в файл `first`: 
   
	```bash
	khr@khr-MS-7A38:~$ echo text > second 
	```

3. Создаем цикл с заданным числом повторений,выводим содержимое файла `first` и записываем это содержимое в файл `second`,окончание цикла: 
   
	```bash
	khr@khr-MS-7A38:~$ for i in i=1 to 3; do cat first >> second; done 
	```

4. Проверяем содержимое файла `first`: 
   
	```bash
	khr@khr-MS-7A38:~$ cat first 
	```
   
	**Вывод**
	
	```bash
	text
	```

5. Проверяем содержимое файла `second`:
   
   ```bash
   khr@khr-MS-7A38:~$ cat second
   ```
   
   **Вывод**
   
   ```bash
   text 
   text 
   text 
   ```

## Задание 2

### Приведите все возможные способы просмотра каталога /usr/bin/

1. Заходим в каталог **/usr/bin**
2. Вводим команду 

	`ls -l` это посмотреть содержимое той или иной папки

	`-l `- выводить подробный список, в котором будет отображаться владелец, группа, дата создания, размер и другие параметры
	
   `head -n 10` выводит первые 10 строк

#### -U (Без сортировки)

```bash
khr@khr-MS-7A38:~$ ls -l -X | head -n 10
```

**Вывод**

```bash
итого 204448
-rwxr-xr-x 1 root root 1254 сен 9 21:00 ps2epsi 
-rwxr-xr-x 1 root root 63576 мар 19 2018 xrandr 
-rwxr-xr-x 1 root root 21624 авг 25 2020 pl2link 
lrwxrwxrwx 1 root root 29 апр 9 00:50 gcov-dump-10 -> x86_64-linux-gnu-gcov-dump-10 
-rwxr-xr-x 1 root root 187672 авг 6 2020 devdump 
-rwxr-xr-x 1 root root 272 сен 9 21:00 ps2pdf 
-rwxr-xr-x 1 root root 31040 фев 22 2021 tset 
-rwxr-xr-x 1 root root 80344 апр 7 18:11 startplasma-wayland
lrwxrwxrwx 1 root root 8 авг 22 22:09 lessfile -> lesspipe 
```

#### -X (Cортировка по расширению файла)

```bash
khr@khr-MS-7A38:~$ ls -l -X | head -n 10 
```

**Вывод**

```bash
итого 204448
-rwxr-xr-x 1 root root 59888 дек 6 2020 [ 
-rwxr-xr-x 1 root root 39 авг 15 2020 7z 
-rwxr-xr-x 1 root root 40 авг 15 2020 7za 
-rwxr-xr-x 1 root root 40 авг 15 2020 7zr 
-rwxr-xr-x 1 root root 35344 июл 1 05:42 aa-enabled 
-rwxr-xr-x 1 root root 35344 июл 1 05:42 aa-exec 
-rwxr-xr-x 1 root root 31248 июл 1 05:42 aa-features-abi 
-rwxr-xr-x 1 root root 22912 апр 14 16:27 aconnect 
-rwxr-xr-x 1 root root 19016 ноя 28 2019 acpi_listen 
```

#### -S (Сортировка по размеру)

```bash
khr@khr-MS-7A38:~$ ls -l -S | head -n 10
```

**Вывод**

```bash
итого 204448 
-rwxr-xr-x 1 root root 24680984 апр 9 00:50 x86_64-linux-gnu-lto-dump-10 
-rwxr-xr-x 1 root root 17331768 июн 15 18:45 snap 
-rwxr-xr-x 1 root root 8976288 апр 11 18:32 gdb 
-rwxr-xr-x 1 root root 5897416 дек 31 2020 cryfs 
-rwxr-xr-x 1 root root 5512664 мая 11 16:20 python3.9 
-rwxr-xr-x 2 root root 3781560 авг 2 20:24 perl 
-rwxr-xr-x 2 root root 3781560 авг 2 20:24 perl5.32.1 
-rwxr-xr-x 1 root root 3067408 июл 29 2020 lsar 
-rwxr-xr-x 1 root root 3050640 июл 29 2020 unar 
```

#### -t (Сортировка по времени изменения)

```bash
khr@khr-MS-7A38:~$ ls -l -t | head -n 10
```

**Вывод**

```bash
итого 204448 
-rwxr-xr-x 1 root root 1007 сен 9 21:00 dvipdf 
-rwxr-xr-x 1 root root 639 сен 9 21:00 eps2eps 
lrwxrwxrwx 1 root root 2 сен 9 21:00 ghostscript -> gs 
-rwxr-xr-x 1 root root 14488 сен 9 21:00 gs 
-rwxr-xr-x 1 root root 350 сен 9 21:00 gsbj 
-rwxr-xr-x 1 root root 352 сен 9 21:00 gsdj 
-rwxr-xr-x 1 root root 352 сен 9 21:00 gsdj500 
-rwxr-xr-x 1 root root 353 сен 9 21:00 gslj 
-rwxr-xr-x 1 root root 350 сен 9 21:00 gslp 
```

#### -v (Сортировки по версиям файлов)
```bash
khr@khr-MS-7A38:~$ ls -l -v | head -n 10
```

**Вывод**

```bash
итого 204448 
-rwxr-xr-x 1 root root 39 авг 15 2020 7z 
-rwxr-xr-x 1 root root 40 авг 15 2020 7za 
-rwxr-xr-x 1 root root 40 авг 15 2020 7zr 
lrwxrwxrwx 1 root root 11 авг 22 22:09 GET -> lwp-request 
lrwxrwxrwx 1 root root 11 авг 22 22:09 HEAD -> lwp-request 
-rwxr-xr-x 1 root root 41720 авг 25 2020 HTMLLinker 
lrwxrwxrwx 1 root root 11 авг 22 22:09 POST -> lwp-request 
lrwxrwxrwx 1 root root 4 июл 6 18:17 X -> Xorg 
lrwxrwxrwx 1 root root 1 авг 22 22:09 X11 -> . 
```

#### -r (Сортировки в обратном порядке)

```bash
khr@khr-MS-7A38:~$ ls -l -r | head -n 10 
```

**Вывод**

```bash
итого 204448 
-rwxr-xr-x 1 root root 4553 янв 28 2021 znew 
-rwxr-xr-x 1 root root 1842 янв 28 2021 zmore 
-rwxr-xr-x 1 root root 2206 янв 28 2021 zless 
-rwxr-xr-x 1 root root 26952 мая 26 2020 zjsdecode 
-rwxr-xr-x 1 root root 93888 фев 3 2021 zipsplit 
-rwxr-xr-x 1 root root 93888 фев 3 2021 zipnote 
-rwxr-xr-x 1 root root 182720 янв 30 2021 zipinfo 
-rwxr-xr-x 1 root root 2959 янв 30 2021 zipgrep 
-rwxr-xr-x 1 root root 51239 авг 2 20:24 zipdetails 
```

## Задание 3

### Найдите в системе файлы, содержащие в имени три гласные буквы подряд.

1. `find` - это команда для поиска файлов и каталогов на основе специальных условий 
2. Команда `find` имеет синтаксис: `find [where to start searching from] [expression determines what to find] [-options] [what to find]`
3. `-type f` - искать только файлы 
4. `-regextype` - изменяет синтаксис регулярного выражения
4. `head -n 10` выводит первые 10 строк
4. `--regex '.*[aAeEiIoOuUyY]{3}.*'` - регулярное выражение

	`.` - Задает один произвольный символ
	
	`*` - Произвольное число повторений одного символа

	`[aAeEiIoOuUyY]` - любой символ, указанный в скобках
	
	`{3}` - указывает число повторений предыдущего символа

```bash 
khr@khr-MS-7A38:~$ find / -type f -regextype posix-extended -regex '.*[aAeEiIoOuUyY]{3}.*' 2>/dev/null | head -n 10
```

**Вывод**

```bash
/run/udev/links/\x2fdisk\x2fby-partuuid\x2f7c823116-8447-4c60-9bb3-8fada041f97d/b8:20
/run/udev/links/\x2fdisk\x2fby-uuid\x2f24BC89A1BC896E5C/b8:20
/run/udev/links/\x2fdisk\x2fby-partuuid\x2f63d66ef7-e079-447a-b84f-358880bb7e0f/b8:19
/run/udev/links/\x2fdisk\x2fby-uuid\x2fD6A2AD31A2AD16D1/b8:19
/run/udev/links/\x2fdisk\x2fby-uuid\x2f059da829-c4cd-4f6a-a316-3b5b7ffd2612/b8:21
/run/udev/links/\x2fdisk\x2fby-partuuid\x2f3fa88706-0e85-4ffe-950e-33a98f188b13/b8:21
/run/udev/links/\x2fdisk\x2fby-partuuid\x2f8af6015f-e924-4abd-8107-222bcfa02a54/b8:18
/run/udev/links/\x2fdisk\x2fby-partuuid\x2fd4f5c47d-25e5-499e-b0c3-9ed315d005de/b8:17
/run/udev/links/\x2fdisk\x2fby-uuid\x2f9EAB-ED3D/b8:17
/run/udev/links/\x2fdisk\x2fby-id\x2fata-WDC_WD5000AAKS-00UU3A0_WD-WCAYU7517177/b8:0
```

## Задание 4 

### Найдите в системе файлы, состоящие из 5 и более заглавных букв подряд.

1. Имеется два вида регулярных выражений

	1. базовые регулярные выражения (basic regular expressions) (BRE) 
	2. Расширенные регулярные выражения (extended regular expressions) (ERE)

	Различия BRE и ERE в метасимволах.
	
	**BRE**
	
	```bash
	^ $ . [ ] *
	```
	**ERE** (символы расцениваются как литералы)
	
	```bash
	( ) { } ? + |
	```
	
	Поскольку функции, которые мы делаем, являются частью **ERE** нам понадобиться использовать аргумент `-E`
	
	```bash
	grep -E
	```
	Аргументы `grep `:
	
	`-n` - выводит номер строки, в которой встретилось данное совпадение, 
	
	`-a` - заставляет обрабатывать бинарные файлы как текстовые и, таким образом, выводить совпадающие сторки из бинарных файлов
	
	`-R` - рекурсия
	
2. `head -n 10` выводит первые 10 строк

3. Регулярное выражение:

	`.` - Задает один произвольный символ
	`*` - Произвольное число повторений одного символа
	
	`[A-Z]` — все заглавные латинские буквы
	
	`{5}` - указывает число повторений предыдущего символа
	
	`()` - Группировка символов внутри

```bash
khr@khr-MS-7A38:~$ grep -E '.*([A-Z]{5})*.' / -naR 2>/dev/null | head -n 10 
```

**Вывод**

```bash
/run/acpid.pid:1:1402 
/run/crond.pid:1:1407 
/run/cups/printcap:1:# This file was automatically generated by cupsd(8) from the 
/run/cups/printcap:2:# /etc/cups/printers.conf file. All changes to this file 
/run/cups/printcap:3:# will be lost. 
/run/avahi-daemon/pid:1:1406 
/run/utmp:1:~~~reboot5.11.0-34-generic =a K5~~~runlevel5.11.0-34-generic tty1khr:0▒ =a} 
pts/0ts/0khr:0▒ =a vl1pts/1ts/1khr:0 =a 
/run/user/1000/KSMserver__0:1:local/khr-MS-7A38:@/tmp/.ICE-unix/2048,unix/khr-MS-7A38:/tmp/.ICE-unix/2048 
/run/user/1000/KSMserver__0:2:2048 
/run/user/1000/dconf/user:1: 
```
## Задание 5 

### Составьте конвейер, при помощи которого слово ABRAKADABRA, выведется на экран с заменой букв R на L (echo, tr) 

1. `echo` - просто выводит строк
2. `tr` - используется для замены, замещения или удаления символов из стандартного ввода

```bash 
khr@khr-MS-7A38:~$ echo "ABRAKADABRA" | tr R L
```

**Вывод**

```bash
ABLAKADABLA 
```

## Задание 6

Переходим в каталог `/usr/bin` и просматриваем файл `passwd`. 

Первый символ `-` обозначает что `passwd` - это именно файл 

> А не, например, директория, каталог, сокет, ссылка и т.п.

Первая триада битов **(права владельца)** `rws` означает, что пользователь `root ` имеет право читать/выполнять/изменять его, плюс на файл установлен **SUID-бит** **(бит смены идентификатора пользователя)**. 

Смысл этого бита состоит в следующем: обычно, когда пользователь запускает некоторую программу на выполнение, эта программа получает те же права доступа к файлам и каталогам, которые имеет пользователь, запустивший программу. 

Если же установлен **"бит смены идентификатора пользователя"**, то программа получит права доступа к файлам и каталогам, которые имеет владелец файла программы (таким образом, рассматриваемый атрибут лучше называть "битом смены идентификатора владельца"). 

Это позволяет решать некоторые задачи, которые иначе было бы трудно выполнить, самый характерный пример - это как раз команда смены пароля `passwd`. 

Все пароли пользователей хранятся в файле `/etc/passwd`, владельцем которого является суперпользователь `root`, поэтому программы, запущенные обычными пользователями, в том числе команда passwd, не могут производить запись в этот файл, значит, пользователь как бы не может менять свой собственный пароль, но для файла `/usr/bin/passwd` установлен **"бит смены идентификатора владельца"**, каковым является пользователь `root`. следовательно, программа смены пароля `passwd` запускается с правами `root` и получает право записи в файл `/etc/passwd`

> Уже средствами самой программы обеспечивается то, что пользователь может изменить только одну строку в этом файле

Вторая триада **(права группы)** `r-x` означает, что все пользователи, входящие в группу `root` могут только читать/выполнять его, не имея права на модификацию этого файла.

Третья триада **(права для всех остальных)** `r-x` означает, что остальные пользователи **(не входящие в группу root)** могут только читать/выполнять его, не имея права на модификацию этого файла(т.е. точно такие же права, как и у пользователей группы root.).

Далее расположено поле со счетчиком ссылок на файл. в данном случае здесь стоит единица, значит `/usr/bin/passwd` - единственное имя, под которым известен данный файл.

Следующие два поля - владелец и группа файла. в данном случае владельцем файла является пользователь `root`, и файл принадлежит группе `root`.

Затем следует поле, отображающее размер файла в байтах. рассматриваемый файл имеет размер `29060 байт`, т.е. чуть больше 28 Кбайт.

Далее указывается дата последнего изменения: `29 октября 2021 г.` и время последнего изменения: `5 часов 12 минуты`.

В последнем поле содержится имя файла - `/usr/bin/passwd`.

```bash
khr@khr-MS-7A38:~$ cd /usr/bin && ls -l passwd
```

```bash
-rwsr-xr-x 1 root root 29060 2021-10-29 05:12 passwd
```

Переходим в каталог /etc и просматриваем файл passwd. первый символ "-" обозначает что passwd - это именно файл.

Первая триада битов **(права владельца)** `rw-` означает, что пользователь **root** имеет право производить чтение/запись этого файла, но не может выполнять его.

Вторая триада(права группы) `r--` означает, что все пользователи, входящие в группу **root** могут только читать его, не имея права на модификацию/выполнение этого файла.

Третья триада **(права для всех остальных)** `r--` означает, что остальные пользователи **(не входящие в группу root)** могут только читать его, не имея права на модификацию/выполнение этого файла.

> Т.е. точно такие же права, как и у пользователей группы root

Далее расположено поле со счетчиком ссылок на файл. в данном случае здесь стоит единица, значит `/etc/passwd` - единственное имя, под которым известен данный файл.

Следующие два поля - владелец и группа файла. в данном случае владельцем файла является пользователь `root`, и файл принадлежит группе `root`.

Затем следует поле, отображающее размер файла в байтах. рассматриваемый файл имеет размер 1237 байт, т.е. чуть больше 1 Кбайта.

Далее указывается дата последнего изменения: `3 ноября 2021 г`. и время последнего изменения: `21 часов 21 минут`.

В последнем поле содержится имя файла - `/etc/passwd`.

```bash
khr@khr-MS-7A38:~$ cd /etc && ls -l passwd
```

```bash
-rw-r--r-- 1 root root 1237 2007-11-24 21:21 passwd
```

## Задание 7 

### Создайте сжатый архив файлов, измененных за последнюю неделю (tar, gzip, find, cpio)

1. Ищем файлы с датой модификации на старше 7 дней

	Результат поиска выводим в `result.txt`
	
	```bash
	khr@khr-MS-7A38:~$ find / -type f -mtime -7 > result.txt 2>/dev/null
	```
	
2. Cоздаем несжатый архив

	* `-с` создает новый архив
	* `-f` задает имя для архива
	* `-T` берет список файлов для архива из `result.txt`

	```bash
	khr@khr-MS-7A38:~$ tar -cf files.tar -T result.txt 2>/dev/null
	```
	
	Получаем несжатый архив
	
	```bash
	-rw-r--r-- 1 khr khr 3.1G Sep 19 17:28  files.tar
	```
3. Сжимаем архив программой `gzip`
	
	```bash
	khr@khr-MS-7A38:~$ gzip files.tar
	```
	
	Получаем сжатый архив
	
	```bash
	-rw-r--r-- 1 khr khr 1.2G Sep 19 17:28  files.tar.gz
	```
## Задание 8 

Программа `ps` используется для получения списка запущенных процессов. с помощью `aux` получаем подробную информацию о каждом запущенном процессе. ключем `-p` задаем конкретный PID процесса - в данном случае это единица, что соответствует процессу `init`

> init - это первый действительный процесс, запускаемый ядром при загрузке, и его PID всегда равен 1 

Вывод перенаправляем в файл processes.txt

 ```bash
 khr@khr-MS-7A38:~$ ps aux -p 1 > processes.txt
 ```

Выводим содержимое файла `processes.txt` на экран. 

```bash
khr@khr-MS-7A38:~$ cat processes.txt
```

```bash
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
root 1 0.7 0.0 1628 536 ? Ss 13:53 0:01 /sbin/init splash
```

* `USER` - отображает имя пользователя, запустившего процесс

* `PID` - идентификатор процесса

* `%CPU` - уровень использования процессора

* `%MEM` - уровень использования памяти

* `VSZ` - объём используемой виртуальной памяти

* `RSS` - объём используемой реальной памяти

* `TTY` - терминал, с которым связан процесс

  > `?` потому, что `init` это первый системный процесс и он не связан ни с одним терминало

* `STAT` - состояние выполнения

  > * `S` - означает, что процесс бездействует
  >
  > * `s` - то что процесс лидер сеанса
  > * `START` - время старта

* `TIME` - время исполнения

  > На процессоре

* `COMMAND` - имя программы

## Задание 9

* `USER` отображает имя пользователя, запустившего процесс

* `PID` - идентификатор процесса

* `%CPU` - уровень использования процессора

* `%MEM` - уровень использования памяти

* `VSZ` - объём используемой виртуальной памяти

* `RSS` - объём используемой реальной памяти

* `TTY` - терминал, с которым связан процесс

* `STAT` - состояние выполнения

* `START` - время старта

* `TIME` - время исполнения

  > На процессоре

* `COMMAND` - имя программы

В выводе этого листинга видно, что процесс `amarok` с `PID 4997`, созданный пользователем `root` является самым ресурсоемким по использованию процессора. он использует процессор на `5.5`, память на `3.8`, его виртуальная память `127632`, реальная память `40044`, он не прикреплен ни к одному терминалу, его статус: 

* `S` - означает, что процесс бездействует

  > Ожидает выполнения

* `L` - означает что это `real-time` процесс, имеются страницы заблокированные в памяти, время запуска процесса `11 часов 56 минут`, время выполнения `16 секунд`.

```bash
khr@khr-MS-7A38:~$ ps aux --sort -pcpu | head -n 3
```

```bash
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
root 4997 5.5 3.8 127632 40044 ? SLl 11:56 0:16 amarok
root 5304 3.9 0.0 1852 776 ? RN 12:00 0:01 /usr/bin/updatedb
```

* `USER` отображает имя пользователя, запустившего процесс

* `PID` - идентификатор процесса

* `%CPU` - уровень использования процессора

* `%MEM` - уровень использования памяти

* `VSZ` - объём используемой виртуальной памяти

* `RSS` - объём используемой реальной памяти

* `TTY` - терминал, с которым связан процесс

* `STAT` - состояние выполнения

* `START` - время старта

* `TIME` - время исполнения

  > На процессоре

* `COMMAND` - имя программы

В выводе этого листинга видно, что процесс `/sbin/init splash` с `PID 1`, созданный пользователем `root` является самым ресурсоемким по использованию оперативной памяти. он использует процессор на `0.2`, память на `0.1`, его виртуальная память `1628`, реальная память `536`, он не прикреплен ни к одному терминалу, его статус: 

* `S` - означает, что процесс бездействует
* `s` - то что процесс лидер сеанса, время запуска процесса `11 часов 54 минуты`, время выполнения `2 секунды`.

```bash
khr@khr-MS-7A38:~$ ps aux --sort -pmem | head -n 3
```
```bash
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
root 1 0.2 0.1 1628 536 ? Ss 11:54 0:02 /sbin/init splash
root 2 0.0 0.0 0 0 ? S 11:54 0:00 [migration/0]
```

## Задание 10 

### Переведите часы на 1 час назад (date, hwclock)

1. Чтобы узнать время, прописываем следующую команду
	
	```bash
	khr@khr-MS-7A38:~$ date
	```
	
	**Вывод**
	
	```bash
	Sun Sep 19 17:09:27 +08 2021
	```

2. Нам надо изменить время на 1 час назад, пишем команду

	```bash
	khr@khr-MS-7A38:~$ sudo date --set -1hour
	```
3. Узнаем сново время: 

	```bash
	khr@khr-MS-7A38:~$ date
	```
	
	**Вывод**
	
	```bash
	Sun Sep 19 16:12:23 +08 2021
	```
	
4. Чтобы сохранить изменения:
	
	```bash
	khr@khr-MS-7A38:~$ sudo hwclock -w
	```