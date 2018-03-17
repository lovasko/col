# col.hpp
This is a header-only library for C++ (C++98 and onwards) that provides the
ANSI coloring capability for outputting text. It integrates well with the
standard library, working with both `std::string` and `std::ostream`.

## Example
First, to define a color, we use the `col::make` function:
```cpp
string red    = col::make(col::red,    col::def, false, false, false);
string yellow = col::make(col::yellow, col::def, false, false, false);
string green  = col::make(col::green,  col::def, false, false, false);
```

Now we are ready to print text to the standard output stream:
```cpp
cout << red << "ERROR" << col::reset << " disk is full"        << endl;
cout << yel << "WARN " << col::reset << " disk is almost full" << endl;
cout << gre << "INFO " << col::reset << " disk is available"   << endl;
```
It is worth to mention the output stream manipulator `col::reset` that can be
used to reset all color effects previously set to the default terminal state.

## Documentation
The full library consists of one type, the color `hue`, and two functions -
`make` and `reset`. All three are located in the `col` namespace. The color
`hue` is an enum with the following values:
 * `black`
 * `red`
 * `green`
 * `yellow`
 * `blue`
 * `magenta`
 * `cyan`
 * `light_gray`
 * `dark_gray`
 * `light_red`
 * `light_green`
 * `light_yellow`
 * `light_blue`
 * `light_magenta`
 * `light_cyan`
 * `white`
 * `def`

The library is intended to be used with instances of `std::ostream`, such as
`std::iostream`, `std::fstream` or `std::stringstream`. The expected usage is
to create an instance of color via the `make` function and just simply direct
it to the stream before writing out the relevant text. This function creates a
string that changes the terminal state to use the appropriate color. Once the
color should be changed to a different color, repeat the direction step with
the desired new color, or use the `reset` manipulator to return back to the
terminal default.

## Installation
The library is not intended to be linked against, nor is it provided as a
package. The aim was to keep the API and code small and readable, so it could
be distributed as a part of any project. The recommendation is to simply copy
the file and use it directly.

## License
The `col.hpp` project is licensed under the terms of the [2-cause BSD
license](LICENSE). In case you would need a different license, please feel free
to contact the author.

## Author
Daniel Lovasko <daniel.lovasko@gmail.com>
