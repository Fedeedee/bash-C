# ANCORA DA TRADURRE IN MARKDOWN

SCRIPTING BASH

eseguire uno script bash significa eseguire in modo sequenziale tutti i comandi all'interno del file sulla shell bash.


	cmd1;cmd2
	cm3
	cm4

	ed eseguo lo script è come se mettessi tutto su una linea, quindi potrei farlo senza creare un file però 	non si capirebbe nulla senza indentazione

	VARIABILE
	*nella shell bash tutto è una stringa quindi stare attento quando si lavora con i numeri.*
	
	a="ciao"
	se io vado a fare direttamente echo $a, non avrò nulla perchè prima devo avviare sulla shell il file.

    MECCANISMO DI ESECUZIONE:

	primo:
	./s.sh 	per eseguirlo, però mi servono i permessi è l'unica quindi scrivo "chmod 744 s.sh" cosi 
	posso eseguirlo, e poi questo script viene eseguito in una sotto shell non interattiva.
	(questo mi aiuta a trovare errori)

	secondo: 
	bash s.sh, con questo non servono i permessi

	terzo: 
	. s.sh
	mi verrà eseguita tutta la comandistica nella shell bash corrente.

	quarto:
	source s.sh
	mi verrà eseguita tutta la comandistica nella shell bash corrente.
	
VARIABILI:

	nome=13 , sarebbe una stringa quindi per farlo diventare un numero bisogna fare:
	declare -i nome=13 , per dire che contiene solo interi.
