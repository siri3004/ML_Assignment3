# ML_Assignment3

Video Link: https://drive.google.com/file/d/1AZ4AJpiH_CR3yAPZleGzHm5cNSxehIWe/view

#Q1. Numpy:
a. Using NumPy create random vector of size 15 having only Integers in the range 1-20.
1. Reshape the array to 3 by 5
2. Print array shape.
3. Replace the max in each row by 0
----> •	To perform the array operations the code uses the numpy libraries. 
•	To create a random vector of size 15 with integers in the range of 1-20, numpy random module’s randint() function is used. 
•	The reshape() method is used to convert the 1-dimensional vector to a 2-dimensional array of shape 3x5. 
•	Replacing the maximum element of each row with 0: random_vector[np.arange(len(random_vector)), np.argmax(random_vector, axis=1)] = 0 (This line replaces the maximum value of each row in the random_vector array with 0. The np.argmax() function is used to get the index of the maximum value in each row,and the np.arange() function is used to create an array of indices from 0 to the length of the array minus 1)
•	create a 2-dimensional array of size 4 x 3. 
•	The dtype parameter is used to set the data type of the array to 32-bit integer.


          import numpy as np

          # create a random vector of size 15 with integers in the range of 1-20
          random_vector = np.random.randint(1, 21, size=15)
          print("Before Update:\n",random_vector)
          # reshape the array to 3 by 5
          random_vector = random_vector.reshape(3, 5)

          # print the array shape
          print("Array Shape:", random_vector.shape)
          print("after Reshape:\n",random_vector)

          # replace the max in each row by 0
          random_vector[np.arange(len(random_vector)), np.argmax(random_vector, axis=1)] = 0

          # print the updated array
          print("Updated Array:\n", random_vector)

          # create a 2-dimensional array of size 4 x 3
          array_2d = np.zeros((4, 3), dtype=np.int32)

          # print the shape, type, and data type of the array
          print("\nArray Shape:", array_2d.shape)
          print("Array Type:", type(array_2d))
          print("Array Data Type:", array_2d.dtype)
          
#b.Write a program to compute the eigenvalues and right eigenvectors of a given square array given below:
[[ 3 -2]
[ 1 0]]    

---> •	The code starts by importing the NumPy library.
•	The square array is defined by square_arr = np.array([[3, -2], [1, 0]]). This line defines a 2x2 NumPy array named square_arr and initializes it with the values [[3, -2], [1, 0]].
•	To calculate the eigenvalues and eigenvectors of square_arr the line uses the NumPy linalg.eig() function. This function takes the square_arr as an argument and returns two NumPy arrays: eigvals and eigvecs. eigvals is a 1D array containing the eigenvalues of square_arr, and eigvecs is a 2D array containing the eigenvectors of square_arr.
•	Finally, the code calculates the eigenvalues and eigenvectors of the 2x2 array [[3, -2], [1, 0]] using the NumPy linalg.eig() function, and then prints the results.

            import numpy as np

            # define the square array
            square_arr = np.array([[3, -2], [1, 0]])

            # compute the eigenvalues and right eigenvectors
            eigvals, eigvecs = np.linalg.eig(square_arr)

            # print the eigenvalues and right eigenvectors
            print("Eigenvalues: ", eigvals)
            print("Right Eigenvectors: \n", eigvecs)
            
#c.Compute the sum of the diagonal element of a given array.
[[0 1 2]
[3 4 5]]   

---> •	We have defined the numpy array which initializes it with the values [[0, 1, 2], [3, 4, 5]].
•	The NumPy trace() function is used to compute the sum of the diagonal elements of my_array.
•	The code calculates the sum of the diagonal elements of a 2x3 NumPy array [[0, 1, 2], [3, 4, 5]] using the NumPy trace() function, and then prints the array and the sum of its diagonal elements.

          import numpy as np

          # define the array
          my_array = np.array([[0, 1, 2], [3, 4, 5]])

          # compute the sum of the diagonal elements
          sum_of_diagonal = np.trace(my_array)
          
#d.Write a NumPy program to create a new shape to an array without changing its data.
Reshape 3x2:
[[1 2]
[3 4]
[5 6]]
Reshape 2x3:
[[1 2 3]
[4 5 6]]     

--->•	A 2D NumPy array named my_array with shape (3,2) and initializes it with the values [[1, 2], [3, 4], [5, 6]].
•	the NumPy reshape() function is used to reshape my_array into a new array new_array of shape (2, 3). The reshape() function takes two arguments: the first argument is the original array to be reshaped, and the second argument is the new shape of the array. In this case, the reshape() function reshapes my_array into a 2x3 array.
•	The print() function is used to display the arrays.

              import numpy as np

              # create the original array
              my_array = np.array([[1, 2], [3, 4], [5, 6]])

              # reshape the array to 2x3
              new_array = np.reshape(my_array, (2, 3))

              # print the original and reshaped arrays
              print("Original array:\n", my_array)
              print("Reshaped array:\n", new_array)
              
              
#2.Matplotlib
1. Write a Python programming to create a below chart of the popularity of programming Languages.
2. Sample data:
Programming languages: Java, Python, PHP, JavaScript, C#, C++
Popularity: 22.2, 17.6, 8.8, 8, 7.7, 6.7

--->•	the pyplot module from the matplotlib library is imported.
•	prog_languages and popularity_scores has been defined and prog_languages list contains the names of different programming languages and the popularity_scores list contains their popularity scores.
•	highest_score_index = popularity_scores.index(max(popularity_scores))[This line finds the index of the highest popularity score in the popularity_scores list].
•	define an explode list to create an effect of separating out the slice corresponding to the language with the highest popularity score.
•	the pie chart using the pie() function from pyplot takes the popularity_scores and prog_languages lists as input data, and uses the explode_list to separate out the slice corresponding to the highest score language.
•	plt.title sets the title of the pie chart.
•	plt.show() displays the pie chart.




          import matplotlib.pyplot as plt

          # define the data
          prog_languages = ["Java", "Python", "PHP", "JavaScript", "C#", "C++"]
          popularity_scores = [22.2, 17.6, 8.8, 8, 7.7, 6.7]

          # find the index of the language with the highest popularity score
          highest_score_index = popularity_scores.index(max(popularity_scores))

          # create the explode list
          explode_list = [0] * len(prog_languages)
          explode_list[highest_score_index] = 0.1

          # create the pie chart with the explode parameter and set the startangle
          plt.pie(popularity_scores, labels=prog_languages, explode=explode_list, autopct='%1.1f%%', startangle=140)

          # set the title
          plt.title("Popularity of Programming Languages")

          # show the plot
          plt.show()

