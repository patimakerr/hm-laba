# Лабораторная работа на тему "восстановление файлов"
## Введение
Первым делом вам необходимо создать файл-образ диска, например размером 500 МБ, а после создать файловую систему ex4 на файле образе. Сделать это можно используя следующие команды:
  ```
dd if=/dev/zero of=disk.img bs=1M count=500
sudo mkfs -t ext4 disk.img
  ```
Далее примонтируйте файловую систему (например, в /mnt/recovery) с помощью команды
  ```
sudo mount -o loop disk.img /mnt/recovery
  ```
Создайте несколько тестовых файлов разных типов в /mnt/recovery
  ```
touch /mnt/recovery/test.txt
echo "test file." > /mnt/recovery/test.txt
cp /usr/share/icons/hicolor/16x16/actions/document-new.png /mnt/recovery/test.png
  ```
проверьте созданные файлы используя команду ls

### Удаление файлов
Вам необходимо удалить ранее созданные файлы. В этом вам поможет следующая команда
  ```
 sudo rm -rf
  ```
а после вам необходимо размонтировать файловую систему.
### Ввостановление файлов
Для восстановления всех файлов из удаленного каталога вы должны запустить extundelete в режиме восстановления с ключом –restore-all.
Далее вам необходимо проверить восстановленные файлы и их типы, а также используйте команду file <имя_файла> для проверки типа восстановленных файлов.
## Источники
https://www.gnu.org/software/coreutils/manual/coreutils.html 

https://losst.pro/vosstanovlenie-udalennyh-fajlov-linux

https://wiki.merionet.ru/articles/tipy-fajlovyh-sistem-linux

![e99d9192c1d6d4f185bc60f3a6df0ec9](https://github.com/user-attachments/assets/4d1d04b5-c776-44d5-a379-63eed8fdb860)

