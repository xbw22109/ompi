.. _mpi_win_unlock:


MPI_Win_unlock
==============

.. include_body

:ref:`MPI_Win_unlock` |mdash| Completes an RMA access epoch started by a call to
:ref:`MPI_Win_lock`.

.. The following file was automatically generated
.. include:: ./bindings/mpi_win_unlock.rst

INPUT PARAMETERS
----------------
* ``rank``: Rank of window (nonnegative integer).
* ``win``: Window object (handle).

OUTPUT PARAMETER
----------------
* ``ierror``: Fortran only: Error status (integer).

DESCRIPTION
-----------

:ref:`MPI_Win_unlock` completes an RMA access epoch started by a call to
:ref:`MPI_Win_lock`. RMA operations issued during this period will have
completed both at the origin and at the target when the call returns.

Locks are used to protect accesses to the locked target window effected
by RMA calls issued between the lock and unlock call, and to protect
local load/store accesses to a locked local window executed between the
lock and unlock call. Accesses that are protected by an exclusive lock
will not be concurrent at the window site with other accesses to the
same window that are lock protected. Accesses that are protected by a
shared lock will not be concurrent at the window site with accesses
protected by an exclusive lock to the same window.


ERRORS
------

.. include:: ./ERRORS.rst

.. seealso::
   * :ref:`MPI_Win_lock`
   * :ref:`MPI_Win_unlock_all`
