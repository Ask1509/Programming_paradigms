# <p style="text-align: center">Парадигмы программирования и языки парадигм (семинары)</p>

## Семинар 2. Структурное и процедурное программирование на практике

*Задача №1*  
Условие
На вход подается число n.
● Задача
Написать скрипт в любой парадигме, который выводит на экран таблицу умножения всех чисел от 1 до n.
Обоснуйте выбор парадигм.
● Пример вывода:
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
1 * 6 = 6
..
1 * 9 = 9

*Доп Задача*
Переписать алгоритм в процедурном стиле
Структурное программирование

Определение функции merge_sort, которая выполняет сортировку методом слияния.

def merge_sort(arr):
if len(arr) > 1: # Проверка, что длина массива больше 1 (иначе сортировка не нужна).
mid = len(arr) // 2 # Вычисление середины массива.
left_half = arr[:mid] # Создание левой половины массива.
right_half = arr[mid:] # Создание правой половины массива.

    # Рекурсивный вызов merge_sort для левой и правой половин массива.
    merge_sort(left_half)
    merge_sort(right_half)

    i = j = k = 0  # Инициализация индексов для объединения двух половин.

    # Объединение левой и правой половин в один отсортированный массив.
    while i < len(left_half) and j < len(right_half):
        if left_half[i] < right_half[j]:  # Сравнение элементов левой и правой половин.
            arr[k] = left_half[i]  # Если элемент из левой меньше, помещаем его в исходный массив.
            i += 1
        else:
            arr[k] = right_half[j]  # Если элемент из правой меньше, помещаем его в исходный массив.
            j += 1
        k += 1

    # Добавление оставшихся элементов из левой и правой половин (если такие есть).
    while i < len(left_half):
        arr[k] = left_half[i]
        i += 1
        k += 1

    while j < len(right_half):
        arr[k] = right_half[j]
        j += 1
        k += 1
my_array = [64, 34, 25, 12, 22, 11, 90] # Создание неотсортированного массива.
merge_sort(my_array) # Вызов функции сортировки слиянием.
print("Отсортированный массив (Merge Sort):", my_array) # Вывод отсортированного массива.

Ответ: 

function merge_sort(array) {
if (array.length > 1) {
var middle = Math.floor(array.length / 2);
var left_half = array.slice(0, middle);
var right_half = array.slice(middle);

    merge_sort(left_half);
    merge_sort(right_half);

    var i = 0,
        j = 0,
        k = 0;

    while (i < left_half.length && j < right_half.length) {
        if (left_half[i] <= right_half[j]) {
            array[k++] = left_half[i++];
        } else {
            array[k++] = right_half[j++];
        }
    }

    while (i < left_half.length) {
        array[k++] = left_half[i++];
    }

    while (j < right_half.length) {
        array[k++] = right_half[j++];
}
}
}

