Sebastian Cojocariu 311CB UPB ACS
				
					                Octave 


ex1)Verificam mai intai daca bazele sunt intre 2 si 30.Apoi verificam daca numarul respecta baza b1 data.Se formeaza numarul dat in baza 10,dupa care se transforma in numarul corespunzator din baza b2,prin retinerea resturilor la impartirea cu b2 si impartirea numarul propriu-zisa,si concatenand acestea in ordine inversa.

ex2)Se arata matematic ca a(1,2k)=(2k-1)*k si a(1,2k-1)-a(1,2k)=-1
Se completeaza prima linie cu obs de mai sus.Cu un for ,respectiv cu cele 2 functii de coborare_scadere si coborare_adunare se parcurge de pe fiecare element a(1,i) in "diagonala" cu mentiunea ca pentru i par se incremeneteaza si pentru i impar se decrementeaza succesiv valoarea lui a(1,i).Dupa aceasta am completat toate elementele de deasupra diag secundare.Tinand cond de relatia a(i,j)+a(n+1-i,n+1-j)=n*n-1 care se deduce usor,cu un for completam si cealalata jumatate.


ex3)morse.m:se implementeaza arborele propriu-zis
	morse_decode.m:Parcurgem arborele dat pentru fiecare char din sir(daca nu se poate inainta se afiseaza un mesaj corespunzator si se iese).Se foloseste functia isempty.
	morse_encode_cautare.m:Cauta o litera mare in Arbore.Acest lucru se realizeaza recursiv.Returneaza '*' daca nu se gaseste nimic ,respectiv litera.Se bazeaza pe urmatoarea idee comuna in arbori:odata ajuns intr-o celula se verifica daca s-a gasit elementul.Daca da se iese si se returneaza codificarea.Altfel se verifica daca se mai poate merge la stanga sau la dreapta si se apeleaza recursiv in caz afirmativ pentru fiecare caz.Se actualizeaza codificarea(in rez1 si rez2)
	morse_encode.m:cauta propriu zis folosind functia anterioara.
	multiple_encode.m:Se foloseste morse_encode.Se ia litera cu litera sirul si daca se poate codifica se codifica.Se afiseaza rezultatul codificat
	multiple_decode.m:Se foloseste morse_decode.Se formeaza "perechile de coduri"(separate prin ' ') si se decodifica.Rezultatul se concateneaza si re afiseaza cuvantul format.


ex4)Am creat mai multe functii ajutatoare:
1)afisare.m:afisam matricea cu X si O la fiecare pas cand o apelam
2)castigare.m:verificam matricea a pentru a stabili daca s-a castigat sau nu.Verificam diagonalele,liniile si coloanele
3)strategie_calculator:verificam mai intai daca poate castiga(calculatorul).Daca nu incearca sa blocheze adversarul sa castige.Daca nu e cazul incearca sa pune in mijloc si pe urma in colturi.Daca toate acestea sunt deja ocupate pune unde mai are loc(primul elemenet liber parcurgand linie cu linie).
4)resetare_tabla.m:reseteaza matricea a;


joc.m:Intr-un while vom face ca jucatorul sa poate alege daca continua sa joace sau nu(in functie de rez,care la inceput e 1 tocmai pentru a intra in primul joc).La apasarea tastei 9 se iese in orice moment din joc.Daca se doreste sa se joace cu 0 se apasa 0,1 altfel.Cel care joaca cu X va incepe primul.Se verifica tocmai acest lucru.In while-ul de mai sus se iau aceste 2 cazuri,daca primul e "utilizatorul" sau "calculatorul".In semn_utilizator si semn_calculator memoram cu ce joaca fiecare('X' SAU 'O').Se cer coordonatele (linia si coloana).Daca nu se introduce un nr intre 1 si 3 sau casuta ceruta e deja ocupata se avertizeaza jucatorul si i se cere sa pune alte coordonate(acest lucru se repeta pana cand se introduc valori viabile).La sfarsit se verifica cine a castigat (in caz de remiza se specifica acest lucru).Se afiseaza scorul si i se cere jucatorului sa aleaga daca mai vrea sa joaca(1) sau sa se opreasca(0).
