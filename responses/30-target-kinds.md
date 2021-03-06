
### Targets

"Targets" are the main things that the `targets` package interacts with (if the name hadn't already implied that :zany_face:). They represent things that are made (they're also the vertices of the [dependency graph](http://en.wikipedia.org/wiki/Dependency_graph)). If you want to make a plot called `plot.pdf`, then that's a target. If you depend on a dataset called `data.csv`, that's a target (even if it already exists).

In `targets`, there are two main types:

* **files**: These are the targets that need to have `format = "file"` added as an argument to `tar_target()` and their command must return the filepath(s). We have learned that file targets can be single files, a vector of filepaths, or a directory. USGS Data Science workflows name file targets using their base name and their file extension, e.g. the target for `"1_fetch/out/data.csv"` would be `data_csv`. If the file name is really long, you can always simplify it for the target name but it is important to include `_[extension]` as a suffix. Additionally, USGS Data Science pipelines include the filenames created by file targets as typed-out arguments in the target recipe, or in a comment in the target definition. This practice ensures that you and your colleagues will only have to read the makefile, not the function code, to learn what file is being created. 
* **objects**: These are R objects that represent intermediate objects in an analysis. Behind the scenes, these objects are stored to disk so that they persist across R sessions. And unlike typical R objects, they do not exist in your workspace unless you explicitly load them (run `tar_load(target_name)`).

---
:keyboard: Activity: Assign yourself to this issue to get started.

<hr>
<h3 align="center">I'll sit patiently until you've assigned yourself to this one.</h3>
