For testing crbug.com/dawn/2360

1. clone the repo
2. checkout the branch for this particular bug
3. git submodule init
4. git submodule update
5. cd third_party/dawn && python3 ./tools/fetch_dawn_dependencies.py && cd ../../
6. mkdir build && cd build && cmake ../ && make
