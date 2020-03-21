# Описание схемы #

Вся схема разбита на 5 [главных](#Главные_задачи) задач, 2 [побочные](#Побочные_задачи) и 2 [бинарных](#Бинарные_семафоры) семафора.


## <a name="Главные_задачи">Главные задачи</a> ##

### 1.TaskUARTGetData ###

В этой задаче происходит прием данных из **UART** и запись в очередь посредством использования функции FreeRTOS

	osMessagePut(RX_Queue, QUEUE_SIZE, uint16_t)

Сама очередь постороена по принципу FIFO, что позволяет не потерять новые данные, пришедшие с UART'а. 

### 2.TaskComputeCommand ###

### 3.TaskActionCommand ###

### 4.TaskPreparationResponse  ###

### 5.TaskUARTPushData ###


## <a name="Побочные_задачи">Побочные задачи</a> ##

### 1.sideTaskDisplayPushData ###

### 2.sideTaskKBGetAction ###


## <a name="Бинарные_семафоры">Бинарные семафоры</a> ##

### 1.BinSemNoParseGoAction ###

### 2.BinSemNoActionGoParse ###