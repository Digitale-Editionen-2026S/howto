# Virtual Environments in Python

Sie können in Python auf den Code anderer Leute zugreifen, indem Sie Pakete installieren. Pakete können wiederum auf anderen Paketen basieren etc. Die Pakete, die Sie zum Verwenden eines Projekts benötigen, sind oft in einer Datei namens `requirements.txt` aufgelistet.

Manchmal können diese Pakete jedoch Konflikte verursachen, wenn sie von unterschiedlichen Versionen des gleichen Pakets abhängig sind. Um dieses Problem zu lösen, können wir virtuelle Umgebungen verwenden.

Virtuelle Umgebungen ermöglichen es Ihnen, isolierte Python-Umgebungen zu erstellen, in denen Sie Pakete installieren können, ohne dass sie mit anderen Projekten oder der globalen Python-Installation auf Ihrem Computer in Konflikt geraten.

## Erstellen und Aktivieren einer virtuellen Umgebung
Um eine virtuelle Umgebung zu erstellen, können Sie das `venv`-Modul verwenden, das in Python 3.3 und höher enthalten ist:
1. navigieren Sie **im Terminal** in das Verzeichnis, in dem Sie Ihre virtuelle Umgebung erstellen möchten.
2. Führen Sie den folgenden Befehl aus, um eine virtuelle Umgebung namens `mein_projekt` zu erstellen:
```bash
python -m venv mein_projekt
``` 
3. Nach der Ausführung dieses Befehls wird ein neues Verzeichnis namens `mein_projekt` erstellt, das die virtuelle Umgebung enthält.
3. Umgebung starten (aktivieren)
macOS / Linux:
```bash
source mein_projekt/bin/activate
```
Windows (CMD):
```cmd
mein_projekt\Scripts\activate
```
Windows (PowerShell):
```ps
mein_projekt\Scripts\Activate.ps1
```
4. Pakete installieren
Nachdem die virtuelle Umgebung aktiviert ist, können Sie Pakete aus der `requirements.txt` installieren.
```bash
pip install -r requirements.txt
```
<br>
<br>

---

**Achtung**: Sobald Sie Ihr Terminal wieder schließen, wird die virtuelle Umgebung deaktiviert. Sie müssen sie erneut aktivieren, wenn Sie an Ihrem Projekt weiterarbeiten möchten. Ausnahme: VS-Code aktiviert die virtuelle Umgebung automatisch, wenn Sie das Projekt öffnen. (Zumindest manchmal.)
Fall Sie die virtuelle Umgebung direkt deatkivieren möchten, können Sie den folgenden Befehl verwenden:
```bash
deactivate
```
---