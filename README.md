# 13.1_K8S_Aleksandr_Molokov

### Задание 1 

Создать Deployment приложения, состоящего из двух контейнеров и обменивающихся данными.

1. Создать Deployment приложения, состоящего из контейнеров busybox и multitool.
2. Сделать так, чтобы busybox писал каждые пять секунд в некий файл в общей директории.
3. Обеспечить возможность чтения файла контейнером multitool.
4. Продемонстрировать, что multitool может читать файл, который периодоически обновляется.
5. Предоставить манифесты Deployment в решении, а также скриншоты или вывод команды из п. 4.

### Ответ

#### 1. ![Deployment](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/blob/e9f961681ccd437bbe0ac6c97c017a1c6c657807/deploy-volume.yaml)

#### Контейнер bysubox

![busybox](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/801c779b-689e-4b98-b0e2-a8a2e57f3b02)

#### Контейнер multitool

![multitool](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/21d7051a-5216-4b0d-95a6-c724fbad4373)


------

### Задание 2

Создать DaemonSet приложения, которое может прочитать логи ноды.

1. Создать DaemonSet приложения, состоящего из multitool.
2. Обеспечить возможность чтения файла `/var/log/syslog` кластера MicroK8S.
3. Продемонстрировать возможность чтения файла изнутри пода.
4. Предоставить манифесты Deployment, а также скриншоты или вывод команды из п. 2.

### Ответ

#### ![DaemonSet](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/blob/76f99df00385450758fbfbe61b612dd3bf234b2d/daemonSet.yaml)

#### Статус daemonSet и Pod

![get ds and pods](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/0e090145-4afe-44a8-90ba-ecee86f40c06)

#### Проверка доступности файлов кластера

#### Подключение к поду

![подключение к поду](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/0cdc4f4d-1a47-4a17-9a13-e1d6530319dd)

#### Сравнение диреткорий кластера /var/log  и volume пода multitool

![var - logs](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/72ac3cc4-ffa3-4321-a5c4-dfb3c4ef9a8f)

#### вывод команды cat syslog из пода multitool

![multitool cat syslog](https://github.com/ALEMOLOKOV/13.1_K8S_Aleksandr_Molokov/assets/109212419/d610c238-117e-4bc1-a80a-eece79e98331)



