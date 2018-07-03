PARSER=c11

all: $(PARSER)

$(PARSER).tab.c $(PARSER).tab.h: $(PARSER).y
	bison -d $(PARSER).y

lex.yy.c: $(PARSER).l $(PARSER).tab.h
	flex $(PARSER).l

$(PARSER): lex.yy.c $(PARSER).tab.c $(PARSER).tab.h
	gcc $(PARSER).tab.c lex.yy.c -lfl -o $(PARSER)

.PHONY: clean
clean:
		rm -f $(PARSER).tab.c $(PARSER).tab.h $(PARSER).output lex.yy.c $(PARSER) a.out
