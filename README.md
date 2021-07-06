Scrieți un program care folosește arbori pentru a evalua expresii matematice cu cifre.

Să considerăm o expresie matematică: 2+4*5+1*2*3.

Pentru a crea un arbore de parsare avem nevoie să folosim următoarele structuri:

stivă rezultat - folosită pentru a reține operanzii si rezultatele intermediare ale operațiilor parcurse până la un moment dat
stivă de operatori - folosit pentru a reține operatorii
       +
      / \
     2    +
         / \
        *    *
       / \  / \
      4  5 1   *
              / \
             2   3 
Algoritmul presupune:

Se parcurge expresia,termen cu termen (un termen poate fi operator sau operand)
Dacă termenul curent este operand aceasta se adaugă in stivă rezultat și se trece la termenul urmator
Daca termenul curent este operator (!)
Daca stiva operatorilor este vidă,se adaugă operatorul in stiva de operatori și se trece la termenul urmator
Dacă stiva nu este vidă:
Și operatorul curent are prioritate mai mare decât capul stivei (ex: crt este *,top(stivă) este +) se adaugă operatorul în stivă și se trece la termenul următor
Și operatorul curent are prioritate mai mică decât capul stivei (ex: crt este +,top(stivă) este *)
Se scot din stivă rezultatele ultimelor două rezultate
Se scoate un operator din stiva operatorilor
Se creează un nou rezultat intermediar,aplicând operatorul extras pe cele două rezultate de mai sus
Acest rezultat intermediar se adaugă în stiva de rezultate
Se verifică condițiile de la ! (se compară din nou același operator curent cu operatorul din vârful stivei).
Construiți arborele asociat expresiei.
