# MongoDB

1. Сначала нужно скачать MongoDB и MongoDB Compass
2. Создаем датабейс с именем db и коллекцию user
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2000.42.38.png)
3. Получили пустой датасет 
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2000.42.48.png)
4. Теперь загружаем скаченный датасет
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2000.43.04.png)
5. Теперь попробуем вывести все элементы, где возраст равняется 20 с помощью комманды '''db.user.find({Age:20})'''
6. Вот что мы получили
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.09.58.png)
7. Теперь попробуем вывести только с полями "Age" и "Genre" с помощью комманды '''db.users.find({ }, {Genre: "Male", Age: 20});'''
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.13.03.png)
8. Также можем делать поиск сразу по нескольким полям как тут
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.13.26.png)
9. Можно и задавать интервалы, используя операторы: $lt — меньше, $lte — меньше или равно, $gt — больше, $gte — больше или равно, $ne — не равно. 
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.14.25.png)
10. Сейчас попробуем обновить строку с данными, используя '''db.user.updateOne({"CustomerID": "0001"}, {$set:{"Genre": "Female"}})'''
вот что было до
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.20.12.png)
применяем комманду
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.20.12.png)
И проверяем нашу работу
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.20.54.png)
11. Давайте проверим удаление с помощью комманды '''db.user.deleteOne({"CustomerID": "0001"})'''. И да, нашей строки больше нет 
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.22.43.png)
12. Ну и аналогичная комманда вставки '''db.user.insert({"CustomerID": "0021"})'''
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.22.43.png)
13. Сделаем запрос без индекса
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.35.13.png)
totalDocsExamined указывает, что MongoDB отсканировал 200 документов. Добавим индекс '''db.user.createIndex({Age: 1 })''' и снова сделаем запрос.
![alt text](https://github.com/KristinaKulabuhova/MongoDB/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-03-08%20%D0%B2%2001.36.15.png)
totalDocsExamined указывает, что MongoDB отсканировал 10 документов. Получили, что при работе с индексом результат запроса очень эффективный.

