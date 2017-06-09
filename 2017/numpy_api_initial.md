# Writing At First

This note I will say something about numpy. And what I will say is most about initial function like some functions that create some objects.

----
# Then I will say what I think
## numpy.array


```
array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)
```
Object is a list or turple which likes `[1,2]` or `(1,2)` or `[[1,2],[1,2]]` or etc.

dtype is to input a type object that is from numpy package.

copy I don't know. I never use this parameter in this function. Also others parameters I never use it. Many times I just want to create a new array object. So I just use the first and the second parameters.

And It's output is a numpy.ndarray object. And it saves the array we uesd.

Example :
```
In [6]: numpy.array([1,2,3])
Out[6]: array([1, 2, 3])
```
And its type is int32.

## numpy.arange

```
arange([start,] stop[, step,], dtype=None)
```
And it's function defined like this:
```
arange(start=None, stop=None, step=None, dtype=None)
```

This function likes range or xrange. In order to create a new array likes `[1,2,3,4,5]`.

start is the array's first number.
stop is the array's length.
step is how long will the nearly number be.
dtype is its type.

Example :
```
In [8]: numpy.arange(5)
Out[8]: array([0, 1, 2, 3, 4])

In [9]: numpy.arange(1,5)
Out[9]: array([1, 2, 3, 4])

In [10]: numpy.arange(1,10,2)
Out[10]: array([1, 3, 5, 7, 9])
```

## numpy.zeros

```
zeros(shape, dtype=None, order='C')
```
Shape is the shape , likes (1,2) and it will create a matrix of one line two column. Also you can create a three dimensions tensor or others.

dtype is its type.

order is how to save in the memory. We don't need to care.

Example :
```
In [12]: numpy.zeros((2,2,2))
Out[12]:
array([[[ 0.,  0.],
        [ 0.,  0.]],

       [[ 0.,  0.],
        [ 0.,  0.]]])

In [13]: numpy.zeros((2,2))
Out[13]:
array([[ 0.,  0.],
       [ 0.,  0.]])


In [14]: numpy.zeros((2,2,2,2))
Out[14]:
array([[[[ 0.,  0.],
         [ 0.,  0.]],

        [[ 0.,  0.],
         [ 0.,  0.]]],


       [[[ 0.,  0.],
         [ 0.,  0.]],

        [[ 0.,  0.],
         [ 0.,  0.]]]])
```

## numpy.ones

```
ones(shape, dtype=None, order='C')
```

The same as numpy.zeros. But the output is some one rather than zero.

Example :
```
In [2]: numpy.ones(5)
Out[2]: array([ 1.,  1.,  1.,  1.,  1.])

In [3]: numpy.ones((2,2))
Out[3]:
array([[ 1.,  1.],
       [ 1.,  1.]])


In [4]: np.ones((2,2,2))
Out[4]:
array([[[ 1.,  1.],
        [ 1.,  1.]],

       [[ 1.,  1.],
        [ 1.,  1.]]])
```
---
# This is numpy's Python doc
## numpy.array
array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)
        Create an array.

        Parameters
        ----------
        object : array_like
            An array, any object exposing the array interface, an
            object whose __array__ method returns an array, or any
            (nested) sequence.
        dtype : data-type, optional
            The desired data-type for the array.  If not given, then
            the type will be determined as the minimum type required
            to hold the objects in the sequence.  This argument can only
            be used to 'upcast' the array.  For downcasting, use the
            .astype(t) method.
        copy : bool, optional
            If true (default), then the object is copied.  Otherwise, a copy
            will only be made if __array__ returns a copy, if obj is a
            nested sequence, or if a copy is needed to satisfy any of the other
            requirements (`dtype`, `order`, etc.).
        order : {'C', 'F', 'A'}, optional
            Specify the order of the array.  If order is 'C', then the array
            will be in C-contiguous order (last-index varies the fastest).
            If order is 'F', then the returned array will be in
            Fortran-contiguous order (first-index varies the fastest).
            If order is 'A' (default), then the returned array may be
            in any order (either C-, Fortran-contiguous, or even discontiguous),
            unless a copy is required, in which case it will be C-contiguous.
        subok : bool, optional
            If True, then sub-classes will be passed-through, otherwise
            the returned array will be forced to be a base-class array (default).
        ndmin : int, optional
            Specifies the minimum number of dimensions that the resulting
            array should have.  Ones will be pre-pended to the shape as
            needed to meet this requirement.

        Returns
        -------
        out : ndarray
            An array object satisfying the specified requirements.

        See Also
        --------
        empty, empty_like, zeros, zeros_like, ones, ones_like, fill

        Examples
        --------
        >>> np.array([1, 2, 3])
        array([1, 2, 3])

        Upcasting:

        >>> np.array([1, 2, 3.0])
        array([ 1.,  2.,  3.])

        More than one dimension:

        >>> np.array([[1, 2], [3, 4]])
        array([[1, 2],
               [3, 4]])

        Minimum dimensions 2:

        >>> np.array([1, 2, 3], ndmin=2)
        array([[1, 2, 3]])

        Type provided:

        >>> np.array([1, 2, 3], dtype=complex)
        array([ 1.+0.j,  2.+0.j,  3.+0.j])

        Data-type consisting of more than one element:

        >>> x = np.array([(1,2),(3,4)],dtype=[('a','<i4'),('b','<i4')])
        >>> x['a']
        array([1, 3])

        Creating an array from sub-classes:

        >>> np.array(np.mat('1 2; 3 4'))
        array([[1, 2],
               [3, 4]])

        >>> np.array(np.mat('1 2; 3 4'), subok=True)
        matrix([[1, 2],
                [3, 4]])

## numpy.arange
arange([start,] stop[, step,], dtype=None)

        Return evenly spaced values within a given interval.

        Values are generated within the half-open interval ``[start, stop)``
        (in other words, the interval including `start` but excluding `stop`).
        For integer arguments the function is equivalent to the Python built-in
        `range <http://docs.python.org/lib/built-in-funcs.html>`_ function,
        but returns an ndarray rather than a list.

        When using a non-integer step, such as 0.1, the results will often not
        be consistent.  It is better to use ``linspace`` for these cases.

        Parameters
        ----------
        start : number, optional
            Start of interval.  The interval includes this value.  The default
            start value is 0.
        stop : number
            End of interval.  The interval does not include this value, except
            in some cases where `step` is not an integer and floating point
            round-off affects the length of `out`.
        step : number, optional
            Spacing between values.  For any output `out`, this is the distance
            between two adjacent values, ``out[i+1] - out[i]``.  The default
            step size is 1.  If `step` is specified, `start` must also be given.
        dtype : dtype
            The type of the output array.  If `dtype` is not given, infer the data
            type from the other input arguments.

        Returns
        -------
        arange : ndarray
            Array of evenly spaced values.

            For floating point arguments, the length of the result is
            ``ceil((stop - start)/step)``.  Because of floating point overflow,
            this rule may result in the last element of `out` being greater
            than `stop`.

        See Also
        --------
        linspace : Evenly spaced numbers with careful handling of endpoints.
        ogrid: Arrays of evenly spaced numbers in N-dimensions.
        mgrid: Grid-shaped arrays of evenly spaced numbers in N-dimensions.

        Examples
        --------
        >>> np.arange(3)
        array([0, 1, 2])
        >>> np.arange(3.0)
        array([ 0.,  1.,  2.])
        >>> np.arange(3,7)
        array([3, 4, 5, 6])
        >>> np.arange(3,7,2)
        array([3, 5])


## numpy.zeros
zeros(shape, dtype=float, order='C')

        Return a new array of given shape and type, filled with zeros.

        Parameters
        ----------
        shape : int or sequence of ints
            Shape of the new array, e.g., ``(2, 3)`` or ``2``.
        dtype : data-type, optional
            The desired data-type for the array, e.g., `numpy.int8`.  Default is
            `numpy.float64`.
        order : {'C', 'F'}, optional
            Whether to store multidimensional data in C- or Fortran-contiguous
            (row- or column-wise) order in memory.

        Returns
        -------
        out : ndarray
            Array of zeros with the given shape, dtype, and order.

        See Also
        --------
        zeros_like : Return an array of zeros with shape and type of input.
        ones_like : Return an array of ones with shape and type of input.
        empty_like : Return an empty array with shape and type of input.
        ones : Return a new array setting values to one.
        empty : Return a new uninitialized array.

        Examples
        --------
        >>> np.zeros(5)
        array([ 0.,  0.,  0.,  0.,  0.])

        >>> np.zeros((5,), dtype=np.int)
        array([0, 0, 0, 0, 0])

        >>> np.zeros((2, 1))
        array([[ 0.],
               [ 0.]])

        >>> s = (2,2)
        >>> np.zeros(s)
        array([[ 0.,  0.],
               [ 0.,  0.]])

        >>> np.zeros((2,), dtype=[('x', 'i4'), ('y', 'i4')]) # custom dtype
        array([(0, 0), (0, 0)],
              dtype=[('x', '<i4'), ('y', '<i4')])


## numpy.ones
Return a new array of given shape and type, filled with ones.

    Parameters
    ----------
    shape : int or sequence of ints
        Shape of the new array, e.g., ``(2, 3)`` or ``2``.
    dtype : data-type, optional
        The desired data-type for the array, e.g., `numpy.int8`.  Default is
        `numpy.float64`.
    order : {'C', 'F'}, optional
        Whether to store multidimensional data in C- or Fortran-contiguous
        (row- or column-wise) order in memory.

    Returns
    -------
    out : ndarray
        Array of ones with the given shape, dtype, and order.

    See Also
    --------
    zeros, ones_like

    Examples
    --------
    >>> np.ones(5)
    array([ 1.,  1.,  1.,  1.,  1.])

    >>> np.ones((5,), dtype=np.int)
    array([1, 1, 1, 1, 1])

    >>> np.ones((2, 1))
    array([[ 1.],
           [ 1.]])

    >>> s = (2,2)
    >>> np.ones(s)
    array([[ 1.,  1.],
           [ 1.,  1.]])
