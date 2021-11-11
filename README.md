# heroku-chicken-scheme

A buildpack for building CHICKEN software on Heroku.

## How To

Put your chicken version in `chicken_version.txt`. Defaults to 5.2.0 if you don't create the version file.

    echo 5.2.0 > ./chicken_version.txt

Put your eggs in `chicken_eggs.txt`.

    cat << EOF > chicken_eggs.txt
    awful
    awful-postgresql
    EOF

Write your `Makefile`.


## Files

  - `Makefile` (required)
  - `chicken_eggs.txt` (required)
  - `chicken_version.txt` (optional)
