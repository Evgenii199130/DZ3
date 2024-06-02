# Домашнее задание к занятию «GitLab» Королев Евгений
#Задание 1
#Что нужно сделать:

#Разверните GitLab локально, используя Vagrantfile и инструкцию, описанные в этом репозитории.
#Создайте новый проект и пустой репозиторий в нём.
#Зарегистрируйте gitlab-runner для этого проекта и запустите его в режиме Docker. Раннер можно регистрировать и запускать на той же виртуальной машине, на которой запущен GitLab.
#В качестве ответа в репозиторий шаблона с решением добавьте скриншоты с настройками раннера в проекте.

#Ответ:
https://github.com/Evgenii199130/DZ3/blob/main/1.png
https://github.com/Evgenii199130/DZ3/blob/main/2.png
https://github.com/Evgenii199130/DZ3/blob/main/3.png
https://github.com/Evgenii199130/DZ3/blob/main/4.png


Задание 2
Что нужно сделать:

Запушьте репозиторий на GitLab, изменив origin. Это изучалось на занятии по Git.
Создайте .gitlab-ci.yml, описав в нём все необходимые, на ваш взгляд, этапы.
В качестве ответа в шаблон с решением добавьте:

файл gitlab-ci.yml для своего проекта или вставьте код в соответствующее поле в шаблоне;
скриншоты с успешно собранными сборками.

Ответ:

https://github.com/Evgenii199130/DZ3/commit/2cfb5a0edee3a00c8740ddbc74b26497066d2397

Код:
image: ubuntu:22.04

stages:
  - build
  - test

build:
  stage: build
  script:
    - apt-get update
    - apt-get install -y build-essential
    - make

test:
  stage: test
  script:
    - make test
