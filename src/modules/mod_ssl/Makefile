
NAME    =       mod_http_ssl
SRCS    =       mod_http_ssl.c
OBJS    =       $(SRCS:.c=.o)

ifndef USE_SSL
	CFLAGS  +=-DUSE_SSL=1
endif

CFLAGS  +=  -fPIC -g -O2 -Wall -D_MODULE -DDEBUG -I ../../include -D_FILE_OFFSET_BITS=64 -D_REENTRANT
LDFLAGS +=  -lssl

all:shared

static  :       $(OBJS)
	${CC} -r lib$(NAME).a $(OBJS)
	ranlib lib$(NAME).a

shared  :       $(OBJS)
	${CC} -shared -o $(NAME).so $(OBJS)

clean   :
	rm -f $(OBJS)

distclean  :       clean
	rm -f lib$(NAME).a $(NAME).so *~
