# Individuelle Themenstellung

## Windows Forms (8 Seiten)

### Was ist Windows Forms?

Windows Forms (WinForms) ist eine grafische Benutzeroberflächenbibliothek, die erstmals mit dem .NET Framework 1.0 veröffentlicht, das im Februar 2002 eingeführt wurde. 

Es wird verwendet, um Desktopanwendungen für das Windows-Betriebssystem zu erstellen.

Windows Forms stellt eine breite Palette von Steuerelementen zur Verfügung, wie z.B. Buttons, Textboxen, Dropdown-Menüs und weitere, die auf einem Formular platziert und dann programmiert werden können, um spezifische Funktionen auszuführen. 
Mit Windows Forms können Entwickler auch Dialogboxen, Menüs und Toolbars erstellen.

Windows Forms-Anwendungen werden in einer ereignisgesteuerten Programmierweise geschrieben. 
Das bedeutet, dass der Code auf Benutzerinteraktionen reagiert, wie z.B. Mausklicks oder Tastendrücke.

Obwohl Windows Forms seit mehreren Jahren eine beliebte Wahl für die Erstellung von Windows-Desktopanwendungen ist, hat Microsoft eine neuere Technologie namens Windows Presentation Foundation (WPF) eingeführt, die mehr Flexibilität und die Möglichkeit für anspruchsvollere Grafiken bietet. 
Zudem wird seit einigen Jahren die plattformübergreifende .NET-Core- bzw. .NET-5/6-Technologie von Microsoft intensiv weiterentwickelt, die unter anderem mit dem UI-Framework Blazor auch moderne Webanwendungen ermöglicht. 
Dennoch wird Windows Forms immer noch in vielen Anwendungsfällen verwendet, insbesondere in Geschäftsanwendungen und bei bestehenden Projekten.


### Eventhandling in Windows Forms.

Eventhandling in Windows Forms basiert auf dem Konzept des Delegierens und Ereignissen (Events). 
Wenn ein bestimmtes Ereignis, wie z.B. ein Mausklick, auftritt, löst das entsprechende Steuerelement (Control) ein Ereignis aus, das dann von einer Ereignisbehandlungsmethode (Event Handler) verarbeitet wird, die von Ihnen definiert wird.

Hier ist ein einfaches Beispiel, wie man einen Button in Windows Forms erstellen und ein Ereignis behandeln können. 
Dieses Beispiel wird in C# geschrieben:

```csharp
using System;
using System.Windows.Forms;

public class MyForm : Form
{
    Button button1;

    public MyForm()
    {
        button1 = new Button();
        button1.Text = "Click me!";
        button1.Click += new EventHandler(button1_Click);
        
        Controls.Add(button1);
    }

    private void button1_Click(object sender, EventArgs e)
    {
        MessageBox.Show("Button clicked!");
    }

    [STAThread]
    static void Main()
    {
        Application.EnableVisualStyles();
        Application.Run(new MyForm());
    }
}

```

In diesem Beispiel wird ein Button button1 erstellt. Das Ereignis Click des Buttons wird dann mit der Methode button1_Click verknüpft, indem wir einen neuen EventHandler hinzufügen. 
Der EventHandler nimmt zwei Parameter: den Sender des Ereignisses (in diesem Fall der Button selbst) und ein EventArgs-Objekt, das weitere Informationen über das Ereignis enthält (für ein Click-Ereignis sind dies in der Regel keine).

Die Methode button1_Click wird aufgerufen, wenn das Click-Ereignis des Buttons ausgelöst wird, also wenn der Benutzer auf den Button klickt. 
In der Ereignisbehandlungsmethode zeigen wir dann eine Nachrichtenbox an, die "Button clicked!" ausgibt.

Der Code in der Main Methode stellt sicher, dass die Anwendung ausgeführt wird und das Formular angezeigt wird, wenn das Programm gestartet wird.

Die [STAThread]-Annotation in Windows Forms Anwendungen wird verwendet, um anzugeben, dass das COM-Threading-Modell der Anwendung ein Single-Threaded Apartment (STA) ist. Diese Anweisung muss am Einstiegspunkt jeder Windows Forms-Anwendung vorhanden sein. Die Anweisung wird tatsächlich von der .NET-Laufzeit beim Starten der Anwendung gelesen, um zu entscheiden, wie die COM-Threading-Umgebung initialisiert werden soll.

### GUI Elemente in Windows Forms.

Windows Forms bietet eine Vielzahl von GUI-Elementen, die auch als Steuerelemente oder Controls bekannt sind. Hier sind einige Beispiele, die im bestehenden Projekt verwendet wurden. 

1. Button: Ein klickbares Steuerelement, das eine Aktion auslöst, wenn es angeklickt wird.
2. Label: Ein Steuerelement, das dazu dient, Text auf der Benutzeroberfläche anzuzeigen.
3. TextBox: Erlaubt dem Benutzer, Text einzugeben.
4. Panel: Ein Container, in dem andere Steuerelemente platziert werden können.
5. DataGridView: Zeigt Daten in tabellarischer Form an.
6. TreeView: Zeigt hierarchische Daten in einer Struktur mit Knoten an, die expandiert und              zusammengeklappt werden können.

## Erstellung eine GUI Mockups (8 Seiten)

### Warum ein Mockup?

TODO

### Möglichkeiten von Adobe XD.

TODO

## Nutzung von Versionsverwaltungssystemem in der Entwicklung (5 Seiten)

### Kommunikation mit dem Auftraggeber.

TODO

### Integration von Jira und BitBucket.

TODO

### Issues und Bugtrack im konkreten Projekt.

TODO
