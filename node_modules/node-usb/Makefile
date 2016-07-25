CC:=/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/bin/mips-openwrt-linux-gcc
CXX:=/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/bin/mips-openwrt-linux-g++
LD:=/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/bin/mips-openwrt-linux-ld
CFLAGS:=-Os -pipe -mno-branch-likely -mips32r2 -mtune=34kc -fno-caller-saves -fhonour-copts -Wno-error=unused-but-set-variable -Wno-error=unused-result -msoft-float -mips16 -minterlink-mips16 -fpic -I /home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/usr/include -I /home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/include -I /home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/target-mips_34kc_uClibc-0.9.33.2/usr/include -I /home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/target-mips_34kc_uClibc-0.9.33.2/include
LDFLAGS:=-L/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/usr/lib -L/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/toolchain-mips_34kc_gcc-4.8-linaro_uClibc-0.9.33.2/lib -L/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/target-mips_34kc_uClibc-0.9.33.2/usr/lib -L/home/rajiv/OpenWRT-Buildroot/openwrt/staging_dir/target-mips_34kc_uClibc-0.9.33.2/lib

# This is the main compiler
CXX := g++
# CXX := clang --analyze # and comment out the linker last line for sanity
SRCDIR := src
INCDIR := include
BUILDDIR := build
BINDIR := bin
TARGET := $(BINDIR)/addon
 
#SRCEXT := cpp
#SOURCES := $(shell find $(SRCDIR) -type f -name *.$(SRCEXT))
#OBJECTS := $(patsubst $(SRCDIR)/%,$(BUILDDIR)/%,$(SOURCES:.$(SRCEXT)=.o))
CXXFLAGS := -g # -Wall
#LIB := -pthread -lmongoclient -L lib -lboost_thread-mt -lboost_filesystem-mt -lboost_system-mt
#INC := $(shell find $(INCDIR) -maxdepth 1 -type d -exec echo -I {}  \;)

$(TARGET): 
	npm install --arch=mips --verbose --build-from-source

#$(BUILDDIR)/%.o: $(SRCDIR)/%.$(SRCEXT)
#    @mkdir -p $(dir $@)
#    @echo " $(CXX) $(CXXFLAGS) $(INC) -c -o $@ $<"; $(CXX) $(CXXFLAGS) $(INC) -c -o $@ $<

clean:
	@echo " Cleaning..."; 
	@echo " $(RM) -r $(BUILDDIR) $(BINDIR)"; $(RM) -r $(BUILDDIR) $(BINDIR)



# Spikes
#ticket:
#  $(CXX) $(CXXFLAGS) spikes/ticket.cpp $(INC) $(LIB) -o bin/ticket

.PHONY: clean
