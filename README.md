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
  `reset(self)`                 called in __init__   <br>
                              create field and also create two spawn <br>
  `move(self,direction)`        inside this function I create move_row_left function <br>
                              to control how to a row of it to move to left<br>
                              and inside this function there is two function <br>
                              called tighten and merge<br>
                              when you execute left_move mission -> there are two step<br>
                              first,you take out all nozero value ,<br>
                              second,when closed field is same number then merge it to be a greater number<br>
                              and after making this function.I create a table to store the position to function<br>
                              like:<br>
                              
                              
                          def move_row_left(row):    
                              def tighten(row):
                                  new_row = [ i for i in row if i != 0]
                                  new_row += [ 0 for i in range(len(row) - len(new_row))]
                                  return new_row
                              
                              def merge(row):
                                  pair = False
                                  new_row = {}
                                  for i in range(len(row)):
                                      if pair == True:
                                          new_row.append(2 * row[i])
                                          self.score += 2 * row[i]
                                          pair = False
                                      
                                      else:
                                          if i + 1 < len(row) and row[i + 1] == row[i]:
                                              pair = True
                                              new_row.append(0)
                                          else:
                                              new_row.append(row[i])
                                  assert(len(new_row) == len(row))
                                  return new_row
                            return tighten(merge(tighten(row)))
                            
                              
                              
                              
                              moves["Left"] = lambda field:[moves_row_left(row) for row in field]
                              (in this function moves_row_left will be executed n time )
                              
                              if direction in moves:
                                  if self.move_is_possible(direction):
                                      self.field = moves[direcrion](self.field)
                                      self.spawn()
                                      return True
                                  else:
                                      return False
                          
  `is_win(self)`                  this is a function to determine wether you win this game<br>
                                
                                
                                  return any(any(i >= self.win_value for i in row) for row in self.field)
  `is_gameover(self)`             this is a function to determine wether you can not move<br>
            
                                return not any(self.move_is_possible(move) for move in actions)
  `spawn(self)`                   create an spawn randomly<br>
                                
                                new_element = 4 if randrange(100) > 89 else 2
                                (i,j) = choice([(i,j) for i in range(self.width) for j in range(self.height) if self.field[i][j] == 0])
                                self.field[i][j] = new_element
  
  `move_is_possible(self,direction)`   this function is quietly similar to move(self,derection)<br>
                                      
                                      
                                      def row_is_left_movable(row):
                                          def change(i):
                                              if row[i] == 0 and row[i + 1] != 0
                                                  return True
                                              if row[i] != 0 and row[i] = row[i+1]
                                                  return True
                                              return False
                                      return any(change(i) for i in range(len(row) - 1))
                                      
                                      check = {}
                                      check["Left"] = lambda field:any(row_is_movable(row) for row in field)
                                      ...
                                      if direction in check:
                                          return check[direction](self.field)
                                      else:
                                          return False
  `draw(self,screen)`
                                
                                      
      
  
    
