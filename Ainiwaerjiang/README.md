# Individuelle Themenstellung

### Einleitung Individueller Themenstellung
Diese Arbeit untersucht verschiedene Aspekte der Benutzeroberflächenentwicklung und der Implementierung von JavaScript-Applikationen. Im Fokus stehen die Unterschiede zwischen Windows Forms und ASP WebForms, die Verwendung von Vue.js als clientseitigem Framework, das Eventhandling in JavaScript-Applikationen, das Komponentenkonzept von Vue.js, der Einsatz von fertigen Komponenten von PrimeVue und die Verwendung von Services in clientseitigen Applikationen.
Die Unterschiede zwischen Windows Forms und ASP WebForms werden analysiert und ihre Vor- und Nachteile untersucht. Vue.js wird als leistungsstarkes clientseitiges Framework betrachtet, das ein effizientes Komponentenkonzept für wiederverwendbare UI-Komponenten bietet. Die Verwendung von PrimeVue-Komponenten zur Beschleunigung der Entwicklung und die Implementierung von Eventhandling in JavaScript-Applikationen werden behandelt. Außerdem werden Services in clientseitigen Applikationen untersucht, insbesondere die Datenstruktur zum Speichern von Call-Objekten und die dynamische Generierung des Layouts basierend auf JSON-Daten.

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
Während des Projekts sind wir auf verschiedene Herausforderungen gestoßen. Hier sind einige Beispiele für die aufgetretenen Probleme und wie wir sie gelöst haben:

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
     > **Hinweis:** Dieser Codeausschnitt ist eine Methode namens `TryParseJson`, die versucht, einen JSON-String in ein Objekt vom Typ `T` zu parsen. Dabei wird die Newtonsoft.Json-Bibliothek für die Deserialisierung verwendet. Der Code richtet einen Ereignishandler ein, um Fehler während der Deserialisierung zu behandeln, und wirft einen Fehler, wenn im JSON fehlende Member vorhanden sind. Die Methode gibt einen booleschen Wert zurück, der den Erfolg oder Misserfolg des Parsing-Vorgangs anzeigt.

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

Vue.js ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Es zeichnet sich durch seine Einfachheit, Flexibilität und leistungsstarke Funktionen aus. Vue.js wurde entwickelt, um die Erstellung interaktiver Webanwendungen zu erleichtern, indem es eine strukturierte und komponentenbasierte Herangehensweise bietet.

## Warum Vue.js verwenden?

- **Einfach zu erlernen und zu verwenden:** Vue.js ist relativ einfach zu erlernen, insbesondere für Entwickler, die bereits Erfahrung mit HTML, CSS und JavaScript haben. Es bietet eine klare und gut dokumentierte Syntax, die leicht verständlich ist.

- **Komponentenbasierte Architektur:** Vue.js ermöglicht es Entwicklern, ihre Benutzeroberfläche in wiederverwendbare Komponenten aufzuteilen. Dies fördert die Wartbarkeit und Wiederverwendbarkeit des Codes und erleichtert die Zusammenarbeit zwischen den Entwicklern.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dadurch bleibt die Benutzeroberfläche stets synchronisiert und Entwickler müssen sich nicht um manuelle Aktualisierungen kümmern.

- **Leistungsfähige Funktionen:** Vue.js bietet eine breite Palette von leistungsstarken Funktionen wie z.B. Routing, Zustandsverwaltung und Animationen. Diese Funktionen werden durch offizielle Plugins und Erweiterungen unterstützt, was die Entwicklung

### Eventhandling in einer JavaScript Applikation.

#### Unterschiede zwischen ASP.NET und Vue.js in Bezug auf die Eventhandlung

## ASP.NET

ASP.NET ist ein serverseitiges Webframework, das zur Entwicklung von Webanwendungen verwendet wird. Bei der Eventbehandlung in ASP.NET wird das Postback-Modell verwendet. Hier sind die grundlegenden Konzepte der Eventbehandlung in ASP.NET:

- **Serverseitige Events:** In ASP.NET werden die meisten Events serverseitig behandelt. Das bedeutet, dass der Server die Events empfängt, verarbeitet und die entsprechende Aktion ausführt. Die Events werden durch die Interaktion des Benutzers mit den Websteuerelementen ausgelöst.

- **PostBack-Modell:** Beim Auslösen eines Events wird eine Postback-Anforderung an den Server gesendet. Der Server verarbeitet das Event, führt die erforderlichen Aktionen aus und rendert die aktualisierte Seite zurück zum Client. Dies führt zu einem vollständigen Seitenneuladen und kann die Benutzererfahrung beeinträchtigen.

- **ViewState:** ASP.NET verwendet das ViewState-Konzept, um den Zustand der Seite und der Websteuerelemente zwischen den Postbacks zu speichern. Dadurch können die Websteuerelemente ihren Zustand beibehalten und die Eventbehandlung erleichtern.

## Vue.js

Vue.js ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Bei der Eventbehandlung in Vue.js wird ein reaktiver Ansatz verwendet. Hier sind die grundlegenden Konzepte der Eventbehandlung in Vue.js:

- **Dom-Events:** Vue.js ermöglicht die direkte Behandlung von DOM-Events in den Vorlagenkomponenten. Sie können den `v-on`-Direktiven verwenden, um Events abzuhören und die entsprechenden Methoden aufzurufen.

- **Komponentenbasierte Events:** Vue.js ermöglicht die Kommunikation zwischen Komponenten über das Eventbus-System. Komponenten können Events auslösen und andere Komponenten können diese Events abhören und entsprechende Aktionen ausführen. Dadurch wird eine lose Kopplung zwischen den Komponenten erreicht.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dies ermöglicht eine effiziente und reibungslose Aktualisierung der Benutzeroberfläche, ohne die gesamte Seite neu zu laden.


### Komponentenkonzept von Vue.js.

Das Komponentenkonzept von Vue.js ermöglicht die Entwicklung von wiederverwendbaren und modularen UI-Komponenten in JavaScript.Komponenten sind eigenständige und isolierte Teile einer Webanwendung, die ihre eigene Logik, Zustand und Darstellung haben können.Mit Vue.js können Sie benutzerdefinierte Komponenten erstellen, indem Sie das `Vue.component()`-Funktion verwenden oder Komponentenobjekte erstellen, die auf der Vue-Komponentenoption basieren. Eine Vue-Komponente besteht aus drei Hauptteilen:
- Template: Das Template definiert die visuelle Darstellung der Komponente. Es enthält HTML-Code mit Vue-Direktiven, die Daten binden und die Logik der Komponente steuern.
- Script: Das Script enthält die Logik und den Zustand der Komponente. Hier können Sie Daten definieren, Methoden erstellen, Lebenszyklushooks nutzen und mit externen Ressourcen interagieren.
- Style: Der Style-Bereich enthält CSS-Regeln, die spezifisch für die Komponente sind. Hier können Sie das Aussehen der Komponente anpassen, indem Sie Klassen, IDs oder andere Selektoren verwenden.
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

TODO

## Services in der clientseitigen Applikation (5 Seiten)

### Datenstruktur zum Speichern der Call Objekte.

TODOd

### Dynamische Generierung des Layout auf Basis von JSON Daten.

TODO
