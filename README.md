# "10.2 Кластеризация" Рогачев Дмитрий

# Задание 1
SMP (symmetric multiprocessing) – симметричная многопроцессорная архитектура. Главной особенностью систем с архитектурой SMP является наличие общей физической памяти, разделяемой всеми процессорами.

MPP (massive parallel processing) – массивно-параллельная архитектура. Главная особенность такой архитектуры состоит в том, что память физически разделена.
Отсутствие общей памяти в MPP архитектуре значительно снижает скорость межпроцессорного обмена, в отличие от SMP архитектуры, в которой общая память присутствует.
Каждый процессор в MPP архитектуре может использовать только ограниченный объем банка памяти, в то время,как процессор в SMP архитектуре охватывает полный объем.
В следствии недостатков MPP архитектура трудно реализуема, что приводит к значительным затратам, реализация SMP архитектуры, напротив, больших затрат не требует.
Главным преимуществом систем с раздельной памятью является хорошая масштабируемость: в отличие от SMP-систем, в машинах с раздельной памятью каждый процессор имеет доступ только к своей локальной памяти, в связи с чем не возникает необходимости в потактовой синхронизации процессоров.
 
 # Задание 2
Ключевое различие между слабосвязанной и тесно связанной системой состоит в том, что слабо связанная система имеет распределенную память, тогда как тесно связанная система имеет общую память. Слабосвязанное является эффективным, когда задачи, выполняемые на разных процессорах, имеют минимальное взаимодействие между ними.

# Задание 3
Кластерные системы отличаются следующими достоинствами.

Большая надежность. При отказе компьютера, входящего в кластер, используются ресурсы прочих серверов из того же кластера.

Высокая масштабируемость. В случае если нагрузка на кластер возрастет, в него просто добавляют еще один сервер.

Возможность перераспределения ресурсов серверов. Можно сделать кластер для серверов приложений и другой кластер — для серверов БД. Далее, в случае, если нагрузка на сервер БД будет выше, чем предполагалось, то рассматривается вопрос о передаче одного сервера из первого кластера во второй или даже вопрос о совместном использовании одной или нескольких машин в двух кластерах

# Задание 4
отказоустойчивые кластеры (High-availability clusters)

кластеры с балансировкой нагрузки (Load balancing clusters)

вычислительные кластеры (High performance computing clusters, HPC)

системы распределенных вычислений

# Задание 5

 Kafka — гибрид распределённой базы данных и брокера сообщений с возможностью горизонтального масштабирования. Kafka собирает у приложений данные, хранит их в своем распределённом хранилище, группируя по топикам, и отдаёт компонентам приложения по подписке. При этом сообщения хранятся на различных узлах-брокерах, что обеспечивает высокую доступность и отказоустойчивость. Kafka — это не СУБД в чистом виде, несмотря на то что она обеспечивает атомарность, согласованность, изолированность и долговечность хранимых данных, а также предоставляет возможность избирательного доступа к данным с помощью KSQL — SQL-движка на базе API Kafka Streams. Платформу используют как журнал фиксации и интеграционный центр для множества внешних СУБД и хранилищ.

Основное назначение — это централизованный сбор, обработка, безопасное хранение и передача большого количества сообщений от отделённых друг от друга сервисов. Эта распределённая, горизонтально масштабируемая платформа обычно применяется там, где очень много больших неструктурированных данных:

Масштабные IoT/IIoT-системы, характеризующиеся архитектурой с множеством датчиков, сенсоров, контроллеров и других конечных устройств.

Системы аналитики. Например, Kafka используется в компаниях IBM и DataSift в качестве коллектора для мониторинга событий и трекера потребления потоков данных пользователями в режиме реального времени.

Финансовые системы. Используют финансовые организации: Сбербанк, Тинькофф, Альфа-Банк, ING Bank.

Социальные сети. В Twitter Kafka — часть инфраструктуры потоковой обработки, а в LinkedIn используется для потоковой передачи данных о деятельности и операционных показателях приложений.

Системы геопозиционирования. Foursquare — для передачи сообщений между онлайн- и офлайн-системами, а также для интеграции средств мониторинга в свою big data инфраструктуру на базе Hadoop.

Телеком-операторы. ВымпелКом, МТС, Ростелеком и др.

Онлайн-игры. Например, Demonware, подразделение Activision Blizzard — для обработки логов пользователей.

Самый простой пример: с помощью Apache Kafka можно собирать логи сеансов от клиентов в потоковом режиме или логи с физических файлов журналов с серверов, а затем помещать их в одном месте, например в HDFS — файловой системе Apache Hadoop. Также сервис позволяет построить конвейер данных, чтобы с помощью алгоритмов машинного обучения извлекать из сырой информации сведения, ценные для бизнеса.




RabbitMQ — брокер сообщений с открытым исходным кодом

RabbitMQ — распределённый и горизонтально масштабируемый брокер сообщений. Упрощённо его устройство можно описать так:

паблишер, который отправляет сообщения;

очередь, где хранятся сообщения;

подписчики, которые выступают получателями сообщений.

RabbitMQ передаёт сообщения между поставщиками и подписчиками через очереди. Сообщения могут содержать любую информацию, например, о событии, произошедшем на сайте. 

RabbitMQ отлично подходит для интеграции разных компонентов, создания микросервисов, потоковой передачи данных в режиме реального времени или при передаче работы удалённым работникам. Его используют крупные компании, в числе которых Bloomberg, Reddit, WeWork, NASA и др. 


Сценарии использования RabbitMQ
Обычно отмечают два варианта, когда стоит использовать RabbitMQ: для фоновой обработки данных и для интеграции внутри приложений и между ними, т.е. в качестве брокера сообщений между микросервисами. Рассмотрим оба сценария. 

Фоновая обработка данных
Фоновая обработка данных — оптимальный сценарий использования RabbitMQ. Вы можете поместить сообщение в очередь без его немедленной обработки.

Пример: вы хотите загрузить отчёт из приложения. Приложение обрабатывает информацию и генерирует PDF-файл в течение 15-20 минут. Затем отправляет его вам по электронной почте. Очередь сообщений позволяет выполнить все задачи асинхронно.

Очереди RabbitMQ служат шинами событий и позволяют веб-серверам быстро реагировать на запросы вместо того, чтобы выполнять трудоемкие задачи на месте.

Посредник в микросервисной архитектуре
Также RabbitMQ часто используется для микросервисной архитектуры, где он выступает средством связи между приложениями и помогает избегать узких мест при передаче сообщений.

























