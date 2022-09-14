# HOME_WORK_8
//Найти минимальный и макисмальный элемент массива.
#include <iostream>
#include <ctime>
using namespace std;
int main()
{
	setlocale(LC_ALL, "Russian");
	srand(time(NULL)); // Генерация всегда разных чисел
	const int SIZE = 10;
	int arr[SIZE];
	int min, max;
	for (int i = 0; i < SIZE; i++) // генератор случайных чисел где 20 это ограничение от 0 до 20
	{
		arr[i] = rand() % 20; // Чтобы увеличить или уменьшить диапозон измените 20 на любое число, но не меньше 10 
		for (int j = 0; j < i; j++)
		{
			if (arr[i] == arr[j]) // Проверка на уникальность числа
			{
				i--;
				continue;
			}
		}
	}
	for (int i = 0; i < SIZE; i++)
	{
		cout << arr[i] << " " << endl; // вывод всех элементов массива в строку через пробел
	}
	min = arr[0]; // Переменной min присваивается значение имеющие 0 index в массиве arr
	for (int i = 0; i < SIZE; i++) // Поиск минимального числа
	{
		if (min > arr[i])
		{
			min = arr[i];
		}
	}
	max = arr[0];
	for (int i = 0; i < SIZE; i++) // Поиск максимального числа
	{
		if (max < arr[i])
		{
			max = arr[i];
		}
	}
	cout << "Минимальное число: " << min << endl;
	cout << "Максимальное число: " << max << endl;
}
