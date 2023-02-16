# Coco3-MPI-GAL
This is a repository to hold the files for a replacement U8 GAL for the 26-3024 Multipak Interface so that it can work with the Tandy Color Computer 3

Based on files found on Gimechip.com (long since taken down) and reposted on StackExchange, I wanted to post these here on Git for two reasons:

1) The posted version on StackExchange is an old PLD version using WinCUPL (an old WinXP era program)
2) I wanted to post a JEDEC version so anyone can program a new GAL

The three files in this repository are:

1) 26-3024-U8-GAL16V8-Coco3.jed - This is the GAL16V8 you need to program and put in U8 of a 26-3024 MPI to make it compatible with a Coco 3.

2) 26-3024-U8-PAL14L4-Coco1-2.jed - This is the original code for the 26-3024 MPI that makes it work with a Coco 1 and 2.

3) Coco3-GAL-WinCUPL.PLD - This is the original WinCUPL PLD file that was posted on StackExchange.

The equations for #1 are as follows:

Inputs:

1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 13, 14, 17, 18, 19

Outputs:

14 (Combinatorial, Output feedback output, Active low)

15 (Combinatorial, No output feedback, Active low)

16 (Combinatorial, No output feedback, Active low)

Equations:

/o14 = /i1 & /i2 & i3 +

       /i19 +
       
       /i18

o14.oe = vcc

/o15 = /i1 & /i2 & i3 & i4 & i5 & i6 & i7 & i8 & i9 & i11 & i12

o15.oe = vcc

/o16 = /i1 & /i2 & i3 & i4 & i5 & i6 & i7 & i8 & i9 & /i11 & i12 & /i13

o16.oe = vcc

The equations for #2 are as follows:

Inputs:

1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 13, 18, 19

Outputs:

14 (Combinatorial, No output feedback, Active low)

15 (Combinatorial, No output feedback, Active low)

16 (Combinatorial, No output feedback, Active low)

17 (Combinatorial, No output feedback, Active low)

Equations:

/o14 = /i1 & /i2 & i3 +

       /i1 & i2 & /i3 & /i4 +
       
       /i19 +
       
       /i18

o14.oe = vcc

/o15 = /i1 & /i2 & i3 & i4 & i5 & i6 & i7 & i8 & i9 & i11 & i12

o15.oe = vcc

/o16 = /i1 & /i2 & i3 & i4 & i5 & i6 & i7 & i8 & i9 & /i11 & i12 & /i13

o16.oe = vcc

/o17 = 

o17.oe = vcc
