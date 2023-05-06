VSOURCE=$(wildcard vsrc/*.v)
EXE=Vtop
CSOURCE=$(wildcard csrc/*.cpp)

all: build

build:
	verilator --cc $(VSOURCE) --trace --exe $(CSOURCE) && make -j -C ./obj_dir -f $(EXE).mk $(EXE)
	./make_compile_commands.sh $(CSOURCE)
clean:
	rm -rf ./obj_dir
run:
	./obj_dir/$(EXE)
sim: build run
	$(call git_commit, "sim RTL") # DO NOT REMOVE THIS LINE!!!

include ../Makefile
