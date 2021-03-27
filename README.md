# NumPy
NumPy is the fundamental package for scientific computing in Python. It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices), and an assortment of routines for fast operations on arrays, including mathematical, logical, shape manipulation, sorting, selecting, I/O, discrete Fourier transforms, basic linear algebra, basic statistical operations, random simulation and much more.
# Array
An array is a data structure that stores values of same types.

## import numpy library to work with arrays
    import numpy as np
# One Dimentional arrays

    num_list=[1,2,3,4,5]
    alpha_list=["A","B","C","D","E"]
    NumArr= np.array(num_list)
    AlphaArr= np.array(alpha_list)
    print("list:", num_list, "array:", NumArr)
    print("list:", alpha_list, "array:", AlphaArr)
    
output
 
    list: [1, 2, 3, 4, 5] array: [1 2 3 4 5]
    list: ['A', 'B', 'C', 'D', 'E'] array: ['A' 'B' 'C' 'D' 'E']
When there is only one square bracket it is a 1D array but to stoo confirmm we can check the shape of the array 
        
     NumArr.shape, AlphaArr.shape #1D array
      
output
   
      ((5,), (5,))
      
# Multi-Dimentional arrays 
    TwoD_Arr= np.array([num_list,alpha_list])
    print(TwoD_Arr)
    L1=[2,3,"d",5]
    L2=[1,2,3,4]
    L3=[9,3,4,"4"]
    Arr1= np.array([L1,L2,L3])
    print((Arr1), '\n', type(Arr1), '\n', Arr1.shape)
    
output

    [['2' '3' 'd' '5']
     ['1' '2' '3' '4']
     ['9' '3' '4' '4']] 
     <class 'numpy.ndarray'> 
     (3, 4)
     
## Reshaping 2D array
     Re_Arr1= Arr1.reshape(4,3)
     print((Re_Arr1), '\n', type(Re_Arr1), '\n', Re_Arr1.shape)
     
output

    [['2' '3' 'd']
     ['5' '1' '2']
     ['3' '4' '9']
     ['3' '4' '4']] 
     <class 'numpy.ndarray'> 
     (4, 3)
     
# Indexing    
    list1=[1,2,3,4,5]
    list2=[2,3,4,5,6]
    list3=[5,6,7,8,9]
    arr = np.array([list1,list2,list3])
    print("ENTIRE ARRAY:" ,'\n' ,arr[:,:] ,'\n' , 
    "FIRST 2 ROWS AND ALL COLUMNS:" ,'\n', arr[0:2,:], "\n", 
    "LAST 2 ROWS AND COLUMNS:" , '\n',arr[1:,-2:]) #[for:rows, for:column]
    
output

    ENTIRE ARRAY: 
     [[1 2 3 4 5]
     [2 3 4 5 6]
     [5 6 7 8 9]] 
     FIRST 2 ROWS AND ALL COLUMNS: 
     [[1 2 3 4 5]
     [2 3 4 5 6]] 
     LAST 2 ROWS AND COLUMNS: 
     [[5 6]
     [8 9]]
     
# arange and linspace
arange

    ARR= np.arange(5,50,5) # ...arange(start, end, step)
    ARR.reshape(3,3)
    
output

    array([[ 5, 10, 15],
           [20, 25, 30],
           [35, 40, 45]])
           
linspace
           
    array_= np.linspace(1,10,50)
    array2_ = np.linspace(1,10,50,endpoint=False,retstep=True)
    
array_ output

    array([ 1.        ,  1.18367347,  1.36734694,  1.55102041,  1.73469388,
            1.91836735,  2.10204082,  2.28571429,  2.46938776,  2.65306122,
            2.83673469,  3.02040816,  3.20408163,  3.3877551 ,  3.57142857,
            3.75510204,  3.93877551,  4.12244898,  4.30612245,  4.48979592,
            4.67346939,  4.85714286,  5.04081633,  5.2244898 ,  5.40816327,
            5.59183673,  5.7755102 ,  5.95918367,  6.14285714,  6.32653061,
            6.51020408,  6.69387755,  6.87755102,  7.06122449,  7.24489796,
            7.42857143,  7.6122449 ,  7.79591837,  7.97959184,  8.16326531,
            8.34693878,  8.53061224,  8.71428571,  8.89795918,  9.08163265,
            9.26530612,  9.44897959,  9.63265306,  9.81632653, 10.        ])

array2_ output

    (array([1.  , 1.18, 1.36, 1.54, 1.72, 1.9 , 2.08, 2.26, 2.44, 2.62, 2.8 ,
            2.98, 3.16, 3.34, 3.52, 3.7 , 3.88, 4.06, 4.24, 4.42, 4.6 , 4.78,
            4.96, 5.14, 5.32, 5.5 , 5.68, 5.86, 6.04, 6.22, 6.4 , 6.58, 6.76,
            6.94, 7.12, 7.3 , 7.48, 7.66, 7.84, 8.02, 8.2 , 8.38, 8.56, 8.74,
            8.92, 9.1 , 9.28, 9.46, 9.64, 9.82]),
     0.18)


# copy() function and broadcasting
    arr= np.arange(5,50,5)
    arr1=arr 
    print(arr, '\n', arr1)
output
    
    [ 5 10 15 20 25 30 35 40 45] 
    [ 5 10 15 20 25 30 35 40 45]
    
making changes is arr

    arr[4:]=0
    arr1
    
output

    array([ 5, 10, 15, 20,  0,  0,  0,  0,  0])
   
change in one (arr or arr1) will cause the same change in other as tey are reference type
## copy() [broadcasting]

    rr_= np.arange(5,50,5)
    arr1_=arr_.copy() #copy() is making a seperate memory space
    arr_[3:]=0
    arr1_[3:]=100
    arr1_, arr_
    
output

    (array([  5,  10,  15, 100, 100, 100, 100, 100, 100]),
     array([ 5, 10, 15,  0,  0,  0,  0,  0,  0]))

# Exploratary data analysis

    print("default array:" , '\n', arr,  '\n',  '\n',

    "array elements *2:" ,'\n', arr*2,'\n',

    "array elements less than 2",'\n',arr<2,'\n',

    "array elements graeter than 2",'\n',arr>2, '\n',

    "array elements + 2",'\n',arr+2,'\n',

    "array elements mod 4 ",'\n',arr%4)
    
output

    default array: 
     [  5  10  15  20 100 100 100 100 100] 

     array elements *2: 
     [ 10  20  30  40 200 200 200 200 200] 
     array elements less than 2 
     [False False False False False False False False False] 
     array elements graeter than 2 
     [ True  True  True  True  True  True  True  True  True] 
     array elements + 2 
     [  7  12  17  22 102 102 102 102 102] 
     array elements mod 4  
     [1 2 3 0 0 0 0 0 0]
     
     
To get elements than meet any given condition out of an array

    arr[arr<100] #elements less than 100
    
output

    array([ 5, 10, 15, 20])
    
## To create arrays with all ones

    arr1= np.ones(9, dtype=int)
    arr1.reshape(3,3)
    
output

    array([[1, 1, 1],
           [1, 1, 1],
           [1, 1, 1]])
           
## Random distribution  

#### np.random.rand:
Create an array of the given shape and populate it with
random samples from a uniform distribution
over ``[0, 1)``.


    ran_arr= np.random.rand(3,5) 
    ran_ar
    
output

    array([[0.56518814, 0.7762626 , 0.06936998, 0.71117541, 0.80860653],
           [0.06819288, 0.66939186, 0.31951503, 0.43075317, 0.08975475],
           [0.68549001, 0.30207218, 0.3077599 , 0.30657229, 0.07670949]])

#### np.random.randn:
Return a sample (or samples) from the "standard normal" distribution.


    ran_ex= np.random.randn(3,5)
    ran_ex
    
output

    array([[-2.72311459, -1.58100908,  2.22215913, -0.49251772,  1.6047709 ],
           [ 0.09896821, -2.26947596,  1.12371458, -0.45994899, -0.61293932],
           [-0.88515314, -0.77258554,  1.51741949, -1.92909538, -0.59673371]])
           
           
#### np.random.randint:
Return random integers from `low` (inclusive) to `high` (exclusive).

    randint_arr= np.random.randint(1,1000,70) #between 1 and 100 select 70 random integers
    randint_arr.reshape(7,10)
    
output

    array([[390, 799, 420, 568, 140, 530, 915,  13, 795, 682],
           [274,  80, 782, 749, 326, 891, 993, 945, 739, 724],
           [249,  83, 471, 468, 204, 989, 446, 219, 698, 641],
           [998, 306, 890, 160, 457, 655, 193, 330, 946, 613],
           [296, 479, 798, 201,  56,  82, 293, 235, 155, 184],
           [540, 607, 624, 905, 237, 139, 295, 872, 944, 296],
           [611, 986, 647, 475, 746, 672, 648, 268, 638,  12]])
#### np.random.random_sample:
Return random floats in the half-open interval [0.0, 1.0).


    randsample_arr= np.random.random_sample(50)
    randsample_arr.reshape(5,10)
    
output:

    array([[0.54493403, 0.73741281, 0.24567399, 0.50360273, 0.52189375,
            0.32752365, 0.77166347, 0.29502252, 0.2936321 , 0.09922019],
           [0.01221841, 0.94321943, 0.81363897, 0.89426754, 0.08158723,
            0.6285567 , 0.9660551 , 0.77054243, 0.89299125, 0.07587734],
           [0.10084908, 0.3639534 , 0.92148602, 0.88232272, 0.6800889 ,
            0.25003577, 0.32686221, 0.16158993, 0.8876177 , 0.62952808],
           [0.46861521, 0.83348458, 0.32266189, 0.59679893, 0.68610698,
            0.05861688, 0.04968956, 0.02885698, 0.87180948, 0.16394557],
           [0.65036274, 0.76963649, 0.37226138, 0.35701132, 0.43709661,
            0.6758923 , 0.59898872, 0.18019871, 0.5377849 , 0.46206702]])
