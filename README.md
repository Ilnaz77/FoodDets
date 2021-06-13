<a name="">Summary</a>
---------------
#### Были полученя следующие результаты на test выборке:
* mean precision over classes in iou_t=0.5           0.2794859625364148
* mean recall over classes in iou_t=0.5              0.47295251939937416
* map@0.5                                            0.4675713441574298
* map@0.5:0.95                                       0.3760961946891499

Вкратце, распределение данных по классам имеет ~логнормальное распределение. Классов, у которых всего 1-2 ббокса на весь датасет очень много. Выборки трэйн\тест делал без ликов используя стратификацию по классам, для этого пришлось немного заапсемплить эти редкие классы. Датасет размечен не самым лучшим образом, полно недоразмеченных объектов и кривых ббоксов.

<a name="">Results download</a>
---------------
Если вы не хотите проходиться по всем шагам, обозначенным ниже, а просто хотите посмотреть результат, то скачайте следующие файлы из google.drive:
* Графики, метрики, top_N из google.drive: @@@@@@@
* Картинки из теста с предсказанными bbox'ами: @@@@@@@


<a name="">Dependencies</a>
---------------
Создать виртульную среду:
```shell
$ conda create --name detection python=3.8
$ conda activate detection
```
Установить все зависимости в эту среду:
```shell
$ pip3 install -r requirements.txt
```

<a name="">Start project</a>
---------------
Чтобы запустить test.py, надо сделать следующее:
1. Скачать подготовленный датасет new_data/ из google.drive: https://drive.google.com/file/d/1NXXmKnkM131Zi4MMG86XrFp-msxBtBdH/view?usp=sharing
2. Переместить папку new_data/ в корневую папку проекта
```shell
$ cd /new_data <your_path>/FoodDets/
```
3. Скачать веса модели из google.drive: https://drive.google.com/file/d/1SZyZeyRM1HCLH7aFRtXzXSN15cPO5ypY/view?usp=sharing
4. Переместить в папку FoodDets/weights/
```shell
$ cp best.pt FoodDets/weights/best.pt
```
5. Запустить:
```shell
$ python3 test.py
```

Таким образом, в корневой папке появится папка graphs/, в которой хранятся все метрики и графики.

<a name="">Create dataset</a>
---------------
Если не хотите скачивать датасет new_data/, а пройтись по шагам и сделать датасет из RAW данных, то:
1. Скачать сырые данные их google.drive: https://drive.google.com/file/d/1x3HbSGahLmz5ajItFUL17ox_BOlyxQVC/view?usp=sharing
2. Положить в корневой каталог FoodDets/
```shell
$ cp data_raw/ FoodDets/data_raw
```
3. Пройтись по шагам в data_preparation.ipynb

В результате появится папка new_data/




![alt text](https://github.com/Ilnaz77/FoodDets/blob/main/git_imgs/test_batch0_pred.jpg?raw=true)
![alt text](https://github.com/Ilnaz77/FoodDets/blob/main/git_imgs/test_batch0_gt.jpg?raw=true)

