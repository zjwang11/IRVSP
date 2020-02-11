
# Please refer to the following reference for more details in the codes:
  https://arxiv.org/abs/2002.04032.

# irvsp
to compute Irreducible Representations of electronic states in Vienna ab-initio Simulation Package (irvsp).

src_irvsp_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_irvsp_v2.tar.gz : for nonsymmorphic crystals 
                      according to the CRTs on the Bilbao Crystallographic Server(BCS).


# vasp2trace
to compute the traces of electronic states in Vienna ab-initio Simulation Package.
The trace file "trace.txt" is generated, which is needed for the CheckTopologicalMat 
on the BCS: www.cryst.ehu.es/cryst/checktopologicalmat
[cite "M.G. Vergniory, et al., Nature 566, 480-485. (2019)"].

src_trace_v1.tar.gz  : for the VASP calculations with ISPIN=1.

src_trace_v1.1.tar.gz: for Hybrid functional calculations with ISPIN=1, 
                       which can skip the first N k-points.

src_trace_v2.tar.gz  : for the VASP calculations with ISPIN=2.


# ir2tb
to compute irreducible representations of electronic states in a tight-binding Hamiltonian.

src_ir2tb_v1.tar.gz : for symmorphic crystals 
                      according to the character tables (CRTs) of point-group (PNG) symmetries.

src_ir2tb_v2.tar.gz : for nonsymmorphic crystals 
                      according to the CRTs on the Bilbao Crystallographic Server(BCS).


