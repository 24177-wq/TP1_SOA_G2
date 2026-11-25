ETAPE 5:

1.
- Opération : emprunterLivre
- Message Fault : LivreIndisponibleFault
- Action SOAP : http://supnum.mr/bib/emprunterLivre
2.
EmpruntType emprunterLivre(String idAdherent, String isbn)
    throws LivreIndisponibleFault;


3. Le type Java généré pour dateRetour est XMLGregorianCalendar, correspondant au type xs:date du WSDL.

4. La classe d'exception générée est LivreIndisponibleFault, issue du message Fault déclaré dans le WSDL.


ETAPE 6:

1.
Oui. Grâce à wsdlLocation, le service utilise le WSDL fourni. Il contient le motif de l’ISBN et le type xs:date.

2. 
Non, il suffit de conserver la même structure SOAP et d'utiliser le bon SOAPAction. Le service contract-first respecte le contrat WSDL.

3. 
- Sans @SchemaValidation : l’ISBN n'est pas nécessairement refusé, car la validation du schéma n'est pas activée.
- Avec @SchemaValidation : il est refusé car il ne respecte pas le motif défini dans le WSDL. Une SOAP Fault de validation est retournée.

4.
Le WSDL est généré à partir de l'interface Java et de ses annotations, au lieu d'utiliser directement le WSDL fourni. Le contrat publié peut donc être différent.

Petite précision : ton dernier test avec 978-2-10-074444-4 a retourné HTTP 500, ce qui indique une erreur côté serveur, mais ne permet pas à lui seul de confirmer le contenu de la Fault. Les réponses 3 et 4 restent à vérifier avec les tests demandés.