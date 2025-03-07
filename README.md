# lab02_home
<details>
  <summary>Part 1</summary>
    </p>

  1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
<br>
<p>Создадим пустой репозиторий - <a href="http://google.com/](https://github.com/BridgeInSky/Repos"
title="ссылка на репозиторий">ссылка на репозиторий</a> <br>
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
<br>
Воспользуемся инструкцией по созданию первого коммита: 
  
```
echo "# Repos" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/BridgeInSky/Repos.git
git push -u origin main
```
Сначала проинициализируем репозиторий (вторая строчка). После активации функции увидим:
```
подсказка: Using 'master' as the name for the initial branch. This default branch name
подсказка: is subject to change. To configure the initial branch name to use in all
подсказка: of your new repositories, which will suppress this warning, call:
подсказка: 
подсказка: 	git config --global init.defaultBranch <name>
подсказка: 
подсказка: Names commonly chosen instead of 'master' are 'main', 'trunk' and
подсказка: 'development'. The just-created branch can be renamed via this command:
подсказка: 
подсказка: 	git branch -m <name>
Инициализирован пустой репозиторий Git в /home/liza/workspace/projects/LR2/.git/
```
Далее создаём файл README.md (первая строка инструкции). Чтобы проверить,что файл был создан, введём команду ```ls``` и увидим, что в нашей папке появился файл с таким названием формата .md. <br>
Далее выполняем действия по порядку, полсе выполнения функции ```commit``` увидели:
```
[master (корневой коммит) 5f08acc] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```
Далее после команды ```push``` от нас потребовали ввести данные для регистрации
```
Username for 'https://github.com': BridgeInSky
Password for 'https://BridgeInSky@github.com':
```
После ввода на экране увидели:
```
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 229 байтов | 229.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/BridgeInSky/Repos.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```
<br>
3. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.<br>
Воспользуемся текстовым редактором

```
vim hello_world.cpp
```
Чтобы проверить содержимое файла, можно воспользоваться следующей командой:
```
cat hello_world.cpp
```
На выходе получили
```
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```
Файл успешно записан<br>
4. Добавьте этот файл в локальную копию репозитория.<br>
```
git add hello_world.cpp
```
5. Закоммитьте изменения с осмысленным сообщением.<br>
```
git commit -m "Add hello_world.cpp with basic Hello World program"
```
В сообщении указываем, что высылавемый файл необходимо добавить к общей программе Hello World.<br>
На выходе получаем:
```
[main 5b28053] Add hello_world.cpp with basic Hello World program
 1 file changed, 7 insertions(+)
 create mode 100644 hello_world.cpp
```
Отправим изменения в удалённый репозиторий
```
git push origin main
```
На выходе получим:
```
Перечисление объектов: 4, готово.
Подсчет объектов: 100% (4/4), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 420 байтов | 420.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/BridgeInSky/Repos.git
   5f08acc..5b28053  main -> main
```
6. Изменить исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение ```Hello world from @name```, где @name имя пользователя.<br>
Снова воспользуемся текстовым редактором
```
vim hello_world.cpp
```
Чтобы проверить корректность внесённых изменений можем запустить программу:
```
g++ hello_world.cpp -o hello_world
./hello_world
```
Получили:
```
Enter your name: Liza
Hello world from Liza!
```
Программа работает корректно.<br>
8. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно ```git add```?<br>
```
git commit -am "Update hello_world.cpp to ask for user's name"
```
Сделали коммит новой версии программы с сообщением о том, что в ней спрашивают имя пользователя.<br>
Файл уже был добавлен в Git (с помощью git add ранее), и Git отслеживает изменения в нём. Команда git commit -am автоматически добавляет изменения в уже отслеживаемые файлы.<br>
В результате вывелось:
```
[main be0ff97] Update hello_world.cpp to ask for user's name
 1 file changed, 5 insertions(+), 1 deletion(-)
```
9. Запуште изменения в удалёный репозиторий.<br>
```
git push origin main
```
На экране увидели:
```
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 454 байта | 454.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/BridgeInSky/Repos.git
   5b28053..be0ff97  main -> main
```

10. Проверьте, что история коммитов доступна в удалёный репозитории.<br>
<p> <a href="https://github.com/BridgeInSky/Repos/commits?author=BridgeInSky"
title="Ссылка на коммиты">Ссылка на коммиты</a> <br>
  </p>
</details>

<details>
  <summary>Part 2</summary>
  <p> 
  <br>
    
  1. В локальной копии репозитория создайте локальную ветку ```patch1```
  ```
git branch patch1
```
  2. Внесите изменения в ветке patch1 по исправлению кода и избавления от ```using namespace std;```.<br>
  Перейдём в ветку ```patch1```:
```
git checkout patch1
```
Получили
```
Переключились на ветку «patch1»
```
Изменим содержимое файла с помощью ```vim```.<br>
  3. ```commit```, ```push``` локальную ветку в удалённый репозиторий.<br>
  ```
git commit -am "vers. without 'using namespace std;'"
```
На выходе получили:
```
[patch1 5a50291] vers. without 'using namespace std;'
 1 file changed, 3 insertions(+), 4 deletions(-)
```
Теперь запушим
```
git push --set-upstream origin patch1
```
На выходе:
```
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 380 байтов | 380.00 КиБ/с, готово.
Всего 3 (изменений 1), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/BridgeInSky/Repos/pull/new/patch1
remote: 
To https://github.com/BridgeInSky/Repos.git
 * [new branch]      patch1 -> patch1
branch 'patch1' set up to track 'origin/patch1'.
```
  4. Проверьте, что ветка patch1 доступна в удалёный репозитории.<br>
<p><a href="https://github.com/BridgeInSky/Repos/branches"
title="ссылка для проверки доступа ветки">ссылка для проверки доступа ветки</a> <br>
  5. Создайте ```pull-request patch1 -> master```.<br>
<img width="50%" height="auto" src="https://github.com/user-attachments/assets/daa08702-3b3c-49bc-8aa9-edb22722a184">
  
  6. В локальной копии в ветке ```patch1``` добавьте в исходный код комментарии.<br>

  Добавим комментарии в код с помощью ```vim```<br>
  7. ```commit, push```.<br>

  
  8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request<br>

  
  9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.<br>

  
  10. Локально выполните ```pull```.<br>

  
  11. С помощью команды ```git log``` просмотрите историю в локальной версии ветки master.<br>

  
  12. Удалите локальную ветку ```patch1```.<br>

  
