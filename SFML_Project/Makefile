EXE := sfml_main.exe
SRC := $(wildcard *.cpp)
OBJ := $(SRC:.cpp=.o)
DEP := $(OBJ:.o=.d)

CPPFLAGS := -ID:/Projects/SFML_Learning/SFML-2.5.1/include/ #-DSFML_STATIC -MMD -MP
# -MMD tells the compiler to output a Makefile snippet for each compiled .cpp file, and save it into a .d file with the same name.
# -MP then tells the compiler to also output a non-dependent target for each header file it encounters.
CXXFLAGS := -std=gnu++11#-Wall -W -pedantic
LDFLAGS  := -LD:/Projects/SFML_Learning/SFML-2.5.1/lib/
LDLIBS   := -lsfml-graphics -lsfml-window -lsfml-system
# Use for static linking:
# LDLIBS   := -lsfml-graphics-s -lsfml-window-s -lsfml-system-s
# LDLIBS   += -lopengl32 -lwinmm -lgdi32 -mwindows

.PHONY: all clean

all: $(EXE)

$(EXE):	$(OBJ)
	$(CXX) $(LDFLAGS) $^ $(LDLIBS) -o $@

clean:
	$(RM) $(EXE) $(OBJ) $(DEP)

ifeq "$(MAKECMDGOALS)" ""
-include $(DEP)
endif