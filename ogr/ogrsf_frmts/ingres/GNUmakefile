
include ../../../GDALmake.opt

OBJ	=	ogringresdriver.o ogringresstatement.o ogringresdatasource.o \
		ogringrestablelayer.o ogringreslayer.o ogringresresultlayer.o

#	ogringresresultlayer.o

CPPFLAGS	:=	-I.. -I../.. $(GDAL_INCLUDE) $(INGRES_INC) $(CPPFLAGS)

PLUGIN_SO	= ogr_Ingres.so

default:	$(O_OBJ:.o=.$(OBJ_EXT))

clean:
	rm -f *.o $(O_OBJ)
	rm -f ogr_Ingres.so
	rm -f *.lo
	rm -rf .libs

plugin: $(PLUGIN_SO)

$(PLUGIN_SO):	$(OBJ) 
	gcc -shared $(LNK_FLAGS) $(OBJ:%.o=.libs/%.o) $(CONFIG_LIBS_INS) $(EXTRA_LIBS) $(INGRES_LIB)\
		-o $(PLUGIN_SO) 

