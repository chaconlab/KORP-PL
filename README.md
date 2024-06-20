# KORP-PL
This simple orientation-dependent coarse-grained knowledge-based scoring function for protein-ligand docking developed in a joint-venture with <a href="https://team.inria.fr/nano-d/team-members/sergei-grudinin/">Sergei Grudinin lab</a> outperforms state-of-the-art statistical potentials using a 3D joint probability and a minimalist protein representation.  Our side-chain independent potential is a fast and highly discriminative energy function for protein-ligand docking, please have a try. This mirrors the methodology site from  <a href="https://team.inria.fr/nano-d/software/korp-pl/"> here</a>

## References

M. Kadukova, K. dos Santos Machado, P. Chacón, S. Grudinin (2021) KORP-PL: a coarse-grained knowledge-based scoring function for protein-ligand interactions, Bioinformatics, 37(7), 943–950 <a href="https://doi.org/10.1093/bioinformatics/btaa748"><img src="https://chaconlab.org/images/publications/pubmed.jpg" alt="" border="0" /></a> <a href="https://chaconlab.org/PDF/2021_bioinfob.pdf"><img src="https://chaconlab.org/images/publications/acrobaticon4.gif" alt="" border="0" /></a>


## User guide

<table style="height: 387px; width: 803px;">
<tbody>
<tr>
<td style="width: 465.917px;">KORP-PL is a novel sidechain-free coarse-grained knowledge-based scoring function for protein-ligand interactions developed together with <a href="https://team.inria.fr/nano-d/team-members/sergei-grudinin/">Sergei Grudinin</a>. To this end, we first collect sidechain-free statistics of the distances and angles between an oriented frame built on a residue backbone and a ligand atom for each residue and ligand atom within a cutoff distance as depicted in the left figure. Similar framework was successfully used for protein and loop modeling in the 6D orientation-dependent knowledge-based potential KORP<sup>[1]</sup>. The interaction potentials are then derived in a classical way<sup>[2]</sup> and keep the full dependence between variables. KORP-PL was trained on PDBBind 2016<sup>[3]</sup> with ligand atom typization similar to the one from Convex-PL<sup>[4]</sup>. Our side-chain independent potential is a fast and highly discriminative energy function for protein ligand docking, please try it.</td>
<td style="width: 319.083px;">
<p><img class="" src="https://team.inria.fr/nano-d/files/2019/12/KORP-PL.jpg" width="318" height="264" /></p>
</td>
</tr>
<tr>
<td style="width: 465.917px;"> </td>
<td style="width: 319.083px;">
<p><em>Schematic view of the relative orientation of a ligand molecule to a protein residue. The residue is represented with a 3D oriented frame built from three backbone atoms. The relative orientation of a ligand atom is described by two spherical angles, θ, the polar angle between the r and z vectors, and φ, the azimuthal angle between x and the projection of r into the xy plane.</em></p>
</td>
</tr>
</tbody>
</table>
<h3>Usage</h3>
<hr />
<p>The usage of KORP-PL is very simple:</p>
<pre>&gt;~/korp-pl/korp-pl-test$ ../KORP-PL --receptor ./10gs/10gs_protein.pdb --ligand ./10gs/10gs_ligand.mol2 --mol2
#************************************************************
#*----------------------------------------------------------*
#*-------------------------KORP-PL--------------------------*
#*-------------------------Authors:-------------------------*
#*--------Maria Kadukova, Karina dos Santos Machado,--------*
#*------------Pablo Chacon, and Sergei Grudinin.------------*
#*-----Copyright (c): Nano-D team, Inria/CNRS Grenoble,-----*
#*-------Rocasolano Institute of Physical Chemistry --------*
#*-----------France, Russia, Spain, 2019 - 2020.------------*
#*-------------e-mail: sergei.grudinin@inria.fr-------------*
#*----------------------------------------------------------*
#************************************************************
Number of decoys: 1
model 0, energy = -343.3552884724235810</pre>
<h3 id="Downloads">Download</h3>
<hr />
<p>Linux:  <a href="https://files.inria.fr/NanoDFiles/Website/Software/KORP-PL/0.1/Linux/KORP-PL.linux.zip">KORP-PL v0.1 binary and test files  </a>macOS <a href="https://files.inria.fr/NanoDFiles/Website/Software/KORP-PL/0.1/macOS/KORP-PL.macOS.zip">KORP-PL v0.1 binary and test files</a></p>
<h3 id="Validation">Validation</h3>
<hr />
<p>CASF Benchmarks contain several exercises measuring the pose prediction (docking test), relative affinity prediction (scoring and ranking tests) powers of a scoring function, and a virtual screening exercise (screening test).</p>
<p><strong>CASF Benchmark 2013</strong><sup>[5]</sup></p>
<p>We obtained top-ranked results in docking and screening tests. However, our performance in affinity prediction exercises was below the average.</p>
<p><a href="https://files.inria.fr/NanoDFiles/Website/Software/KORP-PL/Benchmarks/korp-pl-CASF-2013.tar.zip">files</a> (CASF Benchmark 2013 rescorings)</p>
<p><strong>CASF Benchmark 2016</strong><sup>[6]</sup></p>
<p>We obtained top-ranked results in docking and screening tests. In the screening test evaluated by the enrichment factor metric we outperformed other scoring functions more than 1.5 times. However, our performance in affinity prediction exercises of this benchmark is rather poor.</p>
<p><a href="https://files.inria.fr/NanoDFiles/Website/Software/KORP-PL/Benchmarks/korp-pl-CASF-2016.tar.zip">files</a> (CASF Benchmark 2016 rescorings)</p>
<p><strong>D3R-based benchmark</strong></p>
<p>We compiled a benchmark from the D3R Grand Challenges 2<sup>[7]</sup>, 3<sup>[8]</sup>, and 4<sup>[9]</sup> user submissions and native structures. It contains pose prediction and scoring exercises. The pose prediction test aims to find a near-native pose among user submissions from each of the Challenges (i.e. it does not require manual docking). Scoring test measures the correlation between predicted binding affinities and experimental constants of co-crystal complexes from the Challenges.</p>
<p>KORP-PL showed very good results in all the three D3R pose prediction tests. Among them, it perfectly performed in the test derived from the Grand Challenge 3, which was a tough case for all the non-template-based docking protocols during the challenge timeframe owing to the wide binding pocket hydrophobicity and high chemical diversity of ligands. As for affinity predictions, KORP-PL obtained very nice results for the Grand Challenge 2 and 4 targets, but a near-zero correlation for the Grand Challenge 3.</p>
<p><a href="https://files.inria.fr/NanoDFiles/Website/Software/KORP-PL/Benchmarks/d3r-release-tests.tar.gz">files</a> (all benchmark files + rescorings)</p>
<h3>References</h3>
<hr />
<p>[1] Lopez-Blanco, J. R. and Chacon, P.. <a href="https://doi.org/10.1093/bioinformatics/btz026">KORP: knowledge-based 6D potential for fast protein and loop modeling</a>. <em>Bioinformatics</em>, <em>2019</em></p>
<p>[2] Samudrala, R. and Moult, J.. <a href="https://doi.org/10.1006/jmbi.1997.1479">An all-atom distance-dependent conditional probability discriminatory function for protein structure prediction</a>. <em>J. Mol. Biol., 1998 </em></p>
<p>[3] Wang, R., et al. <a href="https://doi.org/10.1021/jm048957q">The PDBbind database: methodologies and updates</a>. <em>J. Med. Chem. (2015) </em><a href="http://www.pdbbind.org.cn/">link</a></p>
<p>[4] Kadukova, M. and Grudinin, S.. <a href="https://doi.org/10.1007/s10822-017-0068-8">Convex-PL: a novel knowledge-based potential for protein-ligand interactions deduced from structural databases using convex optimization</a>. <em>J. Comput. Aid. Mol. Des., 2017</em></p>
<p>[5] Li, Y., et al.<a href="https://doi.org/10.1038/nprot.2017.114"> Assessing protein–ligand interaction scoring functions with the CASF-2013 benchmark</a>. <em>Nature protocols, 2018, </em><a href="http://www.pdbbind.org.cn/casf.asp">link</a></p>
<p>[6] <span lang="EN-US" xml:lang="EN-US">Su, M., et al. <a href="https://doi.org/10.1021/acs.jcim.8b00545"> Comparative assessment of scoring functions: the CASF-2016 update</a>. <i>J. Chem. Inf. Model.</i>, <em>2019,</em></span> <a href="http://www.pdbbind.org.cn/casf.asp">link</a></p>
<p>[7] Gaieb, Z., et al. <a href="https://doi.org/10.1007/s10822-017-0088-4">D3R Grand Challenge 2: blind prediction of protein–ligand poses, affinity rankings, and relative binding free energies</a>. <em>J. Comput. Aid. Mol. Des., 2018, </em><a href="https://drugdesigndata.org/about/grand-challenge-2">link</a><em><br /> </em></p>
<p>[8] Gaieb, Z., et al.. <a href="https://doi.org/10.1007/s10822-018-0180-4">D3R Grand Challenge 3: blind prediction of protein</a><a href="https://doi.org/10.1007/s10822-020-00289-y">–</a><a href="https://doi.org/10.1007/s10822-018-0180-4">ligand poses and affinity rankings</a>. <em>J. Comput. Aid. Mol. Des., 2019</em>, <a href="https://drugdesigndata.org/about/grand-challenge-3">link</a><em><br /> </em></p>
<p>[9] Parks, C. D., et. al. <a href="https://doi.org/10.1007/s10822-020-00289-y">D3R Grand Challenge 4: blind prediction of protein–ligand poses, affinity rankings, and relative binding free energies</a>. <em>J. Comput. Aid. Mol. Des.</em>, <em>2020, </em><a href="https://drugdesigndata.org/about/grand-challenge-4">link</a><em><br /> </em></p>
