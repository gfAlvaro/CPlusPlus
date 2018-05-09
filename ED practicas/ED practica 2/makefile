NAME=principalProvincia

#
OBJECTS = $(NAME).o funcionesAuxiliares.o Provincia.o Municipio.o \
		ListaDoblementeEnlazadaOrdenadaMunicipios.o

#
CPPFLAGS = -c -g -Wall -ansi -O2


INCLUDESLIST = ListaDoblementeEnlazadaOrdenadaMunicipios.hpp \
				ListaOrdenadaMunicipiosInterfaz.hpp \
				NodoDoblementeEnlazadoMunicipio.hpp  NodoMunicipioInterfaz.hpp \
				Municipio.hpp\
				macros.hpp

INCLUDES = funcionesAuxiliares.hpp \
			$(INCLUDESLIST)

# Macros predefinidas
#
# $@: nombre del objetivo
# $^: todas las dependencias
# $<: primera dependencia
#

objetivo: $(NAME).exe

#Opciones para NO depurar los asertos
ndebug: CPPFLAGS += -DNDEBUG 
ndebug: objetivo

# Primer objetivo 
$(NAME).exe: $(OBJECTS)
			@echo "Generando " $@
			@g++ $^ -o $@

#
$(NAME).o: $(NAME).cpp $(INCLUDES)
			@echo "Compilando " $<
			@g++ $(CPPFLAGS) $<

#
funcionesAuxiliares.o: funcionesAuxiliares.cpp $(INCLUDES)
			@echo "Compilando " $<
			@g++ $(CPPFLAGS) $<

#
Provincia.o: Provincia.cpp Provincia.hpp \
			ListaDoblementeEnlazadaOrdenadaMunicipios.hpp ListaOrdenadaMunicipiosInterfaz.hpp \
			Municipio.hpp 
			@echo "Compilando " $<
			@g++ $(CPPFLAGS) $<

#
Municipio.o: Municipio.cpp Municipio.hpp
			@echo "Compilando " $<
			@g++ $(CPPFLAGS) $<


#
ListaDoblementeEnlazadaOrdenadaMunicipios.o: ListaDoblementeEnlazadaOrdenadaMunicipios.cpp   $(INCLUDESLIST)
			@echo "Compilando " $<
			@g++ $(CPPFLAGS) $<



# Generación de la documentación
doc: Doxyfile 
	@echo "Generando la documentación con doxygen"
	@doxygen
  
# Borrado
.PHONY: clean  
clean:
	@echo "Borrando los ficheros superfluos"
	@rm -f $(OBJECTS) *~ 

