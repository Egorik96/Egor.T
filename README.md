# Egor.T
Калькулятор для математических и Физических Задач
def add(x, y):
    return x + y


def subtract(x, y):
    return x - y


def multiply(x, y):
    return x * y


def divide(x, y):
    if y == 0:
        return "Деление на ноль невозможно!"
    else:
        return x / y


def power(x, y):
    return x ** y


def factorial(x):
    if x == 0:
        return 1
    else:
        result = 1
        for i in range(1, x + 1):
            result *= i
        return result

def rest_1(x, y):
    return x // y

def rest_2(x, y):
    return x % y

def root(x, y):
    return x**(1/y)


def calculate_speed(distance, time):
    if time == 0:
        return "Скорость не может быть рассчитана. Время равно нулю"
    return distance / time

def calculate_acceleration(initial_velocity, final_velocity, time):
    if time == 0:
        return "Ускорение не может быть рассчитано. Время равно нулю"
    return (final_velocity - initial_velocity) / time

def calculate_distance(initial_velocity, acceleration, time):
    return initial_velocity * time + 0.5 * acceleration * time * time

    return guess
# Выбор операций
while True:
    print("\nВыберите операцию:")
    print("1. Сложение")
    print("2. Вычитание")
    print("3. Умножение")
    print("4. Деление")
    print("5. Возведение в степень")
    print("6. Факториал")
    print("7. Деление с остатком")
    print("8. Корень")
    print("9. Скорость")
    print("10. Ускорение ")
    print("11. путь")
    print("12. Выход")

    choice = input("Введите номер операции (1/2/3/4/5/6/7/8/9/10/11/12): ")

    if choice == '12':
        break

    if choice in ('1', '2', '3', '4', '5', '7', '8'):
        try:
            num1 = float(input("Введите первое число: "))
            num2 = float(input("Введите второе число: "))
        except ValueError:
            print("Неверный ввод. Введите числа.")
            continue

        if choice == '1':
            print("\n", num1, "+", num2, "=", add(num1, num2))
        elif choice == '2':
            print("\n", num1, "-", num2, "=", subtract(num1, num2))
        elif choice == '3':
            print("\n", num1, "*", num2, "=", multiply(num1, num2))
        elif choice == '4':
            print("\n", num1, "/", num2, "=", divide(num1, num2))
        elif choice == '5':
            print("\n", num1, "**", num2, "=", power(num1, num2))
        elif choice == '7':
            print("\n", num1, "//", num2, "=", rest_1(num1, num2), "остаток: ", rest_2(num1, num2))
        elif choice == '8':
            print("\n", "Корень", num2, "степени от",num1 , 'является:', num2, "=", root(num1, num2))

    elif choice == '6':
        try:
            num = int(input("Введите число для вычисления факториала: "))
            if num < 0:
                print("\n", "Факториал отрицательного числа не определен.")
            else:
                print("\n", "Факториал", num, "=", factorial(num))
        except ValueError:
            print("Неверный ввод. Введите целое число.")
    elif choice == '9': # Скорость
                distance = float(input("Введите расстояние(M): "))
                time = float(input("Введите время(C): "))
                print("Скорость = ", calculate_speed(distance, time))
                
    elif choice == '10': # Ускорение
                initial_velocity = float(input("Введите начальную скорость(M/C): "))
                final_velocity = float(input("Введите конечную скорость(M/C): "))
                time = float(input("Введите время(C): "))
                print("Ускорение = ", calculate_acceleration(initial_velocity, final_velocity, time))
        
    elif choice == '11': # Расстояние
                initial_velocity = float(input("Введите начальную скорость(M): "))
                acceleration = float(input("Введите ускорение(M/C): "))
                time = float(input("Введите время(C): "))
                print("Расстояние = ", calculate_distance(initial_velocity, acceleration, time))
    else:
        print("Неверный ввод.")

    exit = str(input('Вы хотите продолжить(да, нет); '))
    if exit == 'нет':
        break



print("\nПрограмма завершена.")

print("Надеюсь, программа была полезна!")
