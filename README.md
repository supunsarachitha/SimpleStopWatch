# Simple Stop Watch

Basic stop watch android mobile app by xamarin technology 


## Getting Started

###### Prerequisites
- visual studio with xamarin
- an android mobile device or an emulator


## Built With
- Xamarin.forms


## Deployment
make sure to update latest android sdk and build tools
set target android version same as buld sdk version


## Coding

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
        
        
 ## License

##### The MIT License (MIT)
##### Copyright (c) 2018 <Supun Sarachitha Liyanaarachchi>
        
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
       
