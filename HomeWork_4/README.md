**Процессы CI/CD**

***HomeWork 4. Troubleshooting (диагностика и решение проблем в CI/CD)***

Сделать отдельный репозиторий с шаблонами CI и подключить его к своему основному репозиторию через include.

Ссылка на репозиторий https://gitlab.com/ci_cd9421913/homework_4


Создан локальный файл 
    
    smoke.gitlab-ci.yml

    smoke-test-job:
        script: echo "SMOKE"


Создан основной файл .gitlab-ci.yml

    include:
    - local: smoke.gitlab-ci.yml
   
    - remote: https://gitlab.com/ci-cd7655047/5/-/raw/main/remote-included-file.yml


![](001.png)

![](002.png)

![](003.png)

![](004.png)