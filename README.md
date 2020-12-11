# bibliography!

`proceedings.bib` is a list of conference proceedings in/around distributed systems that are uniformly formatted for good-looking references sections. 

## To use this file in a LaTeX project: 

1. Copy it to your project.

2. Cite papers from conferences listed in the file by using the `crossref` field. E.g., if you want to cite the eRPC paper from NSDI 2019, find the proceedings entry in `proceedings.bib`:
```
@proceedings{nsdi19,
	title = "Proceedings of the 16th USENIX Conference on Networked Systems Design and Implementation (NSDI'19)",
	booktitle = "Proceedings of the 16th USENIX Conference on Networked Systems Design and Implementation (NSDI'19)",
	year = {2019},
	publisher = usenix,
	address = {Berkeley, CA, USA},
	venue = {Boston, MA, USA}
}
```

Then use the label "nsdi19" to include conference info in the `inproceedings` entry:
```
@inproceedings{erpc,
	title={{Datacenter RPCs can be general and fast}},
	author={Kalia, Anuj and Kaminsky, Michael and Andersen, David G},
	crossref="nsdi19",
}
```

3. Include it in your project's main file with the line:
```
\bibliography{<your refs here>,proceedings}
```

4. Make this more useful for everyone by adding conferences that aren't already there!

## Note
Bibtex will try to be fancy and condense redundant proceedings citations into a single, separate entry that individual entries will reference. If you don't want this behavior, you need to set the `min-crossrefs` command line option in bibtex to something large, like 20. 

If you use latexmk, you can do this by adding the following line to your latexmkrc file:
```
$bibtex = "bibtex -min-crossrefs=20";
```

Overleaf uses a [default latexmkrc](https://www.overleaf.com/learn/how-to/How_does_Overleaf_compile_my_project%3F) for all projects unless the user includes one. So, if you use Overleaf, you can copy the default latexmkrc into a file with the same name, add the above line, and add it to your project. 
