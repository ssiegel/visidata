# Loader checklist

## Writing the loader

1) create an `open_foo` function that returns a new `FooSheet`;
2) write a `reload()` function to load the data into a list of `rows`;
3) specify the `columns` as a list of `Column` objects;
4) define the sheet-specific [commands](add-command.md).
5) set an appropriate `rowtype` string (plural)
6) make a `# rowdef: ` comment describing the structure of a row (e.g. its base class)

For additional reading, see our detailed guide on [writing loaders for VisiData](http://visidata.org/docs/loaders/).

## Testing the loader

7) if the loader's dependencies are not part of Python3 stdlib, note the additional dependencies in the `requirements.txt`;
    - include a comment adjacent to the dep with the name of the loader
8) check-in a small sample dataset, in that format, to the `sample_data` folder;
9) add a `load-foo.vd` to the `tests/`;
    - `load-foo.vd` should simply open the checked-in sample dataset and a simple interaction if the source includes multiple tables

## Documenting the loader (to be done once the loader is shippable)

10) add a section on the loader to the "supported sources" of the manpage.
    - include its non-Python3 stdlib dependency requirements (if any)
    - provide a short overview of how the loader allows users to engage with the data
