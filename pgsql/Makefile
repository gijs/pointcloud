# pointcloud

include ../config.mk

MODULE_big = pointcloud
OBJS = \
	pc_inout.o \
	pc_access.o \
	pc_pgsql.o

EXTENSION = pointcloud
DATA = pointcloud--1.0.sql

REGRESS = pointcloud

# Add in build/link flags for lib
PG_CPPFLAGS += -I../lib 
SHLIB_LINK += $(filter -lm, $(LIBS)) $(XML2_LDFLAGS) $(ZLIB_LDFLAGS) ../lib/$(LIBPC_A)

# We are going to use PGXS for sure
PG_CONFIG = pg_config
PGXS := $(shell $(PG_CONFIG) --pgxs)
include $(PGXS)
