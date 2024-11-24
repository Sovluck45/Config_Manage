# ShellEmulator

ShellEmulator — это эмулятор командной оболочки для работы с виртуальной файловой системой. Эмулятор имитирует сеанс shell в UNIX-подобной операционной системе и поддерживает набор ключевых команд.

## Постановка задачи

Разработать эмулятор для языка оболочки ОС. Необходимо сделать работу эмулятора максимально похожей на сеанс shell в UNIX-подобной ОС. Эмулятор должен запускаться из реальной командной строки, а файл с виртуальной файловой системой не должен быть распакован пользователем. Эмулятор принимает образ виртуальной файловой системы в формате `tar` и работает в режиме CLI.

### Аргументы командной строки:
1. Имя компьютера для отображения в приглашении к вводу.
2. Путь к архиву виртуальной файловой системы.
3. Путь к лог-файлу.
4. Путь к стартовому скрипту.

### Особенности:
- Лог-файл формата `xml` записывает все действия во время последнего сеанса работы с эмулятором.
- Стартовый скрипт предназначен для выполнения заранее заданного списка команд из файла.

### Поддерживаемые команды:
1. `ls` — просмотр списка файлов и директорий.
2. `cd` — смена текущей директории.
3. `exit` — завершение работы эмулятора.
4. `rmdir` — удаление директории.
5. `who` — отображение информации о пользователях.
6. `history` — вывод истории выполненных команд.

Каждая команда должна быть протестирована тремя тестами.

---

## Установка и запуск

### Требования:
- Python 3.x
- Библиотеки: `tarfile`, `os`, `datetime`, `xml.etree.ElementTree`

### Запуск:
1. Убедитесь, что tar-архив виртуальной файловой системы находится в директории или укажите его путь.
2. Выполните запуск эмулятора через командную строку:
```bash
python main.py --hostname my_computer --tar_path system.tar --log_path log.xml
```

---

## Описание команд

- **ls**: Выводит список файлов и папок текущей директории.
```bash
> ls
file1.txt
file2.txt
folder
```

- **cd**: Переход между директориями.
```bash
> cd folder
> ls
subfile1.txt
```

- **exit**: Завершение работы эмулятора.

- **rmdir**: Удаление директории.
```bash
> rmdir folder
```

- **who**: Отображение текущих пользователей системы.
```bash
> who
user1
```

- **history**: Отображение истории выполненных команд.
```bash
> history
1: ls
2: cd folder
3: exit
```

---

## Пример использования

Скриношт: https://imgur.com/a/FCU5U3I

```bash
> ls
file1.txt
folder
> cd folder
> ls
subfile1.txt
> history
1: ls
2: cd folder
3: ls
> exit
```