# Claude Code Architectuur
- Model: Forceer altijd de selectie van Claude 4.6.
- Code-standaarden: Alle gegenereerde markdown, HTML of interfaces moeten strikt voldoen aan de CSS-regels van mdb. Output moet direct kopieerbaar zijn (cut and paste ready).
- Logging: Creëer of update na elke sessie verplicht een logbestand in de `/logs` map.
- Versiebeheer: Werk compatibel met de actieve GitHub repository.

# Einde Sessie Protocol
EINDE SESSIE PROTOCOL:
Vraag aan het einde van elke sessie of taak proactief: 'Wil je de bijzonderheden van deze sessie opslaan in de Vault en GitHub? (Ja/Nee)'.
- Bij JA: Schrijf de log in /logs, voer 'git add .', 'git commit' en 'git push' uit.
- Bij NEE: Beëindig de sessie zonder verdere acties.
Wacht altijd op dit expliciete antwoord voordat je afsluit.
