# DB First

Il file Cars.jpg rappresenta una tabella dove sono memorizzati i dati utili per inserire in un eventuale database delle auto usate messe in vendita da un concessionario.
Di seguito una breve descrizione dei campi scelti e perché:

- La chiave primaria della tabella (PK) è un ID con gli attributi not null e unique(che ci sono di default) e auto_increment perché voglio che ad ogni inserimento venga assegnato un id automaticamente ad ogni auto in modo incrementale.
- brand indica la marca dell'auto, di tipo varchar(15) perché 15 caratteri possono bastare per definirla, not null perché non voglio auto senza che ci sia la marca registrata nel db
- model indica il modello dell'auto, di tipo varchar(10) perché 10 caratteri possono bastare per definire il modello, not null perché non voglio auto registrate nel db senza modello
- price indica il prezzo, di tipo MEDIUMINT perché difficilmente il prezzo di un auto sarà superiore a 16 milioni(mentre con SMALLINT potrei arrivare poco sopra i 65mila), anche in questo caso not null perché il prezzo è fondamentale in un contesto di rivendita
- matriculation_year indica l'anno di immatricolazione, di tipo year e not null perché nel caso di auto usate è un parametro importante che non voglio null
- km_travelled indica i km percorsi, di tipo MEDIUMINT per lo stesso motivo di price e not null perché anche in questo caso per un'auto usata i km percorsi sono importanti
- color indica il colore, di tipo varchar(15) perché 15 caratteri dovrebbero bastare per definire un colore e null perché non è fondamentale inserire un'auto indicandone il colore
- plate indica la targa, di tipo char(7) perché le targhe hanno 7 simboli, unique perché non possono esistre targhe uguali per auto diverse e null perché la targa non è un aspetto fondamentale per vendere un'auto
- owners_count indica quanti precedenti proprietari ha avuto l'auto, di tipo TINYINT perché non saranno più di 255 e null
- cv indica i cavalli, di tipo SMALLINT perché può capitare che siano più di 255 ma sicuramente meno di 65mila, null perché non è campo fondamentale per la vendita dell'auto
- displacement indica la cilindrata, SMALLINT e null per gli stessi motivi di cv
- motor_type indica il tipo di motore, di tipo char(1) con l'idea di indicare il tipo con una lettera(esempio B -> benzina, E -> elettrico, D -> diesel) e not null perché il tipo di motore è un'informazione importante nell'acquisto di un'auto
- gearbox indica il tipo di cambio, di tipo char(1) anche in questo caso con l'idea di indicare il cambio con una lettera(esempio A -> automatico, M -> manuale), not null perché è un'informazione che voglio in ogni tupla
- km/l indica quanti km con un litro, di tipo TINYINT perché difficilmente saranno più di 255 e null perché potrei non avere questo dato per tutte le auto
- lenght e width indicano lunghezza e larghezza di un'auto(in mm), di tipo SMALLINT perché in genere si parla di qualche migliaio e null perché non sono dati così importanti
