# ansible

Для проверки дз необходимо запустить Vagrantfile, который поднимет 2 машины.
На одной из них будет развернут ansible, вторая для развертывания nginx с помощью
ansible-playbook. Необходимо чтобы скрипты ansible.sh и nginx.sh (эти скрипты
разворачивают ansible и прокидывают ssh ключи) лежали в 
одной директории с Vagranfile. После поднятия виртуальных машин, заходим на 
машину с ansible:
vagrant ssh ansible
Там выполняем:
ansible-playbook /vagrant/nginx.yml
И проверяем что на второй машине развернулся поднялся nginx
curl 192.168.50.11:8080
Или можно зайти на вторую машину:
vagrant ssh nginx
И там выполнить:
curl localhost:8080