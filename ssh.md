### Опции команды SSH
Теперь давайте рассмотрим самые основные опции команды ssh:

* f - перевести ssh в фоновый режим;
* g - разрешить удаленным машинам обращаться к локальным портам;
* l - имя пользователя в системе;
* n - перенаправить стандартный вывод в /dev/null;
* p - порт ssh на удаленной машине;
* q - не показывать сообщения об ошибках;
* v - режим отладки;
* x - отключить перенаправление X11;
* X - включить перенаправление Х11;
* C - включить сжатие.
#### Секретный ключ:
SSH-ключ — безопасный способ соединения с сервером. Подключение по SSH с помощью ключа исключает риск, который связан с подбором и взломом вашего пароля.
Для аутентификации используются два ключа: приватный и публичный. Публичный ключ хранится на сервере в корневом каталоге, а приватный ключ остаётся на локальном компьютере в зашифрованном виде. Каждый раз, когда вы обращаетесь к серверу, происходит сопоставление ключей.
#### Как мне выйти из SSH-соединения?
Два пути:
Закрытие сеанса оболочки, например, с exit после которого следует Enter, или Ctrl - d обычно позволяет вам нормально выйти из сеанса ssh ,
Если у вас плохое соединение и оболочка не отвечает, нажмите клавишу Enter, затем введите ~. и ssh должен немедленно закрыться и вернуть вас в командную строку.