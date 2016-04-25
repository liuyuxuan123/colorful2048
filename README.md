# colorful2048
A colorful 2048 game writed by python

A simple 2048 writed by python

![image](https://raw.githubusercontent.com/liuyuxuan123/colorful2048/master/picture%20review/colorful2048_description1.png)

and when you get higher grade you will see a more colorful interface 

![image](https://raw.githubusercontent.com/liuyuxuan123/colorful2048/master/picture%20review/colorful2048_description2.png)


#MORE DETAIL:

Inside this project,I create a class called GameField:

##properties:
`height`,                     number of row.  <br>
`width`,                      number of column. <br>
`win_value`,                  How many score do you need to win? <br>
`score`,                      current score.<br>
`high_socre`,                 highest score you ever have. <br>
                                                            
`field`,                       I create this in reset()   <br>
                              according to your given height and width to make a field <br>
##method:
  reset(self)                 called in __init__ 
                              create field and also create two spawn 
  move(self,direction)        inside this function I create move_row_left function 
                              to control how to a row of it to move to left
                              and inside this function there is two function 
                              called tighten and merge
                              when you execute left_move mission -> there are two step
                              first,you take out all nozero value ,
                              second,when closed field is same number then merge it to be a greater number
                              and after making this function.I create a table to store the position to function
                              like:
                              
                              moves["Left"] = lambda field:[moves_row_left(row) for row in field]
                              (in this function moves_row_left will be executed n time )
                              
                              if direction in moves:
                                  if self.move_is_possible(direction):
                                      self.field = moves[direcrion](self.field)
                                      self.spawn()
                                      return True
                                  else:
                                      return False
                          
                      
                        
