cmake_minimum_required(VERSION 3.5.1)
project("pyvxl-contrib-sdet-algo")

# Add pybind11 module
pybind11_add_module(pysdet_algo pysdet_algo.h pysdet_algo.cxx)

# Link to vxl library
target_link_libraries(pysdet_algo PRIVATE sdet_algo)

# Set names
set_target_properties(pysdet_algo PROPERTIES OUTPUT_NAME "_sdet_algo")

# install the .so file to the python install dir
install(TARGETS pysdet_algo DESTINATION ${PYTHON_SITE}/vxl/contrib/sdet/algo)

# copy __init__ file over into module
install(FILES __init__.py DESTINATION ${PYTHON_SITE}/vxl/contrib/sdet/algo)

