CXX = g++
CPPFLAGS = -Wall -g #-I$(LIB_DIR)
BIN_DIR = bin
SRC_DIR = src
LIB_DIR = lib


all: $(BIN_DIR)/.dirstamp $(BIN_DIR)/pokemon

$(BIN_DIR)/pokemon: main.cpp $(BIN_DIR)/attackMove.o $(BIN_DIR)/battle.o $(BIN_DIR)/pokemon.o
	$(CXX) $(CPPFLAGS) main.cpp $^ -o $@


$(BIN_DIR)/attackMove.o: $(LIB_DIR)/attackMove.h $(SRC_DIR)/attackMove.cpp
	$(CXX) $(CPPFLAGS) -c $< -o $@

$(BIN_DIR)/battle.o: $(LIB_DIR)/battle.h $(SRC_DIR)/battle.cpp #$(BIN_DIR)/attackMove.o #$(LIB_DIR)/attackMove.h $(SRC_DIR)/attackMove.cpp
	$(CXX) $(CPPFLAGS) -c $< -o $@

$(BIN_DIR)/pokemon.o: $(LIB_DIR)/pokemon.h $(SRC_DIR)/pokemon.cpp #$(BIN_DIR)/attackMove.o $(BIN_DIR)/battle.o #$(LIB_DIR)/battle.h $(SRC_DIR)/battle.cpp $(LIB_DIR)/attackMove.h $(SRC_DIR)/attackMove.cpp
	$(CXX) $(CPPFLAGS) -c $< -o $@


$(BIN_DIR)/.dirstamp:
	mkdir -p $(BIN_DIR)
	touch $(BIN_DIR)/.dirstamp

.PHONY: clean
clean:
	rm -rf $(BIN_DIR)
