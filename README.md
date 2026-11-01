# quietfeed-rules

Öffentliche Filter-Regeln für die private iOS-App **Calmgram** (Repo `quietfeed`).

Die App lädt `rules.json` beim Start, spätestens alle 6 Stunden und sobald ihre
Selbstdiagnose meldet, dass Instagram etwas verändert hat. Übernommen wird die
Datei nur, wenn sie gültig ist **und** ihre `version` höher ist als die aktuelle.

Inhalt: ausschließlich CSS-Selektoren, Routen-Regeln (Regex) und kurze
Text-Marker wie „Sponsored“. Keine persönlichen Daten.

## Regeln aktualisieren

Die Quelle ist `Calmgram/Filters/rules.json` im App-Repo. Veröffentlichen:

```sh
cd ~/calmgram
# rules.json anpassen, "version" erhöhen, Tests laufen lassen:
(cd Tests/js && npm test)
Tools/publish-rules.sh
```

Raw-URL (in `project.yml` als `REMOTE_RULES_URL` eingetragen):
https://raw.githubusercontent.com/davidfvxts/quietfeed-rules/main/rules.json

GitHub cacht Raw-Dateien bis zu ca. 5 Minuten.
