

Three Elementary Row Operations:  these are the arithmetical operations you can do to rows in a linear system in matrix form

The goal is to achieve a reduced echelon form of the matrix. If applying these rules you get a row of all zeroes that needs to be at the bottom of the matrix.
Your left most column has to be a one up top with zeroes below it
on the next

[1,1]
[0,1]
vs
[1,0]
[0,1]

## Replacement

Replace a row by the sum or the difference of a different row scaled up by some scalar

E.G:  r1 = 2 * r2 - r1

^ Replacing r1 by the difference of double r2 -r1.

any row within in the matrix with any other row in the matrix. 
## Interchange

Rows are swappable

## Scaling

You can scale rows by Scalars.

### Linear System Examples 
#### Example 1

x1 - 2x2 = -1
-x1 + 3x2 = 3

Our goal here is to:    An *identity matrix*, "reduced echelon form" With ones along the diagonal axis and zeros everywhere else. Terms and conditions may apply.


first step, lets put it into a matrix

(Using parenthesis instead of brackets so I don't make new notes)
((1, -2 | -1)
(-1, 3 |  3)) 

Second step: Turn the negative one into a zero. Operating under the rule of thumb that it is usually best to work top left to bottom right, it doesn't matter in terms of result but it can introduce unnecessary complexity to do other orders.  To turn the negative one in row two column one into a zero we're going to use the operation *Replacement*.

Replacement generally:
E.G:  r1 = 2 * r2 - r1
Replacement in our case:
r2 = r1 + r2

(1, -2 | -1) + (-1, 3 |  3) = (0, 1, | 2)

Combined back into the whole matrix

((1, -2 | -1)
(0, 1, | 2))

the next step: We already have ones and zeroes in the left most column. We now want to get zeroes above our one in the second row/column. If there were more rows, we would also want zeroes below one in the second row/column So we're going to use *replacement* again.

This time:

r1 = 2xr2 +r1

Which extends out to

the left column composed of a one at the top and zeroes below it can now be considered a "Pivot" 

- r1 = 2((0, 1, | 2)) + (1, -2 | -1) 
iterate
- r1 = (0,2 | 4) + (1, -2 | -1) 
iterate
- (1,0 | 3)

Resulting in our solved *linear system*, fully reduced echelon form also known as a *identity matrix*:
((1,0 | 3),
(0, 1, | 2))

Parametric Form:
x1  = 3
x2 = 2

Another example!

The goal here is to play with a different shape and more rows. We want to be able to see what happens when there are more columns then there are pivots and such. We need them stinky funky mathematics G.

#### Example 2


0 + x2 - 4x3 = 8
2x1 - 3x2 = 2x3 = 1
4x1 - 8x2 +12x3 = 1

Still shooting for an identity matrix. Our first step is going to be: Shit in garfields lasagna and after that we will do an *interchange*

- r1 = r3

producing:

4x1 - 8x2 +12x3 = 1
2x1 - 3x2 = 2x3 = 1
0 + x2 - 4x3 = 8

Now that we have a number to work with in the first spot, we can scale that whole row by 4 to get our one in the first spot. This is *scaling*

- r1 =r1 * .25

.25(4x1 - 8x2 + 12x3) = .25(1)
- iterate
1x1 - 2x2 + 3x3 = .25

leaving us with

1x1 - 2x2 + 3x3 = .25
2x1 - 3x2 + 2x3 = 1
0 + x2 - 4x3 = 8

Now that we have a one in the top left most spot we can use it to eliminate the two below it, getting just 0s below our one making our first pivot. We're going to use *replacement*

r2 = 2r1 -r2

r2 =  2(1x1 - 2x2 + 3x3 = .25) -
2x1 - 3x2 = 2x3 = 1 

that's a mess, I'm going to make it into matrix form real quick

((1, -2, 3 | .25),
(2, -3, 2 | 1 ),
0, 1, -4 | 8)

r2 = 2(1, -2, 3 | .25) - (2, -3, 2 | 1 )

- iterate
r2 = (2, -4, 6 | .5) - (2, -3, 2 | 1 )

- iterate

r2 = (0, -1, 4 | -.5)

Leaving us with

((1, -2, 3 | .25),
(0, -1, 4 | -.5),
0, 1, -4 | 8)

Hurray! We have a pivot, lets go about making a second pivot, let us try 2. Lets scale r2 by -1

- r2 = -1r2

-1(0, -1, 4 | -.5)
- iterate
- (0, 1, -4 | .5)

Leaving us with 

((1, -2, 3 | .25),
(0, 1, -4 | .5),
0, 1, -4 | 8))

so now we either want to get rid of our 1 or -2, typically it's best to work down so lets get rid of our one.  We can use replacement again:

- r3 = r2 - r3
r3 =(0, 1, -4 | .5) - (0, 1, -4 | 8)

r3 = (0, 0, 0, | -7.5)

Leaving us with

((1, -2, 3 | .25),
(0, 1, -4 | .5),
(0, 0, 0, | -7.5))

That bottom row is weird. We know there's no solution and can stop! Because  0x + 0y + 0z = 7.5 is incoherent.


To do: An example with fewer pivots than there are columns. Potentially illustrates what happens with redundant dimensions. May illuminate why the output of n dimensional linear systems seem.

### Echelon Form

A rectangular matrix is in echelon form (or row echelon form) if it has the
following three properties:
1. All nonzero rows are above any rows of all zeros.
2. Each leading entry of a row is in a column to the right of the leading entry of
the row above it.
3. All entries in a column below a leading entry are zeros.
If a matrix in echelon form satisfies the following additional conditions, then it is
in reduced echelon form (or reduced row echelon form):
4. The leading entry in each nonzero row is 1.
5. Each leading 1 is the only nonzero entry in its column



#Cyberneticist