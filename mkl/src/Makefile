#-----------------------------------------------------------------------

MINIFE_TYPES =  \
        -DMINIFE_SCALAR=double   \
        -DMINIFE_LOCAL_ORDINAL=int      \
        -DMINIFE_GLOBAL_ORDINAL=int

MINIFE_MATRIX_TYPE = -DMINIFE_CSR_MATRIX
# MINIFE_MATRIX_TYPE = -DMINIFE_ELL_MATRIX

#-----------------------------------------------------------------------

CFLAGS = -O3 -mkl -DMINIFE_MKL_DOUBLE -fopenmp -DUSE_MKL_DAXPBY -mavx
CXXFLAGS = $(CFLAGS)

# For debugging, the macro MINIFE_DEBUG will cause miniFE to dump a log file
# from each proc containing various information.
# This macro will also enable a somewhat expensive range-check on indices in
# the exchange_externals function.

# CPPFLAGS = -I. -I../utils -I../fem $(MINIFE_TYPES) -DMINIFE_DEBUG -DHAVE_MPI -DMPICH_IGNORE_CXX_SEEK
CPPFLAGS = -I. -I../utils -I../fem $(MINIFE_TYPES) $(MINIFE_MATRIX_TYPE) -DHAVE_MPI -DMPICH_IGNORE_CXX_SEEK

LDFLAGS=
LIBS=

# The MPICH_IGNORE_CXX_SEEK macro is required for some mpich versions,
# such as the one on my cygwin machine.

CXX=mpiicpc
CC=mpiicc

include make_targets

