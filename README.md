# Corewar

## About corewar

* corewar is a modified version of the famous [corewar](https://en.wikipedia.org/wiki/Core_War) game.

* corewar uses a modified version of RedCode.

* corewar is composed of 3 software: `corewar`, `asm`, and `desasm`.

##### about `corewar`:

* `corewar` is a [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine).

* `corewar` takes as arguments champions, which are binary files with `.cor` extension. `NameOfChamp.cor` is done with `asm`.

* `corewar` reads binary files, writes the instructions in vitual machine memory and executes them.

* `corewar` has a graphic mode done with ncurse.

##### about `asm`:

* `asm` takes as argment a `NameOfChamp.s` and convert on bytecode file with `.cor` extension.

* `asm` acceptes only file with `.s` extension.

##### about `desasm`:

* `desasm` takes as argument `NameOfChamp.cor` and convert on instructions file with `.s` extension.

* `desasm` acceptes only file with `.cor` extension.

##### exemple of a `.s`:

```
.name		"les mlp's"

.comment	"Mark Lou Pierre"

live:   live %42

        ld :live, r10
      
        sti r10, %20, %0
        
        sti r1, %14, %0
        
        fork %:live
```

* If you want more informations about instructions, they are in subject.

## What do you need to compile corewar ?

* gcc or clang

* make

* C library

* ar

* [libncurses5](https://en.wikipedia.org/wiki/Ncurses)

* [libtool](https://www.gnu.org/software/libtool/)

## How to compile corewar ?

* Use `make` to compile `asm`, `desasm`, `corewar`.

* You can compile with `make` `asm`, `desasm` or `corewar` separately by going in `src_asm` for `àsm`, `src_corewar` for `corewar`, and `src_desasm` for `desasm`.

## Usage:

##### `asm`:

* `./asm NameOfChamp.s`, give you a new file `NameOfChamp.cor`.

##### `desasm`:

* `./desasm NameOfChamp.cor`, give you a new file `NameOfChamp.s`.

##### `corewar`:

* `./corewar [-v 0-8 -s] [-dump nbr_cycles] [[-n number] champ1.cor] ...`

###### description of option:

- `-v levelVerbose`= 1 to 8 verbose level.

- `-s`= Graphique option with ncurse.

- `-dump nb_cycle`= print the memory at nb_cycle then exit.

- `-n placeChamp champ.cor`= give a place to champ in virtual machine.

## Rules of Makefile:

all: compile 3 `libft.a`, `asm`, `desasm`, corewar`.

clean: delete objects

fclean: call clean and delete all `libft.a`, `asm`, `desasm`, corewar`.

re: call fclean and all
