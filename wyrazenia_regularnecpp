#include <iostream>
#include <fstream>
#include <regex>

using namespace std;

class wyrazenie {
	ifstream plik1;
	ofstream plik2;
	string wyraz;
	bool pierwszy=true;
	
	public:
		wyrazenie();
		~wyrazenie();
		
		void wypisanie();
		void sprawdzenie(string);
		void zapis(string);
					
};

wyrazenie::wyrazenie() {
	plik1.open("we.txt");
	plik2.open("wy.txt");
}

void wyrazenie::wypisanie() {
	plik2<<"[\n";
	cout<<"[\n";
	
	if(plik1.good())
		while(!plik1.eof()) {
			plik1>>wyraz;
			this->sprawdzenie(wyraz);			
		}
	plik2<<"]";
	cout<<"]";
}

void wyrazenie::sprawdzenie(string wyraz) {
	regex wzor("[A-Z]{1}[a-z]{1,}-[A-Z]{1}[a-z]{1,}");
	if(regex_match(wyraz, wzor)) {
		this->zapis(wyraz);
	}
}

void wyrazenie::zapis(string wyraz) {
	if (pierwszy) {
		plik2<<"{\"nazwisko_podwojne\":\""<<wyraz<<"\"}\n";
		cout<<"{\"nazwisko_podwojne\":\""<<wyraz<<"\"}\n";
		pierwszy=false;
	}
	else {
		plik2<<"{\"nazwisko_podwojne\":\""<<wyraz<<"\"},\n";
		cout<<"{\"nazwisko_podwojne\":\""<<wyraz<<"\"},\n";
	}
}

wyrazenie::~wyrazenie() {
	plik1.close();
	plik2.close();
}

int main(int argc, char** argv) {
	wyrazenie w1;
	w1.wypisanie();
	return 0;
}
