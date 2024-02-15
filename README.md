# Yandex-Cloud

### Задание 1
Выполните действия, приложите скриншот скриптов, скриншот выполненного проекта.

От заказчика получено задание: при помощи Terraform и Ansible собрать виртуальную инфраструктуру и развернуть на ней веб-ресурс.

В инфраструктуре нужна одна машина с ПО ОС Linux, двумя ядрами и двумя гигабайтами оперативной памяти.

Требуется установить nginx, залить при помощи Ansible конфигурационные файлы nginx и веб-ресурса.

Секретный токен от yandex cloud должен вводится в консоли при каждом запуске terraform.

Для выполнения этого задания нужно сгенирировать SSH-ключ командой ssh-keygen. Добавить в конфигурацию Terraform ключ в поле:
 ![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/0b22b5ee-1f67-40d7-bec1-f87484f79cf6) 

 В файле meta прописать:
 ![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/c96f76f6-264a-4fec-8871-728164b7b7b4)

 Где xxx — это ключ из файла /home/"name_ user"/.ssh/id_rsa.pub. Примерная конфигурация Terraform:
 ![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/8ca6fdb9-7559-4fa5-8716-f619f2d636df) 
 ![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/0fb41214-0743-48f0-82b4-f61c82e6f3ea)
 ![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/3f29e362-c5e5-4ec9-84a1-f7fba3270937) 

 В конфигурации Ansible указать:

1. внешний IP-адрес машины, полученный из output external_ ip_ address_ vm_1, в файле hosts;
2. доступ в файле plabook *yml поля hosts.
   
![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/13b59321-e206-42b0-8526-94a32441fc57)


Провести тестирование.

Создаю файл main.tf с настройками провайдера в директории проекта, при этом terraform init 
![1](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/a8f9004d-a87e-4dd4-b884-19b498e9d209)
![2](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/ef76c9f7-ed23-422d-85ac-365021b754a1)
ключ: cat ~/.ssh/id_rsa.pub

terraform apply :
![3](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/c1af4691-9980-40a1-949f-8b8e639630ea)

sudo nano /etc/ansible/hosts :
![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/30ea9e98-cd7c-45a7-8457-92941244ff63)

ansible-playbook playbook.yml:
![6](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/df1781b7-4b33-4342-8ae5-daab52a9bc83)

![image](https://github.com/AnastasiyaEvsseva/Yandex-Cloud/assets/151757353/0a5d48d5-5006-4895-86f1-0bb7fc80ce75)









   




