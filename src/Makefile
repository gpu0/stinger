CC=g++
INC_FLAGS=/opt/rocm/opencl/include
LIB_DIR=/opt/rocm/opencl/lib/x86_64
LIB=OpenCL
CLANG=clang

all: ImageAddRGBA8 ImageAddRGBA16

ImageAddRGBA8:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGBA8.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGBA8

ImageAddR8:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddR8.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddR8

ImageAddRGBA16:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGBA16.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGBA16

ImageAddRGBA32:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGBA32.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGBA32

ImageAddRGBAFloat:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGBAFloat.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGBAFloat

ImageAddRGB101010:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGB101010.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGB101010

ImageAddRGB555:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGB555.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGB555

ImageAddRGFloat:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) ImageAddRGFloat.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/ImageAddRGFloat

image-cl:
	mkdir -p bin
	$(CLANG) -target amdgcn-amd-amdhsa-opencl -x cl -D__AMD__=1 -D__gfx803__=1 -D__gfx803=1 -D__OPENCL_VERSION__=200 -D__IMAGE_SUPPORT__=1 -O3 -m64 -include /opt/rocm/opencl/include/opencl-c.h ./kernels/image.cl 

test:
	./bin/ImageAddRGBA8; ./bin/ImageAddRGBA16

clean:
	rm -rf ./bin a.out

BufferAddFloat:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) BufferAddFloat.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/BufferAddFloat

BufferAddFloatAsm:
	mkdir -p bin
	$(CC) -I$(INC_FLAGS) BufferAddFloatAsm.cpp -L$(LIB_DIR) -l$(LIB) -o ./bin/BufferAddFloatAsm


