# Individuelle Themenstellung
EINLEITUNG INDIVIDUELLER THEMENSTELLUNG
Diese Arbeit untersucht verschiedene Aspekte der Benutzeroberflächenentwicklung und der Implementierung von JavaScript-Applikationen. Im Fokus stehen die Unterschiede zwischen Windows Forms und ASP WebForms, die Verwendung von Vue.js als clientseitigem Framework, das Eventhandling in JavaScript-Applikationen, das Komponentenkonzept von Vue.js, der Einsatz von fertigen Komponenten von PrimeVue und die Verwendung von Services in clientseitigen Applikationen.
Die Unterschiede zwischen Windows Forms und ASP WebForms werden analysiert und ihre Vor- und Nachteile untersucht. Vue.js wird als leistungsstarkes clientseitiges Framework betrachtet, das ein effizientes Komponentenkonzept für wiederverwendbare UI-Komponenten bietet. Die Verwendung von PrimeVue-Komponenten zur Beschleunigung der Entwicklung und die Implementierung von Eventhandling in JavaScript-Applikationen werden behandelt. Außerdem werden Services in clientseitigen Applikationen untersucht, insbesondere die Datenstruktur zum Speichern von Call-Objekten und die dynamische Generierung des Layouts basierend auf JSON-Daten.

## Unterschiede zwischen Windows Forms und ASP WebForms (5 Seiten)

1. Plattformunabhängigkeit
<span style="color: blue">Windows Forms:</span> WF-Anwendungen sind speziell für Windows-Betriebssysteme entwickelt worden und laufen daher nur auf Windows-Plattformen.
<span style="color: green">ASP.NET-Webforms:</span> WF-Anwendungen sind für Webbrowser konzipiert und können auf verschiedenen Betriebssystemen laufen, solange ein kompatibler Webbrowser vorhanden ist.
<span style="color: purple">.NET MAUI:</span> Im Gegensatz zu Windows Forms und ASP.NET ist .NET MAUI eine plattformübergreifende Technologie, die es ermöglicht, Anwendungen für verschiedene Betriebssysteme wie Windows, macOS, iOS und Android zu entwickeln.
2. UI-Framework
<span style="color: blue">Windows Forms:</span> WF verwendet ein Windows-spezifisches UI-Framework, das speziell für die Entwicklung von Desktopanwendungen ausgelegt ist.
<span style="color: green">ASP.NET-Webforms:</span> WF verwendet ebenfalls ein Windows-spezifisches UI-Framework, das jedoch für die Erstellung von Webanwendungen optimiert ist.
<span style="color: purple">.NET MAUI:</span> .NET MAUI verwendet ein modernes plattformübergreifendes UI-Framework, das es Entwicklern ermöglicht, ein einheitliches Benutzererlebnis auf verschiedenen Plattformen zu erstellen.
3. Projektstruktur
<span style="color: blue">Windows Forms:</span> WF-Anwendungen haben eine einheitliche Projektstruktur mit einer einzigen Projektdatei (.csproj), die alle Ressourcen und Code-Dateien enthält.
<span style="color: green">ASP.NET-Webforms:</span> WF-Anwendungen bestehen aus einem Webprojekt mit einer komplexeren Struktur, die spezifische Ordner für Seiten, Steuerelemente, Skripte, Stylesheets usw. enthält.
<span style="color: purple">.NET MAUI:</span> .NET MAUI-Anwendungen haben ebenfalls eine einheitliche Projektstruktur, die sich jedoch von den anderen beiden unterscheidet. Hier werden gemeinsame Code- und Ressourcenprojekte verwendet, um plattformübergreifende Logik und UI-Komponenten zu teilen.
4. Datenbindung
<span style="color: blue">Windows Forms:</span> WF bietet eine einfache Datenbindung zwischen UI-Elementen und Datenquellen auf dem Desktop.
<span style="color: green">ASP.NET-Webforms:</span> WF ermöglicht die Datenbindung zwischen UI-Elementen und Datenquellen auf Webseiten.
<span style="color: purple">.NET MAUI:</span> .NET MAUI bietet erweiterte Datenbindungsfunktionen für plattformübergreifende Anwendungen, einschließlich der Unterstützung von MVVM (Model-View-ViewModel)-Architektur.

Beispiele für aufgetretene Probleme während des Projekts
Während des Projekts sind wir auf verschiedene Herausforderungen gestoßen. Hier sind einige Beispiele für die aufgetretenen Probleme und wie wir sie gelöst haben:

1. Unterschiede in der Verwendung von MessageBox 
     MessageBox-Äquivalent in ASP.NET
     Beim Implementieren des ASP.NET Frameworks stießen wir auf das Problem, dass die MessageBox-Funktion, die in Windows Forms vorhanden ist, in ASP.NET nicht verfügbar ist. Stattdessen mussten wir eine ähnliche Funktion finden, um Benachrichtigungen anzuzeigen. Hierfür haben wir JavaScripts Alert-Funktion verwendet, um eine Modalfenster-ähnliche Benachrichtigung anzuzeigen.
     Lösung: Verwendung von JavaScript alert() und alternativen Ansätzen
     <script>
        alert("Diese Aktion war erfolgreich!");
     </script>

2. Unterschiede in der Konsolenausgabe zwischen Windows Forms und ASP.NET
     ein weiterer Unterschied besteht darin, dass die Console.Write-Funktion in Windows Forms vorhanden ist, jedoch in ASP.NET durch Response.Write ersetzt werden muss.
     Lösung: Verwendung von Response.Write in ASP.NET
     Um das Problem zu lösen, wurde Response.Write anstelle von Console.Write verwendet, um Text in die HTTP-Antwort auszugeben. Beispiel:
     // Windows Forms
         Console.Write("Hello, world!");

     // ASP.NET
         Response.Write("Hello, world!");

3. Unterschiede zwischen DataGridview in Windows Forms und GridView in ASP.NET
     Ein weiterer Unterschied besteht darin, dass in Windows Forms die DataGridview verwendet wird, während in ASP.NET die GridView zum Einsatz kommt. In ASP.NET ist es erforderlich, die Datenquelle festzulegen und den Databind-Vorgang durchzuführen.
     Lösung: Definition der Datenquelle und Databind in ASP.NET GridView
     Um das Problem zu lösen, wurde in ASP.NET die DataSource-Eigenschaft des GridView festgelegt, um die Datenquelle anzugeben, und dann der Databind-Vorgang durchgeführt, um die Daten an das GridView zu binden.
     Beispiel: 
     // ASP.NET
      ![Gridview](/Ainiwaerjiang/img/GridView.png)
       

4. Unterschiede in der Verwendung von Tag Properties in ASP.NET
     Ein weiterer Unterschied zwischen Windows Forms und ASP.NET betraf die Verwendung von Tag-Eigenschaften. In Windows Forms ermöglicht die Tag-Eigenschaft das Zuweisen von zusätzlichen Informationen oder Objekten zu einem Steuerelement. Dies ist besonders nützlich, um das ausgewählte oder bearbeitete Objekt in einem Treeview zu identifizieren.Da ASP.NET Webanwendungen keine direkte Tag-Eigenschaft bieten, mussten wir eine alternative Lösung finden. Wir haben eine Hilfsklasse erstellt und die Informationen über das ausgewählte Objekt in einem JSON gespeichert. Mithilfe eines JsonParsers konnten wir das Objekt in ein JSON umwandeln und speichern. Hier ist ein Indem wir eine Hilfsklasse erstellt und die JSON-Konvertierung verwendet haben, konnten wir die Funktionalität der Tag-Eigenschaft in ASP.NET Webanwendungen replizieren.
     //Win-Form
     ![WindowsForm](/Ainiwaerjiang/img/winForm_TagBsp.png)
     ![WindowsForm](/Ainiwaerjiang/img/winForm_TagBsp2.png)
     //Web-Form
     ![WebForm](/Ainiwaerjiang/img/webForm_helperKlass.png)
     ![WebForm](/Ainiwaerjiang/img/webForm_Addcall.png)
     ![WebForm](/Ainiwaerjiang/img/webForm_deletecall.png)



## Vue.js als clientseitiges Framework. (10 Seiten)

### Eventhandling in einer JavaScript Applikation.

TODO

### Komponentenkonzept von Vue.js.

TODO

### Einsatz fertiger Komponenten von PrimeVue.

TODO

## Services in der clientseitigen Applikation (5 Seiten)

### Datenstruktur zum Speichern der Call Objekte.

TODO

### Dynamische Generierung des Layout auf Basis von JSON Daten.

TODO
