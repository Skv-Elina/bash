# 📌 Практика Bash
**Окружение:** Windows 10, Git Bash
## Задание 1:
Навигация и работа с директориями.
```bash
cd ~                                            # 1. Открыть домашнюю директорию через терминал
pwd                                             # 2. Определить имя папки, в которой вы находитесь
mkdir test1                                     # 3. Создать внутри этой папки каталог с именем test1
cd test1                                        # 4. Перейти в папку test1
touch 1.txt 2.txt 3.txt                         # 5. Создать txt файлы 1,2 и 3 внутри каталога test1
ls                                              # 6. Проверить содержимое каталога test1
cd ~                                            # 7. Перейти в домашнюю директорию
mkdir test2                                     # 8. Создать папку test2 внутри домашней директории
rmdir test2                                     # 9. Удалить папку test2
rm test1/2.txt                                  # 10. Удалить файл 2 из папки test1
mkdir test3                                     # 11. Создать папку в домашней директории test3 и добавить в нее два файла
cd test3
touch 4.txt 5.txt
rm -r test3                                     # 12. Удалить папку test3
mkdir test4                                     # 13. Создать папку test4 в домашней директории
cd test1                                        # 14. Переместить файлы 1 и 3 из папки test1 в папку test4
mv 1.txt 3.txt ~/test4
cd ..                                           # 15. Добавить в файл 1 три строки со словами line
cd test4
echo line >> 1.txt
echo line >> 1.txt
echo line >> 1.txt
cat 1.txt                                       # 16. Посмотреть содержимое файла 1
echo line >> 3.txt                              # 17. Добавьте в файл 3 три строки со словами line
echo line >> 3.txt
echo line >> 3.txt
cat 1.txt 3.txt                                 # 18. Просмотрите содержимое двух файлов (1 и 3) сразу
nano 1.txt                                      # 19. Используя один из редакторов замените все строки в файле 1
```
## Задание 2:
Редактирование файлов, проверка и завершение процессов, проверка доступности веб-сайтов.
```bash
cd ~                                            # 1. Зайти в домашнюю директорию через терминал.
mkdir test3                                     # 2. Создать папку test 3
cd test3                                        # 3. Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4
touch 4.txt 5.txt 6.txt
printf "row1\nrow2\nrow3\nrow4\n" | tee -a 4.txt 5.txt 6.txt
grep "row2" 5.txt                               # 4. Найдите строку row2 в файле 5
grep "row" *                                    # 5. Найдите строку row в папке test3
grep -c "row" 6.txt                             # 6.Посчитайте сколько строк с содержимым row в файле 6
find . -name "5.txt"                            # 7. Найдите файл 5 внутри папки test3
find . -name "5.txt" -exec rm {} \;             # 8. Используя команду find, удалите файл 5
echo test >> 4.txt                              # 9. Используя команду echo, добавьте слово test в файл 4
sed -i 's/test/fail/' 4.txt                     # 10. Замените слово test в файле 4 на fail
echo test >> 4.txt                              # 11. Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
ps aux                                          # 12. Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
kill PID                                        # 13. Убейте любой неважный процесс в консоли. Если боитесь удалить что-то лишнее, то можете просто прислать сам запрос без его запуска.
ping rusau.net                                  # 14. Узнайте доступность ресурса rusau.net, используя ping
ping -n 5 rusau.net                             # 15. Отправьте 5 пакетов на сайт rusau.net

# 16. Используя GET и команду curl, получите информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/
curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=available" 

# 17. Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
curl -X 'POST' \                                
  'https://petstore.swagger.io/v2/user' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 0,
  "username": "test_user",
  "firstName": "Test",
  "lastName": "User",
  "email": "test@example.com",
  "password": "TestPassword123",
  "phone": "000000000",
  "userStatus": 0
}'

```
- При выполнении команды `ping` в Git Bash под Windows 10 использовался параметр `-n` вместо `-c`, используемого в Linux.
- В 13 задании команда представлена без выполнения с конкретным PID во избежание остановки системного процесса.
