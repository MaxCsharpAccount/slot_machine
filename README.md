# slot_machine
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        PictureBox[] p = new PictureBox[4];
        int[] nums = new int[4];
        int count;
        int cheat;
        private void Form1_Load(object sender, EventArgs e)
        {
            pictureBox4.Image = new Bitmap("up.jpg");
            p[1] = pictureBox1;
            p[2] = pictureBox2;
            p[3] = pictureBox3;
            for (int i = 1; i <= p.GetUpperBound(0); i++) ;
        }

        private void pictureBox1_Click(object sender, EventArgs e)
        {

        }

        private void pictureBox4_Click(object sender, EventArgs e)
        {
            if (numericUpDown1.Value > 0 && numericUpDown1.Value <= Convert.ToInt32(label2.Text))
            {
                pictureBox4.Image = new Bitmap("down.jpg");
                timer1.Enabled = true;

                cheat += 1;
            }
            else
            {
                MessageBox.Show("Not Enough Token");
            }
        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            Random r = new Random();
            for (int i = 1; i <= p.GetUpperBound(0); i++)
            {
                nums[i] = r.Next(0, 8);
                p[i].Image = new Bitmap(Convert.ToString(nums[i]) + ".jpg");
            }
            count += 1;
            if (count == 20)
            {
                if (cheat == 3)
                {
                    nums[1] = nums[2] = nums[3];
                    p[1].Image = p[2].Image = p[3].Image;
                }
                {
                    timer1.Enabled = false;
                    pictureBox4.Image = new Bitmap("up.jpg");
                    if (nums[1] == 0 && nums[2] == 0 && nums[3] == 0)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 2);
                        MessageBox.Show("Destructive! (Multiply 2 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 1 && nums[2] == 1 && nums[3] == 1)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 4);
                        MessageBox.Show("Chaotic!! (Multiply 4 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 2 && nums[2] == 2 && nums[3] == 2)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 6);
                        MessageBox.Show("Brutal!! (Multiply 6 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 3 && nums[2] == 3 && nums[3] == 3)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 8);
                        MessageBox.Show("Ararchic!! (Multiply 8 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 4 && nums[2] == 4 && nums[3] == 4)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 10);
                        MessageBox.Show("SUPREME!!! (Multiply 10 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 5 && nums[2] == 5 && nums[3] == 5)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 15);
                        MessageBox.Show("SSADISTIC!! (Multiply 15 Time the Token You Spent.)");
                    }
                    else if (nums[1] == 6 && nums[2] == 6 && nums[3] == 6)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 20);
                        MessageBox.Show("SSSTYLESTORM!! (Multiply 20 Time the Token You Spent.)");

                    }
                    else if (nums[1] == 7 && nums[2] == 7 && nums[3] == 7)
                    {
                        label2.Text = Convert.ToString(Convert.ToInt32(label2.Text) + numericUpDown1.Value * 30);
                        MessageBox.Show("EXODUS!!!! (Multiply 30 Time the Token You Spent.)");
                    }
                }
            }
        }
    }
}
