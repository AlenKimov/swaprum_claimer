# Swaprum airdrop claimer
Claims swaprum.finance/free-tokens airdrop!

- [Установка под Windows](#Установка-под-Windows)
- [Установка под Ubuntu](#Установка-под-Ubuntu)
- [Работа со скриптом](#Работа-со-скриптом)

## Установка под Windows
- Установите [Python 3.11](https://www.python.org/downloads/windows/). Не забудьте поставить галочку напротив "Add Python to PATH".
- Установите пакетный менеджер [Poetry](https://python-poetry.org/docs/). Не забудьте добавить Poetry в переменную окружения Path.
- Установите [git](https://git-scm.com/download/win).
- Склонируйте этот репозиторий, после чего перейдите в него:
```bash
git clone https://github.com/AlenKimov/swaprum_claimer.git
cd swaprum_claimer
```
- Установите требуемые библиотеки с помощью Poetry:
```bash
poetry update
```
- [Подробнее об ошибке "Microsoft Visual C++ 14.0 or greater is required"](https://web3py.readthedocs.io/en/latest/troubleshooting.html#why-am-i-getting-visual-c-or-cython-not-installed-error)

## Установка под Ubuntu
- Обновите систему:
```bash
sudo apt update && sudo apt upgrade -y
```
- Установите [git](https://git-scm.com/download/linux) и screen:
```bash
sudo apt install screen git -y
```
- Установите Python 3.11 и зависимости для библиотеки web3:
```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.11 python3.11-dev build-essential libssl-dev libffi-dev -y
ln -s /usr/bin/python3.11/usr/bin/python
```
- Установите [Poetry](https://python-poetry.org/docs/):
```bash
curl -sSL https://install.python-poetry.org | python -
export PATH="/root/.local/bin:$PATH"
```
- Склонируйте этот репозиторий, после чего перейдите в него:
```bash
git clone https://github.com/AlenKimov/swaprum_claimer.git
cd swaprum_claimer
```
- Следующая команда установит требуемые библиотеки:
```bash
poetry update
```

## Работа со скриптом
После первого запуска создадутся файлы `private_keys.txt` и `public_keys.txt`.

Для автовывода средств на кошелек нужен доступ к его приватному ключу.
Внесите приватные ключи в файл `private_keys.txt`.

Для автосбора наград нужны лишь публичные ключи (адреса кошельков).
Внесите публичные ключи в файл `public_keys.txt`.
Если приватный ключ кошелька внесен в `private_keys.txt`,
НЕ НУЖНО повторно вносить его публичный ключ в `public_keys.txt`!

Для запуска скрипта пропишите следующую команду (или запустите `start.bat` на Windows):
```bash
poetry run python swaprum.py start
```

Для генерации аккаунтов пропишите следующую команду (или запустите `create_100_accounts.bat` на Windows):
```bash
poetry run python swaprum.py create 1000 --ref=your_ref_code
```