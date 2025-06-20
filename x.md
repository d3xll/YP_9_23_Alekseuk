# 1 Задание
```
// Задание 1
// Создание объекта класса Student с именем, группой и массивом оценок
Student student = new Student("Поп Пис Сис", "ПРИВ22-2", new int[] {5, 4, 3, 2});

// Вызов метода GetInfo для вывода информации о студенте
student.GetInfo();




// Задание 2
// Создание объекта класса Cat с именем "Пукиш" и весом 4.2 кг
Cat cat = new Cat("Пукиш", 4.2);

// Вывод информации о коте: имя, вес, тип
Console.WriteLine("Кот: {0}, {1} кг, {2}", cat.Name, cat.Weight, cat.Type);

// Вызов метода MakeSound для кота
cat.MakeSound();

// Создание объекта класса Dog с именем "Попка" и весом 9.5 кг
Dog dog = new Dog("Попка", 9.5);

// Вывод информации о собаке: имя, вес, тип
Console.WriteLine("Собака: {0}, {1} кг, {2}", dog.Name, dog.Weight, dog.Type);

// Вызов метода MakeSound для собаки
dog.MakeSound();

// Создание объекта класса Wolf с именем "Джейкаб" и весом 83.6 кг
Wolf wolf = new Wolf("Джейкаб", 83.6);

// Вывод информации о волке: имя, вес, тип
Console.WriteLine("Волк: {0}, {1} кг, {2}", wolf.Name, wolf.Weight, wolf.Type);

// Вызов метода MakeSound для волка
wolf.MakeSound();




// Задание 3
// Создание объекта класса CheckPassword
CheckPassword checkPassword = new CheckPassword();

// Установка пароля "jopa03"
checkPassword.SetPassword("jopa03");

// Запуск метода PasswordCheck для проверки пароля
checkPassword.PasswordCheck();
```

```
// Определение класса Student
class Student
{
    // Приватное поле для хранения полного имени студента
    private string full_name;
    // Приватное поле для хранения группы студента
    private string group;
    // Приватное поле для хранения массива оценок
    private int[] marks;

    // Конструктор класса Student, принимающий имя, группу и массив оценок
    public Student(string full_name, string group, int[] marks)
    {
        // Инициализация поля full_name переданным значением
        this.full_name = full_name;
        // Инициализация поля group переданным значением
        this.group = group;
        // Инициализация поля marks переданным массивом
        this.marks = marks;
    }

    // Метод для вывода информации о студенте и его оценках
    public void GetInfo()
    {
        // Вывод полного имени и группы студента
        Console.WriteLine($"ФИО: {full_name}, группа: {group}");
        // Вывод заголовка для оценок
        Console.WriteLine("Оценки:");

        // Цикл для перебора всех оценок в массиве marks
        for (int i = 0; i < marks.Length; i++)
        {
            // Использование switch для обработки каждой оценки
            switch (marks[i])
            {
                // Если оценка равна 2
                case 2:
                    // Вывод расшифровки оценки
                    Console.WriteLine("2 - неудовлетворительно");
                    break;
                // Если оценка равна 3
                case 3:
                    // Вывод расшифровки оценки
                    Console.WriteLine("3 - удовлетворительно");
                    break;
                // Если оценка равна 4
                case 4:
                    // Вывод расшифровки оценки
                    Console.WriteLine("4 - хорошо");
                    break;
                // Если оценка равна 5
                case 5:
                    // Вывод расшифровки оценки
                    Console.WriteLine("5 - отлично");
                    break;
            }
        }
    }
}
```

```
// Определение базового класса Animal
class Animal
{
    // Приватные поля для хранения имени, веса и типа животного
    private string name;
    private double weight;
    private string type;

    // Конструктор класса Animal, принимающий имя, вес и тип
    public Animal(string name, double weight, string type)
    {
        // Инициализация полей класса переданными значениями
        this.name = name;
        this.weight = weight;
        this.type = type;
    }

    // Свойство для получения значения поля name (только чтение)
    public string Name
    {
        get { return this.name; }
    }

    // Свойство для получения значения поля weight (только чтение)
    public double Weight
    {
        get { return this.weight; }
    }

    // Свойство для получения значения поля type (только чтение)
    public string Type
    {
        get { return this.type; }
    }

    // Виртуальный метод, который будет переопределяться в производных классах
    public virtual void MakeSound()
    {
        // Вывод звука по умолчанию для базового класса
        Console.WriteLine("каки");
    }
}

// Производный класс Cat, наследующий от Animal
class Cat : Animal
{
    // Конструктор класса Cat, вызывающий конструктор базового класса
    public Cat(string name, double weight) : base(name, weight, "Хищник, домашний") { }

    // Переопределение метода MakeSound для кота
    public override void MakeSound()
    {
        // Вывод звука кота с использованием имени
        Console.WriteLine("{0} говорит: Мяу", this.Name);
    }
}

// Производный класс Dog, наследующий от Animal
class Dog : Animal
{
    // Конструктор класса Dog, вызывающий конструктор базового класса
    public Dog(string name, double weight) : base(name, weight, "Хищник, домашний") { }

    // Переопределение метода MakeSound для собаки
    public override void MakeSound()
    {
        // Вывод звука собаки с использованием имени
        Console.WriteLine("{0} говорит: Гав", this.Name);
    }
}

// Производный класс Wolf, наследующий от Animal
class Wolf : Animal
{
    // Конструктор класса Wolf, вызывающий конструктор базового класса
    public Wolf(string name, double weight) : base(name, weight, "Хищник, дикий") { }

    // Переопределение метода MakeSound для волка
    public override void MakeSound()
    {
        // Вывод звука волка с использованием имени
        Console.WriteLine("{0} говорит: Ауууф", this.Name);
    }
}
```

```
// Определение класса CheckPassword
class CheckPassword
{
    // Приватное поле для хранения установленного пароля
    private string _password;

    // Метод для установки пароля
    public void SetPassword(string password)
    {
        // Присваивание переданного значения полю _password
        _password = password;
    }

    // Метод для проверки введенного пароля
    public void PasswordCheck()
    {
        // Бесконечный цикл для многократного запроса пароля
        while (true)
        {
            // Вывод сообщения с просьбой ввести пароль
            Console.WriteLine("Введите пароль: ");
            // Чтение введенной строки из консоли
            string input = Console.ReadLine();

            // Проверка, если длина введенного пароля меньше 3 символов
            if (input.Length < 3)
            {
                // Вывод сообщения об ошибке
                Console.WriteLine("пароль короткий");
            }
            // Проверка, если длина введенного пароля больше 8 символов
            else if (input.Length > 8)
            {
                // Вывод сообщения об ошибке
                Console.WriteLine("пароль длинный");
            }
            // Проверка, совпадает ли введенный пароль с установленным
            else if (input == _password)
            {
                // Вывод сообщения об успешной авторизации
                Console.WriteLine("Добро пожаловать");
                // Прерывание цикла, если пароль верный
                break;
            }
            // Если пароль не соответствует ни одному условию
            else
            {
                // Вывод сообщения об ошибке
                Console.WriteLine("пароль неверный");
            }
        }
    }
}
```


# 2 Задание
```
// Практическая работа №2, Массивы и Циклы.

// Создание и инициализация массива целых чисел
int[] arr = { 423, 14, 25, 41, 11, 99, 268 }; // Массив с 7 элементами

Console.WriteLine("Цикл for"); // Вывод заголовка для цикла for
for (int i = 0; i < 8; i++) // Цикл for от 0 до 7 (ошибка: выход за пределы массива)
{
    Console.Write(i + " "); // Вывод индекса i
}
Console.WriteLine(); // Пустая строка для форматирования вывода

Console.WriteLine("Цикл while"); // Вывод заголовка для цикла while
int j = 0; // Инициализация счетчика j
while (j < 4) // Цикл while выполняется, пока j меньше 4
{
    Console.Write(j + " "); // Вывод значения j
    j++; // Увеличение j на 1
}
Console.WriteLine(); // Пустая строка для форматирования вывода

Console.WriteLine("Цикл do-while"); // Вывод заголовка для цикла do-while
int k = 0; // Инициализация счетчика k
do
{
    Console.Write(k + " "); // Вывод значения k
    k++; // Увеличение k на 1
} while (k < 6); // Цикл do-while выполняется, пока k меньше 6
Console.WriteLine(); // Пустая строка для форматирования вывода

Console.WriteLine("Цикл foreach"); // Вывод заголовка для цикла foreach
foreach (int num in arr) // Перебор всех элементов массива arr
{
    Console.Write(num + " "); // Вывод каждого элемента массива
}
Console.WriteLine(); // Пустая строка для форматирования вывода

// Вызов методов сортировки с клонированием исходного массива, чтобы не изменять оригинал
int[] bubbleSorted = BubbleSort(arr.Clone() as int[]); // Сортировка пузырьком
int[] selectionSorted = SelectionSort(arr.Clone() as int[]); // Сортировка выбором
int[] quickSorted = QuickSort(arr.Clone() as int[], 0, arr.Length - 1); // Быстрая сортировка

// Метод пузырьковой сортировки
static int[] BubbleSort(int[] arr) // Принимает массив для сортировки
{
    int n = arr.Length; // Получение длины массива
    for (int i = 0; i < n - 1; i++) // Внешний цикл для проходов по массиву
        for (int j = 0; j < n - i - 1; j++) // Внутренний цикл для сравнения соседних элементов
            if (arr[j] > arr[j + 1]) // Если текущий элемент больше следующего
            {
                int temp = arr[j]; // Сохранение текущего элемента во временной переменной
                arr[j] = arr[j + 1]; // Замена текущего элемента на следующий
                arr[j + 1] = temp; // Замена следующего элемента на сохраненный
            }
    return arr; // Возврат отсортированного массива
}

// Метод сортировки выбором
static int[] SelectionSort(int[] arr) // Принимает массив для сортировки
{
    int n = arr.Length; // Получение длины массива
    for (int i = 0; i < n - 1; i++) // Внешний цикл для проходов по массиву
    {
        int minIndex = i; // Предположение, что текущий элемент — минимальный
        for (int j = i + 1; j < n; j++) // Внутренний цикл для поиска минимального элемента
            if (arr[j] < arr[minIndex]) // Если найден элемент меньше текущего минимального
                minIndex = j; // Обновление индекса минимального элемента
        int temp = arr[minIndex]; // Сохранение минимального элемента
        arr[minIndex] = arr[i]; // Замена минимального элемента с текущим
        arr[i] = temp; // Замена текущего элемента на минимальный
    }
    return arr; // Возврат отсортированного массива
}

// Метод быстрой сортировки (рекурсивный)
static int[] QuickSort(int[] arr, int low, int high) // Принимает массив и границы подмассива
{
    if (low < high) // Проверка, что есть элементы для сортировки
    {
        int pi = arr[high]; // Опорный элемент (выбирается последний элемент подмассива)
        int i = low - 1; // Индекс для элементов, меньших опорного
        for (int j = low; j < high; j++) // Цикл для разделения элементов относительно опорного
            if (arr[j] <= pi) // Если текущий элемент меньше или равен опорному
            {
                i++; // Увеличение индекса для меньших элементов
                int temp = arr[i]; // Сохранение текущего элемента
                arr[i] = arr[j]; // Замена с элементом, меньшим опорного
                arr[j] = temp; // Замена на сохраненный элемент
            }
        int temp1 = arr[i + 1]; // Сохранение элемента после меньших
        arr[i + 1] = arr[high]; // Помещение опорного элемента на правильную позицию
        arr[high] = temp1; // Замена на сохраненный элемент
        int piIndex = i + 1; // Индекс опорного элемента
        QuickSort(arr, low, piIndex - 1); // Рекурсивная сортировка левой части
        QuickSort(arr, piIndex + 1, high); // Рекурсивная сортировка правой части
    }
    return arr; // Возврат отсортированного массива
}
```

# 3 Задание
```
// Вызов методов Zadanie1, Zadanie2 и Zadanie3 последовательно
Zadanie1(); // Выполнение первой задачи
Zadanie2(); // Выполнение второй задачи
Zadanie3(); // Выполнение третьей задачи

// Метод для проверки числа на четность и кратность делителю
static void Zadanie1()
{
    int divisor = int.Parse(Console.ReadLine()); // Чтение делителя из консоли
    int number = int.Parse(Console.ReadLine()); // Чтение числа из консоли

    bool isEven = number % 2 == 0; // Проверка, является ли число четным
    bool isDivisible = number % divisor == 0; // Проверка, делится ли число на divisor без остатка

    Console.WriteLine(isEven ? "Четное" : "Нечетное"); // Вывод результата проверки на четность
    Console.WriteLine(isDivisible ? $"Кратно {divisor}" : $"Не кратно {divisor}"); // Вывод результата проверки на кратность
}

// Метод для проверки логина, пароля и оценки сложности пароля
static void Zadanie2()
{
    string correctLogin = "mdaaa"; // Корректный логин
    string correctPassword = "superPas12"; // Корректный пароль
    string login = Console.ReadLine(); // Чтение введенного логина
    string password = Console.ReadLine(); // Чтение введенного пароля

    if (string.IsNullOrEmpty(login) || string.IsNullOrEmpty(password)) // Проверка, пустые ли логин или пароль
    {
        Console.WriteLine("логин или пароль пустые"); // Вывод ошибки, если пустые
        return; // Прерывание выполнения метода
    }

    if (login != correctLogin || password != correctPassword) // Проверка, совпадают ли логин и пароль с корректными
    {
        Console.WriteLine("неверный логин или пароль"); // Вывод ошибки при несовпадении
        return; // Прерывание выполнения метода
    }

    int lengthScore = password.Length >= 8 ? 2 : password.Length >= 6 ? 1 : 0; // Оценка длины пароля: 2 за ≥8, 1 за ≥6, 0 иначе
    bool hasLower = false, hasUpper = false, hasDigit = false, hasSpecial = false; // Флаги для проверки символов

    foreach (char c in password) // Перебор каждого символа в пароле
    {
        if (char.IsLower(c)) hasLower = true; // Проверка на строчную букву
        else if (char.IsUpper(c)) hasUpper = true; // Проверка на заглавную букву
        else if (char.IsDigit(c)) hasDigit = true; // Проверка на цифру
        else hasSpecial = true; // Проверка на специальный символ (любой другой)
    }

    int complexityScore = lengthScore + (hasLower ? 1 : 0) + (hasUpper ? 1 : 0) + // Подсчет баллов сложности
                            (hasDigit ? 1 : 0) + (hasSpecial ? 1 : 0); // Суммирование баллов за каждый критерий

    string complexity = complexityScore >= 6 ? "Отличный" : // Оценка уровня сложности по баллам
                        complexityScore >= 4 ? "Хороший" :
                        complexityScore >= 3 ? "Средний" : "Слабый";

    Console.WriteLine($"Уровень сложности пароля: {complexity}"); // Вывод уровня сложности пароля
}

// Метод для обработки бронирования номера в отеле
static void Zadanie3()
{
    string fullName = Console.ReadLine(); // Чтение полного имени
    DateTime checkIn = DateTime.Parse(Console.ReadLine()); // Чтение даты заезда
    DateTime checkOut = DateTime.Parse(Console.ReadLine()); // Чтение даты выезда
    int guests = int.Parse(Console.ReadLine()); // Чтение количества гостей
    int roomType = int.Parse(Console.ReadLine()); // Чтение типа номера

    List<string> errors = new List<string>(); // Список для хранения ошибок

    if (string.IsNullOrEmpty(fullName)) // Проверка, указано ли имя
        errors.Add("Имя не указано"); // Добавление ошибки, если имя пустое

    if (checkIn < DateTime.Today) // Проверка, не раньше ли дата заезда текущей даты
        errors.Add("Дата заезда не может быть раньше текущей даты");

    if (checkOut <= checkIn) // Проверка, позже ли дата выезда даты заезда
        errors.Add("Дата выезда должна быть позже даты заезда");

    if (guests < 1 || guests > 6) // Проверка, находится ли количество гостей в диапазоне 1–6
        errors.Add("Количество гостей должно быть от 1 до 6");

    if (roomType < 1 || roomType > 4) // Проверка, находится ли тип номера в диапазоне 1–4
        errors.Add("Тип номера должен быть от 1 до 4");

    if (errors.Count > 0) // Если есть ошибки
    {
        foreach (string error in errors) // Перебор всех ошибок
            Console.WriteLine(error); // Вывод каждой ошибки
        return; // Прерывание выполнения метода
    }

    int days = (checkOut - checkIn).Days; // Подсчет количества дней проживания
    int pricePerDay = roomType == 1 ? 1000 : roomType == 2 ? 2500 : // Цена за день в зависимости от типа номера
                        roomType == 3 ? 8000 : 10000; // 1000, 2500, 8000 или 10000 руб.
    int totalCost = days * pricePerDay; // Общая стоимость

    string roomName = roomType == 1 ? "Эконом" : roomType == 2 ? "Стандарт" : // Название номера по типу
                        roomType == 3 ? "Люкс" : "Президенский";

    Console.WriteLine($"Бронирование: {fullName}"); // Вывод имени
    Console.WriteLine($"Заезд: {checkIn:dd.MM.yyyy}"); // Вывод даты заезда
    Console.WriteLine($"Выезд: {checkOut:dd.MM.yyyy}"); // Вывод даты выезда
    Console.WriteLine($"Гостей: {guests}"); // Вывод количества гостей
    Console.WriteLine($"Тип номера: {roomName}"); // Вывод названия номера
    Console.WriteLine($"Стоимость: {totalCost} руб."); // Вывод общей стоимости
}
```

# 4 Задание
```
// Определение перечисления для типов геометрических фигур
public enum FigureType
{
    Circle,    // Круг
    Square,    // Квадрат
    Rectangle, // Прямоугольник
    Triangle   // Треугольник
}

// Класс для вычисления площади и периметра фигур
class GeometrySolver
{
    // Метод для вычисления площади фигуры
    public double CalculateArea(FigureType figureType, params double[] parameters) // Принимает тип фигуры и параметры (переменное число)
    {
        if (!ValidateInput(figureType, parameters, 0)) // Проверка корректности входных данных
            throw new ArgumentException("Некорректные входные параметры");

        // Локальная функция для вычисления площади
        double CalculateAreaLocal()
        {
            switch (figureType) // Выбор формулы в зависимости от типа фигуры
            {
                case FigureType.Circle: // Для круга
                    return Math.PI * parameters[0] * parameters[0]; // Площадь = π * r²
                case FigureType.Square: // Для квадрата
                    return parameters[0] * parameters[0]; // Площадь = a²
                case FigureType.Rectangle: // Для прямоугольника
                    return parameters[0] * parameters[1]; // Площадь = a * b
                case FigureType.Triangle: // Для треугольника
                    double s = (parameters[0] + parameters[1] + parameters[2]) / 2; // Полупериметр
                    return Math.Sqrt(s * (s - parameters[0]) * (s - parameters[1]) * (s - parameters[2])); // Формула Герона
                default:
                    throw new ArgumentException("Неизвестный тип фигуры"); // Ошибка для неизвестного типа
            }
        }

        return CalculateAreaLocal(); // Возврат результата локальной функции
    }

    // Метод для вычисления периметра фигуры
    public double CalculatePerimeter(FigureType figureType, params double[] parameters) // Принимает тип фигуры и параметры
    {
        if (!ValidateInput(figureType, parameters, 0)) // Проверка корректности входных данных
            throw new ArgumentException("Некорректные входные параметры");

        // Локальная функция для вычисления периметра
        double CalculatePerimeterLocal()
        {
            switch (figureType) // Выбор формулы в зависимости от типа фигуры
            {
                case FigureType.Circle: // Для круга
                    return 2 * Math.PI * parameters[0]; // Периметр = 2 * π * r
                case FigureType.Square: // Для квадрата
                    return 4 * parameters[0]; // Периметр = 4 * a
                case FigureType.Rectangle: // Для прямоугольника
                    return 2 * (parameters[0] + parameters[1]); // Периметр = 2 * (a + b)
                case FigureType.Triangle: // Для треугольника
                    return parameters[0] + parameters[1] + parameters[2]; // Периметр = a + b + c
                default:
                    throw new ArgumentException("Неизвестный тип фигуры"); // Ошибка для неизвестного типа
            }
        }

        return CalculatePerimeterLocal(); // Возврат результата локальной функции
    }

    // Метод для валидации входных параметров
    private bool ValidateInput(FigureType figureType, double[] parameters, int depth) // Принимает тип фигуры, параметры и глубину рекурсии
    {
        if (depth > 1) // Проверка на превышение глубины рекурсии
            return false;

        if (parameters == null || parameters.Length == 0) // Проверка на null или пустой массив
            return false;

        foreach (var param in parameters) // Проверка каждого параметра
        {
            if (param <= 0) // Если параметр неположительный
                return ValidateInput(figureType, parameters, depth + 1); // Рекурсивный вызов с увеличением глубины
        }

        switch (figureType) // Проверка количества параметров для каждого типа фигуры
        {
            case FigureType.Circle: // Для круга требуется 1 параметр (радиус)
                return parameters.Length == 1;
            case FigureType.Square: // Для квадрата требуется 1 параметр (сторона)
                return parameters.Length == 1;
            case FigureType.Rectangle: // Для прямоугольника требуется 2 параметра (стороны)
                return parameters.Length == 2;
            case FigureType.Triangle: // Для треугольника требуется 3 параметра (стороны)
                if (parameters.Length != 3)
                    return false;
                return (parameters[0] + parameters[1] > parameters[2] && // Условие существования треугольника
                        parameters[1] + parameters[2] > parameters[0] &&
                        parameters[0] + parameters[2] > parameters[1]);
            default:
                return false; // Неизвестный тип фигуры
        }
    }
}
```

```
// Задание 1
var geometrySolver = new GeometrySolver(); // Создание объекта GeometrySolver
Console.WriteLine(geometrySolver.CalculateArea(FigureType.Square, 3)); // Вычисление площади квадрата со стороной 3

// Задание 2
var taskManager = new TaskManager(); // Создание объекта TaskManager

taskManager.AddTask("чиллить", TaskPriority.High); // Добавление задачи "чиллить" с высоким приоритетом
taskManager.AddTask("пойти спать", TaskPriority.High); // Добавление задачи "пойти спать" с высоким приоритетом
taskManager.AddTask("закончить работу", TaskPriority.Medium); // Добавление задачи "закончить работу" со средним приоритетом

taskManager.DisplayTasks(TaskStatus.Pending); // Отображение задач со статусом Pending
taskManager.MarkAsCompleted(1); // Пометка задачи с ID 1 как завершенной
taskManager.DisplayTasks(TaskStatus.Completed); // Отображение задач со статусом Completed
```

```
// Определение перечисления для приоритетов задач
public enum TaskPriority
{
    Low,    // Низкий
    Medium, // Средний
    High    // Высокий
}

// Определение перечисления для статусов задач
public enum TaskStatus
{
    Pending,   // Ожидает выполнения
    InProgress,// В процессе
    Completed  // Завершена
}

// Класс для управления задачами
public class TaskManager
{
    // Внутренний класс для представления задачи
    internal class Task
    {
        public int Id; // Уникальный идентификатор задачи
        public string Description; // Описание задачи
        public TaskPriority Priority; // Приоритет задачи
        public TaskStatus Status; // Статус задачи

        // Конструктор задачи
        public Task(int id, string description, TaskPriority priority) // Принимает id, описание и приоритет
        {
            Id = id; // Инициализация id
            Description = description; // Инициализация описания
            Priority = priority; // Инициализация приоритета
            Status = TaskStatus.Pending; // Установка статуса по умолчанию
        }
    }

    private List<Task> tasks; // Список задач
    private int nextId; // Следующий доступный идентификатор

    // Конструктор TaskManager
    public TaskManager()
    {
        tasks = new List<Task>(); // Инициализация пустого списка задач
        nextId = 1; // Начальный идентификатор
    }

    // Метод для добавления новой задачи
    public void AddTask(string description, TaskPriority priority) // Принимает описание и приоритет
    {
        if (string.IsNullOrWhiteSpace(description)) // Проверка, не пустое ли описание
            throw new ArgumentException("Описание не может быть пустым");

        tasks.Add(new Task(nextId++, description, priority)); // Добавление новой задачи с увеличением nextId
    }

    // Метод для отображения задач с заданным статусом
    public void DisplayTasks(TaskStatus status) // Принимает статус для фильтрации
    {
        if (!tasks.Any()) // Проверка, есть ли задачи
        {
            Console.WriteLine("Задачи отсутствуют."); // Вывод сообщения, если список пуст
            return;
        }

        // Локальная функция для форматирования задачи
        string FormatTask(Task task) =>
            $"ID: {task.Id}, Описание: {task.Description}, Приоритет: {task.Priority}, Статус: {task.Status}";

        // Рекурсивная функция для отображения задач
        void DisplayTasksRecursive(int index) // Принимает текущий индекс
        {
            if (index >= tasks.Count) // База рекурсии: выход, если индекс превышает длину списка
                return;

            if (tasks[index].Status == status) // Если статус задачи совпадает с требуемым
                Console.WriteLine(FormatTask(tasks[index])); // Вывод информации о задаче

            DisplayTasksRecursive(index + 1); // Рекурсивный вызов для следующего индекса
        }

        Console.WriteLine($"Задачи со статусом {status}:"); // Вывод заголовка
        DisplayTasksRecursive(0); // Запуск рекурсии с индекса 0
    }

    // Метод для пометки задачи как завершенной
    public void MarkAsCompleted(int taskId) // Принимает идентификатор задачи
    {
        var task = tasks.FirstOrDefault(t => t.Id == taskId); // Поиск задачи по ID
        if (task == null) // Проверка, найдена ли задача
            throw new ArgumentException("Задача не найдена");

        task.Status = TaskStatus.Completed; // Установка статуса Completed
    }
}
```