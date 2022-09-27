# --------------------
132. What are pointers
# --------------------

All values are stored in memory. Every location in memory has an address. A pointer is a memory address.
-- & (ampersand) 
-- *int (pointer to an int)
-- * (dereferencing operator)

code
	step 0 - code from video: https://play.golang.org/p/Ysv5Adn3V1
	step 1 - take an address & : https://play.golang.org/p/BO7zRQN4Xm
	step 2 - dereference * : https://play.golang.org/p/ucJYPu3QkP
	step 3 - dereference * : https://play.golang.org/p/KpLImTmQCa

# -----------------------
133. When to use pointers
# -----------------------

code:
	step 1 no pointer: https://play.golang.org/p/lxsWkhTaYv
	step 2 pointer: https://play.golang.org/p/XuI19kjFmb

# --------------
134. Method Sets
# --------------

Method sets determine what methods attach to a TYPE. It is exactly what the name says: What is the set of methods for a given type? That is its method set.

IMPORTANT: “The method set of a type determines the INTERFACES that the type implements.....”

NON-POINTER RECEIVER
	works with values that are POINTERS or NON-POINTERS.
POINTER RECEIVER
	only works with values that are POINTERS.

Receivers 
---------
(t  T) -- T and *T 
(t *T) -- *T

code
	NON-POINTER RECEIVER & NON-POINTER VALUE: https://play.golang.org/p/2ZU0QX12a8
	NON-POINTER RECEIVER & POINTER VALUE: https://play.golang.org/p/glWZmm0gY6
	POINTER RECEIVER & POINTER VALUE: https://play.golang.org/p/pWFxsg6MSe
	POINTER RECEIVER & NON-POINTER VALUE: https://play.golang.org/p/G3lEy-4Mc8 ( code does not run )
		this codes does run - notice the difference - method set determines the 
		INTERFACES that the type implements
	https://play.golang.org/p/KK8gjsAWBZ
