# CheatSheet #
| Mode | Name | Description | Instructions |
| :-: | :-: | :- | :- |
| 0 |  | not use | | `mode`
| 1 | **[MODE_DEBUG](#mode-debug)** | depuration put char | `nill` `stri` `strc` `stro` `strx` `stru` `mode` |
| 2 | **[MODE_STRING](#mode-string)** | console put char | `nill` `stri` `strc` `stro` `strx` `stru` `mode` |
| 3 | **[MODE_INPUT](#mode-input)** | console input keyboard | `nill` `stri` `strc` `stro` `strx` `stru` `mode` |
| 4 | **[MODE_INPUT_SILENT](#mode-input-silent)** | console input keyboard (silent) | `nill` `stri` `strc` `stro` `strx` `stru` `mode` |
| 5 | **[MODE_INPUT_PASSWORD](#mode-input-password)** | console input keyboard (password) | `nill` `stri` `strc` `stro` `strx` `stru` `mode` |
| 6 | **[MODE_MEMORY](#mode-memory)** | main memory controller | `nill` `free` `aloc` `tcfg` `tmin` `tmax` `mode` |
| 7| | not use | |
| 8 | **[MODE_MEMORY_AUX](#mode-memory-aux)** | aux memory controller | `nill` `free` `aloc` `pull` `push` `mode` |
| 9 | **[MODE_JUMP](#mode-jump)** | logical jumps between labels | `nill` `goto` `fgto` `zgto` `pgto` `ngto` `mode` |
| 10 | | reserved | |
| 11 | **[MODE_MATH_SUM](#mode-math-sum)** | basic mathematic sum  | `nill` `math` `mode` |
| 12 | **[MODE_MATH_SUB](#mode-math-sub)** | basic mathematic subtration  | `nill` `math` `mode` |
| 13 | **[MODE_MATH_MUL](#mode-math-mul)** | basic mathematic multiplication | `nill` `math` `mode` |
| 14 | **[MODE_MATH_DIV](#mode-math-div)** | basic mathematic division  | `nill` `math` `mode` |
| 15 | **[MODE_MATH_MOD](#mode-math-mod)** | basic mathematic rest of division  | `nill` `math` `mode` |
| 16 | **[MODE_MATH_POWER](#mode-math-power)** | basic mathematic power | `nill` `math` `mode` |
| 17 | **[MODE_MATH_ROOT](#mode-math-root)** | basic mathematic root | `nill` `math` `mode` |
| 18 | **[MODE_MATH_PERCENTAGE](#mode-math-percentage)** | basic mathematic percentage | `nill` `math` `mode` |
| 19 | **[MODE_MATH_ABS](#mode-math-abs)** | basic mathematic module | `nill` `math` `mode` |
| 20 | **[MODE_MATH_AVERAGE](#mode-math-average)** | basic mathematic avarege | `nill` `math` `mode` |

# Architecture details  #
## COMMON ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `nill` | 0 | 000 | label reference point or skip line (null) |
| `mode` | 7 | 111 | change cpu register bank |

## NO MODE `DONT USE` ##

## MODE DEBUG ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `stri` | 1 | 001 | log literal number |
| `strc` | 2 | 010 | log ascii character |
| `stro` | 3 | 011 | log literal number in octal |
| `strx` | 4 | 100 | log literal number in hexadecimal |
| `stru` | 5 | 101 | log literal number (unsigned) |

## MODE STRING ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `stri` | 1 | 001 | put literal number |
| `strc` | 2 | 010 | put ascii character |
| `stro` | 3 | 011 | put literal number in octal |
| `strx` | 4 | 100 | put literal number in hexadecimal |
| `stru` | 5 | 101 | put literal number (unsigned) |

## MODE INPUT ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `stri` | 1 | 001 | input literal number |
| `strc` | 2 | 010 | input ascii character |
| `stro` | 3 | 011 | input literal number in octal |
| `strx` | 4 | 100 | input literal number in hexadecimal |

## MODE INPUT SILENT ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `stri` | 1 | 001 | input literal number |
| `strc` | 2 | 010 | input ascii character |
| `stro` | 3 | 011 | input literal number in octal |
| `strx` | 4 | 100 | input literal number in hexadecimal |

## MODE INPUT PASSWORD ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `stri` | 1 | 001 | input literal number |
| `strc` | 2 | 010 | input ascii character |
| `stro` | 3 | 011 | input literal number in octal |
| `strx` | 4 | 100 | input literal number in hexadecimal |

## MODE MEMORY ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `free` | 1 | 001 | realese memory |
| `aloc` | 2 | 010 | reserve memory and set a value |
| `smin` | 4 | 011 | set memory min value possible |
| `srev` | 3 | 100 | set memory reversable |
| `smax` | 5 | 101 | set memory max value possible |

## PROTECTED `DONT USE` ##

## MODE MEMORY AUX ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `free` | 1 | 001 | realese memory aux |
| `aloc` | 2 | 010 | set a value in aux memory |
| `pull` | 3 | 011 | pull aux memory to address memory (addr <- aux) |
| `push` | 4 | 100 | push aux memory to address memory (addr -> aux) |

## MODE JUMP ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `goto` | 1 | 001 | jump to the label unconditionally |
| `fgto` | 2 | 010 | jump to the label if aux memory is fill |
| `zgto` | 3 | 011 | jump to the label if aux memory is empty |
| `pgto` | 4 | 100 | jump to the label if aux memory is positive |
| `ngto` | 5 | 101 | jump to the label if aux memory is negative |

## _RESERVED_ `not use` ##
reserved for future memory bank function

## MODE MATH SUM ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | add value in the aux memory |

## MODE MATH SUB ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | subtraction in the aux memory |

## MODE MATH MUL ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | multiplication in the aux memory |

## MODE MATH DIV ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | division in the aux memory |

## MODE MATH MOD ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | rest of the division with aux memory |

## MODE MATH POWER ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | enhance aux memory value |


## MODE MATH ROOT ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | root aux memory value |

## MODE MATH PERCENTAGE ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | percentage aux memory value |

## MODE MATH ABS ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | module positive aux memory value |

## MODE MATH AVERAGE ##
| name | octal | bit | description |
| ------ | - | --- | - |
| `math` | 1 | 001 | avarange values received and storage in the aux memory |