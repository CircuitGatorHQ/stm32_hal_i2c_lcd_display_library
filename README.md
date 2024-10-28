# stm32_hal_i2c_lcd_display_library
Video tutoral showing how to use the library is available on YouTube: 
Code Example:

    //Nomral static Printing
    HD44780_Init(2);
    HD44780_Clear();
    HD44780_Backlight();
    HD44780_SetCursor(0,0);
    HD44780_PrintStr("Welcome To");
    HD44780_SetCursor(0,1);
    HD44780_PrintStr("CircuitGator HQ");

    //Left/Right Scroll Printing
    HD44780_Init(2);
  	HD44780_Clear();
	  HD44780_SetCursor(0,0);
  	HD44780_PrintStr("Welcome To CircuitGator HQ");
  	int x;
  	for(int x=0; x<100; x=x+1)
  	  {
  		HD44780_ScrollDisplayLeft();  //Scrolling left
  		//HD44780_ScrollDisplayRight(); for scrolling right
  		HAL_Delay(500);
  	  }

     //Printing Numbers
     HD44780_Init(2);
    char snum[5];
      for ( int x = 1; x <= 200 ; x++ )
      {
        itoa(x, snum, 10);
        HD44780_Clear();
        HD44780_SetCursor(0,0);
        HD44780_PrintStr(snum);
        HAL_Delay (500);
      }
       
Other general functions

     //Control display backlight
     HD44780_NoBacklight();
     HD44780_Backlight();

     //Displaying and blinking the cursor
    HD44780_Cursor(); 
    HD44780_Blink(); 
    HAL_Delay(5000);
    HD44780_NoBlink();
    HAL_Delay(2000);
    HD44780_NoCursor();

    
