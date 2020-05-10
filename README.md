# PGN-2 SPEC

Specification: Portable Game Notation Version 2

Draft: 2020-05-09

Authors: Brian J. Wiborg


## 0: Preface

> You never change things by fighting the existing reality.
> To change something, build a new model that makes the existing model
> obsolete.  
    -- R. Buckminster Fuller


## 1: Introduction

PGN-2 is the "Portable Game Notation Version 2", the successor of the well
known and widely spread PGN format by *Steven J. Edwards* from 1994-03-12.

PGN-2 is a future compatible redesign of PGN. It follows the core design
principes of the legacy PGN specification but addresses various problems,
that have lead to several extended specifications and a rather broad spectrum
of subtle differences in the various implementations, as well es site-specific
customizations that grew out of necessity over the years.


## 2: Chess Data Representation

PGN-2 leverages [YAML](https://yaml.org/spec/) sytax for structuring the data.
A PGN-2 game consists of two keys, the `tags` key contains the tags as
key-value pairs. The `moves` key contains a list of moves.


## 2.1: Data Interchange Compatibility

In order to reduce compatibility issues betwen platforms and architectures,
PGN-2 defaults to UTF-8 encoding. Older systems may simply fall back to ASCII.


## 2.2: Example PGN-2 File

```pgn2
- tags:
    Event: F/S Return Match
    Site: Belgrade, Serbia JUG
    Date: 1992.11.04
    Round: 29
    White: Fischer, Robert J.
    Black: Spassky, Boris V.
    Result 1/2-1/2
  moves:
    - e4
    - e5
    - Nf3
    - Nc6
    - Bb5
    - a6    # This opening is called the Ruy Lopez.
    - Ba4
    - Nf6
    - O-O
    - Be7
    - Re1
    - b5
    - Bb3
    - d6
    - c3
    - O-O
    - h3
    - Nb8
    - d4
    - Nbd7
    - c4
    - c6
    - cxb5
    - axb5
    - Nc3
    - Bb7
    - Bg5
    - b4
    - Nb1
    - h6
    - Bh4
    - c5
    - dxe5
    - Nxe4
    - Bxe7
    - Qxe7
    - exd6
    - Qf6
    - Nbd2
    - Nxd6
    - Nc4
    - Nxc4
    - Bxc4
    - Nb6
    - Ne5
    - Rae8
    - Bxf7+
    - Rxf7
    - Nxf7
    - Rxe1+
    - Qxe1
    - Kxf7
    - Qe3
    - Qg5
    - Qxg5
    - hxg5
    - b3
    - Ke6
    - a3
    - Kd6
    - axb4
    - cxb4
    - Ra5
    - Nd5
    - f3
    - Bc8
    - Kf2
    - Bf5
    - Ra7
    - g6
    - Ra6+
    - Kc5
    - Ke1
    - Nf4
    - g3
    - Nxh3
    - Kd2
    - Kb5
    - Rd6
    - Kc5
    - Ra6
    - Nf2
    - g4
    - Bd3
    - Re6
    - 1/2-1/2
```

## 3: Annotations

Moves can be annotated by representing them as a key-value pair couple of move
and annotation:

```pgn2
- moves:
    - e4
    - e5
    - Nf3
    - move: h6
      annotation: ...
```
