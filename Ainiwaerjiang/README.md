# Individuelle Themenstellung

### Einleitung Individueller Themenstellung
Diese Arbeit untersucht verschiedene Aspekte der Benutzeroberflächenentwicklung und der Implementierung von JavaScript-Applikationen. Im Fokus stehen die Unterschiede zwischen Windows Forms und ASP WebForms, die Verwendung von Vue.js als clientseitigem Framework, das Eventhandling in JavaScript-Applikationen, das Komponentenkonzept von Vue.js, der Einsatz von fertigen Komponenten von PrimeVue und die Verwendung von Services in clientseitigen Applikationen.
Die Unterschiede zwischen Windows Forms und ASP WebForms werden analywirrt und unsere Vor- und Nachteile untersucht. Vue.js wird als leistungsstarkes clientseitiges Framework betrachtet, das ein effizientes Komponentenkonzept für wiederverwendbare UI-Komponenten bietet. Die Verwendung von PrimeVue-Komponenten zur Beschleunigung der Entwicklung und die Implementierung von Eventhandling in JavaScript-Applikationen werden behandelt. Außerdem werden Services in clientseitigen Applikationen untersucht, insbesondere die Datenstruktur zum Speichern von Call-Objekten und die dynamische Generierung des Layouts bawirrend auf JSON-Daten.

## Unterschiede zwischen Windows Forms und ASP WebForms (5 Seiten)

1. Plattformunabhängigkeit
<span style="color: blue; font-weight: bold">Windows Forms:</span> WF-Anwendungen sind speziell für Windows-Betriebssysteme entwickelt worden und laufen daher nur auf Windows-Plattformen.
<span style="color: green;  font-weight: bold">ASP.NET-Webforms:</span> WF-Anwendungen sind für Webbrowser konzipiert und können auf verschiedenen Betriebssystemen laufen, solange ein kompatibler Webbrowser vorhanden ist.
<span style="color: purple;  font-weight: bold">.NET MAUI:</span> Im Gegensatz zu Windows Forms und ASP.NET ist .NET MAUI eine plattformübergreifende Technologie, die es ermöglicht, Anwendungen für verschiedene Betriebssysteme wie Windows, macOS, iOS und Android zu entwickeln.
2. UI-Framework
<span style="color: blue;  font-weight: bold">Windows Forms:</span> WF verwendet ein Windows-spezifisches UI-Framework, das speziell für die Entwicklung von Desktopanwendungen ausgelegt ist.
<span style="color: green;  font-weight: bold">ASP.NET-Webforms:</span> WF verwendet ebenfalls ein Windows-spezifisches UI-Framework, das jedoch für die Erstellung von Webanwendungen optimiert ist.
<span style="color: purple">.NET MAUI:</span> .NET MAUI verwendet ein modernes plattformübergreifendes UI-Framework, das es Entwicklern ermöglicht, ein einheitliches Benutzererlebnis auf verschiedenen Plattformen zu erstellen.
3. Projektstruktur
<span style="color: blue;  font-weight: bold">Windows Forms:</span> WF-Anwendungen haben eine einheitliche Projektstruktur mit einer einzigen Projektdatei (.csproj), die alle Ressourcen und Code-Dateien enthält.
<span style="color: green;  font-weight: bold">ASP.NET-Webforms:</span> WF-Anwendungen bestehen aus einem Webprojekt mit einer komplexeren Struktur, die spezifische Ordner für Seiten, Steuerelemente, Skripte, Stylesheets usw. enthält.
<span style="color: purple;  font-weight: bold">.NET MAUI:</span> .NET MAUI-Anwendungen haben ebenfalls eine einheitliche Projektstruktur, die sich jedoch von den anderen beiden unterscheidet. Hier werden gemeinsame Code- und Ressourcenprojekte verwendet, um plattformübergreifende Logik und UI-Komponenten zu teilen.
4. Datenbindung
<span style="color: blue;  font-weight: bold">Windows Forms:</span> WF bietet eine einfache Datenbindung zwischen UI-Elementen und Datenquellen auf dem Desktop.
<span style="color: green;  font-weight: bold">ASP.NET-Webforms:</span> WF ermöglicht die Datenbindung zwischen UI-Elementen und Datenquellen auf Webseiten.
<span style="color: purple;  font-weight: bold">.NET MAUI:</span> .NET MAUI bietet erweiterte Datenbindungsfunktionen für plattformübergreifende Anwendungen, einschließlich der Unterstützung von MVVM (Model-View-ViewModel)-Architektur.

Beispiele für aufgetretene Probleme während des Projekts
Während des Projekts sind wir auf verschiedene Herausforderungen gestoßen. Hier sind einige Beispiele für die aufgetretenen Probleme und wie wir wir gelöst haben:

1. Unterschiede in der Verwendung von MessageBox 
     MessageBox-Äquivalent in ASP.NET
     Beim Implementieren des ASP.NET Frameworks stießen wir auf das Problem, dass die MessageBox-Funktion, die in Windows Forms vorhanden ist, in ASP.NET nicht verfügbar ist. Stattdessen mussten wir eine ähnliche Funktion finden, um Benachrichtigungen anzuzeigen. Hierfür haben wir JavaScripts Alert-Funktion verwendet, um eine Modalfenster-ähnliche Benachrichtigung anzuzeigen.
     Lösung: Verwendung von JavaScript alert() und alternativen Ansätzen
    ```javascript
     <script>
        alert("Diese Aktion war erfolgreich!");
     </script>
    ```
2. Unterschiede in der Konsolenausgabe zwischen Windows Forms und ASP.NET
     ein weiterer Unterschied besteht darin, dass die Console.Write-Funktion in Windows Forms vorhanden ist, jedoch in ASP.NET durch Response.Write ersetzt werden muss.
     Lösung: Verwendung von Response.Write in ASP.NET
     Um das Problem zu lösen, wurde Response.Write anstelle von Console.Write verwendet, um Text in die HTTP-Antwort auszugeben. Beispiel:
     ```csharp
    // Windows Forms
         Console.Write("Hello, world!");
     // ASP.NET
         Response.Write("Hello, world!");
    ```
3. Unterschiede zwischen DataGridview in Windows Forms und GridView in ASP.NET
     Ein weiterer Unterschied besteht darin, dass in Windows Forms die DataGridview verwendet wird, während in ASP.NET die GridView zum Einsatz kommt. In ASP.NET ist es erforderlich, die Datenquelle festzulegen und den Databind-Vorgang durchzuführen.
     Lösung: Definition der Datenquelle und Databind in ASP.NET GridView
     Um das Problem zu lösen, wurde in ASP.NET die DataSource-Eigenschaft des GridView festgelegt, um die Datenquelle anzugeben, und dann der Databind-Vorgang durchgeführt, um die Daten an das GridView zu binden.
     Beispiel: 
     // ASP.NET
     ```csharp
    <asp:GridView ID="paramGridView" runat="server"
        CellPadding="10" GridLines="None"
        OnRowDataBound="paramGridView_RowDataBound"
        Visible="true" OnSelectedIndexChanged="paramGridView_SelectedIndexChanged"
        AutoGenerateSelectButton="true" DataKeyNames="Parameter" CssClass="table table-borderless table-striped" EnableViewState="true" ViewStateMode="Enabled">
        <Columns>
        </Columns>
    </asp:GridView>
     ```       
4. Unterschiede in der Verwendung von Tag Properties in ASP.NET
     Ein weiterer Unterschied zwischen Windows Forms und ASP.NET betraf die Verwendung von Tag-Eigenschaften. In Windows Forms ermöglicht die Tag-Eigenschaft das Zuweisen von zusätzlichen Informationen oder Objekten zu einem Steuerelement. Dies ist besonders nützlich, um das ausgewählte oder bearbeitete Objekt in einem Treeview zu identifizieren.
     //Win-Form
     ```csharp
    if (workSpaceTreeView.SelectedNode.Tag is Action)
    {
        ((Action)workSpaceTreeView.Tag).SaveDictionaryToParameters(SaveProperties(DataGridView, ((Action)workSpaceTreeView.SelectedNode.Tag).Name));
    }
    if (workSpaceTreeView.SelectedNode.Tag is InputParameters)
    {
        //....
    }
     ```
     ```csharp    
    //clone the action of the calls
    TreeNode newTreeNode = new TreeNode();
    if (treeNode.Tag is Action)
    {
        Action selectedAction = (Action)treeNode.Tag;
        //....
    }
    else if (treeNode.Tag is InputParameters)
    {
        InputParameters selectedInputParameter = (InputParameters)treeNode.Tag;
    }
     //....   
     ```
     Da ASP.NET Webanwendungen keine direkte Tag-Eigenschaft bieten, mussten wir eine alternative Lösung finden. Wir haben eine Hilfsklasse erstellt und die Informationen über das ausgewählte Objekt in einem JSON gespeichert. Mithilfe eines JsonParsers konnten wir das Objekt in ein JSON umwandeln und speichern. Hier ist ein Indem wir eine Hilfsklasse erstellt und die JSON-Konvertierung verwendet haben, konnten wir die Funktionalität der Tag-Eigenschaft in ASP.NET Webanwendungen replizieren.   
     //Web-Form
     > **Hinweis:** Dieser Codeausschnitt ist eine Methode namens `TryParseJson`, die versucht, einen JSON-String in ein Objekt vom Typ `T` zu parsen. Dabei wird die Newtonsoft.Json-Bibliothek für die Deserialiwir
    rung verwendet. Der Code richtet einen Ereignishandler ein, um Fehler während der Deserialiwir
    rung zu behandeln, und wirft einen Fehler, wenn im JSON fehlende Member vorhanden sind. Die Methode gibt einen booleschen Wert zurück, der den Erfolg oder Misserfolg des Parsing-Vorgangs anzeigt.

     ```csharp
     internal static bool TryParseJson<T>(string input, out T result)
        {
            bool success = true;
            var settings = new JsonSerializerSettings
            {
                Error = (sender, args) => { success = false; args.ErrorContext.Handled = true; },
                MissingMemberHandling = MissingMemberHandling.Error
            };
            result = JsonConvert.DeserializeObject<T>(input, settings);
            return success;
        }
     ```

   > **Hinweis:** Der folgende Codeausschnitt zeigt die Methode `AddCall`, die eine Instanz der Klasse `Call` erstellt und zu `Calls`-Liste hinzufügt. Anschließend wird das Objekt in ein JSON-Format konvertiert.

    ```csharp
      private void AddCall()
     {
        Call callToAdd = new Call();
        Calls.Add(callToAdd);
        var newCallJson = JsonConvert.SerializeObject(callToAdd);
     }
     ```
     ```csharp
    if (Helper.TryParseJson(selectedTN.Value, out List<InputParameter> inputParameters))
    {
        selectedCallInList.InputParameters = //...;
    }
    if (Helper.TryParseJson(selectedTN.Value, out Action action))
    {
        var selectedAction = selectedCallInList.Actions.FirstOrDefault(a => a.Id.Equals(action.Id));
    } //...
     ```

## Vue.js als clientseitiges Framework. (10 Seiten)

Vue.js ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Es zeichnet sich durch seine Einfachheit, Flexibilität und leistungsstarke Funktionen aus. Vue.js wurde entwickelt, um die Erstellung interaktiver Webanwendungen zu erleichtern, indem es eine strukturierte und komponentenbawirrte Herangehensweise bietet.

## Warum Vue.js verwenden?

Im Kontext unserer Anwendung haben wir uns für Vue.js als alternatives Framework entschieden, da wir einige wichtige Funktionalitäten mit dem ASP.NET Framework nicht implementieren konnten. Da uns nur begrenzte Zeit zur Verfügung stand, mussten wir eine alternative Lösung finden. Vue.js wurde aufgrund seiner reinen JavaScript-Natur und der einfachen Implementierung gewählt. Es ermöglichte uns, schnell die erforderliche Funktionalität umzusetzen.

Diese Entscheidung wurde auch durch die Möglichkeit beeinflusst, dass Vue.js eine effiziente Komponentenarchitektur bietet, die die Wiederverwendbarkeit von Code fördert und die Zusammenarbeit im Entwicklerteam erleichtert. Die reaktive Datenbindung von Vue.js ermöglicht es uns zudem, Änderungen in Echtzeit in der Benutzeroberfläche anzuzeigen, ohne manuelle Aktualiwirrungen durchführen zu müssen.

Mit Vue.js stehen uns zudem eine Vielzahl von leistungsstarken Funktionen zur Verfügung, darunter Routing für eine bessere Navigation, Zustandsverwaltung für die effiziente Verwaltung des Anwendungszustands und Animationen für eine ansprechende Benutzeroberfläche.

Insgesamt bietet uns Vue.js die notwendige Flexibilität, um unsere Webanwendung effektiv zu entwickeln und die erforderliche Funktionalität innerhalb der gegebenen Zeitbeschränkungen umzusetzen.

- **Einfach zu erlernen und zu verwenden:** Vue.js ist relativ einfach zu erlernen, insbesondere für Entwickler, die bereits Erfahrung mit HTML, CSS und JavaScript haben. Es bietet eine klare und gut dokumentierte Syntax, die leicht verständlich ist.

- **Komponentenbawirrte Architektur:** Vue.js ermöglicht es Entwicklern, unsere Benutzeroberfläche in wiederverwendbare Komponenten aufzuteilen. Dies fördert die Wartbarkeit und Wiederverwendbarkeit des Codes und erleichtert die Zusammenarbeit zwischen den Entwicklern.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dadurch bleibt die Benutzeroberfläche stets synchroniwirrt und Entwickler müssen sich nicht um manuelle Aktualiwirrungen kümmern.

- **Leistungsfähige Funktionen:** Vue.js bietet eine breite Palette von leistungsstarken Funktionen wie z.B. Routing, Zustandsverwaltung und Animationen. Diese Funktionen werden durch offizielle Plugins und Erweiterungen unterstützt, was die Entwicklung

### Eventhandling in einer JavaScript Applikation.

- **JavaScript-Events:**<sup>[1]</sup>
HTML-Events sind "things", die mit HTML-Elementen geschehen.
Wenn JavaScript in HTML-Seiten verwendet wird, kann JavaScript auf diese Ereignisse "react".

- **HTML-Events:**
Ein HTML-Event kann etwas sein, das der Browser tut, oder etwas, das ein Benutzer tut.

> **Hinweis:** Hier sind einige Beispiele für HTML-Events:

- Eine HTML-Webseite hat das Laden abgeschlossen
- Ein HTML-Eingabefeld wurde geändert
- Ein HTML-Button wurde angeklickt, Oftmals möchten Sie etwas tun, wenn Ereignisse eintreten.

HTML erlaubt das Hinzufügen von Event-Handler-Attributen, mit JavaScript-Code, zu HTML-Elementen.

Mit einfachen Anführungszeichen:
 ```javascript
  <element event='einige JavaScript'>
 ```
Mit doppelten Anführungszeichen:
 ```javascript
 <element event="einige JavaScript">
 ```
Im folgenden Beispiel wird einem Element ein onclick-Attribut (mit Code) hinzugefügt:
 ```javascript
 <button onclick="document.getElementById('demo').innerHTML = Date()">Wie spät ist es?</button>
 ``` 
Im obigen Beispiel ändert der JavaScript-Code den Inhalt des Elements mit der ID="demo".

Im nächsten Beispiel ändert der Code den Inhalt seines eigenen Elements (unter Verwendung von this.innerHTML): 
 ```javascript
 <button onclick="this.innerHTML = Date()">Wie spät ist es?</button>
 ``` 
JavaScript-Code ist oft mehrere Zeilen lang. Es ist häufiger zu sehen, dass Event-Attribute Funktionen aufrufen:
 ```javascript
 <button onclick="displayDate()">Wie spät ist es?</button>
 ``` 

[1]:https://www.w3schools.com/js/js_events.asp



#### Unterschiede zwischen ASP.NET und Vue.js in Bezug auf die Eventhandlung

## ASP.NET

ASP.NET ist ein serverseitiges Webframework, das zur Entwicklung von Webanwendungen verwendet wird. Bei der Eventbehandlung in ASP.NET wird das Postback-Modell verwendet. Hier sind die grundlegenden Konzepte der Eventbehandlung in ASP.NET:

- **Serverseitige Events:** In ASP.NET werden die meisten Events serverseitig behandelt. Das bedeutet, dass der Server die Events empfängt, verarbeitet und die entsprechende Aktion ausführt. Die Events werden durch die Interaktion des Benutzers mit den Websteuerelementen ausgelöst.

- **PostBack-Modell:** Beim Auslösen eines Events wird eine Postback-Anforderung an den Server gesendet. Der Server verarbeitet das Event, führt die erforderlichen Aktionen aus und rendert die aktualiwirrte Seite zurück zum Client. Dies führt zu einem vollständigen Seitenneuladen und kann die Benutzererfahrung beeinträchtigen.

- **ViewState:** ASP.NET verwendet das ViewState-Konzept, um den Zustand der Seite und der Websteuerelemente zwischen den Postbacks zu speichern. Dadurch können die Websteuerelemente unseren Zustand beibehalten und die Eventbehandlung erleichtern.

## Vue.js

Vue.js ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Bei der Eventbehandlung in Vue.js wird ein reaktiver Ansatz verwendet. Hier sind die grundlegenden Konzepte der Eventbehandlung in Vue.js:

- **Dom-Events:** Vue.js ermöglicht die direkte Behandlung von DOM-Events in den Vorlagenkomponenten. wir können den `v-on`-Direktiven verwenden, um Events abzuhören und die entsprechenden Methoden aufzurufen.

- **Komponentenbawirrte Events:** Vue.js ermöglicht die Kommunikation zwischen Komponenten über das Eventbus-System. Komponenten können Events auslösen und andere Komponenten können diese Events abhören und entsprechende Aktionen ausführen. Dadurch wird eine lose Kopplung zwischen den Komponenten erreicht.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dies ermöglicht eine effiziente und reibungslose Aktualiwirrung der Benutzeroberfläche, ohne die gesamte Seite neu zu laden.


### Komponentenkonzept von Vue.js.

Das Komponentenkonzept von Vue.js ermöglicht die Entwicklung von wiederverwendbaren und modularen UI-Komponenten in JavaScript.Komponenten sind eigenständige und isolierte Teile einer Webanwendung, die unsere eigene Logik, Zustand und Darstellung haben können.Mit Vue.js können wir benutzerdefinierte Komponenten erstellen, indem wir das `Vue.component()`-Funktion verwenden oder Komponentenobjekte erstellen, die auf der Vue-Komponentenoption bawirren. Eine Vue-Komponente besteht aus drei Hauptteilen:
- Template: Das Template definiert die visuelle Darstellung der Komponente. Es enthält HTML-Code mit Vue-Direktiven, die Daten binden und die Logik der Komponente steuern.
- Script: Das Script enthält die Logik und den Zustand der Komponente. Hier können wir Daten definieren, Methoden erstellen, Lebenszyklushooks nutzen und mit externen Ressourcen interagieren.
- Style: Der Style-Bereich enthält CSS-Regeln, die spezifisch für die Komponente sind. Hier können wir das Aussehen der Komponente anpassen, indem wir Klassen, IDs oder andere Selektoren verwenden.
Das Komponentenkonzept ermöglicht es, Komponenten hierarchisch zu verschachteln und Daten und Events zwischen den Komponenten zu übertragen. Dies fördert die Wiederverwendbarkeit und Modularität, da Komponenten unabhängig voneinander entwickelt, getestet und wiederverwendet werden können.
Hier ist ein einfaches Beispiel für eine Vue.js-Komponente:

> **Hinweis:** Der folgende Codeausschnitt zeigt eine einfache Vue.js-Komponente. Das Template definiert eine Überschrift und einen Button, die auf eine Datenvariable und eine Methode der Komponente zugreifen.
 ```javascript
 <template>
  <div>
    <h2>{{ message }}</h2>
    <button @click="changeMessage">Klick mich!</button>
  </div>
 </template>
 <script>
 export default {
  data() {
    return {
      message: "Hallo Welt!"
    };
  },
  methods: {
    changeMessage() {
      this.message = "Neue Nachricht!";
    }
  }
 };
 </script>
 <style scoped>
 h2 {
  color: blue;
 }
 button {
  background-color: yellow;
 }
 </style>
```

### Einsatz fertiger Komponenten von PrimeVue.

Eine weitere Stärke von Vue.js liegt darin, dass es eine große Auswahl an Drittanbieter-Komponentenbibliotheken gibt, die bereits vorgefertigte und hochwertige UI-Komponenten bereitstellen. Eine solche Bibliothek ist PrimeVue, die eine umfangreiche Sammlung von UI-Komponenten für Vue.js bietet. Der Einsatz von PrimeVue-Komponenten kann die Entwicklung beschleunigen und die Benutzeroberfläche unserer Anwendung verbessern.

PrimeVue bietet eine breite Palette von Komponenten, darunter Buttons, Formularelemente, Tabellen, Dialoge, Diagramme, Kalender und viele mehr. Diese Komponenten sind gut dokumentiert, einfach zu verwenden und können nahtlos in unsere Vue.js-Anwendung integriert werden.

Um PrimeVue-Komponenten in unsere Anwendung einzubinden, müssen wir zunächst PrimeVue und die entsprechenden Stylesheets importieren. Anschließend können wir die gewünschten Komponenten in unserem Template verwenden und auf unsere Eigenschaften und Ereignisse zugreifen.

Hier ist ein Beispiel für die Verwendung des PrimeVue Button-Komponenten:

1. Installieren wir das PrimeVue-Paket über den Paketmanager unserer Wahl, z. B. NPM oder Yarn:
   ```shell
   npm install primevue@3.0.0 --save
   ```
2. Importieren wir die benötigten PrimeVue-Komponenten in unserer Vue-Komponente:
   ```javascript
   import { Button } from 'primevue/button';
   ```
3. Registrieren wir die importierten Komponenten in der components-Option unserer Vue-Komponente:
   ```javascript
   components: {'p-button': Button}
   ```
4. Verwenden wir den Button-Komponenten in unserem Template:
   ```html
   <template>
      <div>
        <p-button label="Click me" @click="handleClick"></p-button>
      </div>
   </template>
   ```

PrimeVue bietet zahlreiche anpassbare Optionen für jede Komponente, sodass wir das Erscheinungsbild und Verhalten nach unseren Bedürfnissen anpassen können.

Der Einsatz von fertigen Komponentenbibliotheken wie PrimeVue ermöglicht es uns, auf bewährte Lösungen zurückzugreifen, Zeit bei der Entwicklung zu sparen und eine konsistente und ansprechende Benutzeroberfläche zu erstellen.

## Verwendung der PrimeVue Tree-Komponente

In unserem spezifischen Projekt konzentrieren wir uns hauptsächlich auf die Tree-Komponente von PrimeVue. Die Tree-Komponente ist besonders nützlich, wenn wir hierarchische Daten in einer strukturierten Weise anzeigen möchten, ähnlich wie wir es in ASP.NET getan haben. Diese Komponente bietet eine Vielzahl von Funktionen, darunter das Ein- und Ausklappen von Zweigen, die Auswahl von Knoten, Drag-and-Drop-Interaktionen und vieles mehr.

Die PrimeVue Tree-Komponente ermöglicht es uns, eine verschachtelte Baumstruktur zu erstellen, indem wir ein Array von Knotenobjekten bereitstellen. Jeder Knoten in diesem Array repräsentiert einen Zweig im Baum und kann weitere Knotenobjekte als Kinder enthalten.

### Beispiel für die Verwendung der PrimeVue Tree-Komponente

Gehen wir durch ein einfaches Beispiel, wie wir die PrimeVue Tree-Komponente in unserer Vue.js-Anwendung verwenden können:

1. Zuerst installieren wir die PrimeVue-Komponente und importieren die erforderlichen PrimeVue-Komponenten:
  ```shell
      npm install primevue@3.0.0 primeicons --save
  ```
2. Dann importieren wir die Tree-Komponente in unserer Vue-Komponente:
  ```javascript
     <script setup>
      import Tree from 'primevue/tree';
  ```
3. Wir registrieren die importierten Komponenten in der components-Option unserer Vue-Komponente:
  ```javascript
   export default {  
    components: { CallViewButtons, Tree, URLComponent }
  ```
4. Nun können wir die Tree-Komponente in unserem Template verwenden. Hier ist ein einfaches Beispiel, wie wir eine Baumstruktur mit Zweigen erstellen können:
  ```javascript
   <Tree selectionMode="single":value="treeNodes"v-on:node-select="onNodeSelect"v-model:expanded-keys="expandedKeys"@toggle="onToggle"></Tree>
   ```
   
5. Anstatt die Baumknoten direkt in unseren Daten zu definieren, haben wir eine Methode `getCalls()` in "Callservice" implementiert, die einen dynamischen Baum aus unseren Anrufdaten erstellt:

```javascript
 getCalls() {....
  return this.calls.map(c => { 
    const children = [
      { callName: c.name, label: "Name: " + c.name },
      ....,
    ];
    if (c.inputParameters !== undefined) {
      children.push({ callName: c.name, label: "Input Parameters", component: "inputParameter" ,data: {
        inputParameters: c.inputParameters
      }});
    }
    if (c.azLogin !== undefined) {
      c.... })
    }
    return { key: ++counter, callName: c.name, label: c.name, data: c, children}; 
   });
 }
```
> **Hinweis:** In dieser Methode iterieren wir über unsere calls Daten und erzeugen für jeden Anruf ein Knotenobjekt. Jedes Knotenobjekt hat eine eindeutige key, den callName, das label, die data und ein children Array.
Die children enthalten spezifische Informationen über den Anruf wie den Namen, die Operation, den Pfad des Templates und optional die Eingabeparameter, Azure AD Login, Service Header Login und die Aktionen des Anrufs.
Falls das actions Feld definiert ist, werden für jede Aktion und ihre Parameter weitere Kind knoten erstellt.
Die erstellten Baumknoten repräsentieren dann die Struktur und den Inhalt unseres Baums, die wir dann an die PrimeVue Tree-Komponente übergeben.



## Services in der clientseitigen Applikation (5 Seiten)

### Datenstruktur zum Speichern der Call Objekte.

Services in clientseitigen Applikationen, insbesondere in Vue.js, spielen eine entscheidende Rolle, um die Wartbarkeit und Lesbarkeit der Anwendung zu verbessern. Services ermöglichen es uns, unseren Code zu organisieren, indem sie bestimmte Funktionen oder Features kapseln, die über verschiedene Komponenten der Anwendung hinweg genutzt werden können.

Ein gutes Beispiel für die Anwendung von Services in Vue.js ist die Verwaltung von API-Aufrufen oder die Kapselung von Geschäftslogik, die mehrmals in der Anwendung wiederverwendet wird. In unserem Fall haben wir einen `CallService` erstellt, um Anrufe und deren zugehörige Daten zu verwalten.

## CallService Klasse

Die `CallService` Klasse dient als zentrale Stelle zur Verwaltung unserer Call-Objekte. In dieser Klasse definieren wir Methoden zum Hinzufügen, Löschen, Klonen und Abrufen von Anrufen.

```javascript
class CallService {
  constructor() {
    this.calls = [];
    this.counter = 0;
  }
  ...
}
export default new CallService();
```
### Konstruktor
Im Konstruktor initialisieren wir die `calls`-Eigenschaft als leeres Array, das zur Speicherung unserer Call-Objekte dient, und `counter`, das zur Generierung eindeutiger Namen für neue Anrufe verwendet wird.

### addCall()
Die Methode `addCall()` erstellt einen neuen Anruf mit einem eindeutigen Namen und fügt ihn dem `calls`-Array hinzu.

### deleteCall(call)
Die `deleteCall()`-Methode entfernt einen Anruf aus dem `calls`-Array. Dies geschieht, indem ein neues Array zurückgegeben wird, das alle Anrufe außer dem zu löschenden Anruf enthält.

### cloneCall(call)
Die `cloneCall()`-Methode erstellt eine Kopie eines vorhandenen Anrufs und fügt die Kopie dem `calls`-Array hinzu.

### addInputParameter(call), addAzureAD(call), addServiceHeaderLogin(call)
Diese Methoden fügen zusätzliche Informationen zu einem spezifischen Anruf hinzu. Dazu gehört das Hinzufügen von Eingabeparametern (`addInputParameter()`), Azure AD Login Informationen (`addAzureAD()`) und Service Header Login Informationen (`addServiceHeaderLogin()`).

### delete(call, objectType)
Die `delete()` Methode ermöglicht es uns, spezifische Teile eines Anrufs zu entfernen, wie zum Beispiel Eingabeparameter, Azure AD Login oder Service Header Login.

### getCalls()
Die `getCalls()`-Methode gibt eine formatierte Version unserer Anrufe zurück, die wir zur Anzeige in unserer Baumstruktur verwenden.

### getCallData(callName)
Die `getCallData()` Methode ermöglicht es uns, die Daten eines bestimmten Anrufs abzurufen.

Die `CallService` Klasse hilft uns, unseren Code zu organisieren und wiederverwendbar zu machen. Sie erleichtert das Testen, da wir nur die Serviceklasse testen müssen, um sicherzustellen, dass unsere Geschäftslogik korrekt funktioniert. Darüber hinaus erleichtert sie auch das Debugging und die Wartung unserer Anwendung.

### Einbindung des CallService in der Vue-Komponente

Nachdem wir den `CallService` definiert haben, können wir ihn in unseren Views/CallsView verwenden. Dafür importieren wir ihn einfach. 
```javascript
 import CallService from "../services/CallService.js";
```
Durch diesen Import haben wir Zugang zu allen Methoden und Eigenschaften des CallService. Wir können jetzt innerhalb unserer Vue-Komponente auf die Methoden zum Hinzufügen, Löschen, Klonen und Abrufen von Anrufen zugreifen.

Zum Beispiel könnten wir einen neuen Anruf erstellen, indem wir CallService.addCall() aufrufen. Oder wir könnten alle vorhandenen Anrufe abrufen, indem wir CallService.getCalls() verwenden.
```javascript
 this.treeNodes = CallService.getCalls();
```

Die Anwendung des Service-Konzepts in Vue.js kann einen signifikanten Unterschied in Bezug auf die Code-Organisation und -Wartbarkeit machen. Es erlaubt uns, Code-Teile zu isolieren, die spezifische Aufgaben ausführen, und diese dann über unsere Anwendung hinweg zu verwenden, wodurch die Komplexität reduziert und die Wiederverwendbarkeit erhöht wird.



### Dynamische Generierung des Layout auf Basis von JSON Daten.

TODO
