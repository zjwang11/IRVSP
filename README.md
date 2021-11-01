
* Please refer to the following references for more details of the codes:
     
     [1] irvsp  :   J. Gao, et al. Comput. Phys. Comm. 261, 107760 (2021). https://doi.org/10.1016/j.cpc.2020.107760.
     
     [2] pos2aBR:  website http://tm.iphy.ac.cn/UnconvMat.html; source code https://github.com/zjwang11/UnconvMat <br>
       J. Gao, et al. https://arxiv.org/abs/2106.08035; S. Nie, et al. Phys. Rev. B 103, 205133 (2021). https://doi.org/10.1103/PhysRevB.103.205133.

* You are welcome to provide a link to the source code in this repository, but you may not upload the source code to any website.

* If you have no idea of the space group number (SGN) in your system, please run 'Phonopy' to get the SGN.

* Run 'Phonopy' and 'pos2aBR' to standardize POSCAR to be compatible with the convention in 'irvsp'.

# irvsp
to compute Irreducible Representations of electronic states in Vienna ab-initio Simulation Package (irvsp).
The "tqc.txt" and "tqc.data" are generated, which you can upload online (http://tm.iphy.ac.cn/UnconvMat.html)
to solve the aBR (resp. eBR) decompostion and compatibilite relations for unconventional (resp. topological) materials.

src_irvsp_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_irvsp_v2.tar.gz : for all crystals in 1651 magnetic space groups
                      according to the CRTs on the Bilbao Crystallographic Server (BCS).


# vasp2trace
to compute the traces of electronic states in Vienna ab-initio Simulation Package.
The trace file "trace.txt" is generated, which is needed for the CheckTopologicalMat 
on the BCS: www.cryst.ehu.es/cryst/checktopologicalmat
[cite "M.G. Vergniory, et al., Nature 566, 480-485. (2019)"].

src_trace_v1.tar.gz  : for the VASP calculations with ISPIN=1.

src_trace_v1.1.tar.gz: for Hybrid functional calculations with ISPIN=1, 
                       which can skip the first N k-points.

src_trace_v2.tar.gz  : for the VASP calculations with ISPIN=2.

# ir2pw
to compute irreducible representations of states in PW-based ab-initio packages.

src_ir2pw_v2.tar.gz : for all crystals in 1651 magnetic space groups
                      according to the CRTs on the Bilbao Crystallographic Server (BCS).

# ir2tb
to compute irreducible representations of states in the (electronic or phononic) tight-binding Hamiltonian.

src_ir2tb_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_ir2tb_v2.tar.gz : for all crystals 
                      according to the CRTs on the Bilbao Crystallographic Server (BCS).

# irrep_bcs.a 
the associated library can be linked to by various DFT packages, such as VASP, Quantum espresso, Siesta, Abinit, ELK, Wien2k.

# A general workflow for using irvsp
* prepare your POSCAR file ...
* phonopy --symmetry --tolerance 0.01 -c POSCAR
* pos2aBR (* converting PPOSCAR to POSCAR_std *)
* cp POSCAR_std POSCAR
* do vasp calculations ...
* irvsp -sg ...
* solve eBR/aBR (* using tqc.data *)

# Notice
For SOC calculations, please set the MAGMOM tag explicitly in INCAR (for example MAGMOM=9000\*0). The default value of MAGMOM could cause an error when using irvsp.

