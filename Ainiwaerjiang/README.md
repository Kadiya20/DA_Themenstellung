# Individuelle Themenstellung

## Einleitung Individueller Themenstellung
Diese Arbeit untersucht verschiedene Aspekte der Benutzeroberflächenentwicklung und Implementierung von JavaScript-Anwendungen. Im Fokus stehen die Unterschiede zwischen Windows Forms und ASP WebForms, die Verwendung von Vue.js als clientseitiges Framework<sup>[1]</sup>, das Event-Handling in JavaScript-Anwendungen, das Komponenten Konzept von Vue.js, der Einsatz von fertigen Komponenten aus PrimeVue und die Verwendung von Services in clientseitigen Anwendungen.

Die Unterschiede zwischen Windows Forms und ASP WebForms werden analysiert und deren jeweilige Vor- und Nachteile untersucht. Vue.js wird als leistungsstarkes clientseitiges Framework betrachtet, das ein effizientes Konzept für wiederverwendbare UI-Komponenten bietet. Die Verwendung von PrimeVue-Komponenten zur Beschleunigung der Entwicklung und die Implementierung von Event-Handling in JavaScript-Anwendungen werden behandelt.

Außerdem untersuchen wir Services in clientseitigen Anwendungen, insbesondere die Datenstruktur zum Speichern von Call-Objekten und die dynamische Generierung des Layouts basierend auf JSON-Daten.

### Serverseitige Anwendungen
Serverseitige Anwendungen sind Programme, die auf einem Webserver laufen. Sie verarbeiten eingehende Anfragen von Clients, führen Berechnungen durch, interagieren mit Datenbanken und senden Antworten zurück an den Client.
Serverseitige Anwendungen sind in der Regel verantwortlich für Aufgaben wie die Authentifizierung von Benutzern, die Verarbeitung von Formulardaten, das Speichern und Abrufen von Daten und die Erstellung von dynamischen Inhalten, die an den Client gesendet werden.

Einige gebräuchliche Technologien für die serverseitige Entwicklung sind Node.js, Ruby on Rails, Django (Python), Laravel (PHP) und ASP.NET.

### Clientseitige Anwendungen
Clientseitige Anwendungen sind Programme, die in einem Webbrowser auf dem Gerät eines Benutzers laufen. Sie sind verantwortlich für die Interaktion mit dem Benutzer und das Aktualisieren der Benutzeroberfläche ohne die Notwendigkeit, eine neue Anfrage an den Server zu senden.Bei der Webentwicklung bezieht sich der Begriff „Clientseite“ auf alles in einer Webanwendung, was auf dem Client (Endbenutzergerät) dargestellt wird oder stattfindet. Dazu gehört das, was der Benutzer sieht – Text, Bilder und der Rest der Benutzeroberfläche – sowie alle Aktionen, die eine Anwendung im Browser des Benutzers ausführt.

Auszeichnungssprachen wie HTML und CSS werden vom Browser auf der Clientseite interpretiert. Darüber hinaus schließen viele Entwickler heute clientseitige Prozesse in ihre Anwendungsarchitektur ein und lassen nicht mehr alles auf der Serverseite ausführen. Zum Beispiel wird Geschäftslogik für dynamische Webseiten* in einer modernen Webanwendung gewöhnlich auf der Clientseite ausgeführt.Clientseitige Anwendungen werden meist in JavaScript geschrieben und nutzen oft Bibliotheken oder Frameworks wie Vue.js, React oder Angular, um die Entwicklung zu erleichtern.

Ein wichtiger Aspekt von clientseitigen Anwendungen ist das Asynchrone JavaScript und XML (AJAX), eine Technik, die es uns ermöglicht, Daten mit dem Server auszutauschen und Teile einer Webseite zu aktualisieren, ohne die gesamte Seite neu laden zu müssen.


[1]:https://www.cloudflare.com/de-de/learning/serverless/glossary/client-side-vs-server-side/

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
2. Unterschiede in der Konsolen Ausgabe zwischen Windows Forms und ASP.NET
     ein weiterer Unterschied besteht darin, dass die Console.Write-Funktion in Windows Forms vorhanden ist, jedoch in ASP.NET durch Response.Write ersetzt werden muss.
     Lösung: Verwendung von Response.Write in ASP.NET
     Um das Problem zu lösen, wurde Response.Write anstelle von Console.Write verwendet, um Text in die HTTP-Antwort auszugeben. Beispiel:
     ```csharp
    // Windows Forms
         Console.Write("Hello, world!");
     // ASP.NET
         Response.Write("Hello, world!");
    ```
3. Unterschiede zwischen Data Grid_view in Windows Forms und GridView in ASP.NET
     Ein weiterer Unterschied besteht darin, dass in Windows Forms die Data Grid_view verwendet wird, während in ASP.NET die GridView zum Einsatz kommt. In ASP.NET ist es erforderlich, die Datenquelle festzulegen und den Data_bind-Vorgang durchzuführen.
     Lösung: Definition der Datenquelle und Data_bind in ASP.NET GridView
     Um das Problem zu lösen, wurde in ASP.NET die DataSource-Eigenschaft des GridView festgelegt, um die Datenquelle anzugeben, und dann der Data_bind-Vorgang durchgeführt, um die Daten an das GridView zu binden.
     Beispiel: 
     // ASP.NET
     ```csharp
    <asp:GridView ID="paramGridView" runat="server"
        CellPadding="10" GridLines="None"
        OnRowDataBound="paramGridView_RowDataBound"
        Visible="true" OnSelectedIndexChanged="paramGridView_SelectedIndexChanged"
        AutoGenerateSelectButton="true" DataKeyNames="Parameter" CssClass="table table-border less table-striped" EnableViewState="true" ViewStateMode="Enabled">
        <Columns>
        </Columns>
    </asp:GridView>
     ```       
4. Unterschiede in der Verwendung von Tag Properties in ASP.NET
     Ein weiterer Unterschied zwischen Windows Forms und ASP.NET betraf die Verwendung von Tag-Eigenschaften. In Windows Forms ermöglicht die Tag-Eigenschaft das Zuweisen von zusätzlichen Informationen oder Objekten zu einem Steuerelement. Dies ist besonders nützlich, um das ausgewählte oder bearbeitete Objekt in einem `Tree view` zu identifizieren.
     
     Im folgenden Codeblock, der eine Windows Forms-Anwendung darstellt, wird die `Tag`-Eigenschaft verwendet, um das ausgewählte Objekt zu identifizieren und Aktionen darauf auszuführen:
     
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
     
     Im nächsten Codeblock wird die `Tag`-Eigenschaft verwendet, um eine Aktion zu klonen oder andere spezifische Aufgaben zu erfüllen:

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
     
     Da ASP.NET Webanwendungen keine direkte Tag-Eigenschaft bieten, mussten wir eine alternative Lösung finden. Wir haben eine Hilfsklasse erstellt und die Informationen über das ausgewählte Objekt in einem JSON gespeichert. Mithilfe eines JsonParsers konnten wir das Objekt in ein JSON umwandeln und speichern. Hier ist ein Beispiel für diese Umsetzung:

     Der folgende Codeblock stellt eine Methode dar, die versucht, einen JSON-String in ein Objekt vom Typ `T` zu parsen. Dabei wird die Newtonsoft.Json-Bibliothek für die Deserialisierung verwendet. Der Code richtet einen Ereignis handler ein, um Fehler während der Deserialisierung zu behandeln, und wirft einen Fehler, wenn im JSON fehlende Member vorhanden sind. Die Methode gibt einen booleschen Wert zurück, der den Erfolg oder Misserfolg des Parsing-Vorgangs anzeigt.

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
     
     Der nächste Codeblock zeigt die Methode `AddCall`, die eine Instanz der Klasse `Call` erstellt und zur `Calls`-Liste hinzufügt. Anschließend wird das Objekt in ein JSON-Format konvertiert.

    ```csharp
      private void AddCall()
     {
        Call callToAdd = new Call();
        Calls.Add(callToAdd);
        var newCallJson = JsonConvert.SerializeObject(callToAdd);
     }
     ```
     Im letzten Codeausschnitt verwenden wir die zuvor definierte `TryParseJson`-Methode, um das ausgewählte Objekt zu identifizieren und zu verarbeiten. Abhängig von dem resultierenden Objekttyp führen wir verschiedene Aktionen aus:

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

Vue.js<sup>[5]</sup> ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Es zeichnet sich durch seine Einfachheit, Flexibilität und leistungsstarke Funktionen aus. Vue.js wurde entwickelt, um die Erstellung interaktiver Webanwendungen zu erleichtern, indem es eine strukturierte und Komponenten basierte Herangehensweise bietet.


[5]:https://vuejs.org/guide/extras/ways-of-using-vue.html#single-page-application-spa

## Warum Vue.js verwenden?

Im Kontext unserer Anwendung haben wir uns für Vue.js als alternatives Framework entschieden, da wir einige wichtige Funktionalitäten mit dem ASP.NET Framework nicht implementieren konnten. Da uns nur begrenzte Zeit zur Verfügung stand, mussten wir eine alternative Lösung finden. Vue.js wurde aufgrund seiner reinen JavaScript-Natur und der einfachen Implementierung gewählt. Es ermöglichte uns, schnell die erforderliche Funktionalität umzusetzen.

Diese Entscheidung wurde auch durch die Möglichkeit beeinflusst, dass Vue.js eine effiziente Komponenten Architektur bietet, die die Wiederverwendbarkeit von Code fördert und die Zusammenarbeit im Entwicklerteam erleichtert. Die reaktive Datenbindung von Vue.js ermöglicht es uns zudem, Änderungen in Echtzeit in der Benutzeroberfläche anzuzeigen, ohne manuelle Aktualisierung durchführen zu müssen.

Mit Vue.js stehen uns zudem eine Vielzahl von leistungsstarken Funktionen zur Verfügung, darunter Routing für eine bessere Navigation, Zustandsverwaltung für die effiziente Verwaltung des Anwendungszustands und Animationen für eine ansprechende Benutzeroberfläche.

Insgesamt bietet uns Vue.js die notwendige Flexibilität, um unsere Webanwendung effektiv zu entwickeln und die erforderliche Funktionalität innerhalb der gegebenen Zeitbeschränkungen umzusetzen.

- **Einfach zu erlernen und zu verwenden:** Vue.js ist relativ einfach zu erlernen, insbesondere für Entwickler, die bereits Erfahrung mit HTML, CSS und JavaScript haben. Es bietet eine klare und gut dokumentierte Syntax, die leicht verständlich ist.

- **Komponenten basierte Architektur:** Vue.js ermöglicht es Entwicklern, unsere Benutzeroberfläche in wiederverwendbare Komponenten aufzuteilen. Dies fördert die Wartbarkeit und Wiederverwendbarkeit des Codes und erleichtert die Zusammenarbeit zwischen den Entwicklern.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dadurch bleibt die Benutzeroberfläche stets synchronisiert und Entwickler müssen sich nicht um manuelle Aktualisierung kümmern.

- **Leistungsfähige Funktionen:** Vue.js bietet eine breite Palette von leistungsstarken Funktionen wie z.B. Routing, Zustandsverwaltung und Animationen. Diese Funktionen werden durch offizielle Plugins und Erweiterungen unterstützt, was die Entwicklung.
  
#### client-side-vue/dependencies/ <sup>[7]</sup>
  
- **Vue Router:** Vue Router ist das offizielle Router-Plugin für Vue.js. Es ermöglicht die Navigation innerhalb einer Single-Page-Anwendung (SPA).

- **http-vue-loader:** http-vue-loader ist ein Client-seitiger .vue-Komponentenlader für Vue.js. Es ermöglicht das Laden von .vue-Dateien direkt im Browser, ohne dass ein Build-Prozess erforderlich ist.

- **Axios:** Axios ist ein auf Promises basierender HTTP-Client für das Erstellen von Ajax-/HTTP-Anfragen in Vue.js.

[7]:https://github.com/justinwash/Client-Side-Vue

### Event handling in einer JavaScript Applikation.

Die Verarbeitung von Ereignissen in JavaScript ist ein grundlegender Aspekt bei der Entwicklung interaktiver Webanwendungen. In diesem Artikel werden die Grundlagen des Event Handlings in JavaScript erläutert und wie Event-Handler hinzugefügt werden können.

- **JavaScript-Events:**<sup>[2]</sup>
JavaScript-Events sind Ereignisse, die in Verbindung mit HTML-Elementen auftreten. Wenn JavaScript in HTML-Seiten verwendet wird, kann es auf diese Ereignisse reagieren und entsprechende Aktionen ausführen.

- **HTML-Events:**
Ein HTML-Event kann entweder etwas sein, das vom Browser selbst ausgelöst wird, oder etwas, das ein Benutzer auf der Webseite tut. Beispiele für HTML-Events sind das Laden einer Webseite, Änderungen an Eingabefeldern oder das Klicken auf einen Button.

> **Hinweis:** Hier sind einige Beispiele für HTML-Events:

- Eine HTML-Webseite hat das Laden abgeschlossen
- Ein HTML-Eingabefeld wurde geändert
- Ein HTML-Button wurde angeklickt, Oftmals möchten Sie etwas tun, wenn Ereignisse eintreten.

Um auf HTML-Events zu reagieren, können Event-Handler-Attribute mit JavaScript-Code zu HTML-Elementen hinzugefügt werden.

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

 Alternativ zum Hinzufügen von Event-Handlern direkt in HTML-Attributen können Event-Handler auch mit JavaScript-Code hinzugefügt werden.
 ```javascript
 var button = document.getElementById('myButton');
  button.addEventListener('click', handleClick);
  function handleClick() {
   // Event-Handler-Code hier
   }
   ```

 In diesem Beispiel wird ein Event-Handler für den Klick auf den Button mit der ID "myButton" hinzugefügt. Der Event-Handler ist die Funktion handleClick(), die den entsprechenden Code enthält, der beim Klicken des Buttons ausgeführt werden soll.
 Diese Methode bietet eine klarere Trennung zwischen HTML und JavaScript und ermöglicht eine einfachere Wartung und Erweiterbarkeit des Codes.
 Das Event-Handling in JavaScript ist ein umfangreiches Thema mit vielen weiteren Konzepten und Funktionen. Durch das Verständnis der Grundlagen können Entwickler jedoch schon einmal einen guten Startpunkt für die Verarbeitung von Ereignissen in ihren JavaScript-Anwendungen haben.


[2]:https://www.w3schools.com/js/js_events.asp



#### Unterschiede zwischen ASP.NET und Vue.js in Bezug auf die Eventhandlung

## ASP.NET

ASP.NET ist ein serverseitiges Web framework, das zur Entwicklung von Webanwendungen verwendet wird. Bei der Event Behandlung in ASP.NET wird das Postback-Modell verwendet. Hier sind die grundlegenden Konzepte der Event Behandlung in ASP.NET:

- **Serverseitige Events:** In ASP.NET werden die meisten Events serverseitig behandelt. Das bedeutet, dass der Server die Events empfängt, verarbeitet und die entsprechende Aktion ausführt. Die Events werden durch die Interaktion des Benutzers mit den Websteuerelementen ausgelöst.

- **PostBack-Modell:** Beim Auslösen eines Events wird eine Postback-Anforderung an den Server gesendet. Der Server verarbeitet das Event, führt die erforderlichen Aktionen aus und rendert die aktualisierte Seite zurück zum Client. Dies führt zu einem vollständigen Seitenneuladen und kann die Benutzererfahrung beeinträchtigen.

- **ViewState:** ASP.NET verwendet das ViewState-Konzept, um den Zustand der Seite und der Websteuerelemente zwischen den Postbacks zu speichern. Dadurch können die Websteuerelemente unseren Zustand beibehalten und die Event Behandlung erleichtern.

## Vue.js

Vue.js ist ein clientseitiges JavaScript-Framework zur Entwicklung von Benutzeroberflächen. Bei der Event Behandlung in Vue.js wird ein reaktiver Ansatz verwendet. Hier sind die grundlegenden Konzepte der Event Behandlung in Vue.js:

- **Dom-Events:** Vue.js ermöglicht die direkte Behandlung von DOM-Events in den Vorlagenkomponenten. wir können den `v-on`-Direktiven verwenden, um Events abzuhören und die entsprechenden Methoden aufzurufen.

- **Komponenten basierte Events:** Vue.js ermöglicht die Kommunikation zwischen Komponenten über das Eventbus-System. Komponenten können Events auslösen und andere Komponenten können diese Events abhören und entsprechende Aktionen ausführen. Dadurch wird eine lose Kopplung zwischen den Komponenten erreicht.

- **Reaktivität:** Vue.js bietet eine reaktive Datenbindung, bei der Änderungen an den Daten automatisch in der Benutzeroberfläche reflektiert werden. Dies ermöglicht eine effiziente und reibungslose Aktualisierung der Benutzeroberfläche, ohne die gesamte Seite neu zu laden.
  


### Komponenten Konzept von Vue.js.

Das Komponenten Konzept von Vue.js ermöglicht die Entwicklung von wiederverwendbaren und modularen UI-Komponenten in JavaScript.Komponenten sind eigenständige und isolierte Teile einer Webanwendung, die unsere eigene Logik, Zustand und Darstellung haben können.Mit Vue.js können wir benutzerdefinierte Komponenten erstellen, indem wir das `Vue.component()`-Funktion verwenden oder Komponenten Objekte erstellen, die auf der Vue-Komponentenoption basieren. Die Views und Components sind vue Dateien und haben eine bestimmte Syntax. Um sie besser bearbeiten zu können, können wir die Extension `Vetur` in VS Code installieren<sup>[3]</sup>. Der Dateinamen soll aus mindestens 2 Wörtern bestehen (NewsContent, LoginForm, ...) um Verwechslungen mit HTML Elementen zu vermeiden.So eine Datei besteht aus mehreren Teilen: Einem Template für die HTML Darstellung, einem Style Block und einem Script Block. Du kannst die folgende Vorlage in eine neu erstellte vue Datei kopiere, um schneller arbeiten zu können:. Eine Vue-Komponente besteht aus drei Hauptteilen:
1. Template: Das Template definiert die visuelle Darstellung der Komponente. Es enthält HTML-Code mit Vue-Direktiven, die Daten binden und die Logik der Komponente steuern.
  Im Template-Bereich gibt es spezielle Attribute für deine HTML-Elemente, die von Vue gerendert werden<sup>[3]</sup>:
   - `{{ variable }}`: Gibt den Inhalt der Variablen aus, die in `data` oder `props` definiert wurde.
   - `v-if`: Blendet das HTML-Element nur ein, wenn die angegebene Bedingung wahr ist. Kann in Zusammenhang mit `v-else` definiert  werden.
   - `v-for`: Rendert das HTML-Element für jeden Eintrag im Array. Wird in Zusammenarbeit mit `v-bind:key` verwendet.
   - `v-on`: Event handler, die auf Methoden in `methods` verweisen. Beispiel: `v-on:click="method()"`.
   - `v-bind`: Attributs werte, die von `data` gelesen werden sollen. Beispiel: `v-bind:value`.
   - `v-bind:class`: Speziell für das bedingte Aktivieren von CSS-Klassen. Siehe [Binding HTML](https://vuejs.org/guide/essentials/class-and-style.html)Classes.
   - `v-model`: Für Formularfelder. Werte werden in ein Property in `data` geschrieben und von dort gelesen. Beispiel: `v-model=model.myFormField`.

1. Script: Das Script enthält die Logik und den Zustand der Komponente. Hier können wir Daten definieren, Methoden erstellen, Lebenszyklus hooks nutzen und mit externen Ressourcen interagieren.
   
2. Style: Der Style-Bereich enthält CSS-Regeln, die spezifisch für die Komponente sind. Hier können wir das Aussehen der Komponente anpassen, indem wir Klassen, IDs oder andere Selektoren verwenden.
Das Komponenten Konzept ermöglicht es, Komponenten hierarchisch zu verschachteln und Daten und Events zwischen den Komponenten zu übertragen. Dies fördert die Wiederverwendbarkeit und Modularität, da Komponenten unabhängig voneinander entwickelt, getestet und wiederverwendet werden können.

Hier ist ein einfaches Beispiel für eine Vue.js-Komponente:

> **Hinweis:** Der folgende Codeausschnitt zeigt eine einfache Vue.js-Komponente. Das Template definiert eine Überschrift und einen Button, die auf eine Daten variable und eine Methode der Komponente zugreifen.
 ```javascript
<script setup>
    // Imports
</script>
<template>
    <!-- A template must have one (1) root element. Usually a div with the class name
    of your component -->
    <div class="componentName">
       <!-- Your html -->
    </div>
</template>
<style scoped>
    /* Your css */
</style>
<script>
export default {
    props: {
        // Your parameters from the caller. Example: id : Number
    },
    data() {
        return {
            // Your data properties
        };
    },
    mounted() {
        // Your initialization code. Maybe async ( async mounted() {...} )
    },
    methods: {
        // Your methods
    },
    computed: {
        // Your computed properties
    }
};
</script>
```
Weitere Informationen sind auf der Seite [Template Lifecycle](https://vuejs.org/guide/essentials/lifecycle.html) abrufbar.

[3]:https://github.com/schletz/Wmc/blob/171ff1e057b2db672d9c638305cf5e1053e653d0/32_Vuejs/06_VuejsClient.md

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

Der Einsatz von fertigen Komponenten_Bibliotheken wie PrimeVue ermöglicht es uns, auf bewährte Lösungen zurückzugreifen, Zeit bei der Entwicklung zu sparen und eine konsistente und ansprechende Benutzeroberfläche zu erstellen.

## Verwendung der PrimeVue Tree-Komponente

In unserem spezifischen Projekt konzentrieren wir uns hauptsächlich auf die Tree-Komponente von PrimeVue<sup>[4]</sup>. Die Tree-Komponente ist besonders nützlich, wenn wir hierarchische Daten in einer strukturierten Weise anzeigen möchten, ähnlich wie wir es in ASP.NET getan haben. Diese Komponente bietet eine Vielzahl von Funktionen, darunter das Ein- und Ausklappen von Zweigen, die Auswahl von Knoten, Drag-and-Drop-Interaktionen und vieles mehr.

Die PrimeVue Tree-Komponente ermöglicht es uns, eine verschachtelte Baumstruktur zu erstellen, indem wir ein Array von Knotenobjekten bereitstellen. Jeder Knoten in diesem Array repräsentiert einen Zweig im Baum und kann weitere Knotenobjekte als Kinder enthalten.

[4]:https://primevue.org/installation 

### Beispiel für die Verwendung der PrimeVue Tree-Komponente

Gehen wir durch ein einfaches Beispiel, wie wir die PrimeVue Tree-Komponente<sup>[5]</sup> in unserer Vue.js-Anwendung verwenden können:

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
   
5. Anstatt die Baumknoten direkt in unseren Daten zu definieren, haben wir eine Methode `getCalls()` in `CallService` implementiert, die einen dynamischen Baum aus unseren Anrufdaten erstellt:

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

[5]:https://primevue.org/tree/

## Services in der clientseitigen Applikation (5 Seiten)
### Die Rolle von Services in Vue.js

In Vue.js spielen Services eine wichtige Rolle, um die Funktionalität, Wartbarkeit und Lesbarkeit der Anwendung zu verbessern. Services ermöglichen es uns, unseren Code zu organisieren, indem sie bestimmte Funktionen oder Features kapseln, die über verschiedene Komponenten der Anwendung hinweg genutzt werden können.

Ein gutes Beispiel für die Anwendung von Services in Vue.js ist die Verwaltung von API-Aufrufen oder die Kapselung von Geschäftslogik, die mehrmals in der Anwendung wiederverwendet wird. In unserem Fall haben wir einen `CallService` erstellt, um Anrufe und deren zugehörige Daten zu verwalten.

Es ist auch wichtig, den Service korrekt in die Vue.js-Anwendung zu integrieren. Dies kann durch das Erstellen einer Service-Instanz und deren Registrierung in der Vue-Komponente erfolgen. Dadurch wird sichergestellt, dass der Service in der gesamten Anwendung verwendet werden kann und seine Funktionen den Komponenten zur Verfügung stehen.

Die Verwendung von Services in Vue.js bringt mehrere Vorteile mit sich:

- **Wiederverwendbarkeit**: Durch die Kapselung von Funktionen oder Logik in einem Service können wir diese an verschiedenen Stellen in der Anwendung wiederverwenden, ohne den Code duplizieren zu müssen.

- **Separation von Concerns**: Services ermöglichen eine klare Trennung der Verantwortlichkeiten in der Anwendung. Die Komponenten können sich auf die Darstellung und Interaktion mit der Benutzeroberfläche konzentrieren, während die Services die Geschäftslogik und den Datenzugriff handhaben.

- **Testbarkeit**: Services können leicht isoliert getestet werden, da sie unabhängig von den Komponenten funktionieren. Dadurch wird die Testbarkeit der Anwendung verbessert.

- **Lesbarkeit und Wartbarkeit**: Durch die Verwendung von Services wird der Code strukturierter und leichter lesbar. Änderungen oder Erweiterungen an der Funktionalität können einfach in den entsprechenden Service implementiert werden, ohne den gesamten Code der Komponenten zu ändern.

Es gibt verschiedene Möglichkeiten, Services in Vue.js zu implementieren, je nach den Anforderungen und der Komplexität der Anwendung. Einige Entwickler bevorzugen die Verwendung von JavaScript-Klassen, während andere einfache JavaScript-Objekte als Services nutzen. Die Wahl der Implementierung hängt von den spezifischen Anforderungen der Anwendung ab.

Um weitere Informationen und Beispiele zur Verwendung von Services in Vue.js zu erhalten, können Sie die offizielle Vue.js-Dokumentation und andere qualitativ hochwertige Online-Ressourcen konsultieren.

Referenzen:
- Vue.js Dokumentation: [https://vuejs.org/v2/guide/](https://vuejs.org/v2/guide/)
- Vue.js Style Guide: [https://vuejs.org/v2/style-guide/](https://vuejs.org/v2/style-guide/)
- "Vue.js 2 Cookbook" von Andrea Passaglia (Packt Publishing, 2017)
- "Mastering Vue.js" von Olga Filipova (Packt Publishing, 2017)


### Datenstruktur zum Speichern der Call Objekte.

Es ist wichtig, eine saubere und strukturierte Datenstruktur zu haben, um die Call-Objekte zu speichern. Eine gängige Methode ist die Verwendung eines Arrays oder eines Objekts, um die verschiedenen Call-Objekte zu verwalten. Dies ermöglicht es uns, leicht auf die einzelnen Calls zuzugreifen, sie zu bearbeiten oder zu löschen.

Zusätzlich zur Speicherung der Call-Objekte kann der Service auch Methoden enthalten, um die Daten abzurufen, zu aktualisieren oder neue Calls hinzuzufügen. Diese Methoden können dann von den verschiedenen Komponenten der Anwendung aufgerufen werden, um auf die Call-Daten zuzugreifen und sie zu manipulieren.

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

In unserer Diplomarbeit konzentrieren wir uns auf die dynamische Implementierung von JSON-Daten, insbesondere für die Funktionen der Aktionen, die von externen Ressourcen stammen. Hierzu haben wir zuerst eine `JsonService.js` erstellt, um dynamisch eine JSON-Datei von einer Website abzurufen.

In der `JsonService.js` versuchen wir, mittels des `axios`-Pakets eine Anfrage an die bereitgestellte URL zu senden, um die JSON-Daten abzurufen. 

```javascript
// import axios from 'axios';
// for local testing
import actions from "./serverdesigneroutputactions";

export default async function () {
  // try {
  //   const response = await axios.get('https://www.dox42.com/modules/serverdesigneroutputactions.json');
  //   return response.data;
  // } catch (error) {
  //   console.error('Error fetching JSON schema:', error);
  //   throw error;
  // }
  return actions.actions;
} 
```
Da wir jedoch keinen Zugriff auf den JSON-Dateilink des Unternehmens hatten, haben wir die JSON-Datei manuell in unsere lokale Umgebung heruntergeladen. Als Alternative für die spätere Verwendung haben wir die Möglichkeit zur dynamischen Abfrage als Kommentar im Code hinterlegt.

Anschließend haben wir in unserer Vue.js-Klasse `CallsView` im `setup`-Skript den Json-Dienst als `fetchJSONSchema` importiert.

```javascript
import fetchJSONSchema from "../services/jsonActionService"
```

Wir setzten diesen Dienst in der mounted-Methode ein, um die in der JSON-Datei definierten Aktionen abzurufen und sowohl im `CallsService` als auch in der lokalen Zustands variable der `CallsView`-Klasse zu speichern.

```javascript
async mounted() {
    const actions = await fetchJSONSchema();
    console.table(actions);
    CallService.actions = actions;
    this.actions = actions;
}       
```
Durch diese Implementierung können wir dynamisch auf die Aktionen aus der JSON-Datei zugreifen und diese in unserer Vue.js-Anwendung verwenden. Diese Methode bietet Flexibilität und erleichtert die Wartung, da wir die JSON-Datei einfach aktualisieren können, um neue Aktionen hinzuzufügen oder bestehende zu ändern. Des Weiteren ermöglicht diese Methode das dynamische Rendering von Layouts basierend auf den in der JSON-Datei definierten Daten.

Nach dem Speichern der JSON-Objekte in unseren lokalen Variablen haben wir eine `ActionComponent` erstellt, um das Objekt mit der korrekten Struktur zu lesen.

```vue
<template>
    .....
        <div v-if="actions.length > 0" class="ActionList">
          <div class="row" v-for="(action, index) in actions" :key="index">
            <div class="column" v-for="(param, paramIndex) in action.parameters" :key="paramIndex">
                <div class="label">{{ param.name }}</div>
          ..
                  <input v-model="param.value" v-on:change="$emit('change')" />
          ..
   .....
</template>
```
Diese Komponente verarbeitet die "actions" als Eigenschaft und rendert sie dynamisch im Template. Jede Aktion besteht aus mehreren Parametern, die ebenfalls dynamisch gerendert werden. Jeder Parameter besteht aus einem Namen und einem Wert, der in einem Eingabefeld dargestellt wird. Änderungen an diesen Werten lösen ein "change"-Ereignis aus, das an die übergeordnete Komponente gesendet wird.

Wir haben diese ActionComponent in unsere CallsView-Klasse importiert und sie in unserem Template eingebunden.
```javascript
<ActionComponent v-if="selectedAction !== null"
  v-bind:actions="selectedAction.actions">
</ActionComponent>
```
In diesem Ausschnitt binden wir die Aktionen der ausgewählten Aktion an die ActionComponent. Wenn eine Aktion ausgewählt ist (selectedAction !== null), wird die ActionComponent gerendert und die Aktionen der ausgewählten Aktion werden übergeben.

Zudem haben wir in unserer data-Methode ein Array namens actions hinzugefügt, um die Aktionen zu speichern.
```javascript
data() {
  return {
    actions: [],
    //...
  };
}
```
Um eine Aktion in unseren `Tree` hinzuzufügen, haben wir in unserer CallService-Klasse eine Methode namens `addAction` implementiert. Diese Methode sucht nach dem entsprechenden `Call` basierend auf dem Namen und fügt die übergebene `Aktion` hinzu.

In der `CallsView` haben wir eine Methode implementiert, um die Aktionen mit dem Name des Actions zu unterscheiden. Hier ist ein Beispiel, wie dies aussehen,In diesem Codeausschnitt suchen wir die SharePoint-Aktion in den verfügbaren Aktionen (dies wird durch die Methode find erreicht, die das erste Element in dem Array zurückgibt, das die Testfunktion erfüllt). Wenn die Aktion gefunden wird, rufen wir die Methode `addAction` auf und fügen die `Aktion` zum ausgewählten `Call` hinzu.

```javascript
addSharepointAction(call) {
  const spAction = this.actions.find(action => action.name === "SharepointAction");
  if (spAction) {
    CallService.addAction(call.data, spAction);
    console.log("Sharepoint action added to call:", call.data.name);
  } else {
    console.error("Could not find Sharepoint action in JSON file");
  }
},
```




