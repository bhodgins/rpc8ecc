#
# makefile for CC65 runtime library
#

.SUFFIXES: .o .s .c

#--------------------------------------------------------------------------
# Programs and flags

SYS	= none

AS	= ../../bin/ca65
CC	= ../../bin/cc65
LD	= ../../bin/ld65

AFLAGS	= -t $(SYS) --forget-inc-paths -I../asminc --cpu $(CPU)
CFLAGS	= -Osir -g -T -t $(SYS) --forget-inc-paths -I . -I ../../include --cpu $(CPU)

#--------------------------------------------------------------------------
# Rules

%.o:   	%.c
	@$(CC) $(CFLAGS) $<
	@$(AS) -g -o $@ $(AFLAGS) $(*).s

%.o:	%.s
	@$(AS) -g -o $@ $(AFLAGS) $<

#--------------------------------------------------------------------------
# Rules to help us see what code the compiler and assembler make.

%.s :	%.c
	@$(CC) $(CFLAGS) -S $<

%.lst :	%.s
	@$(AS) $(AFLAGS) -l -o /dev/null $<


#--------------------------------------------------------------------------
# Object files

# From C source-files
 C_OBJS =	strtok.o	        \
        strtol.o                \
        strtoul.o               \
 		strxfrm.o				\
  		_hextab.o	        
 		#    strftime.o  \
#_afailed.o	        \

#                 _poserror.o             \
# 		_scanf.o	        \
# 		abort.o		        \
#                 asctime.o               \
# 		bsearch.o	        \
# 		errormsg.o	        \
# 		fdopen.o	        \
# 		fgetc.o		        \
# 		fgetpos.o	        \
# 		fgets.o		        \
# 		fputc.o		        \
# 		fputs.o		        \
# 		freopen.o	        \
# 		fseek.o		        \
# 		fsetpos.o	        \
# 		ftell.o		        \
# 		getchar.o	        \
# 		gets.o		        \
#                 gmtime.o                \
# 		locale.o	        \
#                 localtime.o             \
#                 mktime.o                \
# 		perror.o	        \
#                 pmemalign.o             \
# 		puts.o 		        \
# 		qsort.o		        \
# 		realloc.o	        \
# 		rewind.o	        \
# 		sleep.o		        \
        
#                 system.o                \
#                 timezone.o

# From assembly source-files
S_OBJS = zerobss.o \
    copydata.o \
	abs.o	  	\
	atoi.o	  	\
	isalnum.o	\
	isalpha.o	\
	isblank.o	\
	iscntrl.o	\
	isdigit.o 	\
	isgraph.o	\
	islower.o	\
	isprint.o	\
	ispunct.o	\
	isspace.o	\
	isupper.o	\
	isxdigit.o	\
	itoa.o		\
	memchr.o    	\
	memcmp.o    	\
	memcpy.o      	\
	memmove.o       \
	memset.o      	\
#	mkdir.o		\
	strcat.o    	\
	strchr.o	\
	strcmp.o	\
	strcoll.o	\
	strcpy.o	\
	strcspn.o	\
	strdup.o	\
	strerror.o	\
	stricmp.o	\
	strlen.o	\
	strlower.o	\
	strncat.o	\
	strncmp.o	\
	strncpy.o	\
	strnicmp.o	\
	stroserr.o      \
	strpbrk.o	\
	strrchr.o	\
	strspn.o	\
	strstr.o	\
	strtoimax.o     \
	strtoumax.o     \
	strupper.o	\
	tolower.o	\
	toupper.o	
	# _cwd.o          \
	# _environ.o	\
	# _fdesc.o 	\
	# _file.o  	\
	# _fopen.o	\
	# _heap.o	 	\
	# _heapadd.o 	\
	# _heapblocksize.o\
	# _heapmaxavail.o \
	# _heapmemavail.o \
	# _oserror.o	\
	# _printf.o 	\
	# _seterrno.o     \
	# _swap.o	  	\
	# _sys.o	  	\

	# atexit.o  	\

	# calloc.o  	\
	# chdir.o         \
	# copydata.o	\
	# creat.o         \
	# ctime.o         \
	# divt.o          \
	# errno.o		\
	# fclose.o	\
	# fmisc.o 	\
	# fopen.o		\
	# fprintf.o	\
	# fread.o		\
	# free.o		\
	# fscanf.o        \
	# fwrite.o	\
	# getcpu.o	\
	# getcwd.o        \
	# getenv.o	\
	# interrupt.o     \

	# labs.o		\
	# longjmp.o	\
	# ltoa.o	    	\
	# malloc.o	\
	# maperrno.o  	\

	# modfree.o       \
	# modload.o       \
	# oserrcheck.o    \
	# printf.o      	\
	# putchar.o	\
	# putenv.o	\
	# rand.o	      	\
	# raise.o         \
	# remove.o        \
	# rename.o        \
	# rmdir.o		\
	# scanf.o         \
	# searchenv.o	\
	# setjmp.o      	\
	# signal.o        \
	# sigtable.o      \
	# snprintf.o      \
	# sprintf.o	\
	# sscanf.o	\

	# time.o          \

	# uname.o         \
	# ungetc.o        \
	# unlink.o        \s
	# utscopy.o       \
	# vfprintf.o	\
	# vfscanf.o       \
	# vprintf.o       \
	# vscanf.o        \
	# vsnprintf.o     \
	# vsprintf.o	\
	# vsscanf.o       \
	# zerobss.o


#--------------------------------------------------------------------------
# Targets

.PHONY:	all clean zap

all:  	$(C_OBJS) $(S_OBJS)

clean:
	@$(RM) *~ *.lst
	@$(RM) $(C_OBJS:.o=.s)
	@$(RM) $(C_OBJS)
	@$(RM) $(S_OBJS)

zap:	clean

