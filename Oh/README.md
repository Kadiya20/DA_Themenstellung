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

Quelle: https://chat.openai.com/?model=gpt-4, abgerufen am 26.5.2023

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

In diesem Beispiel wird ein Button button1 erstellt. Das Ereignis Click des Buttons wird dann mit der Methode *button1_Click* verknüpft, indem wir einen neuen EventHandler hinzufügen. 
Der EventHandler nimmt zwei Parameter: den Sender des Ereignisses (in diesem Fall der Button selbst) und ein EventArgs-Objekt, das weitere Informationen über das Ereignis enthält (für ein Click-Ereignis sind dies in der Regel keine).

Die Methode *button1_Click* wird aufgerufen, wenn das Click-Ereignis des Buttons ausgelöst wird, also wenn der Benutzer auf den Button klickt. 
In der Ereignisbehandlungsmethode zeigen wir dann eine Nachrichtenbox an, die "Button clicked!" ausgibt.

Der Code in der Main Methode stellt sicher, dass die Anwendung ausgeführt wird und das Formular angezeigt wird, wenn das Programm gestartet wird.

Quelle: https://chat.openai.com/?model=gpt-4, abgerufen am 26.5.2023

### Die Parameter object sender und EventArgs e

**object sender:** Dieser Parameter enthält eine Referenz auf das Objekt, das das Ereignis ausgelöst hat. Beispielsweise, wenn ein Button angeklickt wurde und dadurch ein Click-Ereignis ausgelöst hat, dann ist das sender-Objekt eine Referenz auf diesen speziellen Button. Es wird üblicherweise zu dem entsprechenden Typ gecastet, um auf spezifische Eigenschaften oder Methoden des auslösenden Objekts zugreifen zu können.

**EventArgs e:** Dieser Parameter enthält zusätzliche Ereignis-spezifische Informationen. Für viele Ereignisse, einschließlich der meisten UI-Events wie Click, gibt es nicht wirklich zusätzliche Informationen, die übermittelt werden müssen, und so ist der EventArgs-Parameter oft einfach ein leerer EventArgs-Wert oder null. Bei einigen anderen Ereignissen, zum Beispiel MouseMove, enthält der EventArgs-Parameter nützliche Informationen. In diesem Fall wäre es eigentlich ein Objekt von einem Untertyp von EventArgs, wie MouseEventArgs, und es enthält Informationen wie die Position der Maus.

**[STAThread]-Annotation**
Die [STAThread]-Annotation in Windows Forms Anwendungen wird verwendet, um anzugeben, dass das COM-Threading-Modell der Anwendung ein Single-Threaded Apartment (STA) ist.<sup>[2]</sup> Diese Anweisung muss am Einstiegspunkt jeder Windows Forms-Anwendung vorhanden sein. Die Anweisung wird tatsächlich von der .NET-Laufzeit beim Starten der Anwendung gelesen, um zu entscheiden, wie die COM-Threading-Umgebung initialisiert werden soll.

[2]: http://learn.microsoft.com/en-us/dotnet/api/, abgerufen am 26.5.2023

### GUI Elemente in Windows Forms.

Windows Forms bietet eine Vielzahl von GUI-Elementen, die auch als Steuerelemente oder Controls bekannt sind. Hier sind einige Beispiele, die im bestehenden Projekt verwendet wurden. 

1. Button: Ein klickbares Steuerelement, das eine Aktion auslöst, wenn es angeklickt wird.
   
```csharp
public class Button : System.Windows.Forms.ButtonBase, System.Windows.Forms.IButtonControl

private void InitializeMyButton()
 {
    // Create and initialize a Button.
    Button button1 = new Button();
 
    // Set the button to return a value of OK when clicked.
    button1.DialogResult = DialogResult.OK;
 
    // Add the button to the form.
    Controls.Add(button1);
 }
```
2. Label: Ein Steuerelement, das dazu dient, Text auf der Benutzeroberfläche anzuzeigen.
```csharp
[System.ComponentModel.DefaultBindingProperty("Text")]
public class Label : System.Windows.Forms.Control, System.Windows.Forms.Automation.IAutomationLiveRegion

public void CreateMyLabel()
{
   // Create an instance of a Label.
   Label label1 = new Label();

   // Set the border to a three-dimensional border.
   label1.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;
   // Set the ImageList to use for displaying an image.
   label1.ImageList = imageList1;
   // Use the second image in imageList1.
   label1.ImageIndex = 1;
   // Align the image to the top left corner.
   label1.ImageAlign = ContentAlignment.TopLeft;

   // Specify that the text can display mnemonic characters.
   label1.UseMnemonic = true;
   // Set the text of the control and specify a mnemonic character.
   label1.Text = "First &Name:";
   
   /* Set the size of the control based on the PreferredHeight and PreferredWidth values. */
   label1.Size = new Size (label1.PreferredWidth, label1.PreferredHeight);

   //...Code to add the control to the form...
}
```
3. TextBox: Erlaubt dem Benutzer, Text einzugeben.
```csharp
public class TextBox : System.Windows.Forms.TextBoxBase

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;

public class Form1 : Form
{
    private TextBox textBox1;

    public Form1()
    {
        InitializeComponent();
    }

    private void InitializeComponent()
    {
        this.textBox1 = new System.Windows.Forms.TextBox();
        this.SuspendLayout();
        // 
        // textBox1
        // 
        this.textBox1.AcceptsReturn = true;
        this.textBox1.AcceptsTab = true;
        this.textBox1.Dock = System.Windows.Forms.DockStyle.Fill;
        this.textBox1.Multiline = true;
        this.textBox1.ScrollBars = System.Windows.Forms.ScrollBars.Vertical;
        // 
        // Form1
        // 
        this.ClientSize = new System.Drawing.Size(284, 264);
        this.Controls.Add(this.textBox1);
        this.Text = "TextBox Example";
        this.ResumeLayout(false);
        this.PerformLayout();
    }

    [STAThread]
    static void Main()
    {
        Application.EnableVisualStyles();
        Application.SetCompatibleTextRenderingDefault(false);
        Application.Run(new Form1());
    }
}
```
4. Panel: Ein Container, in dem andere Steuerelemente platziert werden können.
```csharp
[System.Windows.Forms.Docking(System.Windows.Forms.DockingBehavior.Ask)]
public class Panel : System.Windows.Forms.ScrollableControl

public void CreateMyPanel()
{
   Panel panel1 = new Panel();
   TextBox textBox1 = new TextBox();
   Label label1 = new Label();
   
   // Initialize the Panel control.
   panel1.Location = new Point(56,72);
   panel1.Size = new Size(264, 152);
   // Set the Borderstyle for the Panel to three-dimensional.
   panel1.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;

   // Initialize the Label and TextBox controls.
   label1.Location = new Point(16,16);
   label1.Text = "label1";
   label1.Size = new Size(104, 16);
   textBox1.Location = new Point(16,32);
   textBox1.Text = "";
   textBox1.Size = new Size(152, 20);

   // Add the Panel control to the form.
   this.Controls.Add(panel1);
   // Add the Label and TextBox controls to the Panel.
   panel1.Controls.Add(label1);
   panel1.Controls.Add(textBox1);
}
```
5. DataGridView: Zeigt Daten in tabellarischer Form an.
```csharp
using System;
using System.Windows.Forms;
using System.Data;

namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Create a new DataTable instance.
            DataTable dt = new DataTable();

            // Add columns to the DataTable.
            dt.Columns.Add("UserID");
            dt.Columns.Add("UserName");
            dt.Columns.Add("UserEmail");

            // Add rows to the DataTable.
            dt.Rows.Add(1, "John Doe", "john.doe@example.com");
            dt.Rows.Add(2, "Jane Doe", "jane.doe@example.com");
            dt.Rows.Add(3, "Robert Smith", "robert.smith@example.com");

            // Assign the DataTable as the DataSource for the DataGridView.
            dataGridView1.DataSource = dt;
        }
    }
}
```


6. TreeView: Zeigt hierarchische Daten in einer Struktur mit Knoten an, die expandiert und              zusammengeklappt werden können.
```csharp
using System;
using System.Windows.Forms;

namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Create root node
            TreeNode rootNode = new TreeNode("Root Node");
            treeView1.Nodes.Add(rootNode);

            // Create child nodes
            TreeNode childNode1 = new TreeNode("Child Node 1");
            TreeNode childNode2 = new TreeNode("Child Node 2");

            // Add child nodes to root node
            rootNode.Nodes.Add(childNode1);
            rootNode.Nodes.Add(childNode2);

            // Create subchild nodes
            TreeNode subChildNode1 = new TreeNode("Subchild Node 1");
            TreeNode subChildNode2 = new TreeNode("Subchild Node 2");

            // Add subchild nodes to child node 1
            childNode1.Nodes.Add(subChildNode1);
            childNode1.Nodes.Add(subChildNode2);
        }
    }
}
```

***Quelle*** 

Microsoft https://learn.microsoft.com/en-us/dotnet/api/
ChatGPT https://chat.openai.com/?model=gpt-4, abgerufen am 26.5.2023

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
