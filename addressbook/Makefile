all: add_person list_people

protoc_middleman: addressbook.proto
	protoc --cpp_out=. addressbook.proto

add_person: add_person.cc protoc_middleman
	g++ add_person.cc addressbook.pb.cc -o add_person -lprotobuf

list_people: list_people.cc protoc_middleman
	g++ list_people.cc addressbook.pb.cc -o list_people -lprotobuf

.PHONY: clean

clean:
	rm -f add_person list_people
	rm -f addressbook.pb.h addressbook.pb.cc
