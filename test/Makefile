BIN_PATH=../bin
SRC_PATH=../src
INC_PATH=../include
SOURCES = main_test.cpp \
          test_bin_tools.cpp \
          test_issues.cpp \
          $(SRC_PATH)/BinStream.cpp \
          $(SRC_PATH)/bin_tools.cpp \
          $(SRC_PATH)/utils.cpp
TARGET = $(BIN_PATH)/test_binmake
OBJECTS=$(notdir $(SOURCES:.cpp=.o))

$(shell mkdir -p $(BIN_PATH))

CXX=g++
CFLAGS = -std=c++11 -Wall -Wextra -I$(INC_PATH) -I. -I$(SRC_PATH)
LDFLAGS =

all: $(SOURCES) $(TARGET)

$(TARGET): $(OBJECTS)
	$(CXX) $^ -o $@ $(LDFLAGS)

%.o: $(SRC_PATH)/%.cpp
	$(CXX) -o $@ -c $< $(INC) $(CFLAGS)

%.o: %.cpp
	$(CXX) -o $@ -c $< $(INC) $(CFLAGS)

run-tests: $(TARGET)
	$(TARGET)

clean:
	rm -rf *.o $(TARGET)
