SRCS = \
01-implied.a \
02-immediate.a \
03-zero_page.a \
04-zp_xy.a \
05-absolute.a \
06-abs_xy.a \
07-ind_x.a \
08-ind_y.a \
09-branches.a \
10-stack.a \
11-special.a \

OBJS = $(SRCS:%.a=%.bin)

EX_INC = -I /share/cc65/asminc/

all: $(OBJS)

%.bin: %.o
	ld65 -C nes.cfg $< -o $@

%.o: %.a
	ca65 $(EX_INC) -I common -l $*.lst -o $@ $<

clean:
	rm -f *.o *.bin

.PHONY: all clean
