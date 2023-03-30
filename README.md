# C#-Homework

```csharp
using System;
using System.Linq;
using System.Windows.Forms;
using static System.Windows.Forms.VisualStyles.VisualStyleElement;

namespace WindowsFormsApplication
{
    public partial class Form1 : Form
    {
        private int[] arr = { 848, 239, 736, 612, 969, 896, 976, 457, 266, 516, 488, 350, 323, 204, 969 };

        public Form1()
        {
            InitializeComponent();
            PrintArray();
        }
        private void PrintArray()
        {
            // Выводим исходный массив в TextBox1
            textBox1.Text = string.Join(" ", arr.Select(x => x.ToString()));
        }

        private void button1_Click(object sender, EventArgs e)
        {
            // Сортировка массива с помощью метода OrderBy из Linq
            arr = arr.OrderBy(x => x).ToArray();
            // Выводим отсортированный массив в TextBox2
            textBox2.Text = string.Join(" ", arr.Select(x => x.ToString()));
        }
    }
}
``` 
