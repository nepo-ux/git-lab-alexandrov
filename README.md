1. Откат изменений
- создать файл config.txt с тектом "Версия 1.0" и закоммитить
команды:
echo "Версия 1.0" > config_alexandrov.txt
git add config_alexandrov.txt
git commit -m "Добавлена версия 1.0"
Результат: коммит конфига в основой ветке
- изменить текст на "Версия 2.0" и сделать второй коммит
команды:
echo "Версия 2.0" > config_alexandrov.txt
git add config_alexandrov.txt
got commit -m "Обновлена до версии 2.0"
Результат: коммит конфига в основной ветке
- откатиться к первому коммиту, сохранив измения в рабочей директории
git reset --mixed HEAD~1
Результат: откат и сохранение измений в файле без индексации

2. Конфликт в одном файле
- В файле script.js на ветке main внести изменения, закоммитить. Потом в другой ветке feature изменить
файл script.js , коммит.
bash
echo "console.log("line in main branch");" > script.js
git add script.js
git commit -m "Update line 1 in script.js in main branch"

git checkout -b feature
echo "console.log("line in feature branch");" > script.js
git add script.js
git commit -m "update line 1 in script.js in feature branch"

- Результат: создание двух веток с файлами script.js но содержащие разные строки

- Слияние веток
bash
git checkout main
git merge feature
- Вручную разрешить конфликт. и сделать коммит

bash
git add script.js
git commit -m "solved merge conflict"
