# Рынок заведений общественного питания Москвы
Презентация для заказчика исследования: https://disk.yandex.ru/i/O7V414QV1Qc47g

## Описание проекта:
Мне — аналитику, поступил заказ — провести исследование рынка общественного питания Москвы, найти интересные особенности и презентовать полученные результаты, которые в будущем помогут заказчику в выборе подходящего места расположения объекта общепита. На основе результатов моего исследования, заказчик будет определять место расположения, категорию заведения: кафе, ресторан, пиццерия, паб или бар, — и какими будут меню и цены.

С открытых источников мне стал доступен датасет с заведениями общественного питания Москвы, составленный на основе данных сервисов Яндекс Карты и Яндекс Бизнес на лето 2022 года. Информация, размещённая в сервисе Яндекс Бизнес, могла быть добавлена пользователями или найдена в общедоступных источниках. Она носит исключительно справочный характер.

## Описание данных: Файл moscow_places.csv:
* name — название заведения;
* address — адрес заведения;
* category — категория заведения, например «кафе», «пиццерия» или «кофейня»;
* hours — информация о днях и часах работы;
* lat — широта географической точки, в которой находится заведение;
* lng — долгота географической точки, в которой находится заведение;
* rating — рейтинг заведения по оценкам пользователей в Яндекс Картах (высшая оценка — 5.0);
* price — категория цен в заведении, например «средние», «ниже среднего», «выше среднего» и так далее;
* avg_bill — строка, которая хранит среднюю стоимость заказа в виде диапазона, например:
  * «Средний счёт: 1000–1500 ₽»;
  * «Цена чашки капучино: 130–220 ₽»;
  * «Цена бокала пива: 400–600 ₽». и так далее;
* middle_avg_bill — число с оценкой среднего чека, которое указано только для значений из столбца avg_bill, начинающихся с подстроки «Средний счёт»:
  * Если в строке указан ценовой диапазон из двух значений, в столбец войдёт медиана этих двух значений.
  * Если в строке указано одно число — цена без диапазона, то в столбец войдёт это число.
  * Если значения нет или оно не начинается с подстроки «Средний счёт», то в столбец ничего не войдёт.
* middle_coffee_cup — число с оценкой одной чашки капучино, которое указано только для значений из столбца avg_bill, начинающихся с подстроки «Цена одной чашки капучино»:
  * Если в строке указан ценовой диапазон из двух значений, в столбец войдёт медиана этих двух значений.
  * Если в строке указано одно число — цена без диапазона, то в столбец войдёт это число.
  * Если значения нет или оно не начинается с подстроки «Цена одной чашки капучино», то в столбец ничего не войдёт.
* chain — число, выраженное 0 или 1, которое показывает, является ли заведение сетевым (для маленьких сетей могут встречаться ошибки):
  * 0 — заведение не является сетевым
  * 1 — заведение является сетевым
* district — административный район, в котором находится заведение, например Центральный административный округ;
* seats — количество посадочных мест.

## Этапы выполнения проекта:

 Шаг 1. Загрузка данных и изучение общей информации.

   * Загрузка данных о заведениях общественного питания Москвы.
   * Изучить общую информацию о датасете: Сколько заведений представлено? Что можно сказать о каждом столбце? Значения какого типа они хранят?

 Шаг 2. Выполнить предобработку данных.

   * Изучить, есть ли дубликаты в данных. Проверить наличие пропусков: встречаются ли они, в каких столбцах? Можно ли их обработать или оставить как есть?
   * Выполнить предобработку данных:
   * Создать столбец street с названиями улиц из столбца с адресом,
   * Создать столбец is_24_7 с обозначением, что заведение работает ежедневно и круглосуточно (24/7):
        * логическое значение True — если заведение работает ежедневно и круглосуточно; 
        * логическое значение False — в противоположном случае.

 Шаг 3. Выполнить анализ данных

   * Какие категории заведений представлены в данных? Исследовать количество объектов общественного питания по категориям: рестораны, кофейни, пиццерии, бары и так далее. 
     Построить визуализации. Ответить на вопрос о распределении заведений по категориям.

   * Исследовать количество посадочных мест в местах по категориям: рестораны, кофейни, пиццерии, бары и так далее. Построить визуализации. Проанализировать результаты и сделать 
     выводы.

   * Рассмотреть и изобразить соотношение сетевых и несетевых заведений в датасете. Каких заведений больше?

   * Какие категории заведений чаще являются сетевыми? Исследовать данные и ответить на вопрос графиком.

   * Сгруппировать данные по названиям заведений и найти топ-15 популярных сетей в Москве. Построить подходящую для такой информации визуализацию. Знакомы ли вам эти сети? Есть 
   ли какой-то признак, который их объединяет? К какой категории заведений они относятся? Отобразите общее количество заведений и количество заведений каждой категории по районам.

   * Какие административные районы Москвы присутствуют в датасете? Отобразите общее количество заведений и количество заведений каждой категории по районам. Попробуйте 
   проиллюстрировать эту информацию одним графиком.

   * Визуализируйте распределение средних рейтингов по категориям заведений. Сильно ли различаются усреднённые рейтинги в разных типах общепита?

   * Найдите топ-15 улиц по количеству заведений. Постройте график распределения количества заведений и их категорий по этим улицам. Попробуйте проиллюстрировать эту информацию 
    одним графиком.

   * Найдите улицы, на которых находится только один объект общепита. Что можно сказать об этих заведениях?
   
   * Анализируйте цены в центральном административном округе и других. Как удалённость от центра влияет на цены в заведениях? 
    
   * Необязательное задание: проиллюстрируйте другие взаимосвязи, которые вы нашли в данных. Например, по желанию исследуйте часы работы заведений и их зависимость от 
     расположения и категории заведения. Также можно исследовать особенности заведений с плохими рейтингами, средние чеки в таких местах и распределение по категориям заведений.

   * Соберите наблюдения по вопросам выше в один общий вывод.

Шаг 4. Детализация исследования: открытие кофейни. 

   * Рекомендации для инвестора.
     
   * Подготовка презентации для заказчика.

