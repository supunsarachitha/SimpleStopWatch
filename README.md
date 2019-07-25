# SimpleStopWatch





//=================in C# code =================//

        Stopwatch stopwatch;
        public MainPage()
        {
            InitializeComponent();
            stopwatch = new Stopwatch();
            stopwatch.Reset();
        }
        
        private void btnStart_Clicked(object sender, EventArgs e)
        {
            if (!stopwatch.IsRunning)
            {
                stopwatch.Start();                
                Device.StartTimer(TimeSpan.FromMilliseconds(100), () =>
                {
                    Device.BeginInvokeOnMainThread(() =>
                    lblstopwatch.Text = stopwatch.Elapsed.ToString());
                    if (!stopwatch.IsRunning)
                    {
                        return false;
                    }                        
                    else
                    {
                        return true;
                    }                    
                });
            }            
        }

        private void btnStop_Clicked(object sender, EventArgs e)
        {
            btnStart.Text = "Resume";
            stopwatch.Stop();
        }

        private void btnReset_Clicked(object sender, EventArgs e)
        {
            stopwatch.Reset();
        }
       
