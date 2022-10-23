# IRVSP/IR2TB and Library
* Please refer to the following references for more details of the codes:
     
     [1] IRVSP  :   J. Gao, et al. Comput. Phys. Comm. 261, 107760 (2021). https://doi.org/10.1016/j.cpc.2020.107760.
     
     [2] pos2aBR:  website http://tm.iphy.ac.cn/UnconvMat.html; </br> source code https://github.com/zjwang11/UnconvMat. </br>
       J. Gao, et al. Sci. Bull. 67, 598 (2022) https://doi.org/10.1016/j.scib.2021.12.025; </br>S. Nie, et al. Phys. Rev. B 103, 205133 (2021). https://doi.org/10.1103/PhysRevB.103.205133.

* You are welcome to provide a link to the source code in this repository, but you may not upload the source code to any website.

* If you have no idea of the space group number (SGN) in your system, please run 'Phonopy' to get the SGN.

* Run 'Phonopy' and 'pos2aBR' to standardize POSCAR to be compatible with the convention in 'IRVSP'.

# IRVSP
to compute Irreducible Representations of electronic states in Vienna ab-initio Simulation Package v5.3 (IRVSP).</br>
The "tqc.txt" and "tqc.data" are generated, which you can upload online (http://tm.iphy.ac.cn/) </br>
to solve the eBR/aBR decompostion and compatibilite relations for topological/unconventional materials.</br>
(http://tm.iphy.ac.cn/TopMat_1651msg.html; http://tm.iphy.ac.cn/UnconvMat.html)

src_irvsp_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_irvsp_v2.tar.gz : for all crystals in 1651 magnetic space groups
                      according to the CRTs on the Bilbao Crystallographic Server (BCS).


# vasp2trace
to compute the traces of electronic states in Vienna ab-initio Simulation Package.
The trace file "trace.txt" is generated, which is needed for the CheckTopologicalMat 
on the BCS: www.cryst.ehu.es/cryst/checktopologicalmat
["M.G. Vergniory, et al., Nature 566, 480-485. (2019)"].

src_trace_v1.tar.gz  : for the VASP calculations with ISPIN=1.

src_trace_v1.1.tar.gz: for Hybrid functional calculations with ISPIN=1, 
                       which can skip the first N k-points.

src_trace_v2.tar.gz  : for the VASP calculations with ISPIN=2.


# IRVSP library 
The library can be linked to by DFT packages, such as Quantum Espresso, VASP, Siesta, Abinit, ELK, Wien2k.
* https://github.com/zjwang11/ir2pw

# A general workflow for using IRVSP
* prepare your POSCAR file ...
* phonopy --symmetry --tolerance 0.01 -c POSCAR
* pos2aBR (* converting PPOSCAR to POSCAR_std *)
* use POSCAR_std to do DFT (VASP, QE ...) calculations ...
* irvsp -sg xxx -nb xx xx > outir2
* solve eBR/aBR (* using tqc.data *)

# IR2TB
to compute irreducible representations of states in (electronic or phononic) tight-binding Hamiltonians (Wannier90, Slater-Koster).

src_ir2tb_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_ir2tb_v2.tar.gz : for all crystals 
                      according to the CRTs on the Bilbao Crystallographic Server (BCS).

# Notices in VASP calculation
* Please do NOT set ISYM tag in INCAR (Default ISYM=2).
* For SOC calculations, please set the MAGMOM tag explicitly in INCAR (for example, MAGMOM=900\*0). The default values of MAGMOM could cause the SYMMETRY error when using IRVSP.
* For detailed magnetic calculations, please refer to http://tm.iphy.ac.cn/TopMat_1651msg.html.
* For VASP6.x, please modify the line "CALL SET_SPINROT_WRAPPER(LATT_CUR%B(1,1),-1)" in mkpoints.F to "CALL SET_SPINROT_WRAPPER(LATT_CUR%B(1,1),IU6)" and recompile VASP before using IRVSP.

