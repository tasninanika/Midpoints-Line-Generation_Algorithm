# **Midpoint Line Algorithm**  

The **Midpoint Line Algorithm** is a rasterization technique used in computer graphics to efficiently draw a straight line between two points. It optimizes performance by using integer arithmetic instead of floating-point calculations, making it faster and more suitable for low-resolution displays.  

This algorithm works by evaluating the midpoint between two possible pixel locations and selecting the one closest to the ideal line. By incrementally updating a decision parameter, it determines whether the next pixel should be placed straight (E) or diagonally (NE), ensuring smooth and accurate line rendering.  


## **Algorithm**  

#### **Step 1:** Enter the coordinates of the two endpoints, \( (x_1, y_1) \) and \( (x_2, y_2) \).  

#### **Step 2:** Compute the differences:  
   - \( dx = x_2 - x_1 \)  
   - \( dy = y_2 - y_1 \)  

#### **Step 3:** Initialize the decision parameter:  
   - \( d = 2dy - dx \)  

#### **Step 4:** Set the starting point:  
   - \( (x, y) = (x_1, y_1) \)  

#### **Step 5:** Repeat the following steps until reaching \( (x_2, y_2) \):  
   - Plot the point \( (x, y) \).  
   - If \( d < 0 \):  
     - Update \( d = d + 2dy \) (**Choose E pixel**).  
   - Else:  
     - Update \( y = y + 1 \) (**Choose NE pixel**).  
     - Update \( d = d + 2(dy - dx) \).  
   - Increment \( x \) by 1.  

#### **Step 6:** Continue this process until the endpoint \( (x_2, y_2) \) is reached.  
