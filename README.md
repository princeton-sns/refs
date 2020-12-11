# refs

To use this file in a LaTeX project: 

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
\bibliography{<your refs here>,**proceedings**}
```

4. Make this more useful for everyone by adding conferences that aren't already there!

