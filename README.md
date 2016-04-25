# colorful2048
A colorful 2048 game writed by python

A simple 2048 writed by python

![image](https://raw.githubusercontent.com/liuyuxuan123/colorful2048/master/picture%20review/colorful2048_description1.png)

and when you get higher grade you will see a more colorful interface 

![image](https://raw.githubusercontent.com/liuyuxuan123/colorful2048/master/picture%20review/colorful2048_description2.png)


#MORE DETAIL:

Inside this project,I create a class called GameField:

##properties:
  *height,                     //number of row.  
  *width,                      //number of column. 
  *win_value,                  //How many score do you need to win? 
  *score,                      //current score.
  *high_socre,                 //highest score you ever have. 
                                                            
  *field,                      // I create this in reset()   
                              //according to your given height and width to make a field 
##method:
  reset(self)                 //called in __init__ 
                              //create field and also create two spawn 
  move(self,direction)
