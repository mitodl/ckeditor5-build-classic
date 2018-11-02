# OL CKEditor5 Custom Build

This is our custom build for CKEditor5. It's forked from their 'classic' build
([here](https://github.com/ckeditor/ckeditor5-build-classic)).

## Development setup

Install the deps with `yarn install`. Then if you want to check out the editor
you can do `npm start` and visit `localhost:8080` to see a development build of
the editor with an example document. There's both an editable and a read-only example.

Remember to `npm run fmt` and `npm run lint`!

## Building and publishing

You can run `npm run build` to run the webpack build. If you want to test the
integration with another project, like open-discussions, you can do the
following:

In this repo:

```
npm run build
rm -rf *.tgz
npm pack
```

This will create a `.tgz` just like what would be pushed to the npm registry,
but without publishing anything. We can use this in other projects to try out
installing the package without having to push a new version up to npm.

To use it, copy the `.tgz` file to your local clone of the open-discussions (or
other project) repo and run:

```
docker-compose run watch yarn add ./name-of-the-file.tgz
```

This will add the `.tgz` file in such a way that looks, to node, like a normal
npm package has been installed from the registry. You can then go ahead to
include the code in OD and try it out.
