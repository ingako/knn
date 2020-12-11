# CMakeLists.txt
#
#     Author: Fabian Meyer
# Created On: 19 Jul 2019

include_directories(
    ${FLANN_INCLUDE_DIRS}
    "/usr/include/eigen3"
    "/usr/lib/x86_64-linux-gnu/"
)

add_executable(brute_force_search "brute_force_search.cpp")
add_executable(kdtree_minkowski_search "kdtree_minkowski_search.cpp")
add_executable(kdtree_flann_search "kdtree_flann_search.cpp")
add_executable(test_knn "test_knn.cpp")

target_link_libraries(kdtree_flann_search ${FLANN_LIBRARIES} liblz4.so)
target_link_libraries(test_knn ${FLANN_LIBRARIES} liblz4.so)

# g++ kdtree_flann_search.cpp -I/usr/include/eigen3 -L/usr/lib/x86_64-linux-gnu -llz4
