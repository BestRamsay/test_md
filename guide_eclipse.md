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
Необходимо уставновить :С/С++ GDB Hardware Debugging. Его можно найти по пути
Help -> Install New Software...
В писать в Work with: ресурс, с которого вы будете скачивать. [Например](https://download.eclipse.org/releases/2019-12/) 
или 
Help -> Eclipse Marketplase...
В этом маркетплейсе вы аналогично можете найти GDB Hardware Debugging.

В итоге в Run -> Debug Configurations... должен появится GDB Hardware Debugging

### Правильная генерация кода STM32CubeMx ###

Необходимо при 
Cross GCC 