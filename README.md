# heroku-chicken-scheme

A buildpack for building CHICKEN software on Heroku.

## How To

Put your chicken version in `chicken_version.txt`. Defaults to 5.2.0
if you don't create the version file.

    echo 5.2.0 > ./chicken_version.txt

Put your eggs in `chicken_eggs.txt`.

    cat << EOF > chicken_eggs.txt
    awful
    awful-postgresql
    EOF

Write a `Makefile` that has `heroku` as a target.

## Files

  - `Makefile` (required)
  - `chicken_eggs.txt` (required)
  - `chicken_version.txt` (optional)

## Notes

All the shared libraries potentially used by your app are put into
`${BUILD_DIR}/chicken-libs` (or `/app/chicken-libs` when the slug is
compiled). If you statically compiled your app, you should remove this
directory during the build.

If you are using the shared libraries, you'll need to set
`LD_LIBRARY_PATH` accordingly.
