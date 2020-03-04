# Установка Eclipse на Ubuntu #
## Скачивание и установка основного ПО ##

### JRE/Java ###
	sudo apt-get install default-jdk
или используя гайды с русскоязычной версии [сайта](https://help.ubuntu.ru/wiki/java) посвещенного Ubuntu.
### Openocd ###
	sudo apt-get install openocd
или скачайте с официального [сайта](http://openocd.org/).
### Eclipse ###
Скачайте [Eclipse](https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2019-12/R/eclipse-inst-linux64.tar.gz) для вашего ПК и установите его. 
### GDB ###
Скачайте [arm-none-eabi-gdb](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) и распакуйте в удобную для вас папку.
### STM32CubeMX ###
Скачайте [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html) и установите его. 


## Промежуточные действия ##

### Добавление в Eclipse расширений ###
Необходимо уставновить: ***С/С++ GDB Hardware Debugging***. Его можно найти по пути
**Help -> Install New Software...**
В писать в Work with: ресурс, с которого вы будете скачивать, [например](https://download.eclipse.org/releases/2019-12/),
или **Help -> Eclipse Marketplase...** в этом маркетплейсе вы аналогично можете найти GDB Hardware Debugging.

В итоге в **Run -> Debug Configurations...** должен появится GDB Hardware Debugging

### Изменение правил UDEV  ###
Для этого надо положить в **/etc/udev/rules.d/** файл, находящийся по пути, **/usr/share/openocd/contrib/99-openocd.rules**, который идет в комплекте с openocd. 
Если вы не нашли этого файла у себя в системе, можно попробовать добавить скачать [файл](https://github.com/ntfreak/openocd/blob/master/contrib/60-openocd.rules) и добавить уже его. 
Перезагрузить правила UDEV:

	sudo udevadm control --reload-rules


### Правильная генерация кода STM32CubeMx ###
После того, как вы настроили нужную для себя периферию, необходимо во вкладке **Project Manager** выбрать в параметрах **Tolchain/IDE ->Makefile**

### Импортирование проекта в Eclipse ###


## Запуск отладки ##
1. Запуск openocd
	sudo openocd  -f /usr/share/openocd/scripts/board/stm32fXX.cfg
Где **XX** модель вашей платы. 
2. Работа в Eclipse
А в Eclipse нажимаем на отладку(Debbug). Если все ок, то Eclipse предложит перейти в перспективу отладки и остановит программу. Можно ставить точку останова в коде и возобновить работу программы.