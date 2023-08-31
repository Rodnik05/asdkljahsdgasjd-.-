# Tinkoff_Sirius_ML_2023_CV

## Для начала нужно описать инопланетян.


1. Инопланетяне питаются энергией солнца.
2. Инопланетяне воспринимают формы лучше чем цвета.
3. Инопланетяне могут проходить сквозь объекты.

### Инопланетяне выглядят так:

![Aliens_v8](https://github.com/Rodnik05/Tinkoff_Sirius_ML_2023_CV/assets/89382155/de20c491-c614-4913-ad3a-1b72a81567a0)


#### Что же из этого следует?

1. Инопланетяне любят дома с большими окнами и не знают, что такое кухня
2. Инопланетяне любят дома с большим количеством неровностей и углов.
3. Инопланетянам не нужны двери


### Идеальный отелья для инопланетянина выглядит так:

![PerfectHotelForAliens_v1](https://github.com/Rodnik05/Tinkoff_Sirius_ML_2023_CV/assets/89382155/3dc4572d-e5b9-4e41-b436-eb918aad5b28)



## Изучение датасета фотографий

#### Для начала нужно ознакомиться с темой и ее проблематикой. Необходимо ответить на вопросы:

1. Что такое image captioning?

2. Почему над этим работают?

3. Как формулируется задача?

#### Ответы

1. Цель image captioning в том, чтобы предугадать описание изображения по нему самому.
2. Текстовое описание изображение увеличивает доступность информации, например люди, которые неспособны видеть, смогут понимать, что изображено на картинке. Также это может быть полезно для обучения сетей, так как это задает другую метритку сходства изображений(с точки зрения сходства описаний).
3. X - множество изображений;
  Y - множество описаний;
  Нужно обучиться на тренировочной выборке и выдавать для элемента из X наиболее подходящий элемент из Y(по какой-то метрике)


## Далее проведем обзор датасета

Тренировочный датасет не устанавливается(NET::ERR_CERT_DATE_INVALID).
Тестовый датасет устанавливается частично, но изображения повреждены.

Вообще в датасете должно быть такое количество изображений отелей:
1. test - 16171
2. train - 1124214

## Предобработка
Можно убрать все изображения с кухнями.
Желательно привести изображения к одному размеру
## Комментарии

Так как датасет не получилось установить, я могу лишь описать, что я бы стал делать.

1. Я бы смотрел на максимальные и минимальные значения по каждому каналу в RGB, чтобы оценить "угловатость" отеля(в качестве шкалы можно использовать что-то по типу: 1 - round, 2 - square, 3 - triangle, 4 - pentagon star, 5 - hexagon star)
2. 3. Привел бы изображения к одному размеру
3. Я бы создал теги("bed", "kitchen", "dining table" и т.п.), по которым бы производил классификацию
4. Удалил бы изображения с кухнями(изображения, на которых есть что-то кроме кухни можно оставить)
5. С изображений нужно убрать все двери(no doors)
6. Можно не переводить изображения в черно-белые, так как инопланетяне не отличают цвета



