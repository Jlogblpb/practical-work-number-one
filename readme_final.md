    ## Веб-сервер на Go, который реализует функциональность простейшего планировщика задач.
    
    Планировщик хранит задачи, каждая из них содержит дату дедлайна и заголовок с комментарием. 
    Задачи могут повторяться по заданному правилу: например, ежегодно, через какое-то количество
    дней. Если отметить такую задачу как выполненную, она переносится на следующую дату в 
    соответствии с правилом. Обычные задачи при выполнении просто удаляются. 
    
API содержит следующие операции:
- добавить задачу;
- получить список задач;
- удалить задачу;
- получить параметры задачи;
- изменить параметры задачи;
- отметить задачу как выполненную.

Задания повышенной трудности не выполнялись.

Для запуска кода необходимо в терминале, в директории с проектом ввести команду go run ./...
В браузере необходимо ввести адрес: http://localhost:7540/

Для запуска тестов использовать следующие команды:



 Виду того что задания повышенной сложности не выполнялись, в директории с тестами в файле settings.go 
 значение переменной FullNextDate должно быть false.
 Так же можно проверить значения других переменных:
 Port = 7540;
 DBFile = "../scheduler.db";
 Search = false;
 Token = ``.

Сброс кеша тестов в случае если тесты запускались ранее: 

go clean -testcache

Тесты можно запускать как по одному, так и все сразу, скопировав все 9 строк и вставив их в терминал:
go test -run ^TestApp$ ./tests
go test -run ^TestDB$ ./tests
go test -run ^TestNextDate$ ./tests
go test -run ^TestAddTask$ ./tests
go test -run ^TestTasks$ ./tests
go test -run ^TestTask$ ./tests
go test -run ^TestEditTask$ ./tests
go test -run ^TestDone$ ./tests
go test -run ^TestDelTask$ ./tests