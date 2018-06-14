^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package ros_boost_numpy
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------
* Fixed 'catkin_make install'
* Cleaning up package.xml.
* Fixing a few unused variable warnings.
* Converting to ROS package.
* Deprecation notice for move to Boost.Python proper
* Add travis ci badge to readme.
* Merge branch 'osx_fix'
* Bump cmake required version for MACOSX_RPATH feature.
* MNT:Add cmake flag to fix osx build
* Update SConsChecks submodule
* Update README to reflect preference for CMake.
* Merge pull request `#63 <https://github.com/rsinnet/ros_boost_numpy/issues/63>`_ from ndarray/add-travis-ci
  Add CI with both cmake and scons builds.
* Add SCons build for Python 2 only.
* Add CI using CMake builds.
* Merge branch '`#58 <https://github.com/rsinnet/ros_boost_numpy/issues/58>`_'
* Only define half-precision floats if NumPy does.
* Merge branch '`#60 <https://github.com/rsinnet/ros_boost_numpy/issues/60>`_'
  Improve support for Python 3.
* Rework handling of NumPy import macros.
  We now wrap import_ufunc against early returns as well,
  and initialize() now returns a bool indicating success
  or failure.
* Limit use of 'long' to Python 2.
* Merge branch 'library-dir-suffix'
  Use lib64 for default lib installation directory on x86_64 arch.
* Augment message for lib dir arch detection.
* Add buildsystem variable to control library directory suffix on installation
* Merge pull request `#56 <https://github.com/rsinnet/ros_boost_numpy/issues/56>`_ from termoshtt/cmake_pythonlib
  Use PythonLibs (cmake) instead of PythonLibsNew
* Remove FindPythonLibsNew since we use FindPythonLibs
* Use PythonLibs instead of PythonLibsNew (cmake)
* Merge pull request `#51 <https://github.com/rsinnet/ros_boost_numpy/issues/51>`_ from willyd/vscompat
  Visual Studio compatibility fixes
* Visual Studio compatibility fixes
  Static linking fix
* Fix some confusing magic numbers in docs for stride (`#50 <https://github.com/rsinnet/ros_boost_numpy/issues/50>`_).
  Documentation here needs a bigger cleanup than I can give it
  right now, but this at least removes the ambiguity as to whether
  "4" means the shape or sizeof(int).
* Update README and convert it to Markdown.
* Enable tests in CMake build and fix relative path problems.
  As reported in `#46 <https://github.com/rsinnet/ros_boost_numpy/issues/46>`_, tests were not being built with CMake due
  to a typo.  But they were also broken, because the relative path
  to the dynamic library used in the link commands for the test
  Python modules wasn't appropriate for running the tests from
  the source directory.  Instead, we now copy the Python test
  scripts to the build directory and run them there.
* Remove const from rvalue returns (`#42 <https://github.com/rsinnet/ros_boost_numpy/issues/42>`_).
  I'd originally thought this was a useful way to prevent no-op
  assignments to rvalues, but compilers now check for that
  without using const, and it was probably only non-standard
  compiler behavior that ever made it useful.
* Switch from int to Py_intptr_t for shape/stride returns.
* Removed unnecessary defaults.
* Updated build system behaviour and comments for the --with-boost option.
* Resolve dtype equivalence issue in MSVC
* Fixed unsigned long test error.
* Switch SCons to use SConsChecks submodule for Windows support
* Merge pull request `#39 <https://github.com/rsinnet/ros_boost_numpy/issues/39>`_ from termoshtt/cmake_python3
  (with minor modification from Jim Bosch)
* Revise example/wrap.cpp for python3
* Append python version detector
  Slight modifications from Jim Bosch for more standard language in
  build system language.
* Merge pull request `#36 <https://github.com/rsinnet/ros_boost_numpy/issues/36>`_ from ChrislS/master
  SCons change to build a static lib for Windows
* * SCons change to build a static lib for Windows.
* Merge pull request `#35 <https://github.com/rsinnet/ros_boost_numpy/issues/35>`_ from karlssonper/master
  Examples and tests optional to build in CMake
* Examples and tests are now optional to build. The default behavior is the same as before where both are built.
* Merge pull request `#34 <https://github.com/rsinnet/ros_boost_numpy/issues/34>`_ from karlssonper/master
  added the NPY_FLOAT16 dtype
* added the NPY_FLOAT16 dtype
* Merge pull request `#31 <https://github.com/rsinnet/ros_boost_numpy/issues/31>`_ from nbecker/master
  SCons build system updates to support Python 3
* Use equivalent, but doesn't seem to help
* port to py3
* Merge pull request `#29 <https://github.com/rsinnet/ros_boost_numpy/issues/29>`_ from coroa/master
  cmake: switch from using deprecated linklibraries to target_linklibraries
* cmake: switch from using deprecated linklibraries to target_linklibraries
  the total information duplication actually decreases and it
  facilitates reusing CMake instructions from outer projects.
* Avoid Python 3 compile warnings in NumPy initialization
* Qualify calls to template member functions in invoke_matching.
  This is necessary to avoid a bug in which a template struct from another
  namespace can be confused with the member function by the parser
  (see gcc bug 55576; it's apparently a defect in the C++98 standard).
* Update README to mention CMake build system.
* Add cmake build system, fix examples for Windows compatibility.
* Fix embedding issues with statically-compiled Python, at least on Linux.  Use LINKFLAGS instead of LDFLAGS (see also `#23 <https://github.com/rsinnet/ros_boost_numpy/issues/23>`_; patch from Luc Bourhis)
* Merge pull request `#17 <https://github.com/rsinnet/ros_boost_numpy/issues/17>`_ from awishnick/master
  Added astype to ndarray
* Add astype to ndarray.
* replace non-constant array sizes with scoped_array
* Add license file and license header to source files.
* Merge pull request `#12 <https://github.com/rsinnet/ros_boost_numpy/issues/12>`_ from barnabyrobson/patch-1
  Update SConscript to print the correct message when Boost.Python config test cannot be run.
* Update SConscript
  Fixing copy and pasted comment to say correct thing when program built against Boost.Python can not run.
* add more permissive equivalence test for dtypes, start using it in tests
* ufunc tests now ensure that return value is the same object as the 'output' (if it is provided) argument being the same object as the ufunc return value
* ufunc test now uses assert_array_almost_equal instead of bitwise(?) comparison
* Add example (wrap.py) to demonstrate how to wrap simple functions that operate on C arrays into functions that operate on NumPy arrays  (`#6 <https://github.com/rsinnet/ros_boost_numpy/issues/6>`_).
* Switch to use RPATH in test and example builds (`#5 <https://github.com/rsinnet/ros_boost_numpy/issues/5>`_).
* Overhauled how builtin dtype objects are accessed for better consistency, added converters for array scalars.
* Remove unused special handling for bool dtype.
* fix LoadableModule suffix on darwin
* Fix bug in boost/numpy.hpp install location
* added as_matrix call policy
* untabify python test files
* Change how external environment variables are propagated to SCons to allow it to find executables in $PATH.
* more SCons refactoring
* Make CheckLibs available to ndarray SConstruct file.
* Prepend Boost paths rather than append them; puts explicit paths at a higher priority than paths pulled from distutils (patch from Neal Becker).
* Added support for specifying installation directories for headers and libraries separately (modified patch from Neal Becker).
  Signed-off-by: Jim Bosch <jbosch@astro.princeton.edu>
* Remove unnecessary shared_ptr in class\_ for ufuncs (from Neal Becker).
  Signed-off-by: Jim Bosch <jbosch@astro.princeton.edu>
* allow CCFLAGS to be passed on command line or through construction variable; default is now '-O2 -g'
* switch to using LoadableModule instead of SharedLibrary for test Python modules
* add bang lines to Python unit test scripts
* add custom rpath option to SCons builds
* modifications to SCons build system to be friendlier to ndarray
* fix GitHub URL in readme
* added README file
* overhauled scons scripts
* added .gitignore
* fixed header order in gaussian example; Python.h should always come before system headers
* removed ublas dependency from gaussian example
* Refine style.
* Refine style.
* Add navigation bar.
* build new 'gaussian.cpp' extension.
* added gaussian example, updated scons build
* Fix formatting issues in the Reference Manual.
* Remove implementation details from documentation.
* Restructure documentation sources to build with sphinx.
* Added temporary directory for Reference documentation
* boost/numpy - enabled new unit tests in old SCons build system
* Added tutorial for ufunc
* Added example for ufunc
* Added non-unit strides example
* Added non-unit strides example
* Removed todo
* Added tutorial for fromdata, i.e. copy free data access
* Made a few modifications
* Added example for data access using pointers
* Added a line for zeros
* Added working custom dtype example
* Added working custom dtype exampel
* Added example for custom dtype
* Added tutorial for dtype
* Added ndarray.rst
* Tutorial for ndarrays
* Added from_data implementation, zeros(..) examples
* Modified Jamfile
* New examples
* Add support for ReST docs.
* Add example(s)
* Fix indexing tests.
* Rename (and move) boost.python.numpy to boost.numpy.
* Rename (and move) boost.python.numpy to boost.numpy.
* Added index array and boolean tests
* Tidy indexing tests.
* Added test for slices with steps. Auto-detection of step not implemented yet
* Added tests for indexing
* Added more tests for ndarray
* Fix ndarray tests.
* Fix ndarray tests.
* Adding test for ndarray.Fails as of now.
* Added build rule for shapes
* Test to check the shape of the ndarray
* Move build system improvements
* Work on numpy configuration
* First build of numpy.jam module to  check for the location of the numpy build directory
* Updated to include the numpy.jam module
* Updated to include the numpy.jam module
* New addition to support boost.build
* New addition to support boost.build
* Patch to fix scons issue
* New addition to support boost.build
* Boost.Python.Numpy - moved convenience header one directory lower
* Boost.Python.Numpy - removing malfunctioning variant build directories
* Boost.Python.Numpy - cleaning up build system
* boost.python.numpy - updates to build system, added some svn:ignores
* numpy - (build system) fixed setting lib output path in tests
* numpy - added missing doxygen builder
* numpy - updates to site_scons, header documentation
* boost.python.numpy - switched to simpler syntax for invoke_matching_array
* boost.python.numpy - moved dtype::invoke_matching_template into separate header, added similar code for invocation based on dimensionality
* boost.python.numpy - fixed missing bool instantiation for dtype::get_builtin
* boost.python.numpy - adding missing symbols, fixed constness in dtype
* boost.python.numpy - added ndarray::reshape
* boost.python.numpy - added dtype template invoker
* boost.python numpy - build system separates debug and standard builds
* boost.python numpy support - improvements to build system
* boost python numpy extensions - updated source files to reflect previous header move
* numpy python extensions - moved main header file inside subdirectory
* numpy python extension - added basic SCons build system, started on unit tests
* initial sandbox import for numpy utilities in boost.python
* folder for new numpy project: improved boost.python bindings for numpy
* Contributors: Aaron Wishnick, Ankit Daftery, Christoph Lassner, Guillaume Dumont, Ilya Kolpakov, Jim Bosch, Jonas Hoersch, Neal D. Becker, Nikita Kosolobov, Per, Philip Miller, Ryan Sinnet, Sergey Popov, Stefan Seefeld, Toshiki Teramura, arkilic, barnabyrobson, per
