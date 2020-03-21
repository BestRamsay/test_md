# Описание схемы #

Вся схема разбита на 5 [главных](#Главные_задачи) задач, 2 [побочные](#Побочные_задачи) и 2 [бинарных](#Бинарные_семафоры) семафора.



## <a name="Главные_задачи">Главные задачи</a> ##

### 1.TaskUARTGetData ###

![TaskUARTGetData](/img/1.TaskUARTGetData.png)

В этой задаче происходит прием данных из **UART** и запись в очередь посредством использования функции FreeRTOS

	osMessagePut(RX_Queue, QUEUE_SIZE, uint16_t)

Сама очередь постороена по принципу FIFO, что позволяет не потерять новые данные, пришедшие с UART'а. 

### 2.TaskComputeCommand ###

![TaskComputeCommand](/img/2.TaskComputeCommand.png)

В этой задаче данные из очереди отправляются в парсер. В результате анализа из команды выдедяется 3 типа данных

1.	Параметр
2.	Действие
3.	Ответ

Найденный параметр **не обрабатывается** самим парсером, а отправляется в задачу с выполнением действий для последующей постобработки(). 

### 3.TaskActionCommand ###

![TaskActionCommand](/img/3.TaskActionCommand.png)

### 4.TaskPreparationResponse  ###

![TaskPreparationResponse](/img/4.TaskPreparationResponse.png)

### 5.TaskUARTPushData ###

![TaskUARTPushData](/img/5.TaskUARTPushData.png)



## <a name="Побочные_задачи">Побочные задачи</a> ##

### 1.sideTaskDisplayPushData ###

### 2.sideTaskKBGetAction ###



## <a name="Бинарные_семафоры">Бинарные семафоры</a> ##

### 1.BinSemNoParseGoAction ###

### 2.BinSemNoActionGoParse ###