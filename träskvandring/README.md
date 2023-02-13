# Träskvandring

Solution to [Träskvandring](https://github.com/IndaPlus22/AssignmentInstructions-BlueNote/blob/main/task-17/Assignment.pdf).

## a)

För det första fallet där Tina får starta var som helst på vänsterkanten och får sluta var som helst på högerkanten, går det att lösa det genom att använda en dynamisk programmeringslösning. Lösningen kan beskrivas som följande:

1. Skapa en 2D-matris dp med samma storlek som träsket där varje element i matrisen representerar det minimala arbetet att nå den rutan från vänsterkanten.
1. Fyll först första raden i dp-matrisen med "arbetsvärden" för rutorna i första raden.
1. För varje rad i matrisen från rad 2 till sista raden, uppdatera värden i dp-matrisen för varje ruta i raden med det lägsta värdet från de tre föregående rutorna i den föregående raden plus arbetsvärdet för den aktuella rutan.
1. Sista elementet i varje rad i dp-matrisen kommer att representera det minsta arbetet att nå den högra kanten från den aktuella raden.
1. Hitta det minsta värdet i sista raden i dp-matrisen och det kommer att vara det minsta arbetet att ta sig igenom träsket.

## b)

För det andra fallet där Tina alltid startar i rutan (n/2, 1), kan man använda samma lösning som i det första fallet, men börja bara från rad (n/2) och fylla i dp-matrisen från den raden.

## c)

För det tredje fallet där Tina måste sluta i rutan (n/2, n), kan man använda samma lösning som i det andra fallet, men bara fylla i dp-matrisen fram till sista kolumnen (n-1) och sista raden (n/2). Sista elementet i dp-matrisen (n/2, n-1) kommer att vara det minsta arbetet att ta sig från rutan (n/2, 1) till rutan (n/2, n).

## d)

För att hitta den minst jobbiga vägen Tina kan ta genom träsket i det tredje fallet (c), kan man "backtracka" från den sista rutan (n/2, n) till den första rutan (n/2, 1) i dp-matrisen och hitta den väg som leder till det minsta arbetet.
