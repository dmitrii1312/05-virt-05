## Задача 1
Дайте письменые ответы на следующие вопросы:

- В чём отличие режимов работы сервисов в Docker Swarm кластере: replication и global?
Replicated - запускает определённое в команде количество реплик сервиса
global - запускает одну реплику на каждом хосте Swarm

- Какой алгоритм выбора лидера используется в Docker Swarm кластере?
Лидер выбирается при помощи алгоритма Raft

- Что такое Overlay Network?
Это виртуальная сеть для взаимодействия между контейнерами

## Задача 2
Создать ваш первый Docker Swarm кластер в Яндекс.Облаке
![image](https://user-images.githubusercontent.com/93075740/159244936-4889e67b-addd-4bdd-adeb-52a8af37f366.png)


## Задача 3
Создать ваш первый, готовый к боевой эксплуатации кластер мониторинга, состоящий из стека микросервисов.
![image](https://user-images.githubusercontent.com/93075740/159246828-9d96caf3-a1f7-49c9-b249-19ba0d8cfe13.png)

## Задача 4 (*)
Выполнить на лидере Docker Swarm кластера команду (указанную ниже) и дать письменное описание её функционала, что она делает и зачем она нужна

```
[root@node01 ~]# docker swarm update --autolock=true
Swarm updated.
To unlock a swarm manager after it restarts, run the `docker swarm unlock`
command and provide the following key:

    SWMKEY-1-qFOgPeFch3TgnTV4lIG9QQdL9jRInbNAe1AsMV8VzT8

Please remember to store this key in a password manager, since without it you
will not be able to restart the manager.
```
Эта команда включает шифрование TLS ключей, использующихся для связи с другими нодами и для шифрования/расшифровки логов Raft. Эти ключи будут храниться в зашифрованном виде. После выполнения этой команды, в случае перезагрузки manager-нод, нужно будет на них выполнять команду docker swarm unlock и ввести указанный ключ. 
