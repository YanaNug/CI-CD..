**Процессы CI/CD**

***HomeWork 2. Continuous integration (непрерывная интеграция)***
Переписать test stage для тестирования docker-а. Достаточно проверить, что docker контейнер на базе нашего собранного образа в предыдущей job запускается.

    docker build:
    image: docker:latest
    stage: build
    services:
        - docker:dind
    script:
        - docker login -u $GITLAB_CI_USER -p $GITLAB_CI_PASSWORD $CI_REGISTRY
        - echo $GITLAB_CI_USER $GITLAB_CI_PASSWORD $CI_REGISTRY $CI_REGISTRY_IMAGE:$IMAGE_TAG
        - docker build -t $CI_REGISTRY_IMAGE:$IMAGE_TAG .
        - docker push $CI_REGISTRY_IMAGE:$IMAGE_TAG

    testdocker:
    stage: test
    script:
        - docker pull $CI_REGISTRY_IMAGE:$IMAGE_TAG
        - docker images 
        - echo "----------MY DOCKER IMAGE TEST----------"


Прислать ссылку на gitlab_ci.yaml либо скриншот gitlab_ci.yaml test stage и скриншот успешно отработанной job-ы test.

Ссылка на файл gitlab_ci.yaml

https://gitlab.com/ci_cd9421913/homework_2/-/tree/main

Тест, к сожалению не прошел

![](001.png)

![](002.png)