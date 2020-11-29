# Inhalt der Vorlage
Dies ist eine LaTeX-Vorlage, die genutzt werden kann, um Seminar, Studien-, Masterarbeiten oder ähnliches am DHBW CAS mit LaTeX zu verfassen. Die Vorlage basiert auf einer [Vorlage der DHBW Horb](https://github.com/dhbw-horb/latexVorlage) und wurde etzwas angepasst, um den Richtlinien des DHBW CAS (bzw. dem dortigen Fachbereich Technik) zu entsprechen. Dies ist keine offizielle Vorlage des DHBW CAS, daher erfolgt die Verwendung natürlich auf eigene Gefahr.

# Vorschau
Eine Vorschau, wie ein Dokument unter Verwendung dieser Vorlage aussieht (ohne es selbst bauen zu müssen), kann unter den [GitHub-Actions](https://github.com/maxkde/latextemplate-dhbwcas/actions) für dieses Repository angeschaut werden. Den neuesten Eintrag dort anklicken und das Artefakt `documentation-paper` herunterladen, darin liegt dann die `dokumentation.pdf`.

# Vorlage verwenden und anpassen
Pflichtangaben und einigen weitere Einstellungen können in `einstellungen.tex` geändert werden. Kapitel werden in `content` nach dem Schema `<nn>kapitel.tex` angelegt, wobei &lt;nn&gt; eine mindestens zweistellige Zahl sein muss. Das Logo der Firma kann durch das Ersetzen der Datei `images/fima-deckblatt.png` geändert werden. Die Größe des Bildes ändert man durch das Verkleinern/Vergrößern der Datei.

# Kompilieren
Für das Paket _latexmk_ und die Erzeugung eines Glossars muss ein Perl-Interpreter installiert sein. Linux- und Mac-User haben normalerweise diesen schon im System installiert. Windows-Nutzern ist ActivePerl zu empfehlen (http://www.activestate.com/activeperl/downloads). Die Vorlage nutzt außerdem _biblatex_ mit dem Backend _biber_ für die Bibliographie. 
Tipp: Am komfortabelsten funktioniert das Bearbeiten und Bauen des Dokuments mit einem LaTeX-Editor wie beispielsweise [TeXstudio](https://www.texstudio.org/). Als TeX-Distribution hat sich im Zusammenhang mit dieser Vorlage [MiKTeX](https://miktex.org/) bewährt.

## Über latexmk:
* Bauen: `latexmk`
* Aufräumen: `latexmk -c`

Oder über das makefile:
* Bauen: `make` oder `make all`
* Aufräumen:
  * `make clean` (entfernt output/, dokumentation.pdf und dokumentation.synctex.gz)
  * `make cleanup` (entfernt nur temporäre Build-Dateien)

## Ohne latexmk
Wenn kein latexmk installiert werden kann oder soll, stellt das makefile auch die entsprechenden Befehle ohne latexmk bereit: 
* `make all-legacy`
* `make clean-legacy`
* `make cleanup-legacy`

# Ordnerstruktur
* **ads/** - enthält die notwendigen Seiten, z.B. Abstract, Deckblatt etc., sowie einige Interna
	* **ads/glossary.tex** - Glossareinträge
	* **ads/acronyms.tex** - Einträge des Abkürzungsverzeichnisses
* **content/** - enthält pro Kapitel eine Datei (Schema: `<nn>kapitel.tex`)
* **images/** - enthält Bilder und Logos
	* **images/logo.png** - Logo der Firma auf Deckblatt.
* **einstellungen.tex** - hier werden z.B. die Pflichtangaben auf dem Deckblatt geändert
* **dokumentation.tex** - die Hauptdatei, die alles andere einbindet
* **bibliographie.bib** - Einträge der Bibliographie
* **latexmkrc** - die Regeln, nach denen latexmk das Dokument baut

# Nur Deckblatt verwenden
```latex
% .....
\includepdf[pages=1]{../latexVorlage/dokumentation.pdf}
```
