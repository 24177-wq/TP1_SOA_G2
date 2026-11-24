1- @WebService : cette annotation permet de déclarer la classe EmpruntService comme un service web SOAP.

2- @WebFault : cette annotation permet de déclarer LivreIndisponibleException comme une exception SOAP (Fault) dans le contrat WSDL.

1_

Opération	     Message d'entrée	     Message de sortie
rendreLivre 	 rendreLivre 	         rendreLivreResponse
emprunterLivre	 emprunterLivre	         emprunterLivreResponse


2-
Style: document

Use: literal

Version: SOAP 1.1

3-