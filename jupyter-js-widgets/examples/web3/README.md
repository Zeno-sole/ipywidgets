# Using jupyter-js-widgets in non-notebook, web context

## Description

This directory is an example project that shows how to use `jupyter-js-widgets`
and `ipywidgets` in a web context other than the notebook.

Unlike the `web1` and `web2` example, this example requires a Jupyter notebook
server to be running. The user is prompted with a dialog to provide the URL
with a running notebook server.

Besides, this example also displays read-only text area containing the code
provided in the `widget_code.json`, which we used to generate the widget state.

The `web5` and `web6` examples are similar to this one, but instead of
requiring a notebook server to be running, they use the `tmpnb` and the
`mybinder` services to spawn a new transient notebook server.

## Try it

1. Start with a development install of `jupyter-js-widgets` by running
   `npm install` in the `jupyter-js-widgets` subfolder of the repo root
   (see the [README.md](../../../README.md) in the repo root for more details).
2. Cd into this directory and run `npm install`.
3. Run `npm run host`
4. In a new terminal run `python -m notebook --no-browser --NotebookApp.allow_origin="*" --NotebookApp.disable_check_xsrf=True --NotebookApp.token=''`
5. In a web browser, navigate to `http://localhost:8080/` (or the address specified by the `npm run host` command)

## Details

If you plan to reproduce this in your own project, pay careful attention to the
`package.json` file. The dependency to `jupyter-js-widgets`, which reads
`"jupyter-js-widgets": "file:../../../ipywidgets"`, **should not** point to
`"file:../../../ipywidgets"`.

Instead point it to the version you want to use on npm.

(but really, you should let npm do this for you by running

`npm install --save jupyter-js-widgets`.)
