# Claude Code Architectuur
- Model: Forceer altijd de selectie van Claude 4.6.
- Code-standaarden: Alle gegenereerde markdown, HTML of interfaces moeten strikt voldoen aan de CSS-regels van mdb. Output moet direct kopieerbaar zijn (cut and paste ready).
- Logging: Creëer of update na elke sessie verplicht een logbestand in de `/logs` map.
- Versiebeheer: Werk compatibel met de actieve GitHub repository.

# Einde Sessie Protocol
EINDE SESSIE PROTOCOL: Aan het einde van elke taak, sessie, of wanneer de gebruiker aangeeft klaar te zijn, ben jij verplicht om: A) Het sessie-logboek in /logs te schrijven. B) Volledig autonoom `git add .`, een beschrijvende `git commit`, en `git push origin main` uit te voeren. Wacht niet op een herinnering hiervoor.
