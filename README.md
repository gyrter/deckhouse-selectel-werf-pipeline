# Пример Werf Pipeline

Это простой пример Werf Pipiline.

# Как использовать

Для его работы требуются следующие переменные:
* `WERF_KUBECONFIG_BASE64` - конфиг для доступа в Kubernetes;
* `SEL_REGISTRY_DOMAIN` со значением cr.selcloud.ru;
* `SEL_REGISTRY` c именем нашей Registry – в нашем случае example, имя выбирается при создании Registry;
* `WERF_USERNAME` со значением token;
* `WERF_PASSWORD` с токеном, который мы получили из админ панели Selectel для доступа к CRaaS.

Так же вам потребуется Gitlab Runner с тегом `werf` и установленной утилитой `werf`. Как поставить можно прочитать на [официальном сайте](https://werf.io/installation.html).

Pipeline можно подключать к репозиториям, указав в `.gitlab-ci.yml`, где **deploy-lib** проект с шаблонным CI/CD
```
include:
  - project: "deploy-lib"
    ref: main
    file:
      - "/gitlab-ci.yml"
```
