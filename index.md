# Welcome to my Portfolio!

Here are some of my works from Programing 101 in C#!

## **The Artifact**
##### [GitHub Repository](https://github.com/LeftRightDown/TheArtifactGame)
![AdventureGame](https://user-images.githubusercontent.com/82528207/140170185-b35f223a-bd3e-47c1-a296-03274300237b.PNG)
A space adventure game created as a midterm project. 

#### *Premise*
>In The Artifact, you play as wandering voyager on their way to meet up with a black-market
merchant. When suddenly you receive a distress signal from another ship but upon arrival you 
receive no response. This is where your story begins, exploring an unknown ship as you try to
find any loot before it explodes. 

## **Tip Calculator**
##### [GitHub Repository](https://github.com/LeftRightDown/TipCalculator2.0) 
![CalculatorApplication](https://user-images.githubusercontent.com/82528207/140174107-0e270c0d-2389-4f55-95bc-04ac046d91ac.PNG)
Console application tip calculator.

## **Keyboard Console**
Console application that uses arrow keys and the enter key as input.
>Menu code From [Mike Hadley](https://www.youtube.com/watch?v=qAWhGEPMlS8)

#### **C# Code**
    
    class Menu
    {
        private int SelectedIndex;
        private string[] Options;
        private string Prompt;


        public  Menu(string prompt, string[] options)
        {
            Prompt = prompt;
            Options = options;
            SelectedIndex = 0;
        }


        private void DisplayOptions()
        {

            WriteLine(Prompt);
            for (int i = 0; i < Options.Length; i++)
            {
                string currentOptions = Options[i];
                string prefix;

                if (i== SelectedIndex)
                {
                    prefix = "*";
                    ForegroundColor = ConsoleColor.Black;
                    BackgroundColor = ConsoleColor.White;
                }
                else
                {
                    prefix = "";
                    ForegroundColor = ConsoleColor.White;
                    BackgroundColor = ConsoleColor.Black;
                }
                WriteLine($"{prefix} << {currentOptions} >>");
               
            }
            ResetColor();
        }

            public int Run()
            {

             ConsoleKey keyPressed;
               do
                {
                Clear();
                DisplayOptions();


                ConsoleKeyInfo keyInfo = ReadKey(true);
                keyPressed = keyInfo.Key;

                //Update SelectedIndex based on ArrowKeys
                if (keyPressed == ConsoleKey.UpArrow)
                {
                    SelectedIndex--;
                    if (SelectedIndex == -1)
                    {
                        SelectedIndex = Options.Length - 1;
                    }

                }
                else if (keyPressed == ConsoleKey.DownArrow)
                {
                    SelectedIndex++;
                    if (SelectedIndex == Options.Length)
                    {
                        SelectedIndex = 0;
                    }
                }
               } while (keyPressed != ConsoleKey.Enter);

            return SelectedIndex;

            } 
    } 
   
   ## Study Application
  A Console Application that displays term and players much input the correct response.
