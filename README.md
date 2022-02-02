# Calculating-and-finding-plotting-slope-on-graph
import matplotlib.pyplot as plt # imports pyplot
import time
def coordinates2tuple(x, y):
    return (x, y) #tuple and setting the x and y

def plotLine(p1, p2, p3):
    x = (p1[0], p2[0], p3[0]) # Extracting x's values of points 
    y = (p1[1], p2[1], p3[1]) # Extracting y's values of points
    plt.plot(x,y, '-o',label='x,y') # Plotting all three points
    

    
works = True
while works:
  x = input('enter first x value: ')
  y = input('enter first y value: ')
  X = input('enter second x value: ')
  Y = input('enter second y value: ') 
  #users input

  try:
    float(x) and float(X) and float(Y) and float(y) # only allows numbers
    
  except:
    print("Enter a number!")
    time.sleep(1)
  else:
    if (x != X):
      SUBY = float(Y) - float(y)
      SUBX = float(X) - float(x)
      slope = SUBY / SUBX
      slope = str(slope)
      
      x1 = input("The slope given your two points is " + slope + "\nNow enter another X cordinate point to give you the second one: \n")

      try:
        float(x1)
      except:
        print("Enter a number") # also only allows numbers
        time.sleep(1)
      else:
        x1 = float(x1) 
        X = float(X)
        Y = float(Y)
        x1 = float(x1)
        y1 = 6
        slope = float(slope)
        x = float(x)
        y1 = float(y1)
        y = float(y)
        y1 = (slope * x1) + y - (slope * x)

        y1 = str(y1)
        print("Your missing coordinate point is " + y1 + ".")
        print("time to plot!!!\n")
        works = False


        y1 = float(y1)



        p1 = coordinates2tuple(x, y)#100, 20
        p2 = coordinates2tuple(X, Y)#10, 34 #Which ones to plot 
        p3 = coordinates2tuple(x1, y1)#5, 5.1111

        plotLine(p1, p2, p3)#plots them

        plt.xlabel('x')
        plt.ylabel('y')
        plt.legend()
        plt.grid()
        minX = min(x,X,x1)
        minY = min(y,Y,y1)
        maxX = max(x,X,x1) # shows the max andmin of the coordinates and sets height and width with a 20% as extra space
        maxY = max(y,Y,y1)
        topX = max(abs(minX), abs(maxX)) * 0.4
        topY = max(abs(minY), abs(maxY)) * 0.4
        plt.axis([minX - topX, maxX + topX, minY - topY, maxY + topY])
        plt.title('two lines')
        plt.show()
    else:
      print("Float division by zero is illegal !") # if slope == infinate then
      time.sleep(1)
