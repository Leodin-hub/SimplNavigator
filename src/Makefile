WWW = -Wall -Werror -Wextra -lstdc++ -std=c++17
LIBS= -lgtest

all: s21_console_menu.a
	g++ $(WWW) main.cc s21_console_menu.a -o main.exe
	./main.exe

s21_graph.a:
	g++ -lstdc++ -c containers/s21_matrix.cc s21_graph.cc
	ar rcs s21_graph.a s21_matrix.o s21_graph.o
	ranlib s21_graph.a

s21_graph_algorithms.a:
	g++ -lstdc++ -c containers/s21_matrix.cc s21_graph.cc s21_graph_algorithms.cc
	ar rcs s21_graph_algorithms.a s21_matrix.o s21_graph.o s21_graph_algorithms.o
	ranlib s21_graph_algorithms.a

s21_console_menu.a:
	g++ -lstdc++ -c s21_console_menu.cc s21_graph.cc s21_graph_algorithms.cc containers/s21_matrix.cc
	ar rcs s21_console_menu.a s21_console_menu.o s21_graph.o s21_graph_algorithms.o s21_matrix.o
	ranlib s21_console_menu.a

test: s21_graph_algorithms.a
	g++ $(WWW) graph_test.cc s21_graph.a -o test $(LIBS)

clean:
	rm -rf s21_console_menu.o
	rm -rf s21_console_menu.a
	rm -rf s21_graph.o
	rm -rf s21_graph.a
	rm -rf s21_graph_algorithms.o
	rm -rf s21_graph_algorithms.a
	rm -rf s21_matrix.o
	rm -rf s21_matrix.a