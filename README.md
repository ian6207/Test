# Test
        Install-Package MaterialSkin.2
        public partial class Form1 : MaterialSkin.Controls.MaterialForm
        {
            // ...
        }
        public Form1()
        {
            InitializeComponent();
            var materialSkinManager = MaterialSkin.Manager.Instance;
            materialSkinManager.AddFormToManage(this);
            materialSkinManager.Theme = MaterialSkin.Manager.Themes.LIGHT; // Or DARK
            materialSkinManager.ColorScheme = new MaterialSkin.ColorScheme(
                MaterialSkin.Primary.BlueGrey800, MaterialSkin.Primary.BlueGrey900,
                MaterialSkin.Primary.BlueGrey500, MaterialSkin.Accent.LightBlue200,
                MaterialSkin.TextShade.WHITE);
        }



