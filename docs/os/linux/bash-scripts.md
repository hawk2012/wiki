## 🖥️ Введение в Bash-скрипты

Bash — это стандартный shell в большинстве дистрибутивов Linux. С его помощью можно автоматизировать рутинные задачи, проверять логи, управлять файлами и запускать программы.

---

### 📄 Создание скрипта

1. Создайте файл:
```bash
nano myscript.sh
```

2. Напишите содержимое:
```bash
#!/bin/bash
echo "Привет, мир!"
```

3. Сохраните и сделайте исполняемым:
```bash
chmod +x myscript.sh
```

4. Запустите:
```bash
./myscript.sh
```

📌 `#!/bin/bash` называется shebang — он указывает, какой интерпретатор использовать.

---

### 🧮 Переменные и аргументы

```bash
NAME="Linux"
echo "Привет, $NAME"

# Аргументы
echo "Первый аргумент: $1"
```

Вызов:
```bash
./myscript.sh мир
```

---

### 🔄 Условия и циклы

#### if / else
```bash
if [ "$NAME" == "Linux" ]; then
  echo "Правильно!"
else
  echo "Неправильно"
fi
```

#### Цикл for
```bash
for i in {1..5}; do
  echo "Число: $i"
done
```

#### Цикл while
```bash
COUNT=1
while [ $COUNT -le 5 ]; do
  echo "Счётчик: $COUNT"
  COUNT=$((COUNT + 1))
done
```

---

### 🧰 Полезные примеры

#### Поиск файлов и вывод размера
```bash
#!/bin/bash
find /home/user/logs -name "*.log" -exec du -h {} \;
```

#### Автоматическое резервное копирование
```bash
#!/bin/bash
tar -czf backup_$(date +%Y%m%d).tar.gz /home/user/docs
```

---

### 🌐 Полезные ссылки

- [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/)
- [ShellCheck — проверка скриптов](https://www.shellcheck.net/)
- [ExplainShell — объяснение команд](https://explainshell.com/)
