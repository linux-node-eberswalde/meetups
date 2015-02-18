Das hier sind die commands unter Linux, die wir uns in der Session am 13. August angeschaut haben. Ein Dank geht an Arvid und Mike für die Überlassung ihrer Mitschriften.

Funktionen:

Standard Ein- und ausgabe
std-in (0 <) → Prozess → std-out (1 > oder >>)
|
std-err (2 > oder >>)

> → Ausgabe überschreibt vorhandene Daten
>> → Ausgabe wird an vorhandene Daten angehangen

Zufallszahlen:

random erzeugt echte Zufallszahlen (aus Nutzereingaben)
urandom erzeugt Zufallszahlen aus mathematischen Vorgaben

Befehle:

df disk file – zeigt Dateisystem an (u.a. Ansicht der verschiedenen Partitionen)
cat <hallo >hallo2 der Befehl cat nimmt als Standardeingabe die Datei hallo und und schreibt die Daten in hallo2; cat legt so eine Kopie der Datei an
cat >brief die Standardeingabe (Tastatur) wird in die Datei brief gespeichert, bis der Befehl aufgehoben wird
ls /usr /xxx >liste 2>error die Auflistung der Verzeichnisse /usr und /xxx wird in die Datei liste geschrieben; Fehler während des Vorgangs werden in die Datei error geschrieben
strg+D ↔ strg+C strg+D beendet einen Befehl; strg+C bricht einen Befehl ab
cat </dev/zero >/dev/sdb beschreibt die Festplatte sdb mit Nullen (aus der Funktion /dev/zero)
cat </dev/random >/dev/sdb beschreibt die Festplatte sdb mit Zufallszahlen (aus der Funktion /dev/random)
find . name passwd gibt im aktuellen Verzeichnis Dateien mit dem Namen passwd aus
find . name passwd 2>/dev/null gibt im aktuellen Verzeichnis Dateien mit dem Namen passwd aus, ohne die Fehlermeldungen anzuzeigen
ps zeigt aktuelle Prozesse an
ls /etc | grep passwd gibt den Inhalt des Verzeichnis /etc ,mit den Zeilen die das Wort passwd beinhalten, aus
ls /etc | tee liste gibt den Inhalt des Verzeichnis /etc in der Standardausgabe (Monitor) aus und schreibt ihn gleichzeitig in die Datei liste
groupadd kurs Gruppe mit dem Namen kurs anlegen
useradd -m klaus User klaus anlegen, mit einem eigenen Home-Verzeichnis (-m)
passwd klaus ein Passwort für den User klaus vergeben
useradd -m -g kurs susi User susi in der Gruppe kurs anlegen
chmod -u -g -o -a + – = chmod verändert Dateiberechtigungen für den User (u), die Gruppe (g), andere (o) oder alle (a); Berechtigungen hinzufügen (+), entziehen (-), ersetzt alle alten Berechtigungen durch neue (=)
chmod o+w hallo fügt der Datei hallo die Schreibberechtigung für andere hinzu
chmod g=rx hallo setzt für die Datei hallo die Gruppenberechtigungen r und x
Ordner:
- Unterscheidung zwischen Inhalten des root-Verzeichnisses und Inhalten auf anderen Partitionen (disk file … Dateisystem); das root-Verzeichnis ist Ausgang für alle anderen Verzeichnisse
- . und .. verweisen in Ordnern immer auf den inode des darüber bzw. darunter liegenden Verzeichnisses; d.h. ein Ordner hat immer mindesten einen Link-Counter von 2
/dev/null Ausgabedatei; eine Art Papierkorb
Berechtigungen
r read (lesen)
w write (schreiben)
x execute (ausführen)
Dateien:
-rw-r–r– eddy users hallo rw- → Eigner; r– → Gruppe; r– → andere; Eigner, Gruppe, Datei
