# -.-namespace-c-125
Пространства имен  . namespace c++   #125
namespace firstNS//неглобальное пространство имен. ТО, что за ней - глобальное пространство имен
{
	void Foo()
	{
		cout << "Ф-ция из первого пространства имен" << endl;
	}
}
namespace secondNS
{
	void Foo()
	{
		cout << "Ф-ция из второго пространства имен" << endl;
	}
}
namespace thirdNS
{
	namespace secondNS
	{
		void Foo()
		{
			cout << "Ф-ция из третьего пространства имен" << endl;
		}
	}
}

int main()
{
	setlocale(LC_ALL, "ru");
    secondNS::Foo();//если ф-ция в неглобальном пространстве, то н. указать его имя, либо без имени пространства
	//но тогда в глобальном пространстве д. присутствовать using namespace secondNS;
	thirdNS::secondNS::Foo();//верхняя реал-я не б. конфликтовать с нижней, т к эти секондНС разные,
	//находятся в разных пространствах имен
	cout << "test";//без using namespace std не б. работать
	std::cout << "test";
	
	return 0;
}



