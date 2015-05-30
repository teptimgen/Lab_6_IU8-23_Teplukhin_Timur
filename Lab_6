/** \include <iostream>
    \include <string>
*/
#include <iostream>
#include <string>

///- Используем пространство стандартных имен
using namespace std;

/** \tparam T {Шаблонный тип, отвечающий за подаваемые в метода класса типы int и string}
*/
template <typename T>

/** \class List
    \brief Класс "Список", реализованный с помощью линейного односвязного списка
*/
class List {
    ///- Указатель на следующий элемент
    List* pNext;
    ///- Значение элемента шаблонного типа
    T value;
public:
    ///- Конструктор с параметром
    List(T value) {
        this->value = value;
    }
    ///- Метод добавления элемента в список
    void add(List* p, List* &pF) {
        p->pNext = pF;
        pF = p;
    }
    ///- Метод вывода списка на экран
    void printAll(List *pF) {
        List* p = pF;
        int i = 0;
        while (p != NULL) {
            cout << "Element #" << ++i << ": ";
            cout << p->value << endl;
            p = p->pNext;
        }
    }
};

/**\return {0} - выход из функции
*/
/// Функция main() − точка входа в программу
int main() {
    ///> Алгоритм функции
    ///- Инициализация переменных
    int N, n;
    char type;
    ///- Вводим количество тестов
    cout << "Enter the number of tests: N = ";
    cin >> N;
    ///- Реализация N-го количества тестов
    for (int i = 1; i <= N; ++i) {
        ///- Вводим количество элементов списка
        cout << endl << "Enter the number of list elements: n = ";
        cin >> n;
        ///- Вводим тип элементов списка
        cout << "Enter the type of list elements ('i' - integer, 's' - string): ";
        cin >> type;
        ///- В зависимости от типа выбираем определенную ветвь case. В случае ошибки выбираем ветвь default
        switch (type) {
            case 's': {
                List<string>* pF = NULL;
                ///- Вводим элементы
                for (int k = 1; k <= n; ++k) {
                    string str = "";
                    cout << "Element #" << k << ": ";
                    cin >> str;
                    List<string>* list = new List<string>(str);
                    pF->add(list, pF);
                }
                ///- Вызываем метод вывода элементов списка
                cout << endl << "Test #" << i << endl;
                pF->printAll(pF);
                delete pF;
                break;
            }
            case 'i': {
                List<int>* pF = NULL;
                ///- Вводим элементы
                for (int k = 1; k <= n; ++k) {
                    int num;
                    cout << "Element #" << k << ": ";
                    cin >> num;
                    List<int>* list = new List<int>(num);
                    pF->add(list, pF);
                }
                ///- Вызываем метод вывода элементов списка
                cout << endl << "Test #" << i << endl;
                pF->printAll(pF);
                delete pF;
                break;
            }
            ///- В случае неверно введенного типа выводим сообщение об ошибке на экран
            default:
                cout << "Undefined type" << endl;
                break;
        }
    }
    cout << endl;
    ///- Пауза в работе программы
    system("pause");
    return 0;
}

