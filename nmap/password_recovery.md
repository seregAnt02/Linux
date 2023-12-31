##### Восстановление паролей и ключей из памяти процессов:
* Восстановление паролей и ключей из памяти процессов в Linux реализовано не так разнообразно как в Windows, но тоже остается возможным. Для этого используются специальные инструменты и подходы.
* Пример:
* Mimipenguin — это инструмент для перехвата паролей из памяти процессов, работающих на Linux-системе. Обычно он
используется для получения паролей, введенных пользователем в терминал, например, паролей от системы или приложений.
После запуска Mimipenguin начнет мониторить процессы в системе и попытается извлечь пароли из памяти процессов. Если он найдет пароли — он отобразит их в терминале.

* Другой пример:
* truffleproc — это инструмент для перехвата паролей из памяти любых процессов работающих в системе Linux, который ищет
пароли и ключи API в процессах по регулярным выражениям выполняя выгрузку памяти процесса и анализируя ее.

* Ссылка на инструмент: https://github.com/controlplaneio/truffleproc

##### Вы можете сделать то же самое вручную, выбрав нужный процесс.
* Если вы обнаружите, что процесс аутентификации запущен:
*  ps -ef | grep "authenticator"
* > root 2027 2025 0 11:46 ? 00:00:00 authenticator

* Вы можете сделать дамп процесса (например, инструментом memory-dump) и поискать учетные данные в памяти:
*  ./dump-memory.sh 2027
*  strings *.dump | grep -i

###### Прочие подобные утилиты:

* 3snake – перехват паролей ssh, sudo и su (experimental)
* SSHPry2.0 – перехват данных в терминале
* Gimmecredz – дамп паролей в памяти (на основе bash)

##### Внесение изменений в ядро ОС и в предустановленные службы на нем
* Самые продвинутые и зачастую самые надежные подходы по закреплению доступа - это серия методов, позволяющих проникать глубоко в ядро ОС и изменять стандартные службы удаленного доступа, аутентификации, обработки событий и пр.

###### Плюсы подхода:

* Некоторые из методов почти невозможно обнаружить при использовании стандартных средств анализа ОС, только используя глубокий анализ дампа памяти ОС. (Существуют методы, которые скрывают свое наличие при входе на сервер администратора и потом возвращают свое присутствие)
Такие методы зачастую могут действовать даже после обновления ОС, и в частных случаях даже после переустановки ОС.
Реализовать такой метод без действий, которые могут быть замечены в ходе выполнения, может быть не просто.
* Минусы подхода:

* Высокая сложность реализации таких методов, а также сложность их отладки.
Разница в версии ОС или дистрибутиве может быть критически важной для выбора метода закрепления из этой категории.
Одним из самых популярных примеров внесения изменений в ядро ОС и закреплением на уровне ядра, может быть использование программ под общим названием RootKit.

* Rootkit — это вид вредоносного программного обеспечения, которое скрывает свою присутствие на компьютере или другом
устройстве, изменяя функциональность операционной системы и скрывая свои следы от пользователей и системных программ.

* Например:

* TripleCross - это Linux eBPF-руткит с открытым исходным кодом, который демонстрирует наступательные возможности технологии eBPF*.
eBPF (Extended Berkeley Packet Filter) - это технология ядра Linux, которая позволяет расширять функциональность стандартного фильтра Berkeley Packet Filter (BPF) для обработки пакетов и мониторинга событий в ядре.
Работа eBPF осуществляется через специальное виртуальное машинное окружение (VM), которое запускается внутри ядра Linux.Оно позволяет загружать и исполнять программы на языке C, которые могут обрабатывать пакеты на уровне ядра, принимать решения о пересылке или отбрасывании пакетов, создавать и мониторить события в ядре и многое другое.

* Также для закрепления доступа используют ПО, именуемое Remote Admin Tool, что по своей сути очень похоже на RootKit, но
иногда не претендует на скрытность. Тем не менее, в этой категории также присутствуют заметные представители. В том числе существуют легальные RAT-средства.

* Утилиты RAT (Remote Access Tool) — это программные инструменты, которые позволяют удаленно управлять компьютером или устройством без ведома пользователя. RAT-утилиты могут быть использованы для различных целей, в том числе для управления компьютером из удаленного места, сбора конфиденциальной информации, мониторинга активности пользователя и т.д.

* Например: https://github.com/n1nj4sec/pupy
