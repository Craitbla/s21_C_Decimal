## О запуске

```git clone``` \
```cd src```

Есть возможность запустить тесты с использованием Docker контейнера (предполагается установленный Docker)

```docker pull alpine:3.20``` \
```docker build -t s21_decimal .``` \
```docker run -it --rm s21_decimal``` \

Также можно проверить стиль

```cd ../materials/build``` \
```sh run.sh```
