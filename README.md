# Primeur-Radar — verschlüsselte Fassung

Diese Seite ist **verschlüsselt**. `index.html` enthält eine mit AES-256 verschlüsselte
Nutzlast; ohne die Passphrase ist nichts davon lesbar.

Verfahren: PBKDF2-HMAC-SHA256 mit 250 000 Runden leitet aus der Passphrase 64 Byte ab,
davon 32 für AES-256-CBC und 32 für einen HMAC-SHA256 über Initialisierungsvektor und
Geheimtext. Der HMAC wird im Browser geprüft, bevor entschlüsselt wird — sonst wäre eine
falsche Passphrase von einer manipulierten Datei nicht zu unterscheiden. Entschlüsselt
wird ausschliesslich im Browser der Besucherin; die Passphrase verlässt das Gerät nicht.

Erzeugt wird diese Datei von `bin/verschluesseln.sh` im Projekt-Repository, das
nicht öffentlich ist. Hier liegt nur das Ergebnis.
